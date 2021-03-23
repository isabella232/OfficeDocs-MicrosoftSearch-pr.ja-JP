---
title: Microsoft Search SQL Oracle のグラフ コネクタ
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Microsoft Search 用の Oracle SQLグラフ コネクタをセットアップします。
ms.openlocfilehash: 7ad3d03c73ce051c43f3b3ea094130a837d3177f
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031424"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a>Oracle SQL グラフ コネクタ

Oracle SQL グラフ コネクタを使用すると、組織はオンプレミスの Oracle データベースからデータを検出してインデックスを作成できます。 コネクタは、指定されたコンテンツを Microsoft Search にインデックス付けします。 ソース データを使用してインデックスを最新の状態に保つために、定期的なフル クロールと増分クロールをサポートします。 Oracle SQLコネクタを使用すると、特定のユーザーの検索結果へのアクセスを制限できます。

> [!NOTE]
> Graph コネクタ [**のセットアップの一**](configure-connector.md) 般的な手順については、Graph コネクタのセットアップに関する記事をご覧ください。

この記事は、Oracle データ グラフ コネクタを構成、実行、および監視するSQLです。 これは、一般的なセットアップ プロセスを補足し、Oracle SQL Graph コネクタにのみ適用される手順を示します。 この記事には、トラブルシューティングと [制限事項に関](#troubleshooting) する情報 [も含まれています](#limitations)。

## <a name="before-you-get-started"></a>使用を開始する前に

### <a name="install-the-graph-connector-agent"></a>Graph コネクタ エージェントのインストール

オンプレミスのサードパーティ データにアクセスするには、Graph コネクタ エージェントをインストールして構成する必要があります。 詳細については [、「Graph コネクタ エージェントのインストール](on-prem-agent.md) 」を参照してください。  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターに Graph コネクタを追加する

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

Oracle SQLコネクタをデータ ソースに接続するには、クロールするデータベース サーバーとオンプレミスの Graph コネクタ エージェントを構成する必要があります。 その後、必要な認証方法でデータベースに接続できます。

Oracle SQL コネクタの場合は、優先認証方法、ユーザー名、およびパスワードと共に、ホスト名、ポート、およびサービス (データベース) 名を指定する必要があります。

> [!NOTE]
> コネクタを接続するには、データベースで Oracle データベース バージョン 11g 以降を実行する必要があります。 コネクタは、Windows、Linux、Azure VM プラットフォームでホストされる Oracle データベースをサポートします。

データベース コンテンツを検索するには、コネクタを構成するときにSQLクエリを指定する必要があります。 これらのSQLクエリでは、インデックスを作成するデータベース列 (つまり、ソース プロパティ) に名前を付け、すべての列を取得するために実行する必要がある SQL 結合を含む必要があります。 検索結果へのアクセスを制限するには、コネクタを構成するときに、アクセス制御リスト (ACL) をSQLクエリ内で指定する必要があります。

## <a name="step-3a-full-crawl-required"></a>手順 3a: フル クロール (必須)

この手順では、データベースのフル クロールSQLクエリを構成します。 フル クロールでは、クエリ、検索、または取得のオプションを選択するすべての列または **プロパティが** 選択 **されます**。 ACL 列を指定して、検索結果へのアクセスを特定のユーザーまたはグループに制限することもできます。

> [!Tip]
> 必要なすべての列を取得するには、複数のテーブルを結合できます。

![サンプル プロパティを含む OrderTable と AclTable を示すスクリプト](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>データ列の選択 (必須) 列と ACL 列 (オプション)

この例では、OrderId、OrderTitle、OrderDesc、CreatedDateTime、IsDeleted の 5 つのデータ列の選択を示しています。 データ行ごとに表示権限を設定するには、必要に応じて、次の ACL 列 (AllowedUsers、AllowedGroups、DeniedUsers、DeniedGroups) を選択できます。 これらすべてのデータ列について、クエリ、検索、または **取得** の **オプションを****選択できます**。

次のクエリ例に示すように、データ列を選択します。 `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

検索結果へのアクセスを管理するには、クエリで 1 つ以上の ACL 列を指定できます。 このSQLを使用すると、レコード レベルごとにアクセスを制御できます。 テーブル内のすべてのレコードに対して同じアクセス制御を使用できます。 ACL 情報が別のテーブルに格納されている場合は、クエリでそれらのテーブルとの結合を行う必要がある場合があります。

上記のクエリで各 ACL 列を使用する方法を以下に示します。 次の一覧では、4 つのアクセス **制御メカニズムについて説明します**。

* **AllowedUsers**: このオプションは、検索結果にアクセスできるユーザー ID の一覧を指定します。 次の例では、ユーザーの一覧 (john@contoso.com、keith@contoso.com、lisa@contoso.com が OrderId = 12 のレコードにのみアクセスできます。
* **AllowedGroups**: このオプションは、検索結果にアクセスできるユーザーのグループを指定します。 次の例では、グループ sales-team@contoso.com OrderId = 12 のレコードにのみアクセスできます。
* **DeniedUsers**: このオプションは、検索結果にアクセスできないユーザーの一覧を指定します。 次の例では、ユーザー john@contoso.com および keith@contoso.com OrderId = 13 のレコードにアクセスできないのに対し、他のすべてのユーザーは、このレコードにアクセスできます。
* **DeniedGroups**: このオプションは、検索結果にアクセスできないユーザーのグループを指定します。 次の例では、グループ engg-team@contoso.com グループ pm-team@contoso.com OrderId = 15 のレコードにアクセスすることはできませんが、他のすべてのユーザーは、このレコードにアクセスできます。  

![サンプル プロパティを含む OrderTable および AclTable を示すサンプル データ](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>サポートされているデータ型

次の表に、Oracle コネクタでサポートされているデータ型SQL示します。 この表では、サポートされているデータ型のインデックスデータ型SQL示します。 インデックス作成でサポートされる Microsoft Graph コネクタのデータ型の詳細については、プロパティ リソースの種類に関する [ドキュメントを参照してください](/graph/api/resources/property?preserve-view=true&view=graph-rest-beta#properties)。

| カテゴリ | ソース データ型 | データ型のインデックス作成 |
| ------------ | ------------ | ------------ |
| 数値データ型 | NUMBER(p,0) | int64 (p <= 18) <br> double (p > 18) |
| 浮動小数点数のデータ型 | NUMBER(p,s) <br> FLOAT(p) | double |
| 日付データ型 | DATE <br> TIMESTAMP <br> TIMESTAMP(n) | 日付型 |
| 文字データ型 | CHAR(n) <br> VARCHAR <br> VARCHAR2 <br> LONG <br> CLOB <br> NCLOB | string |
| Unicode 文字のデータ型 | NCHAR <br> NVARCHAR | string |
| RowID データ型 | ROWID <br> UROWID | string |

現在直接サポートされていない他のデータ型では、列をサポートされているデータ型に明示的にキャストする必要があります。

### <a name="watermark-required"></a>透かし (必須)

データベースの過負荷を防ぐために、コネクタはフル クロール透かし列を使用してフル クロール クエリをバッチ処理して再開します。 透かし列の値を使用すると、後続の各バッチがフェッチされ、最後のチェックポイントからクエリが再開されます。 基本的に、これはフル クロールのデータ更新を制御するメカニズムです。

次の例に示すように、透かしのクエリ スニペットを作成します。

* `WHERE (CreatedDateTime > @watermark)`. 予約済みのキーワードで透かしの列名を引用します `@watermark` 。 透かし列は昇順でのみ並べ替えできます。
* `ORDER BY CreatedDateTime ASC`. 透かしの列を昇順で並べ替えます。

次の図に示す構成では `CreatedDateTime` 、選択した透かし列です。 行の最初のバッチをフェッチするには、透かし列のデータ型を指定します。 この場合、データ型は `DateTime` .

![透かし列の構成](media/MSSQL-watermark.png)

最初のクエリでは、"CreatedDateTime > 1753 00:00:00" (DateTime データ型の最小値) を使用して、最初の **N** 行数をフェッチします。 最初のバッチがフェッチされた後、行を昇順に並べ替えた場合、バッチで返される最高値はチェックポイント `CreatedDateTime` として保存されます。 たとえば、2019 年 3 月 1 日 03:00:00:00 です。 次に、 **クエリ** で "CreatedDateTime > 2019 年 3 月 1 日 03:00:00" を使用して、N 行の次のバッチをフェッチします。

### <a name="skipping-soft-deleted-rows-optional"></a>ソフト削除された行のスキップ (オプション)

データベース内のソフト削除された行のインデックス作成を除外するには、その行が削除されたかどうかを示す、削除可能な列名と値を指定します。

![ソフト削除の設定: "Soft delete column" と "削除された行を示すソフト削除列の値"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>フル クロール: 検索アクセス許可を管理する

[ **アクセス許可の管理]** を選択して、アクセス制御メカニズムを指定するさまざまなアクセス制御 (ACL) 列を選択します。 クエリのフル クロールで指定した列名SQLします。

各 ACL 列は、複数値の列である必要があります。 これらの複数の ID 値は、セミコロン (;)、コンマ (、)など) で区切ることができます。 値の区切り記号フィールドにこの区切り **記号を指定する必要** があります。

ACL として使用するには、次の ID の種類がサポートされています。

* **ユーザー プリンシパル名 (UPN)**: ユーザー プリンシパル名 (UPN) は、電子メール アドレス形式のシステム ユーザーの名前です。 UPN (たとえば、john.doe@domain.com) は、ユーザー名 (ログオン名)、区切り記号 (@ 記号)、およびドメイン名 (UPN サフィックス) で構成されます。
* **Azure Active Directory (AAD) ID**: Azure AD では、すべてのユーザーまたはグループに、'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b' のようなオブジェクト ID があります。
* **Active Directory (AD)** セキュリティ ID : オンプレミスの AD セットアップでは、すべてのユーザーとグループに、'S-1-5-21-3878594291-2115959936-132693609-65242.

![アクセス制御リストを構成するための検索アクセス許可設定](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>手順 3b: 増分クロール (オプション)

このオプションの手順では、データベースSQL増分クロールを実行するためのクエリを提供します。 このクエリを使用すると、SQLコネクタによって、前回の増分クロール以降のデータに対する変更が決定されます。 フル クロールと同様に、クエリ、検索、または **取得のオプション****の間** で **選択します**。 フル クロール クエリで指定したのと同じ ACL 列のセットを指定します。

次の図のコンポーネントは、1 つの例外を除き、フル クロール コンポーネントに似たものとなります。 この場合、「ModifiedDateTime」は選択された透かし列です。 フル クロール [の手順を確認して](#step-3a-full-crawl-required) 、増分クロール クエリを記述する方法を説明し、例として次のイメージを参照してください。

![OrderTable、AclTable、および使用できるプロパティの例を示す増分クロール スクリプト。](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>手順 4: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a>手順 5: スキーマの管理

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a>手順 6: 検索アクセス許可を管理する

フル クロール画面で指定された [ACL](#full-crawl-manage-search-permissions) を使用するか、または ACL を上書きしてコンテンツをすべてのユーザーに表示することができます。

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

Oracle SQL コネクタは、フル クロールと増分クロールの両方の更新スケジュールをサポートします。 両方を設定することをお勧めします。

完全クロール スケジュールでは、以前に Microsoft Search インデックスに同期された削除済み行と、同期フィルターから移動した行が検索されます。 最初にデータベースに接続すると、フル クロールが実行され、フル クロール クエリから取得された行すべてが同期されます。 新しい行を同期して更新するには、増分クロールをスケジュールする必要があります。

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!--- ## Next steps: Customize the search results page

Create your own verticals and result types, so end users can view search results from new connections. Without this step, data from your connection won't show up on the search results page.

To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md). -->

## <a name="troubleshooting"></a>トラブルシューティング

その下に、コネクタの構成中に発生する一般的なエラーとその考えられる理由の一覧を示します。

| 構成手順 | エラー メッセージ | 考えられる理由 |
| ------------ | ------------ | ------------ |
| データベース設定 | データベース サーバーからのエラー: 接続要求のタイム アウト | ホスト名が無効です <br> ホストに到達できない |
| データベース設定 | データベース サーバーからのエラー: ORA-12541: TNS: リスナーなし | 無効なポート |
| データベース設定 | データベース サーバーからのエラー: ORA-12514: TNS: リスナーは現在、コネクタ記述子で要求されたサービスを知りません | 無効なサービス (データベース) 名 |
| データベース設定 | データベース サーバーからのエラー: ユーザー ' '' のログインに `user` 失敗しました。 | 無効なユーザー名またはパスワード |

## <a name="limitations"></a>制限事項

Oracle SQL コネクタには、プレビュー リリースで次の制限があります。

* オンプレミス データベースは、Oracle Database バージョン 11g 以降を実行する必要があります。
* ACL は、ユーザー プリンシパル名 (UPN)、Azure Active Directory (Azure AD)、または Active Directory セキュリティを使用してのみサポートされます。
* データベース列内のリッチ コンテンツのインデックス作成はサポートされていません。 このようなコンテンツの例としては、データベース列内のリンクとして存在する HTML、JSON、XML、BLOB、およびドキュメント解析があります。