---
title: Microsoft Search の microsoft SQL connector
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の Microsoft SQL コネクタをセットアップします。
ms.openlocfilehash: a5e0b26277345814ed095b54583ea635341295ad
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949901"
---
# <a name="microsoft-sql-server-connector"></a>Microsoft SQL server コネクタ

Microsoft SQL server コネクタを使用すると、組織は社内の SQL Server データベースからデータを検出し、インデックスを作成できます。 コネクタは、指定されたコンテンツを Microsoft Search にインデックス付けします。 ソースデータのインデックスを最新の状態に保つために、フルクロールと増分クロールを定期的に行います。 SQL Server コネクタを使用すると、特定のユーザーに対する検索結果へのアクセスを制限することもできます。

この記事は、Microsoft 365 管理者または Microsoft SQL server コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

## <a name="install-a-data-gateway"></a>Data gateway をインストールする
サードパーティのデータにアクセスするためには、Microsoft Power BI ゲートウェイをインストールして構成する必要があります。 詳細については[、「Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) 」を参照してください。  

## <a name="connect-to-a-data-source"></a>データソースへの接続
Microsoft SQL server コネクタをデータソースに接続するには、クロールするデータベースサーバーとオンプレミスゲートウェイを構成する必要があります。 その後、必要な認証方法を使用してデータベースに接続できます。

> [!NOTE]
> データベースでは、SQL server バージョン2008以降を実行する必要があります。

データベースコンテンツを検索するには、コネクタを構成するときに SQL クエリを指定する必要があります。 これらの SQL クエリは、すべての列を取得するために実行する必要があるすべての SQL 結合を含む、インデックスを作成するすべてのデータベース列に名前を付ける必要があります (つまり、ソースプロパティ)。 検索結果へのアクセスを制限するには、Microsoft SQL server コネクタを構成するときに、SQL クエリでアクセス制御リスト (Acl) を指定する必要があります。

## <a name="full-crawl-required"></a>フルクロール (必須)
この手順では、データベースのフルクロールを実行する SQL クエリを構成します。 フルクロールでは、**クエリ**可能、**検索**可能、または取得可能にするすべての列またはプロパティが選択**されます。** また、ACL 列を指定して、検索結果のアクセスを特定のユーザーまたはグループに制限することもできます。

> [!Tip]
> 必要なすべての列を取得するには、複数のテーブルに結合することができます。

![プロパティの例を使用して、OrderTable と AclTable を示すスクリプト](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>データ列の選択 (必須) と ACL 列 (省略可能)
この例では、検索のデータを保持する5つのデータ列 (OrderId、OrderTitle、Ordertitle、Htmldatetime、および IsDeleted) の選択例を示します。 データの各行に対して表示権限を設定するには、必要に応じて、次の ACL 列を選択できます。 AllowedUsers、Allowedusers、DeniedUsers、および DeniedGroups。 これらのすべてのデータ列は、**クエリ**可能、**検索**可能 **、または**取得可能にすることができます。

次のクエリ例に示すように、データ列を選択します。`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

### <a name="watermark-required"></a>ウォーターマーク (必須)
データベースが過負荷にならないようにするために、コネクタはフルクロールのウォーターマーク列を使用して、フルクロールクエリをバッチ処理および再開します。 [すかし] 列の値を使用すると、以降の各バッチが取得され、最後のチェックポイントからクエリが再開されます。 基本的には、フルクロールのデータ更新を制御するメカニズムを示します。

次の例に示すように、ウォーターマークに対してクエリスニペットを作成します。
* `WHERE (CreatedDateTime > @watermark)`. 予約済みのキーワード`@watermark`を使用して、ウォーターマーク列名を指定します。 [すかし] 列の並べ替え順序が昇順の場合は`>`、を使用します。それ以外の`<`場合は、を使用します。
* `ORDER BY CreatedDateTime ASC`. [すかし] 列の昇順または降順に並べ替えます。

次の図に示す構成では、 `CreatedDateTime` [選択されたウォーターマーク] 列が選択されています。 行の最初のバッチをフェッチするには、[すかし] 列のデータ型を指定します。 この例では、データ型は`DateTime`です。

![](media/MSSQL-watermark.png)

最初のクエリは、次の値を使用して、最初の**N 個**の行をフェッチします。 "/1 月1日 > 1753 00:00:00" (datetime データ型の最小値)。 最初のバッチをフェッチした後、バッチで`CreatedDateTime`返される最大値は、行が昇順で並べ替えられている場合に、チェックポイントとして保存されます。 例としては、2019年3月1日、03:00:00 があります。 その後、 **N**行の次のバッチは、クエリ内の "/datetime > 03:00:00 2019 年3月1日を使用してフェッチされます。

### <a name="skipping-soft-deleted-rows-optional"></a>削除された削除済みの行をスキップする (オプション)
データベース内の削除済みの行をインデックス作成から除外するには、その行が削除されたことを示す、回復可能な削除の列名と値を指定します。

![論理削除の設定: "削除済みの行を示す" 論理削除列 "および" 値 (論理削除列) "](media/MSSQL-softdelete.png)

## <a name="incremental-crawl-optional"></a>増分クロール (オプション)
このオプションの手順では、データベースの増分クロールを実行するための SQL クエリを指定します。 このクエリを使用すると、Microsoft SQL server コネクタによって、前回の増分クロール以降のデータが変更されます。 フルクロールの場合と同様に、**クエリ**可能、**検索**可能、または取得可能にするすべての列を**選択します**。 フルクロールクエリで指定したものと同じ ACL 列のセットを指定します。

次の図のコンポーネントは、完全なクロールコンポーネントに似ていますが、1つの例外があります。 この例では、"ModifiedDateTime" は選択された透かし列です。 [フルクロールの手順](#full-crawl-required)を確認して、増分クロールクエリを記述する方法を説明し、次の画像を例として示します。

![OrderTable、AclTable、使用できるプロパティの例を示す増分クロールスクリプト。](media/MSSQL-incrcrawl.png)

## <a name="limitations"></a>制限事項
Microsoft SQL server コネクタには、次のようなプレビューリリースの制限があります。
* オンプレミスデータベースでは、SQL server バージョン2008以降を実行する必要があります。
* Acl は、ユーザープリンシパル名 (UPN)、Azure Active Directory (Azure AD)、または Active Directory セキュリティを使用する場合にのみサポートされます。
* データベース列内のリッチコンテンツのインデックス作成はサポートされていません。 このようなコンテンツの例としては、HTML、JSON、XML、blob、ドキュメント parsings などがあります。これらは、データベース列内のリンクとして存在します。

