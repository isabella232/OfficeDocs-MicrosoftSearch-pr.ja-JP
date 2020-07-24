---
title: Microsoft が開発したコネクタを Microsoft Search 用に構成する
ms.author: mounika.narayanan
author: monaray
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft が開発したコネクタを Microsoft Search 用に構成する
ms.openlocfilehash: 30c60e94e8e633bce90bbc1984eee35d3ceda771
ms.sourcegitcommit: f2323c43fc732890213223efac32006df5b92c28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "45387975"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="set-up-your-microsoft-built-connector-for-microsoft-search"></a><span data-ttu-id="d8918-103">Microsoft が開発したコネクタを Microsoft Search 用にセットアップする</span><span class="sxs-lookup"><span data-stu-id="d8918-103">Set up your Microsoft-built connector for Microsoft Search</span></span>

<span data-ttu-id="d8918-104">この記事では、Microsoft によって作成されたコネクタを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8918-104">This article guides you through the steps of configuring a Microsoft-built connector.</span></span> <span data-ttu-id="d8918-105">この記事では、Microsoft 365[管理センター](https://admin.microsoft.com)での接続のセットアップフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d8918-105">It outlines the flow of setting up a connection in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="d8918-106">特定の Microsoft が作成したコネクタをセットアップする方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8918-106">For more information on how to set up specific Microsoft-built connectors, see these articles:</span></span>

* [<span data-ttu-id="d8918-107">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="d8918-107">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="d8918-108">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="d8918-108">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="d8918-109">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="d8918-109">Azure SQL</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="d8918-110">大企業の Web サイト</span><span class="sxs-lookup"><span data-stu-id="d8918-110">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="d8918-111">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="d8918-111">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="d8918-112">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="d8918-112">Microsoft SQL server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="d8918-113">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="d8918-113">ServiceNow</span></span>](servicenow-connector.md)

## <a name="set-up"></a><span data-ttu-id="d8918-114">セットアップ</span><span class="sxs-lookup"><span data-stu-id="d8918-114">Set up</span></span>

<span data-ttu-id="d8918-115">Microsoft によって作成されたコネクタのいずれかを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d8918-115">Complete the following steps to configure any of the Microsoft-built connectors.</span></span>

1. <span data-ttu-id="d8918-116">[Microsoft 365 管理センター](https://admin.microsoft.com)の [[コネクタ] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)に移動します。</span><span class="sxs-lookup"><span data-stu-id="d8918-116">Go to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="d8918-117">[Microsoft 365](https://www.microsoft.com/microsoft-365)テナントの資格情報を使用して、アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="d8918-117">Sign in to your account with the credentials for your [Microsoft 365](https://www.microsoft.com/microsoft-365) tenant.</span></span>
3. <span data-ttu-id="d8918-118">[**コネクタの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8918-118">Select **Add a connector**.</span></span>
4. <span data-ttu-id="d8918-119">使用可能なコネクタのリストから、選択したコネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="d8918-119">From the list of available connectors, select the connector of your choice.</span></span>

![利用可能なデータソースは次のとおりです。 Azure DevOps Connector、ServiceNow、ADLS Gen2、エンタープライズ web サイト、MediaWiki、Microsoft SQL server、および Azure SQL。](media/add_connector.png)

### <a name="name-the-connector"></a><span data-ttu-id="d8918-121">コネクタに名前を指定する</span><span class="sxs-lookup"><span data-stu-id="d8918-121">Name the connector</span></span>

<span data-ttu-id="d8918-122">接続を作成するには、最初に次の属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8918-122">To create a connection, first specify these attributes:</span></span>

1. <span data-ttu-id="d8918-123">接続の名前</span><span class="sxs-lookup"><span data-stu-id="d8918-123">Name of the connection</span></span>
2. <span data-ttu-id="d8918-124">接続 ID</span><span class="sxs-lookup"><span data-stu-id="d8918-124">Connection ID</span></span>
3. <span data-ttu-id="d8918-125">説明 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="d8918-125">Description (optional)</span></span>

<span data-ttu-id="d8918-126">接続 ID は、コネクタの暗黙的なプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="d8918-126">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="d8918-127">このファイルには、英数字のみが含まれ、最大32文字の文字が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8918-127">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span>

### <a name="connect-to-a-data-source"></a><span data-ttu-id="d8918-128">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="d8918-128">Connect to a data source</span></span>

<span data-ttu-id="d8918-129">データ接続プロセスは、コネクタの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="d8918-129">The data connection process varies based on the type of connector.</span></span> <span data-ttu-id="d8918-130">オンプレミスのデータソースへの接続の詳細については、「[オンプレミスのデータゲートウェイをインストール](https://aka.ms/configuregateway)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8918-130">To learn more about connecting to your on-premises data source, see [Install an on-premises data gateway](https://aka.ms/configuregateway).</span></span>

### <a name="select-source-properties"></a><span data-ttu-id="d8918-131">ソースのプロパティの選択</span><span class="sxs-lookup"><span data-stu-id="d8918-131">Select source properties</span></span>

<span data-ttu-id="d8918-132">サードパーティのデータソースによって設定されたデータフィールドは、ソースプロパティとして Microsoft Search にインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="d8918-132">The data fields set by your third-party data source as source properties are indexed into Microsoft Search.</span></span> <span data-ttu-id="d8918-133">これらのプロパティを変更するには、[**コネクタ**] ページの右側にあるサイドバーで [**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d8918-133">To modify these properties, select **Edit properties** in the side bar on the right of the **Connectors** page.</span></span> <span data-ttu-id="d8918-134">**最大64のソースプロパティ**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d8918-134">You can select **up to 64 source properties**.</span></span>

### <a name="manage-the-search-schema"></a><span data-ttu-id="d8918-135">検索スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="d8918-135">Manage the search schema</span></span>

<span data-ttu-id="d8918-136">管理者は、検索スキーマの属性を設定して、各ソースプロパティの検索機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="d8918-136">Admins can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="d8918-137">検索スキーマは、検索結果ページに表示される結果と、エンドユーザーが表示およびアクセスできる情報を決定するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="d8918-137">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="d8918-138">検索スキーマの属性には、検索可能、**クエリ**可能 **、および取得**可能**なものが**あります。</span><span class="sxs-lookup"><span data-stu-id="d8918-138">Search schema attributes include **searchable**, **queryable**, and **retrievable**.</span></span> <span data-ttu-id="d8918-139">次の表に、Microsoft Graph コネクタがサポートしている各属性とその機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="d8918-139">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="d8918-140">検索スキーマの属性</span><span class="sxs-lookup"><span data-stu-id="d8918-140">Search schema attribute</span></span> | <span data-ttu-id="d8918-141">関数</span><span class="sxs-lookup"><span data-stu-id="d8918-141">Function</span></span> | <span data-ttu-id="d8918-142">例</span><span class="sxs-lookup"><span data-stu-id="d8918-142">Example</span></span>
--- | --- | ---
<span data-ttu-id="d8918-143">サーチ</span><span class="sxs-lookup"><span data-stu-id="d8918-143">SEARCHABLE</span></span> | <span data-ttu-id="d8918-144">プロパティのテキストコンテンツを検索可能にします。</span><span class="sxs-lookup"><span data-stu-id="d8918-144">Makes the text content of a property searchable.</span></span> <span data-ttu-id="d8918-145">プロパティの内容は、フルテキストインデックスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="d8918-145">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="d8918-146">プロパティが**title**の場合、**エンタープライズ**のクエリは、テキストまたはタイトルに " **enterprise** " が含まれている回答を返します。</span><span class="sxs-lookup"><span data-stu-id="d8918-146">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="d8918-147">クエリ可能</span><span class="sxs-lookup"><span data-stu-id="d8918-147">QUERYABLE</span></span> | <span data-ttu-id="d8918-148">クエリによって特定のプロパティの一致が検索されます。</span><span class="sxs-lookup"><span data-stu-id="d8918-148">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="d8918-149">プロパティ名は、プログラムまたは逐語的にクエリで指定できます。</span><span class="sxs-lookup"><span data-stu-id="d8918-149">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="d8918-150">**Title**プロパティがクエリ可能な場合は、クエリ**タイトル: Enterprise**がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="d8918-150">If the **Title** property is queryable, then the query **Title: Enterprise** is supported.</span></span>
<span data-ttu-id="d8918-151">だっ</span><span class="sxs-lookup"><span data-stu-id="d8918-151">RETRIEVABLE</span></span> | <span data-ttu-id="d8918-152">検索結果の種類には取得可能なプロパティのみを使用し、検索結果に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d8918-152">Only retrievable properties can be used in the result type and display in the search result.</span></span> |

<span data-ttu-id="d8918-153">すべてのコネクタについて、カスタムの種類を手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8918-153">For all connectors, custom types must be set manually.</span></span> <span data-ttu-id="d8918-154">各フィールドの検索機能をアクティブにするには、プロパティのリストにマップされた検索スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8918-154">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="d8918-155">接続ウィザードは、選択したソースプロパティのセットに基づいて検索スキーマを自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="d8918-155">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="d8918-156">このスキーマを変更するには、[検索スキーマ] ページで各プロパティと属性のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d8918-156">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

![コネクタのスキーマは、クエリ、検索、および取得機能を追加または削除することでカスタマイズできます。](media/manageschema.png)

<span data-ttu-id="d8918-158">これらの制限と推奨事項は、検索スキーマ設定に適用されます。</span><span class="sxs-lookup"><span data-stu-id="d8918-158">These restrictions and recommendations apply to search schema settings:</span></span>

* <span data-ttu-id="d8918-159">カスタム型のインデックスを作成するコネクタの場合は、取得可能なメインコンテンツを含むフィールドを**マークし\*\*\*\*ない**ことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d8918-159">For connectors that index custom types, we recommend that you **do not** mark the field that contains the main content **retrievable**.</span></span> <span data-ttu-id="d8918-160">検索結果が検索属性を使用して表示される場合、パフォーマンスの著しい問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="d8918-160">Significant performance issues occur when search results render with that search attribute.</span></span> <span data-ttu-id="d8918-161">この例は、 [ServiceNow](https://www.servicenow.com)ナレッジベースの記事の**テキスト**コンテンツフィールドです。</span><span class="sxs-lookup"><span data-stu-id="d8918-161">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>
* <span data-ttu-id="d8918-162">検索結果には、取得可能としてマークされたプロパティのみが表示され、モダンの検索結果の種類 (MRTs) を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="d8918-162">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>
* <span data-ttu-id="d8918-163">検索可能としてマークできるのは、文字列のプロパティだけです。</span><span class="sxs-lookup"><span data-stu-id="d8918-163">Only string properties can be marked searchable.</span></span>

> [!Note]
> <span data-ttu-id="d8918-164">接続を作成した後、スキーマを変更する**ことはできません**。</span><span class="sxs-lookup"><span data-stu-id="d8918-164">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="d8918-165">そのためには、接続を削除して、新しい接続を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8918-165">To do that, you need to delete your connection and create a new one.</span></span>

### <a name="manage-search-permissions"></a><span data-ttu-id="d8918-166">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="d8918-166">Manage search permissions</span></span>

<span data-ttu-id="d8918-167">アクセス制御リスト (Acl) は、組織内のどのユーザーがデータの各アイテムにアクセスできるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d8918-167">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span> <span data-ttu-id="d8918-168">すべてのコネクタは、すべてのユーザーに表示される検索アクセス許可をサポートします。</span><span class="sxs-lookup"><span data-stu-id="d8918-168">All the connectors support search permissions that are visible to all users.</span></span>

### <a name="set-the-refresh-schedule"></a><span data-ttu-id="d8918-169">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="d8918-169">Set the refresh schedule</span></span>

<span data-ttu-id="d8918-170">更新スケジュールは、Microsoft Graph と Microsoft Search のインデックスとデータを同期する頻度を決定します。</span><span class="sxs-lookup"><span data-stu-id="d8918-170">The refresh schedule determines how often your data is synced with the index in Microsoft Graph and Microsoft Search.</span></span> <span data-ttu-id="d8918-171">フルクロールまたは増分クロールの2つの方法で更新をスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8918-171">You can schedule the refresh in two ways: full crawl or incremental crawl.</span></span>

<span data-ttu-id="d8918-172">**フルクロール**では、検索エンジンは、以前のクロールに関係なく、コンテンツソース内のすべてのアイテムを処理してインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="d8918-172">With a **full crawl**, the search engine processes and indexes every item in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="d8918-173">フルクロールは、次のような場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="d8918-173">Full crawl works best in these situations:</span></span>

* <span data-ttu-id="d8918-174">データの削除を検出します。</span><span class="sxs-lookup"><span data-stu-id="d8918-174">Detecting deletions of data.</span></span>
* <span data-ttu-id="d8918-175">増分クロールで、エラーのためにコンテンツをクロールできませんでした。</span><span class="sxs-lookup"><span data-stu-id="d8918-175">The incremental crawl failed to crawl content for errors.</span></span>
* <span data-ttu-id="d8918-176">Acl が変更されました。</span><span class="sxs-lookup"><span data-stu-id="d8918-176">ACLs were modified.</span></span>
* <span data-ttu-id="d8918-177">クロールルールが変更されました。</span><span class="sxs-lookup"><span data-stu-id="d8918-177">Crawl rules were modified.</span></span>
* <span data-ttu-id="d8918-178">Microsoft Search のソフトウェア更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="d8918-178">A software update for Microsoft Search is required.</span></span> <span data-ttu-id="d8918-179">更新プログラムによって検索スキーマが変更されます。</span><span class="sxs-lookup"><span data-stu-id="d8918-179">Updates modify the search schema.</span></span>

<span data-ttu-id="d8918-180">**増分クロール**では、検索エンジンは、最後に成功したクロール以降に作成または変更されたアイテムのみを処理してインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="d8918-180">With an **incremental crawl**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="d8918-181">そのため、コンテンツソース内のすべてのデータが再インデックス化されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="d8918-181">Therefore, not all the data in the content source is re-indexed.</span></span> <span data-ttu-id="d8918-182">増分クロールは、コンテンツ、メタデータ、アクセス許可、その他の更新プログラムを検出するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="d8918-182">Incremental crawls work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="d8918-183">増分クロールは、変更されていないアイテムは処理されないので、フルクロールよりもはるかに高速です。</span><span class="sxs-lookup"><span data-stu-id="d8918-183">Incremental crawls are much faster than full crawls because unchanged items aren’t processed.</span></span> <span data-ttu-id="d8918-184">コンテンツソースと検索インデックスとの間で正確なデータ同期を維持するには、両方のクロールを定期的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d8918-184">To maintain an accurate data sync between the content source and the search index, you need to run both crawls periodically.</span></span>

<span data-ttu-id="d8918-185">各コネクタには、データが変更される頻度と変更の種類に基づいて、更新スケジュールの最適なセットがあります。</span><span class="sxs-lookup"><span data-stu-id="d8918-185">Each connector will have a different optimal set of refresh schedules based on how often data is modified and the type of modifications.</span></span>

![増分クロールとフルクロール間隔の設定は、増分は15分で、フルクロールは1週間で表示されます。](media/refreshschedule.png)

### <a name="review-connector-settings"></a><span data-ttu-id="d8918-187">コネクタの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="d8918-187">Review connector settings</span></span>

<span data-ttu-id="d8918-188">コネクタを構成した後は、[管理センター](https://admin.microsoft.com)から設定を確認できるページに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8918-188">After you configure your connector, the [admin center](https://admin.microsoft.com) takes you to a page where you can review your settings.</span></span> <span data-ttu-id="d8918-189">接続を確認する前に、構成プロセスに戻って設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="d8918-189">You can go back through the configuration process to edit any setting before you confirm the connection.</span></span> <span data-ttu-id="d8918-190">詳細については、「[コネクタの管理](manage-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8918-190">To learn more, see [Manage your connector](manage-connector.md).</span></span>

## <a name="next-steps-customize-the-search-results-page"></a><span data-ttu-id="d8918-191">次の手順: 検索結果ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="d8918-191">Next steps: Customize the search results page</span></span>

<span data-ttu-id="d8918-192">Microsoft 検索ユーザーインターフェイス (UI) を使用すると、エンドユーザーは[microsoft 365](https://www.microsoft.com/microsoft-365)プロダクティビティアプリと microsoft の広範なエコシステムからコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d8918-192">With the Microsoft Search user interface (UI), your end users can search content from your [Microsoft 365](https://www.microsoft.com/microsoft-365) productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="d8918-193">縦方向検索は、ユーザーが[Bing](https://Bing.com)で[SharePoint](https://sharepoint.com/)、 [Microsoft Office](https://Office.com)、および microsoft search の検索結果を表示するときに表示されるタブを示します。</span><span class="sxs-lookup"><span data-stu-id="d8918-193">A search vertical refers to the tabs that are shown when a user views their search results in [SharePoint](https://sharepoint.com/), [Microsoft Office](https://Office.com), and Microsoft Search in [Bing](https://Bing.com).</span></span> <span data-ttu-id="d8918-194">検索結果を絞り込んで検索結果の特定の種類だけが表示されるように、検索対象をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="d8918-194">You can customize search verticals to narrow down results, so that only a certain type of search results is displayed.</span></span> <span data-ttu-id="d8918-195">これらの業種は、検索結果ページの上部にタブとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="d8918-195">These verticals appear as a tab on the top of the search results page.</span></span> <span data-ttu-id="d8918-196">モダン検索結果の種類 (MRT) は、結果の表示方法を指定する UI です。</span><span class="sxs-lookup"><span data-stu-id="d8918-196">A modern result type (MRT) is the UI that designates how results are presented.</span></span>

<span data-ttu-id="d8918-197">独自の業種と結果の種類を作成することで、エンドユーザーは新しい接続から検索結果を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="d8918-197">Create your own verticals and result types, so end users can view search results from new connections.</span></span> <span data-ttu-id="d8918-198">この手順を行わないと、接続からのデータが検索結果ページに表示されません。</span><span class="sxs-lookup"><span data-stu-id="d8918-198">Without this step, data from your connection won’t show up on the search results page.</span></span>

<span data-ttu-id="d8918-199">業種および MRTs の作成方法の詳細については、「[検索結果ページのカスタマイズ](customize-search-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8918-199">To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).</span></span>

## <a name="how-do-i-know-the-connection-setup-worked"></a><span data-ttu-id="d8918-200">接続セットアップが動作していることを確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="d8918-200">How do I know the connection setup worked?</span></span>

<span data-ttu-id="d8918-201">[管理センター](https://admin.microsoft.com)の [**コネクタ**] タブで、公開されている接続の一覧に移動します。</span><span class="sxs-lookup"><span data-stu-id="d8918-201">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="d8918-202">更新と削除を行う方法については、「[コネクタの管理](manage-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8918-202">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
