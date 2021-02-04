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

# <a name="azure-sql-and-microsoft-sql-server-graph-connectors"></a><span data-ttu-id="5de0d-103">Azure SQLおよび Microsoft SQL サーバー Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="5de0d-103">Azure SQL and Microsoft SQL server Graph connectors</span></span>

<span data-ttu-id="5de0d-104">Microsoft SQL サーバーまたは Azure SQL Graph コネクタを使用すると、組織はオンプレミスの SQL Server データベース、またはクラウド内の Azure SQL インスタンスでホストされているデータベースからデータを検出してインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-104">The Microsoft SQL server or Azure SQL Graph connector allows your organization to discover and index data from an on-premises SQL Server database, or a database hosted in your Azure SQL instance in the cloud.</span></span>
<span data-ttu-id="5de0d-105">Graph コネクタは、指定されたコンテンツのインデックスを Microsoft Search に作成します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-105">The Graph connector indexes specified content into Microsoft Search.</span></span> <span data-ttu-id="5de0d-106">ソース データを使用してインデックスを最新の状態に保つために、定期的なフル クロールと増分クロールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5de0d-106">To keep the index up to date with source data, it supports periodic full and incremental crawls.</span></span> <span data-ttu-id="5de0d-107">これらのコネクタSQL、特定のユーザーの検索結果へのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-107">With these SQL connectors, you can also restrict access to search results for certain users.</span></span>

> [!NOTE]
> <span data-ttu-id="5de0d-108">Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、一般的な Graph コネクタのセットアップ プロセスについて理解してください。</span><span class="sxs-lookup"><span data-stu-id="5de0d-108">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="5de0d-109">この記事は、Azure SQL および Microsoft SQL Graph コネクタを構成、実行、および監視するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="5de0d-109">This article is for anyone who configures, runs, and monitors a Azure SQL and Microsoft SQL server Graph connector.</span></span> <span data-ttu-id="5de0d-110">一般的なセットアップ プロセスを補完し、Azure SQL および Microsoft SQL Server Graph コネクタにのみ適用される手順を示します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-110">It supplements the general setup process, and shows instructions that apply only for the Azure SQL and Microsoft SQL server Graph connector.</span></span> <span data-ttu-id="5de0d-111">この記事には、Microsoft [](#limitations) SQL Server および Azure SQL コネクタに関する情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="5de0d-111">This article also includes information about [Limitations](#limitations) for the Microsoft SQL server and Azure SQL connectors.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="5de0d-112">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="5de0d-112">Before you get started</span></span>

### <a name="install-the-graph-connector-agent-required-for-on-premises-microsoft-sql-server-connector-only"></a><span data-ttu-id="5de0d-113">Graph コネクタ エージェントをインストールする (オンプレミスの Microsoft SQL サーバー コネクタにのみ必要)</span><span class="sxs-lookup"><span data-stu-id="5de0d-113">Install the Graph connector agent (required for on-premises Microsoft SQL server connector only)</span></span>

<span data-ttu-id="5de0d-114">オンプレミスのサードパーティ データにアクセスするには、Graph コネクタ エージェントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-114">In order to access your on-premises third-party data, you must install and configure the Graph connector agent.</span></span> <span data-ttu-id="5de0d-115">詳細 [については、「Graph コネクタ エージェントのインストール」](on-prem-agent.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5de0d-115">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="5de0d-116">手順 1: Microsoft 365 管理センターで Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="5de0d-116">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="5de0d-117">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-117">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="5de0d-118">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="5de0d-118">Step 2: Name the connection</span></span>

<span data-ttu-id="5de0d-119">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-119">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="5de0d-120">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5de0d-120">Step 3: Configure the connection settings</span></span>

### <a name="register-an-app-for-azure-sql-connector-only"></a><span data-ttu-id="5de0d-121">アプリを登録する (Azure SQL コネクタのみ)</span><span class="sxs-lookup"><span data-stu-id="5de0d-121">Register an app (for Azure SQL connector only)</span></span>

<span data-ttu-id="5de0d-122">Azure SQL コネクタの場合は、Azure Active Directory にアプリを登録して、Microsoft Search アプリがインデックス作成用のデータにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-122">For Azure SQL connector, you must register an app in Azure Active Directory to allow Microsoft Search app to access data for indexing.</span></span> <span data-ttu-id="5de0d-123">アプリの登録の詳細については、アプリの登録方法に関する Microsoft Graph ドキュメント [を参照してください](https://docs.microsoft.com/graph/auth-register-app-v2)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-123">To learn more about registering an app, refer Microsoft Graph documentation on how to [register an app](https://docs.microsoft.com/graph/auth-register-app-v2).</span></span>

<span data-ttu-id="5de0d-124">アプリの登録を完了し、アプリ名、アプリケーション (クライアント) ID、テナント ID をメモした後、新しいクライアント シークレットを [生成する必要があります](https://docs.microsoft.com/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-124">After completing the app registration and taking note of the app name, application (client) ID and tenant ID, you need to [generate a new client secret](https://docs.microsoft.com/azure/healthcare-apis/register-confidential-azure-ad-client-app#application-secret).</span></span> <span data-ttu-id="5de0d-125">クライアント シークレットは 1 回だけ表示されます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-125">The client secret will only be displayed once.</span></span> <span data-ttu-id="5de0d-126">クライアント シークレットを安全&保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-126">Remember to note & store the client secret securely.</span></span> <span data-ttu-id="5de0d-127">Microsoft Search で新しい接続を構成する場合は、クライアント ID とクライアント シークレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-127">Use the client ID and client secret while configuring a new connection in Microsoft Search.</span></span>

<span data-ttu-id="5de0d-128">登録済みのアプリを Azure SQL Database に追加するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-128">To add the registered app to your Azure SQL Database, you need to:</span></span>

- <span data-ttu-id="5de0d-129">Azure SQL DB にログインします。</span><span class="sxs-lookup"><span data-stu-id="5de0d-129">Log in to your Azure SQL DB</span></span>
- <span data-ttu-id="5de0d-130">新しいクエリ ウィンドウを開く</span><span class="sxs-lookup"><span data-stu-id="5de0d-130">Open a new query window</span></span>
- <span data-ttu-id="5de0d-131">コマンド 「CREATE USER [app name] FROM EXTERNAL PROVIDER」を実行して新しいユーザーを作成する</span><span class="sxs-lookup"><span data-stu-id="5de0d-131">Create a new user by running the command 'CREATE USER [app name] FROM EXTERNAL PROVIDER'</span></span>
- <span data-ttu-id="5de0d-132">コマンド 'exec sp_addrolemember 'db_datareader', [アプリ名]' または 'ALTER ROLE db_datareader ADD MEMBER [アプリ名]' を実行してユーザーをロールに追加する</span><span class="sxs-lookup"><span data-stu-id="5de0d-132">Add user to role by running command 'exec sp_addrolemember 'db_datareader', [app name]'  Or  'ALTER ROLE db_datareader ADD MEMBER [app name]'</span></span>

>[!NOTE]
><span data-ttu-id="5de0d-133">Azure Active Directory に登録されているアプリへのアクセスを取り消す場合は、登録されているアプリの削除に関する Azure の [ドキュメントを参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-remove-app)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-133">To revoke access to any app registered in Azure Active Directory, refer the Azure documentation on [removing a registered app](https://docs.microsoft.com/azure/active-directory/develop/quickstart-remove-app).</span></span>

### <a name="connection-settings"></a><span data-ttu-id="5de0d-134">接続設定</span><span class="sxs-lookup"><span data-stu-id="5de0d-134">Connection settings</span></span>

<span data-ttu-id="5de0d-135">Microsoft SQL サーバー コネクタをデータ ソースに接続するには、クロールするデータベース サーバーと、オンプレム エージェントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-135">To connect your Microsoft SQL server connector to a data source, you must configure the database server you want crawled and the on-prem agent.</span></span> <span data-ttu-id="5de0d-136">その後、必要な認証方法でデータベースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-136">You can then connect to the database with the required authentication method.</span></span>

> [!NOTE] 
> <span data-ttu-id="5de0d-137">Microsoft SQL SQL サーバー コネクタが接続するには、データベースをサーバー バージョン 2008 以降SQL実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-137">Your database must run SQL server version 2008 or later for the Microsoft SQL server connector to be able to connect.</span></span>

<span data-ttu-id="5de0d-138">Azure SQL コネクタの場合は、接続先のサーバー名または IP アドレスのみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-138">For the Azure SQL connector, you only need to specify the server name or IP address you want to connect to.</span></span> <span data-ttu-id="5de0d-139">Azure SQL コネクタは、データベースに接続するための Azure Active Directory Open ID Connect (OIDC) 認証のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5de0d-139">Azure SQL connector only supports Azure Active Directory Open ID connect (OIDC) authentication to connect to the database.</span></span>

<span data-ttu-id="5de0d-140">セキュリティを強化するには、Azure サーバーまたはデータベースに対して IP SQLを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-140">For added security, you may configure IP firewall rules for your Azure SQL server or database.</span></span> <span data-ttu-id="5de0d-141">IP ファイアウォール規則の設定の詳細については、IP ファイアウォール規則に関 [するドキュメントを参照してください](https://docs.microsoft.com/azure/azure-sql/database/firewall-configure)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-141">To learn more about setting up IP firewall rules, refer documentation on [IP firewall rules](https://docs.microsoft.com/azure/azure-sql/database/firewall-configure).</span></span> <span data-ttu-id="5de0d-142">ファイアウォール設定に次のクライアント IP 範囲を追加します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-142">Add the following client IP ranges in the firewall settings.</span></span>

| <span data-ttu-id="5de0d-143">Region</span><span class="sxs-lookup"><span data-stu-id="5de0d-143">Region</span></span> | <span data-ttu-id="5de0d-144">IP 範囲</span><span class="sxs-lookup"><span data-stu-id="5de0d-144">IP Range</span></span> |
| ------------ | ------------ |
| <span data-ttu-id="5de0d-145">NAM</span><span class="sxs-lookup"><span data-stu-id="5de0d-145">NAM</span></span> | <span data-ttu-id="5de0d-146">52.250.92.252/30, 52.224.250.216/30</span><span class="sxs-lookup"><span data-stu-id="5de0d-146">52.250.92.252/30, 52.224.250.216/30</span></span> |
| <span data-ttu-id="5de0d-147">EUR</span><span class="sxs-lookup"><span data-stu-id="5de0d-147">EUR</span></span> | <span data-ttu-id="5de0d-148">20.54.41.208/30, 51.105.159.88/30</span><span class="sxs-lookup"><span data-stu-id="5de0d-148">20.54.41.208/30, 51.105.159.88/30</span></span> |
| <span data-ttu-id="5de0d-149">APC</span><span class="sxs-lookup"><span data-stu-id="5de0d-149">APC</span></span> | <span data-ttu-id="5de0d-150">52.139.188.212/30, 20.43.146.44/30</span><span class="sxs-lookup"><span data-stu-id="5de0d-150">52.139.188.212/30, 20.43.146.44/30</span></span> |

<span data-ttu-id="5de0d-151">データベースコンテンツを検索するには、コネクタを構成するときにSQLクエリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-151">To search your database content, you must specify SQL queries when you configure the connector.</span></span> <span data-ttu-id="5de0d-152">これらのSQLクエリでは、すべての列を取得するために実行する必要がある SQL 結合を含め、インデックスを作成するデータベース列 (ソース プロパティ) の名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-152">These SQL queries need to name all the database columns that you want to index (that is, source properties), including any SQL joins that need to be performed to get all the columns.</span></span> <span data-ttu-id="5de0d-153">検索結果へのアクセスを制限するには、コネクタを構成するときに、アクセス制御リスト (ACL) SQLクエリ内で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-153">To restrict access to search results, you must specify Access Control Lists (ACLs) within SQL queries when you configure the connector.</span></span>

## <a name="step-3a-full-crawl-required"></a><span data-ttu-id="5de0d-154">手順 3a: フル クロール (必須)</span><span class="sxs-lookup"><span data-stu-id="5de0d-154">Step 3a: Full crawl (Required)</span></span>

<span data-ttu-id="5de0d-155">この手順では、データベースのフル SQL実行するクエリを構成します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-155">In this step, you configure the SQL query that runs a full crawl of the database.</span></span> <span data-ttu-id="5de0d-156">フル クロールでは、クエリ、検索、または取得のオプションを選択する列またはプロパティ **すべてが選択\*\*\*\*されます**。</span><span class="sxs-lookup"><span data-stu-id="5de0d-156">The full crawl selects all the columns or properties where you want to select the options **Query**, **Search**, or **Retrieve**.</span></span> <span data-ttu-id="5de0d-157">ACL 列を指定して、検索結果へのアクセスを特定のユーザーまたはグループに制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-157">You can also specify ACL columns to restrict access of search results to specific users or groups.</span></span>

> [!Tip]
> <span data-ttu-id="5de0d-158">必要なすべての列を取得するには、複数のテーブルを結合できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-158">To get all the columns that you need, you can join multiple tables.</span></span>

![プロパティの例を含む OrderTable と AclTable を示すスクリプト](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a><span data-ttu-id="5de0d-160">データ列の選択 (必須) と ACL 列 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="5de0d-160">Select data columns (Required) and ACL columns (Optional)</span></span>

<span data-ttu-id="5de0d-161">この例では、OrderId、OrderTitle、OrderDesc、CreatedDateTime、IsDeleted という検索データを保持する 5 つのデータ列を選択する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-161">The example demonstrates a selection of five data columns that hold the data for the search: OrderId, OrderTitle, OrderDesc, CreatedDateTime, and IsDeleted.</span></span> <span data-ttu-id="5de0d-162">データ行ごとに表示権限を設定するには、必要に応じて、次の ACL 列 (AllowedUsers、AllowedGroups、DeniedUsers、DeniedGroups) を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-162">To set view permissions for each row of data, you can optionally select these ACL columns: AllowedUsers, AllowedGroups, DeniedUsers, and DeniedGroups.</span></span> <span data-ttu-id="5de0d-163">これらすべてのデータ列には、クエリ、検索、**または取得\*\*\*\*の** オプション **があります**。</span><span class="sxs-lookup"><span data-stu-id="5de0d-163">All these data columns also have the options to **Query**, **Search**, or **Retrieve**.</span></span>

<span data-ttu-id="5de0d-164">次のクエリ例に示すように、データ列を選択します。 `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span><span class="sxs-lookup"><span data-stu-id="5de0d-164">Select data columns as shown in this example query: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span></span>

<span data-ttu-id="5de0d-165">検索結果へのアクセスを管理するには、クエリで 1 つ以上の ACL 列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-165">To manage access to the search results, you can specify one or more ACL columns in the query.</span></span> <span data-ttu-id="5de0d-166">このSQLコネクタを使用すると、レコード レベルごとにアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-166">The SQL connector allows you to control access at per record level.</span></span> <span data-ttu-id="5de0d-167">テーブル内のすべてのレコードに対して同じアクセス制御を持つオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-167">You can choose to have the same access control for all records in a table.</span></span> <span data-ttu-id="5de0d-168">ACL 情報が別のテーブルに格納されている場合は、クエリでそれらのテーブルとの結合を行う必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-168">If the ACL information is stored in a separate table, you might have to do a join with those tables in your query.</span></span>

<span data-ttu-id="5de0d-169">上記のクエリでの各 ACL 列の使用について、以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-169">The use of each of the ACL columns in the above query is described below.</span></span> <span data-ttu-id="5de0d-170">次の一覧では、4 つの **アクセス制御メカニズムについて説明します**。</span><span class="sxs-lookup"><span data-stu-id="5de0d-170">The following list explains the four **access control mechanisms**.</span></span>

- <span data-ttu-id="5de0d-171">**AllowedUsers**: この列は、検索結果にアクセスできるユーザー ID のリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-171">**AllowedUsers**: This column specifies the list of user IDs who can access the search results.</span></span> <span data-ttu-id="5de0d-172">次の例では、ユーザーのリスト: john@contoso.com、keith@contoso.com、および lisa@contoso.com は、OrderId = 12 のレコードにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-172">In the following example, list of users: john@contoso.com, keith@contoso.com, and lisa@contoso.com would only have access to a record with OrderId = 12.</span></span>
- <span data-ttu-id="5de0d-173">**AllowedGroups**: この列は、検索結果にアクセスできるユーザーのグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-173">**AllowedGroups**: This column specifies the group of users who will be able to access the search results.</span></span> <span data-ttu-id="5de0d-174">次の例では、グループsales-team@contoso.com OrderId = 12 のレコードにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-174">In the following example, group sales-team@contoso.com would only have access to record with OrderId = 12.</span></span>
- <span data-ttu-id="5de0d-175">**DeniedUsers**: この列は、検索結果にアクセスできないユーザーのリストを指定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-175">**DeniedUsers**: This column specifies the list of users who do **not** have access to the search results.</span></span> <span data-ttu-id="5de0d-176">次の例では、ユーザー john@contoso.comおよび keith@contoso.com OrderId = 13 のレコードにアクセスできないのに対し、他のすべてのユーザーは、このレコードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-176">In the following example, users john@contoso.com and keith@contoso.com do not have access to record with OrderId = 13, whereas everyone else has access to this record.</span></span>
- <span data-ttu-id="5de0d-177">**DeniedGroups**: この列は、検索結果にアクセスできないユーザーのグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-177">**DeniedGroups**: This column specifies the group of users who do **not** have access to the search results.</span></span> <span data-ttu-id="5de0d-178">次の例では、グループ engg-team@contoso.comおよび pm-team@contoso.com は OrderId = 15 のレコードにアクセスすることはできませんが、他のすべてのユーザーは、このレコードにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-178">In the following example, groups engg-team@contoso.com and pm-team@contoso.com do not have access to record with OrderId = 15, whereas everyone else has access to this record.</span></span>  

![プロパティの例を含む OrderTable と AclTable を示すサンプル データ](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a><span data-ttu-id="5de0d-180">サポートされるデータ型</span><span class="sxs-lookup"><span data-stu-id="5de0d-180">Supported data types</span></span>

<span data-ttu-id="5de0d-181">次の表に、MS SQL コネクタと Azure コネクタでサポートされているデータ型のSQLをSQLします。</span><span class="sxs-lookup"><span data-stu-id="5de0d-181">The below table summarizes the SQL data types that are supported in the MS SQL and Azure SQL connectors.</span></span> <span data-ttu-id="5de0d-182">この表では、サポートされているデータ型のインデックスデータ型SQL要約します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-182">The table also summarizes the indexing data type for the supported SQL data type.</span></span> <span data-ttu-id="5de0d-183">インデックス作成でサポートされている Microsoft Graph コネクタのデータ型の詳細については、プロパティ リソースの種類に関する [ドキュメントを参照してください](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-183">To learn more about Microsoft Graph connectors supported data types for indexing, refer documentation on [property resource types](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true).</span></span>

| <span data-ttu-id="5de0d-184">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="5de0d-184">Category</span></span> | <span data-ttu-id="5de0d-185">ソース データ型</span><span class="sxs-lookup"><span data-stu-id="5de0d-185">Source data type</span></span> | <span data-ttu-id="5de0d-186">インデックス作成データ型</span><span class="sxs-lookup"><span data-stu-id="5de0d-186">Indexing data type</span></span> |
| ------------ | ------------ | ------------ |
| <span data-ttu-id="5de0d-187">日時</span><span class="sxs-lookup"><span data-stu-id="5de0d-187">Date and time</span></span> | <span data-ttu-id="5de0d-188">date</span><span class="sxs-lookup"><span data-stu-id="5de0d-188">date</span></span> <br> <span data-ttu-id="5de0d-189">日付型</span><span class="sxs-lookup"><span data-stu-id="5de0d-189">datetime</span></span> <br> <span data-ttu-id="5de0d-190">datetime2</span><span class="sxs-lookup"><span data-stu-id="5de0d-190">datetime2</span></span> <br> <span data-ttu-id="5de0d-191">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="5de0d-191">smalldatetime</span></span> | <span data-ttu-id="5de0d-192">日付型</span><span class="sxs-lookup"><span data-stu-id="5de0d-192">datetime</span></span> |
| <span data-ttu-id="5de0d-193">正確な数値</span><span class="sxs-lookup"><span data-stu-id="5de0d-193">Exact numeric</span></span> | <span data-ttu-id="5de0d-194">bigint</span><span class="sxs-lookup"><span data-stu-id="5de0d-194">bigint</span></span> <br> <span data-ttu-id="5de0d-195">int</span><span class="sxs-lookup"><span data-stu-id="5de0d-195">int</span></span> <br> <span data-ttu-id="5de0d-196">smallint</span><span class="sxs-lookup"><span data-stu-id="5de0d-196">smallint</span></span> <br> <span data-ttu-id="5de0d-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="5de0d-197">tinyint</span></span> | <span data-ttu-id="5de0d-198">int64</span><span class="sxs-lookup"><span data-stu-id="5de0d-198">int64</span></span> |
| <span data-ttu-id="5de0d-199">正確な数値</span><span class="sxs-lookup"><span data-stu-id="5de0d-199">Exact numeric</span></span> | <span data-ttu-id="5de0d-200">bit</span><span class="sxs-lookup"><span data-stu-id="5de0d-200">bit</span></span> | <span data-ttu-id="5de0d-201">ブール値</span><span class="sxs-lookup"><span data-stu-id="5de0d-201">boolean</span></span> |
| <span data-ttu-id="5de0d-202">近似数値</span><span class="sxs-lookup"><span data-stu-id="5de0d-202">Approximate numeric</span></span> | <span data-ttu-id="5de0d-203">浮動小数点数</span><span class="sxs-lookup"><span data-stu-id="5de0d-203">float</span></span> <br> <span data-ttu-id="5de0d-204">本当の</span><span class="sxs-lookup"><span data-stu-id="5de0d-204">real</span></span> | <span data-ttu-id="5de0d-205">double</span><span class="sxs-lookup"><span data-stu-id="5de0d-205">double</span></span> |
| <span data-ttu-id="5de0d-206">文字の文字列</span><span class="sxs-lookup"><span data-stu-id="5de0d-206">Character string</span></span> | <span data-ttu-id="5de0d-207">char</span><span class="sxs-lookup"><span data-stu-id="5de0d-207">char</span></span> <br> <span data-ttu-id="5de0d-208">varchar</span><span class="sxs-lookup"><span data-stu-id="5de0d-208">varchar</span></span> <br> <span data-ttu-id="5de0d-209">text</span><span class="sxs-lookup"><span data-stu-id="5de0d-209">text</span></span> | <span data-ttu-id="5de0d-210">string</span><span class="sxs-lookup"><span data-stu-id="5de0d-210">string</span></span> |
| <span data-ttu-id="5de0d-211">Unicode 文字文字列</span><span class="sxs-lookup"><span data-stu-id="5de0d-211">Unicode character strings</span></span> | <span data-ttu-id="5de0d-212">nchar</span><span class="sxs-lookup"><span data-stu-id="5de0d-212">nchar</span></span> <br> <span data-ttu-id="5de0d-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5de0d-213">nvarchar</span></span> <br> <span data-ttu-id="5de0d-214">ntext</span><span class="sxs-lookup"><span data-stu-id="5de0d-214">ntext</span></span> | <span data-ttu-id="5de0d-215">string</span><span class="sxs-lookup"><span data-stu-id="5de0d-215">string</span></span> |
| <span data-ttu-id="5de0d-216">その他のデータ型</span><span class="sxs-lookup"><span data-stu-id="5de0d-216">Other data types</span></span> | <span data-ttu-id="5de0d-217">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5de0d-217">uniqueidentifier</span></span> | <span data-ttu-id="5de0d-218">string</span><span class="sxs-lookup"><span data-stu-id="5de0d-218">string</span></span> |

<span data-ttu-id="5de0d-219">現在直接サポートされていないその他のデータ型では、列をサポートされているデータ型に明示的にキャストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-219">For any other data type currently not directly supported, the column needs to be explicitly cast to a supported data type.</span></span>

### <a name="watermark-required"></a><span data-ttu-id="5de0d-220">透かし (必須)</span><span class="sxs-lookup"><span data-stu-id="5de0d-220">Watermark (Required)</span></span>

<span data-ttu-id="5de0d-221">データベースの過負荷を防ぐために、コネクタはフル クロール の透かし列を使用してフル クロール クエリをバッチ処理して再開します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-221">To prevent overloading the database, the connector batches and resumes full-crawl queries with a full-crawl watermark column.</span></span> <span data-ttu-id="5de0d-222">透かし列の値を使用すると、後続の各バッチがフェッチされ、最後のチェックポイントからクエリが再開されます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-222">By using the value of the watermark column, each subsequent batch is fetched, and querying is resumed from the last checkpoint.</span></span> <span data-ttu-id="5de0d-223">基本的に、このメカニズムはフル クロールのデータ更新を制御します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-223">Essentially this mechanisms controls data refresh for full crawls.</span></span>

<span data-ttu-id="5de0d-224">次の例に示すように、透かしのクエリ スニペットを作成します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-224">Create query snippets for watermarks as shown in these examples:</span></span>

- <span data-ttu-id="5de0d-225">`WHERE (CreatedDateTime > @watermark)`.</span><span class="sxs-lookup"><span data-stu-id="5de0d-225">`WHERE (CreatedDateTime > @watermark)`.</span></span> <span data-ttu-id="5de0d-226">予約済みのキーワードで透かしの列名を引用します `@watermark` 。</span><span class="sxs-lookup"><span data-stu-id="5de0d-226">Cite the watermark column name with the reserved keyword `@watermark`.</span></span> <span data-ttu-id="5de0d-227">透かしの列の並べ替え順序が昇順の場合は、使用 `>` します。それ以外の場合は、使用します `<` 。</span><span class="sxs-lookup"><span data-stu-id="5de0d-227">If the sort order of the watermark column is ascending, use `>`; otherwise, use `<`.</span></span>
- <span data-ttu-id="5de0d-228">`ORDER BY CreatedDateTime ASC`.</span><span class="sxs-lookup"><span data-stu-id="5de0d-228">`ORDER BY CreatedDateTime ASC`.</span></span> <span data-ttu-id="5de0d-229">透かしの列を昇順または降順で並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-229">Sort on the watermark column in ascending or descending order.</span></span>

<span data-ttu-id="5de0d-230">次の図に示す構成では `CreatedDateTime` 、選択されている透かし列です。</span><span class="sxs-lookup"><span data-stu-id="5de0d-230">In the configuration shown in the following image, `CreatedDateTime` is the selected watermark column.</span></span> <span data-ttu-id="5de0d-231">行の最初のバッチをフェッチするには、透かし列のデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-231">To fetch the first batch of rows, specify the data type of the watermark column.</span></span> <span data-ttu-id="5de0d-232">この場合、データ型は次の値です `DateTime` 。</span><span class="sxs-lookup"><span data-stu-id="5de0d-232">In this case, the data type is `DateTime`.</span></span>

![透かし列の構成](media/MSSQL-watermark.png)

<span data-ttu-id="5de0d-234">最初のクエリは、"CreatedDateTime > January 1, 1753 00:00:00" (DateTime データ型の最小値) を使用して、最初の **N** 行数をフェッチします。</span><span class="sxs-lookup"><span data-stu-id="5de0d-234">The first query fetches the first **N** number of rows by using: "CreatedDateTime > January 1, 1753 00:00:00" (min value of DateTime data type).</span></span> <span data-ttu-id="5de0d-235">最初のバッチがフェッチされた後、行が昇順で並べ替えらた場合、バッチで返される最高値はチェックポイントとして `CreatedDateTime` 保存されます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-235">After the first batch is fetched, the highest value of `CreatedDateTime` returned in the batch is saved as the checkpoint if the rows are sorted in ascending order.</span></span> <span data-ttu-id="5de0d-236">たとえば、2019 年 3 月 1 日 03:00:00 です。</span><span class="sxs-lookup"><span data-stu-id="5de0d-236">An example is March 1, 2019 03:00:00.</span></span> <span data-ttu-id="5de0d-237">次に、クエリで "CreatedDateTime > March 1, 2019 03:00:00" を使用して **N** 行の次のバッチがフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-237">Then the next batch of **N** rows is fetched by using "CreatedDateTime > March 1, 2019 03:00:00" in the query.</span></span>

### <a name="skipping-soft-deleted-rows-optional"></a><span data-ttu-id="5de0d-238">回復可能な削除によって削除された行をスキップする (省略可能)</span><span class="sxs-lookup"><span data-stu-id="5de0d-238">Skipping soft-deleted rows (Optional)</span></span>

<span data-ttu-id="5de0d-239">データベース内の回復可能な削除によって削除された行のインデックス作成を除外するには、行が削除されたかどうかを示す回復可能な削除によって削除される列の名前と値を指定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-239">To exclude soft-deleted rows in your database from being indexed, specify the soft-delete column name and value that indicates the row is deleted.</span></span>

![削除済み (回復) の設定: "削除済み (回復) 列" および "削除済み行を示す削除済み (回復済み) 列の値"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a><span data-ttu-id="5de0d-241">フル クロール: 検索権限を管理する</span><span class="sxs-lookup"><span data-stu-id="5de0d-241">Full crawl: Manage search permissions</span></span>

<span data-ttu-id="5de0d-242">アクセス **制御メカニズムを指定** するさまざまなアクセス制御 (ACL) 列を選択するには、[アクセス許可の管理] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-242">Select **Manage permissions** to choose the various access control (ACL) columns that specify the access control mechanism.</span></span> <span data-ttu-id="5de0d-243">フル クロール クエリで指定した列名SQLします。</span><span class="sxs-lookup"><span data-stu-id="5de0d-243">Select the column name you specified in the full crawl SQL query.</span></span>

<span data-ttu-id="5de0d-244">各 ACL 列は、複数値を持つ列である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-244">Each of the ACL columns is expected to be a multi-valued column.</span></span> <span data-ttu-id="5de0d-245">これらの複数の ID 値は、セミコロン (;)、コンマ (,)) などの区切り文字で区切ることができます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-245">These multiple ID values can be separated by separators such as semicolon (;), comma (,), and so on.</span></span> <span data-ttu-id="5de0d-246">この区切り記号は、値の区切り記号 **フィールドに指定する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-246">You need to specify this separator in the **value separator** field.</span></span>

<span data-ttu-id="5de0d-247">ACL として使用するには、次の ID の種類がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5de0d-247">The following ID types are supported for using as ACLs:</span></span>

- <span data-ttu-id="5de0d-248">**ユーザー プリンシパル名 (UPN)**: ユーザー プリンシパル名 (UPN) は、電子メール アドレス形式のシステム ユーザーの名前です。</span><span class="sxs-lookup"><span data-stu-id="5de0d-248">**User Principal Name (UPN)**: A User Principal Name (UPN) is the name of a system user in an email address format.</span></span> <span data-ttu-id="5de0d-249">UPN (例: john.doe@domain.com) は、ユーザー名 (ログオン名)、区切り記号 (@ 記号)、およびドメイン名 (UPN サフィックス) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-249">A UPN (for example: john.doe@domain.com) consists of the username (logon name), separator (the @ symbol), and domain name (UPN suffix).</span></span>
- <span data-ttu-id="5de0d-250">**Azure Active Directory (AAD) ID**: Azure AD では、すべてのユーザーまたはグループに、'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b' のようなオブジェクト ID があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-250">**Azure Active Directory (AAD) ID**: In Azure AD, every user or group has an object ID that looks something like 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'.</span></span>
- <span data-ttu-id="5de0d-251">**Active Directory (AD)** セキュリティ ID : オンプレミスの AD セットアップでは、すべてのユーザーとグループに、"S-1-5-21-3878594291-2115959936-132693609-65242" のような不変の一意のセキュリティ識別子があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-251">**Active Directory (AD) Security ID**: In an on-premises AD setup, every user and group have an immutable, unique security identifier that looks something like 'S-1-5-21-3878594291-2115959936-132693609-65242.'</span></span>

![アクセス制御リストを構成するための検索アクセス許可設定](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a><span data-ttu-id="5de0d-253">手順 3b: 増分クロール (オプション)</span><span class="sxs-lookup"><span data-stu-id="5de0d-253">Step 3b: Incremental crawl (Optional)</span></span>

<span data-ttu-id="5de0d-254">このオプションの手順では、データベースの増分SQL実行するためのクエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-254">In this optional step, provide a SQL query to run an incremental crawl of the database.</span></span> <span data-ttu-id="5de0d-255">このクエリを使用すると、SQLコネクタは、前回の増分クロール以降のデータに対する変更を決定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-255">With this query, the SQL connector determines any changes to the data since the last incremental crawl.</span></span> <span data-ttu-id="5de0d-256">フル クロールの場合と同様に、クエリ、検索、または取得のオプションを選択する **列を選択\*\*\*\*します**。</span><span class="sxs-lookup"><span data-stu-id="5de0d-256">As in the full crawl, select all columns where you want to select the options **Query**, **Search**, or **Retrieve**.</span></span> <span data-ttu-id="5de0d-257">フル クロール クエリで指定したのと同じ ACL 列のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="5de0d-257">Specify the same set of ACL columns that you specified in the full crawl query.</span></span>

<span data-ttu-id="5de0d-258">次の図のコンポーネントは、1 つの例外を除き、フル クロール コンポーネントに似たものとなります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-258">The components in the following image resemble the full crawl components with one exception.</span></span> <span data-ttu-id="5de0d-259">この場合、"ModifiedDateTime" は選択された透かしの列です。</span><span class="sxs-lookup"><span data-stu-id="5de0d-259">In this case, "ModifiedDateTime" is the selected watermark column.</span></span> <span data-ttu-id="5de0d-260">フル クロール [の手順を確認して](#step-3a-full-crawl-required) 、増分クロール クエリを作成する方法を確認し、例として次の画像を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5de0d-260">Review the [full crawl steps](#step-3a-full-crawl-required) to learn how to write your incremental crawl query and see the following image as an example.</span></span>

![OrderTable、AclTable、および使用できるプロパティの例を示す増分クロール スクリプト。](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="5de0d-262">手順 4: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5de0d-262">Step 4: Assign property labels</span></span>

<span data-ttu-id="5de0d-263">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-263">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-5-manage-schema"></a><span data-ttu-id="5de0d-264">手順 5: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="5de0d-264">Step 5: Manage schema</span></span>

<span data-ttu-id="5de0d-265">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-265">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="5de0d-266">手順 6: 検索権限を管理する</span><span class="sxs-lookup"><span data-stu-id="5de0d-266">Step 6: Manage search permissions</span></span>

<span data-ttu-id="5de0d-267">フル クロール画面で指定された [ACL](#full-crawl-manage-search-permissions) を使用するか、ACL を上書きしてすべてのユーザーにコンテンツを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-267">You can choose to use the [ACLs specified in the full crawl screen](#full-crawl-manage-search-permissions) or you can override them to make your content visible to everyone.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="5de0d-268">手順 7: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="5de0d-268">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="5de0d-269">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-269">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="5de0d-270">手順 8: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="5de0d-270">Step 8: Review connection</span></span>

<span data-ttu-id="5de0d-271">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-271">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="next-steps-customize-the-search-results-page"></a><span data-ttu-id="5de0d-272">次の手順: 検索結果ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="5de0d-272">Next steps: Customize the search results page</span></span>

<span data-ttu-id="5de0d-273">独自のバーティカルと結果の種類を作成して、エンド ユーザーが新しい接続からの検索結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-273">Create your own verticals and result types, so end users can view search results from new connections.</span></span> <span data-ttu-id="5de0d-274">この手順を実行しない場合、接続からのデータは検索結果ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-274">Without this step, data from your connection won't show up on the search results page.</span></span>

<span data-ttu-id="5de0d-275">バーティカルと MRT を作成する方法の詳細については、「検索結果ページのカスタマイズ」 [を参照してください](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="5de0d-275">To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).</span></span>

<!---## Troubleshooting-->

<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="5de0d-276">制限事項</span><span class="sxs-lookup"><span data-stu-id="5de0d-276">Limitations</span></span>

<span data-ttu-id="5de0d-277">プレビュー SQLコネクタには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-277">The SQL connectors have these limitations in the preview release:</span></span>

- <span data-ttu-id="5de0d-278">Microsoft SQL サーバー コネクタ: オンプレミス データベースは、サーバー SQLバージョン 2008 以降で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-278">Microsoft SQL server connector: The on-premises database must run SQL server version 2008 or later.</span></span>
- <span data-ttu-id="5de0d-279">M365 サブスクリプションと Azure サブスクリプション (Azure SQL データベースをホスト) は、同じ Azure Active Directory 内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-279">The M365 subscription and Azure subscription (hosting Azure SQL database) must lie within the same Azure Active Directory.</span></span>
- <span data-ttu-id="5de0d-280">ACL は、ユーザー プリンシパル名 (UPN)、Azure Active Directory (Azure AD)、または Active Directory セキュリティを使用する場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="5de0d-280">ACLs are only supported by using a User Principal Name (UPN), Azure Active Directory (Azure AD), or Active Directory Security.</span></span>
- <span data-ttu-id="5de0d-281">データベース列内のリッチ コンテンツのインデックス作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5de0d-281">Indexing rich content inside database columns is not supported.</span></span> <span data-ttu-id="5de0d-282">このようなコンテンツの例としては、データベース列内のリンクとして存在する HTML、JSON、XML、BLOB、およびドキュメント解析があります。</span><span class="sxs-lookup"><span data-stu-id="5de0d-282">Examples of such content are HTML, JSON, XML, blobs, and document parsings that exist as links inside the database columns.</span></span>
