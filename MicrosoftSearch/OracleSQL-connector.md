---
title: Oracle SQL Microsoft Search 用 Graph コネクタ
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Microsoft Search 用の Oracle SQL Graph コネクタをセットアップします。
ms.openlocfilehash: a13c9ea71b115e84d313489214d424f77337a062
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084976"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a>Oracle SQL Graph コネクタ

Oracle SQL Graph コネクタを使用すると、組織はオンプレミスの Oracle データベースからデータを検出してインデックスを作成できます。 コネクタは、指定されたコンテンツを Microsoft Search にインデックス付けします。 ソース データを使用してインデックスを最新の状態に保つために、定期的なフル クロールと増分クロールをサポートします。 Oracle SQLコネクタを使用すると、特定のユーザーの検索結果へのアクセスを制限できます。

> [!NOTE]
> Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、Graph コネクタの一般的なセットアップ プロセスを理解してください。

この記事は、ServiceNow Graph コネクタを構成、実行、および監視するユーザーを対象にしています。 一般的なセットアップ プロセスを補完し、ServiceNow Graph コネクタにのみ適用する手順を示します。 この記事には、トラブルシューティングと [制限事項に関する](#troubleshooting) 情報も [含まれています](#limitations)。

## <a name="before-you-get-started"></a>使用を開始する前に

### <a name="install-the-graph-connector-agent"></a>Graph コネクタ エージェントをインストールする

オンプレミスのサードパーティ データにアクセスするには、Graph コネクタ エージェントをインストールして構成する必要があります。 詳細 [については、「Graph コネクタ エージェントのインストール」](on-prem-agent.md) を参照してください。  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

Oracle SQL コネクタをデータ ソースに接続するには、クロールするデータベース サーバーとオンプレミスの Graph コネクタ エージェントを構成する必要があります。 その後、必要な認証方法でデータベースに接続できます。

Oracle SQLコネクタの場合は、ホスト名、ポートとサービス (データベース) 名と、優先される認証方法、ユーザー名、およびパスワードを指定する必要があります。

> [!NOTE]
> コネクタを接続するには、データベースで Oracle データベース バージョン 11g 以降を実行する必要があります。 このコネクタは、Windows、Linux、Azure VM プラットフォームでホストされる Oracle データベースをサポートします。

データベースコンテンツを検索するには、コネクタを構成するときにSQLクエリを指定する必要があります。 これらのSQLクエリでは、すべての列を取得するために実行する必要がある SQL 結合を含め、インデックスを作成するデータベース列 (ソース プロパティ) の名前を指定する必要があります。 検索結果へのアクセスを制限するには、コネクタを構成するときに、アクセス制御リスト (ACL) SQLクエリ内で指定する必要があります。

## <a name="step-3a-full-crawl-required"></a>手順 3a: フル クロール (必須)

この手順では、データベースのフル SQL実行するクエリを構成します。 フル クロールでは、クエリ、検索、または取得のオプションを選択する列またはプロパティ **すべてが選択****されます**。 ACL 列を指定して、検索結果へのアクセスを特定のユーザーまたはグループに制限することもできます。

> [!Tip]
> 必要なすべての列を取得するには、複数のテーブルを結合できます。

![プロパティの例を含む OrderTable と AclTable を示すスクリプト](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>データ列の選択 (必須) と ACL 列 (省略可能)

この例では、OrderId、OrderTitle、OrderDesc、CreatedDateTime、IsDeleted という検索データを保持する 5 つのデータ列を選択する方法を示します。 データ行ごとに表示権限を設定するには、必要に応じて、次の ACL 列 (AllowedUsers、AllowedGroups、DeniedUsers、DeniedGroups) を選択できます。 これらすべてのデータ列について、クエリ、検索、または取得の **オプションを** 選択 **できます**。

次のクエリ例に示すように、データ列を選択します。 `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

検索結果へのアクセスを管理するには、クエリで 1 つ以上の ACL 列を指定できます。 このSQLコネクタを使用すると、レコード レベルごとにアクセスを制御できます。 テーブル内のすべてのレコードに対して同じアクセス制御を持つオプションを選択できます。 ACL 情報が別のテーブルに格納されている場合は、クエリでそれらのテーブルとの結合を行う必要がある場合があります。

上記のクエリでの各 ACL 列の使用について、以下に説明します。 次の一覧では、4 つの **アクセス制御メカニズムについて説明します**。

* **AllowedUsers**: このオプションは、検索結果にアクセスできるユーザー ID のリストを指定します。 次の例では、ユーザーのリスト: john@contoso.com、keith@contoso.com、および lisa@contoso.com は、OrderId = 12 のレコードにのみアクセスできます。
* **AllowedGroups**: このオプションは、検索結果にアクセスできるユーザーのグループを指定します。 次の例では、グループsales-team@contoso.com OrderId = 12 のレコードにのみアクセスできます。
* **DeniedUsers**: このオプションは、検索結果にアクセスできないユーザーのリストを指定します。 次の例では、ユーザー john@contoso.comおよび keith@contoso.com OrderId = 13 のレコードにアクセスできないのに対し、他のすべてのユーザーは、このレコードにアクセスできます。
* **DeniedGroups**: このオプションは、検索結果にアクセスできないユーザーのグループを指定します。 次の例では、グループ engg-team@contoso.comおよび pm-team@contoso.com は OrderId = 15 のレコードにアクセスすることはできませんが、他のすべてのユーザーは、このレコードにアクセスできます。  

![プロパティの例を含む OrderTable と AclTable を示すサンプル データ](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>サポートされるデータ型

次の表に、Oracle コネクタでサポートされているデータ型SQLします。 この表では、サポートされているデータ型のインデックスデータ型SQL要約します。 インデックス作成でサポートされている Microsoft Graph コネクタのデータ型の詳細については、プロパティ リソースの種類に関する [ドキュメントを参照してください](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)。

| カテゴリ | ソース データ型 | インデックス作成データ型 |
| ------------ | ------------ | ------------ |
| 数値データ型 | NUMBER(p,0) | int64 (p <= 18) <br> double (p > 18 の場合) |
| 浮動小数点数のデータ型 | NUMBER(p,s) <br> FLOAT(p) | double |
| 日付データ型 | DATE <br> TIMESTAMP <br> TIMESTAMP(n) | 日付型 |
| 文字データ型 | CHAR(n) <br> VARCHAR <br> VARCHAR2 <br> LONG <br> 最も近い <br> NCLOB | string |
| Unicode 文字データ型 | NCHAR <br> NVARCHAR | string |
| RowID データ型 | ROWID <br> UROWID | string |

現在直接サポートされていないその他のデータ型では、列をサポートされているデータ型に明示的にキャストする必要があります。

### <a name="watermark-required"></a>透かし (必須)

データベースの過負荷を防ぐために、コネクタはフル クロール の透かし列を使用してフル クロール クエリをバッチ処理して再開します。 透かし列の値を使用すると、後続の各バッチがフェッチされ、最後のチェックポイントからクエリが再開されます。 基本的に、これはフル クロールのデータ更新を制御するメカニズムです。

次の例に示すように、透かしのクエリ スニペットを作成します。

* `WHERE (CreatedDateTime > @watermark)`. 予約済みのキーワードで透かしの列名を引用します `@watermark` 。 透かしの列は昇順でのみ並べ替えできます。
* `ORDER BY CreatedDateTime ASC`. 透かしの列を昇順で並べ替えます。

次の図に示す構成では `CreatedDateTime` 、選択されている透かし列です。 行の最初のバッチをフェッチするには、透かし列のデータ型を指定します。 この場合、データ型は次の値です `DateTime` 。

![透かし列の構成](media/MSSQL-watermark.png)

最初のクエリは、"CreatedDateTime > January 1, 1753 00:00:00" (DateTime データ型の最小値) を使用して、最初の **N** 行数をフェッチします。 最初のバッチがフェッチされた後、行が昇順で並べ替えらた場合、バッチで返される最高値はチェックポイントとして `CreatedDateTime` 保存されます。 たとえば、2019 年 3 月 1 日 03:00:00 です。 次に、クエリで "CreatedDateTime > March 1, 2019 03:00:00" を使用して **N** 行の次のバッチがフェッチされます。

### <a name="skipping-soft-deleted-rows-optional"></a>回復可能な削除によって削除された行のスキップ (省略可能)

データベース内の回復可能な削除によって削除された行のインデックス作成を除外するには、行が削除されたかどうかを示す回復可能な削除によって削除される列の名前と値を指定します。

![削除済み (回復) の設定: "削除済み (回復) 列" および "削除済み行を示す削除済み (回復済み) 列の値"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>フル クロール: 検索権限を管理する

アクセス **制御メカニズムを指定する** さまざまなアクセス制御 (ACL) 列を選択するには、[アクセス許可の管理] を選択します。 フル クロール クエリで指定した列名SQLします。

各 ACL 列は、複数値を持つ列である必要があります。 これらの複数の ID 値は、セミコロン (;)、コンマ (,)) などの区切り文字で区切ることができます。 この区切り記号は、値の区切り記号 **フィールドに指定する必要** があります。

ACL として使用するには、次の ID の種類がサポートされています。

* **ユーザー プリンシパル名 (UPN)**: ユーザー プリンシパル名 (UPN) は、電子メール アドレス形式のシステム ユーザーの名前です。 UPN (例: john.doe@domain.com) は、ユーザー名 (ログオン名)、区切り記号 (@ 記号)、およびドメイン名 (UPN サフィックス) で構成されます。
* **Azure Active Directory (AAD) ID**: Azure AD では、すべてのユーザーまたはグループに、'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b' のようなオブジェクト ID があります。
* **Active Directory (AD)** セキュリティ ID : オンプレミスの AD セットアップでは、すべてのユーザーとグループに、"S-1-5-21-3878594291-2115959936-132693609-65242" のような不変の一意のセキュリティ識別子があります。

![アクセス制御リストを構成するための検索アクセス許可設定](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>手順 3b: 増分クロール (オプション)

このオプションの手順では、データベースの増分SQL実行するためのクエリを指定します。 このクエリを使用すると、SQLコネクタは、前回の増分クロール以降のデータに対する変更を決定します。 フル クロールの場合と同様に、[クエリ]、[検索]、または [取得]**のオプション** を選択 **します**。 フル クロール クエリで指定したのと同じ ACL 列のセットを指定します。

次の図のコンポーネントは、1 つの例外を除き、フル クロール コンポーネントに似たものとなります。 この場合、"ModifiedDateTime" は選択された透かしの列です。 フル クロール [の手順を確認して](#step-3a-full-crawl-required) 、増分クロール クエリを作成する方法を確認し、例として次の画像を参照してください。

![OrderTable、AclTable、および使用できるプロパティの例を示す増分クロール スクリプト。](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>手順 4: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a>手順 5: スキーマを管理する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a>手順 6: 検索権限を管理する

フル クロール画面で指定された [ACL](#full-crawl-manage-search-permissions) を使用するか、ACL を上書きしてすべてのユーザーにコンテンツを表示することができます。

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

Oracle SQL コネクタは、フル クロールと増分クロールの両方の更新スケジュールをサポートします。 両方を設定することをお勧めします。

フル クロール スケジュールでは、以前に Microsoft Search インデックスに同期された削除済み行と、同期フィルターから移動した行が検索されます。 初めてデータベースに接続すると、フル クロールが実行され、フル クロール クエリから取得した行すべてが同期されます。 新しい行を同期して更新するには、増分クロールをスケジュールする必要があります。

## <a name="step-8-review-connection"></a>手順 8: 接続を確認する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="next-steps-customize-the-search-results-page"></a>次の手順: 検索結果ページをカスタマイズする

独自のバーティカルと結果の種類を作成して、エンド ユーザーが新しい接続からの検索結果を表示できます。 この手順を実行しない場合、接続からのデータは検索結果ページに表示されます。

バーティカルと MRT を作成する方法の詳細については、「検索結果ページのカスタマイズ」 [を参照してください](customize-search-page.md)。

## <a name="troubleshooting"></a>トラブルシューティング

その下に、コネクタの構成中に発生する一般的なエラーとその考えられる理由の一覧を示します。

| 構成手順 | エラー メッセージ | 考えられる理由 |
| ------------ | ------------ | ------------ |
| データベース設定 | データベース サーバーからのエラー: 接続要求がタイム アウトしました | ホスト名が無効です <br> ホストに到達できない |
| データベース設定 | データベース サーバーからのエラー: ORA-12541: TNS: リスナーなし | 無効なポート |
| データベース設定 | データベース サーバーからのエラー: ORA-12514: TNS: リスナーは現在、コネクタ記述子で要求されたサービスを知らない | 無効なサービス (データベース) 名 |
| データベース設定 | データベース サーバーからのエラー: ユーザー ' ' のログイン `user` に失敗しました。 | 無効なユーザー名またはパスワード |

## <a name="limitations"></a>制限事項

Oracle SQL コネクタには、プレビュー リリースで次の制限があります。

* オンプレミス データベースは Oracle データベース バージョン 11g 以降を実行する必要があります。
* ACL は、ユーザー プリンシパル名 (UPN)、Azure Active Directory (Azure AD)、または Active Directory セキュリティを使用する場合にのみサポートされます。
* データベース列内のリッチ コンテンツのインデックス作成はサポートされていません。 このようなコンテンツの例としては、データベース列内のリンクとして存在する HTML、JSON、XML、BLOB、およびドキュメント解析があります。
