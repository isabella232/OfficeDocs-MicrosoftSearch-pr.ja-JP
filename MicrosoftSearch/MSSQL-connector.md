---
title: Microsoft Search SQL Azure SQLおよび Microsoft SQL Graph コネクタ
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
description: Microsoft Search 用の Azure SQL および Microsoft SQL Graph コネクタをセットアップします。
ms.openlocfilehash: 9f0a0a617541c6e27196a183d3283e0f05163dec
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097441"
---
<!---Previous ms.author: vivg --->

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a>Azure SQLおよび Microsoft SQL サーバー Graph コネクタ

Microsoft SQL サーバーまたは Azure SQL Graph コネクタを使用すると、組織はオンプレミスの SQL Server データベース、またはクラウド内の Azure SQL インスタンスでホストされているデータベースからデータを検出してインデックスを作成できます。
Graph コネクタは、指定されたコンテンツのインデックスを Microsoft Search に作成します。 ソース データを使用してインデックスを最新の状態に保つために、定期的なフル クロールと増分クロールをサポートします。 これらのコネクタSQL、特定のユーザーの検索結果へのアクセスを制限できます。

> [!NOTE]
> Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、一般的な Graph コネクタのセットアップ プロセスについて理解してください。

この記事は、Azure SQL および Microsoft SQL Graph コネクタを構成、実行、および監視するユーザーを対象にしています。 一般的なセットアップ プロセスを補完し、Azure SQL および Microsoft SQL Server Graph コネクタにのみ適用される手順を示します。 この記事には、Microsoft [](#limitations) SQL Server および Azure SQL コネクタに関する情報も含まれています。

## <a name="before-you-get-started"></a>使用を開始する前に

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a>Graph コネクタ エージェントをインストールする (オンプレミスの Microsoft SQL サーバー コネクタにのみ必要)

オンプレミスのサードパーティ データにアクセスするには、Graph コネクタ エージェントをインストールして構成する必要があります。 詳細 [については、「Graph コネクタ エージェントのインストール」](on-prem-agent.md) を参照してください。  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

### <a name="register-an-app-for-azure-sql-connector-only"></a>アプリを登録する (Azure SQL コネクタのみ)

Azure SQL コネクタの場合は、Azure Active Directory にアプリを登録して、Microsoft Search アプリがインデックス作成用のデータにアクセスできる必要があります。 アプリの登録の詳細については、アプリの登録方法に関する Microsoft Graph ドキュメント [を参照してください](https://docs.microsoft.com/graph/auth-register-app-v2)。

アプリの登録を完了し、アプリ名、アプリケーション (クライアント) ID、テナント ID をメモした後、新しいクライアント シークレットを [生成する必要があります](https://docs.microsoft.com/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret)。 クライアント シークレットは 1 回だけ表示されます。 クライアント シークレットを安全&保存する必要があります。 Microsoft Search で新しい接続を構成する場合は、クライアント ID とクライアント シークレットを使用します。

登録済みのアプリを Azure SQL Database に追加するには、次の必要があります。

- Azure SQL DB にログインします。
- 新しいクエリ ウィンドウを開く
- コマンド 「CREATE USER [app name] FROM EXTERNAL PROVIDER」を実行して新しいユーザーを作成する
- コマンド 'exec sp_addrolemember 'db_datareader', [アプリ名]' または 'ALTER ROLE db_datareader ADD MEMBER [アプリ名]' を実行してユーザーをロールに追加する

>[!NOTE]
>Azure Active Directory に登録されているアプリへのアクセスを取り消す場合は、登録されているアプリの削除に関する Azure の [ドキュメントを参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-remove-app)。

### <a name="connection-settings"></a>接続設定

Microsoft SQL サーバー コネクタをデータ ソースに接続するには、クロールするデータベース サーバーと、オンプレム エージェントを構成する必要があります。 その後、必要な認証方法でデータベースに接続できます。

> [!NOTE] 
> Microsoft SQL SQL サーバー コネクタが接続するには、データベースをサーバー バージョン 2008 以降SQL実行する必要があります。

Azure SQL コネクタの場合は、接続先のサーバー名または IP アドレスのみを指定する必要があります。 Azure SQL コネクタは、データベースに接続するための Azure Active Directory Open ID Connect (OIDC) 認証のみをサポートします。

セキュリティを強化するには、Azure サーバーまたはデータベースに対して IP SQLを構成できます。 IP ファイアウォール規則の設定の詳細については、IP ファイアウォール規則に関 [するドキュメントを参照してください](https://docs.microsoft.com/azure/azure-sql/database/firewall-configure)。 ファイアウォール設定に次のクライアント IP 範囲を追加します。

| Region | IP 範囲 |
| ------------ | ------------ |
| NAM | 52.250.92.252/30, 52.224.250.216/30 |
| EUR | 20.54.41.208/30, 51.105.159.88/30 |
| APC | 52.139.188.212/30, 20.43.146.44/30 |

データベースコンテンツを検索するには、コネクタを構成するときにSQLクエリを指定する必要があります。 これらのSQLクエリでは、すべての列を取得するために実行する必要がある SQL 結合を含め、インデックスを作成するデータベース列 (ソース プロパティ) の名前を指定する必要があります。 検索結果へのアクセスを制限するには、コネクタを構成するときに、アクセス制御リスト (ACL) SQLクエリ内で指定する必要があります。

## <a name="step-3a-full-crawl-required"></a>手順 3a: フル クロール (必須)

この手順では、データベースのフル SQL実行するクエリを構成します。 フル クロールでは、クエリ、検索、または取得のオプションを選択する列またはプロパティ **すべてが選択****されます**。 ACL 列を指定して、検索結果へのアクセスを特定のユーザーまたはグループに制限することもできます。

> [!Tip]
> 必要なすべての列を取得するには、複数のテーブルを結合できます。

![プロパティの例を含む OrderTable と AclTable を示すスクリプト](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>データ列の選択 (必須) と ACL 列 (省略可能)

この例では、OrderId、OrderTitle、OrderDesc、CreatedDateTime、IsDeleted という検索データを保持する 5 つのデータ列を選択する方法を示します。 データ行ごとに表示権限を設定するには、必要に応じて、次の ACL 列 (AllowedUsers、AllowedGroups、DeniedUsers、DeniedGroups) を選択できます。 これらすべてのデータ列には、クエリ、検索、**または取得****の** オプション **があります**。

次のクエリ例に示すように、データ列を選択します。 `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

検索結果へのアクセスを管理するには、クエリで 1 つ以上の ACL 列を指定できます。 このSQLコネクタを使用すると、レコード レベルごとにアクセスを制御できます。 テーブル内のすべてのレコードに対して同じアクセス制御を持つオプションを選択できます。 ACL 情報が別のテーブルに格納されている場合は、クエリでそれらのテーブルとの結合を行う必要がある場合があります。

上記のクエリでの各 ACL 列の使用について、以下に説明します。 次の一覧では、4 つの **アクセス制御メカニズムについて説明します**。

- **AllowedUsers**: この列は、検索結果にアクセスできるユーザー ID のリストを指定します。 次の例では、ユーザーのリスト: john@contoso.com、keith@contoso.com、および lisa@contoso.com は、OrderId = 12 のレコードにのみアクセスできます。
- **AllowedGroups**: この列は、検索結果にアクセスできるユーザーのグループを指定します。 次の例では、グループsales-team@contoso.com OrderId = 12 のレコードにのみアクセスできます。
- **DeniedUsers**: この列は、検索結果にアクセスできないユーザーのリストを指定します。 次の例では、ユーザー john@contoso.comおよび keith@contoso.com OrderId = 13 のレコードにアクセスできないのに対し、他のすべてのユーザーは、このレコードにアクセスできます。
- **DeniedGroups**: この列は、検索結果にアクセスできないユーザーのグループを指定します。 次の例では、グループ engg-team@contoso.comおよび pm-team@contoso.com は OrderId = 15 のレコードにアクセスすることはできませんが、他のすべてのユーザーは、このレコードにアクセスできます。  

![プロパティの例を含む OrderTable と AclTable を示すサンプル データ](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>サポートされるデータ型

次の表に、MS SQL コネクタと Azure コネクタでサポートされているデータ型のSQLをSQLします。 この表では、サポートされているデータ型のインデックスデータ型SQL要約します。 インデックス作成でサポートされている Microsoft Graph コネクタのデータ型の詳細については、プロパティ リソースの種類に関する [ドキュメントを参照してください](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)。

| カテゴリ | ソース データ型 | インデックス作成データ型 |
| ------------ | ------------ | ------------ |
| 日時 | date <br> 日付型 <br> datetime2 <br> smalldatetime | 日付型 |
| 正確な数値 | bigint <br> int <br> smallint <br> tinyint | int64 |
| 正確な数値 | bit | ブール値 |
| 近似数値 | 浮動小数点数 <br> 本当の | double |
| 文字の文字列 | char <br> varchar <br> text | string |
| Unicode 文字文字列 | nchar <br> nvarchar <br> ntext | string |
| その他のデータ型 | uniqueidentifier | string |

現在直接サポートされていないその他のデータ型では、列をサポートされているデータ型に明示的にキャストする必要があります。

### <a name="watermark-required"></a>透かし (必須)

データベースの過負荷を防ぐために、コネクタはフル クロール の透かし列を使用してフル クロール クエリをバッチ処理して再開します。 透かし列の値を使用すると、後続の各バッチがフェッチされ、最後のチェックポイントからクエリが再開されます。 基本的に、このメカニズムはフル クロールのデータ更新を制御します。

次の例に示すように、透かしのクエリ スニペットを作成します。

- `WHERE (CreatedDateTime > @watermark)`. 予約済みのキーワードで透かしの列名を引用します `@watermark` 。 透かしの列の並べ替え順序が昇順の場合は、使用 `>` します。それ以外の場合は、使用します `<` 。
- `ORDER BY CreatedDateTime ASC`. 透かしの列を昇順または降順で並べ替えます。

次の図に示す構成では `CreatedDateTime` 、選択されている透かし列です。 行の最初のバッチをフェッチするには、透かし列のデータ型を指定します。 この場合、データ型は次の値です `DateTime` 。

![透かし列の構成](media/MSSQL-watermark.png)

最初のクエリは、"CreatedDateTime > January 1, 1753 00:00:00" (DateTime データ型の最小値) を使用して、最初の **N** 行数をフェッチします。 最初のバッチがフェッチされた後、行が昇順で並べ替えらた場合、バッチで返される最高値はチェックポイントとして `CreatedDateTime` 保存されます。 たとえば、2019 年 3 月 1 日 03:00:00 です。 次に、クエリで "CreatedDateTime > March 1, 2019 03:00:00" を使用して **N** 行の次のバッチがフェッチされます。

### <a name="skipping-soft-deleted-rows-optional"></a>回復可能な削除によって削除された行をスキップする (省略可能)

データベース内の回復可能な削除によって削除された行のインデックス作成を除外するには、行が削除されたかどうかを示す回復可能な削除によって削除される列の名前と値を指定します。

![削除済み (回復) の設定: "削除済み (回復) 列" および "削除済み行を示す削除済み (回復済み) 列の値"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>フル クロール: 検索権限を管理する

アクセス **制御メカニズムを指定** するさまざまなアクセス制御 (ACL) 列を選択するには、[アクセス許可の管理] を選択します。 フル クロール クエリで指定した列名SQLします。

各 ACL 列は、複数値を持つ列である必要があります。 これらの複数の ID 値は、セミコロン (;)、コンマ (,)) などの区切り文字で区切ることができます。 この区切り記号は、値の区切り記号 **フィールドに指定する必要** があります。

ACL として使用するには、次の ID の種類がサポートされています。

- **ユーザー プリンシパル名 (UPN)**: ユーザー プリンシパル名 (UPN) は、電子メール アドレス形式のシステム ユーザーの名前です。 UPN (例: john.doe@domain.com) は、ユーザー名 (ログオン名)、区切り記号 (@ 記号)、およびドメイン名 (UPN サフィックス) で構成されます。
- **Azure Active Directory (AAD) ID**: Azure AD では、すべてのユーザーまたはグループに、'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b' のようなオブジェクト ID があります。
- **Active Directory (AD)** セキュリティ ID : オンプレミスの AD セットアップでは、すべてのユーザーとグループに、"S-1-5-21-3878594291-2115959936-132693609-65242" のような不変の一意のセキュリティ識別子があります。

![アクセス制御リストを構成するための検索アクセス許可設定](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>手順 3b: 増分クロール (オプション)

このオプションの手順では、データベースの増分SQL実行するためのクエリを指定します。 このクエリを使用すると、SQLコネクタは、前回の増分クロール以降のデータに対する変更を決定します。 フル クロールの場合と同様に、クエリ、検索、または取得のオプションを選択する **列を選択****します**。 フル クロール クエリで指定したのと同じ ACL 列のセットを指定します。

次の図のコンポーネントは、1 つの例外を除き、フル クロール コンポーネントに似たものとなります。 この場合、"ModifiedDateTime" は選択された透かしの列です。 フル クロール [の手順を確認して](#step-3a-full-crawl-required) 、増分クロール クエリを作成する方法を確認し、例として次の画像を参照してください。

![OrderTable、AclTable、および使用できるプロパティの例を示す増分クロール スクリプト。](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>手順 4: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a>手順 5: スキーマを管理する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a>手順 6: 検索権限を管理する

フル クロール画面で指定された [ACL](#full-crawl-manage-search-permissions) を使用するか、ACL を上書きしてすべてのユーザーにコンテンツを表示することができます。

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a>手順 8: 接続を確認する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="next-steps-customize-the-search-results-page"></a>次の手順: 検索結果ページをカスタマイズする

独自のバーティカルと結果の種類を作成して、エンド ユーザーが新しい接続からの検索結果を表示できます。 この手順を実行しない場合、接続からのデータは検索結果ページに表示されます。

バーティカルと MRT を作成する方法の詳細については、「検索結果ページのカスタマイズ」 [を参照してください](customize-search-page.md)。

<!---## Troubleshooting-->

<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>制限事項

プレビュー SQLコネクタには、次の制限があります。

- Microsoft SQL サーバー コネクタ: オンプレミス データベースは、サーバー SQLバージョン 2008 以降で実行する必要があります。
- M365 サブスクリプションと Azure サブスクリプション (Azure SQL データベースをホスト) は、同じ Azure Active Directory 内に存在する必要があります。
- ACL は、ユーザー プリンシパル名 (UPN)、Azure Active Directory (Azure AD)、または Active Directory セキュリティを使用する場合にのみサポートされます。
- データベース列内のリッチ コンテンツのインデックス作成はサポートされていません。 このようなコンテンツの例としては、データベース列内のリンクとして存在する HTML、JSON、XML、BLOB、およびドキュメント解析があります。
