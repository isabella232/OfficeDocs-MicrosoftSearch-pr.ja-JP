---
title: Microsoft が開発したコネクタを Microsoft Search 用に構成する
ms.author: monaray
author: monaray97
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
ms.openlocfilehash: ce2515b3eaa859a8fbb00d83c4727865ab55e174
ms.sourcegitcommit: 6aea7102c94855e9f80711c0f3d7bf5833ce8fb5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464478"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="set-up-your-microsoft-built-connector-for-microsoft-search"></a><span data-ttu-id="12184-103">Microsoft が開発したコネクタを Microsoft Search 用にセットアップする</span><span class="sxs-lookup"><span data-stu-id="12184-103">Set up your Microsoft-built connector for Microsoft Search</span></span>

<span data-ttu-id="12184-104">この記事では、Microsoft によって作成されたコネクタを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="12184-104">This article guides you through the steps of configuring a Microsoft-built connector.</span></span> <span data-ttu-id="12184-105">この記事では、Microsoft 365 [管理センター](https://admin.microsoft.com)での接続のセットアップフローについて説明します。</span><span class="sxs-lookup"><span data-stu-id="12184-105">It outlines the flow of setting up a connection in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="12184-106">特定の Microsoft が作成したコネクタをセットアップする方法の詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12184-106">For more information on how to set up specific Microsoft-built connectors, see these articles:</span></span>

* [<span data-ttu-id="12184-107">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="12184-107">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="12184-108">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="12184-108">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="12184-109">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="12184-109">Azure SQL</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="12184-110">大企業の Web サイト</span><span class="sxs-lookup"><span data-stu-id="12184-110">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="12184-111">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="12184-111">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="12184-112">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="12184-112">Microsoft SQL server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="12184-113">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="12184-113">ServiceNow</span></span>](servicenow-connector.md)

## <a name="set-up"></a><span data-ttu-id="12184-114">セットアップ</span><span class="sxs-lookup"><span data-stu-id="12184-114">Set up</span></span>

<span data-ttu-id="12184-115">Microsoft によって作成されたコネクタのいずれかを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="12184-115">Complete the following steps to configure any of the Microsoft-built connectors.</span></span>

1. <span data-ttu-id="12184-116">[Microsoft 365 管理センター](https://admin.microsoft.com)の [[コネクタ] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)に移動します。</span><span class="sxs-lookup"><span data-stu-id="12184-116">Go to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="12184-117">[Microsoft 365](https://www.microsoft.com/microsoft-365)テナントの資格情報を使用して、アカウントにサインインします。</span><span class="sxs-lookup"><span data-stu-id="12184-117">Sign in to your account with the credentials for your [Microsoft 365](https://www.microsoft.com/microsoft-365) tenant.</span></span>
3. <span data-ttu-id="12184-118">[ **コネクタの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12184-118">Select **Add a connector**.</span></span>
4. <span data-ttu-id="12184-119">使用可能なコネクタのリストから、選択したコネクタを選択します。</span><span class="sxs-lookup"><span data-stu-id="12184-119">From the list of available connectors, select the connector of your choice.</span></span>

![利用可能なデータソースは次のとおりです。 Azure DevOps Connector、ServiceNow、ADLS Gen2、エンタープライズ web サイト、MediaWiki、Microsoft SQL server、および Azure SQL。](media/add_connector.png)

### <a name="name-the-connector"></a><span data-ttu-id="12184-121">コネクタに名前を指定する</span><span class="sxs-lookup"><span data-stu-id="12184-121">Name the connector</span></span>

<span data-ttu-id="12184-122">接続を作成するには、最初に次の属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="12184-122">To create a connection, first specify these attributes:</span></span>

1. <span data-ttu-id="12184-123">接続の名前</span><span class="sxs-lookup"><span data-stu-id="12184-123">Name of the connection</span></span>
2. <span data-ttu-id="12184-124">接続 ID</span><span class="sxs-lookup"><span data-stu-id="12184-124">Connection ID</span></span>
3. <span data-ttu-id="12184-125">説明 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="12184-125">Description (optional)</span></span>

<span data-ttu-id="12184-126">接続 ID は、コネクタの暗黙的なプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="12184-126">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="12184-127">このファイルには、英数字のみが含まれ、最大32文字の文字が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="12184-127">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span>

### <a name="connect-to-a-data-source"></a><span data-ttu-id="12184-128">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="12184-128">Connect to a data source</span></span>

<span data-ttu-id="12184-129">データ接続プロセスは、コネクタの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="12184-129">The data connection process varies based on the type of connector.</span></span> <span data-ttu-id="12184-130">オンプレミスのデータソースへの接続の詳細については、「 [オンプレミスのデータゲートウェイをインストール](https://aka.ms/configuregateway)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12184-130">To learn more about connecting to your on-premises data source, see [Install an on-premises data gateway](https://aka.ms/configuregateway).</span></span>

### <a name="select-source-properties"></a><span data-ttu-id="12184-131">ソースのプロパティの選択</span><span class="sxs-lookup"><span data-stu-id="12184-131">Select source properties</span></span>

<span data-ttu-id="12184-132">サードパーティのデータソースによって設定されたデータフィールドは、ソースプロパティとして Microsoft Search にインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="12184-132">The data fields set by your third-party data source as source properties are indexed into Microsoft Search.</span></span> <span data-ttu-id="12184-133">これらのプロパティを変更するには、[**コネクタ**] ページの右側にあるサイドバーで [**プロパティの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12184-133">To modify these properties, select **Edit properties** in the side bar on the right of the **Connectors** page.</span></span> <span data-ttu-id="12184-134">**最大64のソースプロパティ**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="12184-134">You can select **up to 64 source properties**.</span></span>

### <a name="manage-the-search-schema"></a><span data-ttu-id="12184-135">検索スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="12184-135">Manage the search schema</span></span>

#### <a name="content-property"></a><span data-ttu-id="12184-136">Content プロパティ</span><span class="sxs-lookup"><span data-stu-id="12184-136">Content property</span></span>

<span data-ttu-id="12184-137">**コンテンツ**プロパティのドロップダウンから任意の文字列プロパティを選択することによって、どの source プロパティが**content**プロパティ (アイテムのフルテキストインデックス) であるかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="12184-137">You can select which source property is the **content** property (full-text index of the item) by selecting any string property from the **content** property dropdown.</span></span> <span data-ttu-id="12184-138">または、既定の選択されたプロパティがある場合は、そのプロパティをそのまま使用できます。</span><span class="sxs-lookup"><span data-stu-id="12184-138">Alternatively, you can keep the default selected property if one is present.</span></span>

<span data-ttu-id="12184-139">このプロパティは、コンテンツのフルテキストインデックス作成、検索結果ページスニペットの生成、言語検出、HTML/テキストのサポート、ランク付けと関連性、およびクエリ formulation に使用されているため、適切なプロパティが選択されていることが特に重要です。</span><span class="sxs-lookup"><span data-stu-id="12184-139">It is especially important that the correct property is selected since this property used for full-text indexing of content, search results page snippet generation, language detection, HTML/text support, ranking and relevance, and query formulation.</span></span>

<span data-ttu-id="12184-140">**コンテンツ**のプロパティを選択すると、[検索結果の種類を作成](customize-results-layout.md)するときに、システムで生成されたプロパティの**resultsnippet**を使用するオプションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12184-140">If you select a property for **content**, you will have the option of using the system-generated property **ResultSnippet** when you [create your result type](customize-results-layout.md).</span></span> <span data-ttu-id="12184-141">このプロパティは、クエリ時に **content** プロパティから生成される動的スニペットのプレースホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="12184-141">This property serves as a placeholder for the dynamic snippets that are generated from the **content** property at query time.</span></span> <span data-ttu-id="12184-142">結果の種類でこのプロパティを使用すると、検索結果にスニペットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="12184-142">If you use this property in your result type, snippets will be generated in your search results.</span></span>

#### <a name="search-schema-attributes"></a><span data-ttu-id="12184-143">検索スキーマの属性</span><span class="sxs-lookup"><span data-stu-id="12184-143">Search schema attributes</span></span>

<span data-ttu-id="12184-144">検索スキーマの属性を設定して、各 source プロパティの検索機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="12184-144">You can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="12184-145">検索スキーマは、検索結果ページに表示される結果と、エンドユーザーが表示およびアクセスできる情報を決定するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="12184-145">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="12184-146">検索スキーマの属性には、検索可能、**クエリ**可能 **、および取得**可能**なものが**あります。</span><span class="sxs-lookup"><span data-stu-id="12184-146">Search schema attributes include **searchable**, **queryable**, and **retrievable**.</span></span> <span data-ttu-id="12184-147">次の表に、Microsoft Graph コネクタがサポートしている各属性とその機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="12184-147">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="12184-148">検索スキーマの属性</span><span class="sxs-lookup"><span data-stu-id="12184-148">Search schema attribute</span></span> | <span data-ttu-id="12184-149">関数</span><span class="sxs-lookup"><span data-stu-id="12184-149">Function</span></span> | <span data-ttu-id="12184-150">例</span><span class="sxs-lookup"><span data-stu-id="12184-150">Example</span></span>
--- | --- | ---
<span data-ttu-id="12184-151">サーチ</span><span class="sxs-lookup"><span data-stu-id="12184-151">SEARCHABLE</span></span> | <span data-ttu-id="12184-152">プロパティのテキストコンテンツを検索可能にします。</span><span class="sxs-lookup"><span data-stu-id="12184-152">Makes the text content of a property searchable.</span></span> <span data-ttu-id="12184-153">プロパティの内容は、フルテキストインデックスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="12184-153">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="12184-154">プロパティが **title**の場合、 **エンタープライズ** のクエリは、テキストまたはタイトルに " **enterprise** " が含まれている回答を返します。</span><span class="sxs-lookup"><span data-stu-id="12184-154">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="12184-155">クエリ可能</span><span class="sxs-lookup"><span data-stu-id="12184-155">QUERYABLE</span></span> | <span data-ttu-id="12184-156">クエリによって特定のプロパティの一致が検索されます。</span><span class="sxs-lookup"><span data-stu-id="12184-156">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="12184-157">プロパティ名は、プログラムまたは逐語的にクエリで指定できます。</span><span class="sxs-lookup"><span data-stu-id="12184-157">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="12184-158">**Title**プロパティがクエリ可能な場合は、クエリ**タイトル: Enterprise**がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="12184-158">If the **Title** property is queryable, then the query **Title: Enterprise** is supported.</span></span>
<span data-ttu-id="12184-159">だっ</span><span class="sxs-lookup"><span data-stu-id="12184-159">RETRIEVABLE</span></span> | <span data-ttu-id="12184-160">検索結果の種類には取得可能なプロパティのみを使用し、検索結果に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="12184-160">Only retrievable properties can be used in the result type and display in the search result.</span></span> |

<span data-ttu-id="12184-161">すべてのコネクタについて、カスタムの種類を手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12184-161">For all connectors, custom types must be set manually.</span></span> <span data-ttu-id="12184-162">各フィールドの検索機能をアクティブにするには、プロパティのリストにマップされた検索スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="12184-162">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="12184-163">接続ウィザードは、選択したソースプロパティのセットに基づいて検索スキーマを自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="12184-163">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="12184-164">このスキーマを変更するには、[検索スキーマ] ページで各プロパティと属性のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="12184-164">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

![コネクタのスキーマは、クエリ、検索、および取得機能を追加または削除することでカスタマイズできます。](media/manageschema.png)

#### <a name="restrictions-and-recommendations-for-search-schema-settings"></a><span data-ttu-id="12184-166">検索スキーマ設定の制限事項と推奨事項</span><span class="sxs-lookup"><span data-stu-id="12184-166">Restrictions and recommendations for search schema settings</span></span>

* <span data-ttu-id="12184-167">**コンテンツ**プロパティは検索可能でのみあります。</span><span class="sxs-lookup"><span data-stu-id="12184-167">The **content** property is searchable only.</span></span> <span data-ttu-id="12184-168">ドロップダウンで選択すると、このプロパティを取得または**クエリ\*\*\*\*可能とし**てマークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="12184-168">Once selected in the dropdown, this property cannot be marked **retrievable** or **queryable**.</span></span> <span data-ttu-id="12184-169">**コンテンツ**プロパティを使用して検索結果が表示される場合、パフォーマンスの著しい問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="12184-169">Significant performance issues occur when search results render with the **content** property.</span></span> <span data-ttu-id="12184-170">この例は、 [ServiceNow](https://www.servicenow.com)ナレッジベースの記事の**テキスト**コンテンツフィールドです。</span><span class="sxs-lookup"><span data-stu-id="12184-170">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>

* <span data-ttu-id="12184-171">検索結果には、取得可能としてマークされたプロパティのみが表示され、モダンの検索結果の種類 (MRTs) を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="12184-171">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>

* <span data-ttu-id="12184-172">検索可能としてマークできるのは、文字列のプロパティだけです。</span><span class="sxs-lookup"><span data-stu-id="12184-172">Only string properties can be marked searchable.</span></span>


> [!Note]
> <span data-ttu-id="12184-173">接続を作成した後、スキーマを変更する **ことはできません** 。</span><span class="sxs-lookup"><span data-stu-id="12184-173">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="12184-174">そのためには、接続を削除して、新しい接続を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12184-174">To do that, you need to delete your connection and create a new one.</span></span>

### <a name="manage-search-permissions"></a><span data-ttu-id="12184-175">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="12184-175">Manage search permissions</span></span>

<span data-ttu-id="12184-176">アクセス制御リスト (Acl) は、組織内のどのユーザーがデータの各アイテムにアクセスできるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="12184-176">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span> <span data-ttu-id="12184-177">すべてのコネクタは、すべてのユーザーに表示される検索アクセス許可をサポートします。</span><span class="sxs-lookup"><span data-stu-id="12184-177">All the connectors support search permissions that are visible to all users.</span></span>

### <a name="set-the-refresh-schedule"></a><span data-ttu-id="12184-178">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="12184-178">Set the refresh schedule</span></span>

<span data-ttu-id="12184-179">更新スケジュールは、Microsoft Graph と Microsoft Search のインデックスとデータを同期する頻度を決定します。</span><span class="sxs-lookup"><span data-stu-id="12184-179">The refresh schedule determines how often your data is synced with the index in Microsoft Graph and Microsoft Search.</span></span> <span data-ttu-id="12184-180">フルクロールまたは増分クロールの2つの方法で更新をスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="12184-180">You can schedule the refresh in two ways: full crawl or incremental crawl.</span></span>

<span data-ttu-id="12184-181">**フルクロール**では、検索エンジンは、以前のクロールに関係なく、コンテンツソース内のすべてのアイテムを処理してインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="12184-181">With a **full crawl**, the search engine processes and indexes every item in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="12184-182">フルクロールは、次のような場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="12184-182">Full crawl works best in these situations:</span></span>

* <span data-ttu-id="12184-183">データの削除を検出します。</span><span class="sxs-lookup"><span data-stu-id="12184-183">Detecting deletions of data.</span></span>
* <span data-ttu-id="12184-184">増分クロールで、エラーのためにコンテンツをクロールできませんでした。</span><span class="sxs-lookup"><span data-stu-id="12184-184">The incremental crawl failed to crawl content for errors.</span></span>
* <span data-ttu-id="12184-185">Acl が変更されました。</span><span class="sxs-lookup"><span data-stu-id="12184-185">ACLs were modified.</span></span>
* <span data-ttu-id="12184-186">クロールルールが変更されました。</span><span class="sxs-lookup"><span data-stu-id="12184-186">Crawl rules were modified.</span></span>
* <span data-ttu-id="12184-187">Microsoft Search のソフトウェア更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="12184-187">A software update for Microsoft Search is required.</span></span> <span data-ttu-id="12184-188">更新プログラムによって検索スキーマが変更されます。</span><span class="sxs-lookup"><span data-stu-id="12184-188">Updates modify the search schema.</span></span>

<span data-ttu-id="12184-189">**増分クロール**では、検索エンジンは、最後に成功したクロール以降に作成または変更されたアイテムのみを処理してインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="12184-189">With an **incremental crawl**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="12184-190">そのため、コンテンツソース内のすべてのデータが再インデックス化されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="12184-190">Therefore, not all the data in the content source is re-indexed.</span></span> <span data-ttu-id="12184-191">増分クロールは、コンテンツ、メタデータ、アクセス許可、その他の更新プログラムを検出するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="12184-191">Incremental crawls work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="12184-192">増分クロールは、変更されていないアイテムは処理されないので、フルクロールよりもはるかに高速です。</span><span class="sxs-lookup"><span data-stu-id="12184-192">Incremental crawls are much faster than full crawls because unchanged items aren’t processed.</span></span> <span data-ttu-id="12184-193">コンテンツソースと検索インデックスとの間で正確なデータ同期を維持するには、両方のクロールを定期的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12184-193">To maintain an accurate data sync between the content source and the search index, you need to run both crawls periodically.</span></span>

<span data-ttu-id="12184-194">各コネクタには、データが変更される頻度と変更の種類に基づいて、更新スケジュールの最適なセットがあります。</span><span class="sxs-lookup"><span data-stu-id="12184-194">Each connector will have a different optimal set of refresh schedules based on how often data is modified and the type of modifications.</span></span>

![増分クロールとフルクロール間隔の設定は、増分は15分で、フルクロールは1週間で表示されます。](media/refreshschedule.png)

### <a name="review-connector-settings"></a><span data-ttu-id="12184-196">コネクタの設定を確認する</span><span class="sxs-lookup"><span data-stu-id="12184-196">Review connector settings</span></span>

<span data-ttu-id="12184-197">コネクタを構成した後は、 [管理センター](https://admin.microsoft.com) から設定を確認できるページに移動します。</span><span class="sxs-lookup"><span data-stu-id="12184-197">After you configure your connector, the [admin center](https://admin.microsoft.com) takes you to a page where you can review your settings.</span></span> <span data-ttu-id="12184-198">接続を確認する前に、構成プロセスに戻って設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="12184-198">You can go back through the configuration process to edit any setting before you confirm the connection.</span></span> <span data-ttu-id="12184-199">詳細については、「 [コネクタの管理](manage-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12184-199">To learn more, see [Manage your connector](manage-connector.md).</span></span>

## <a name="next-steps-customize-the-search-results-page"></a><span data-ttu-id="12184-200">次の手順: 検索結果ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="12184-200">Next steps: Customize the search results page</span></span>

<span data-ttu-id="12184-201">Microsoft 検索ユーザーインターフェイス (UI) を使用すると、エンドユーザーは [microsoft 365](https://www.microsoft.com/microsoft-365) プロダクティビティアプリと microsoft の広範なエコシステムからコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="12184-201">With the Microsoft Search user interface (UI), your end users can search content from your [Microsoft 365](https://www.microsoft.com/microsoft-365) productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="12184-202">縦方向検索は、ユーザーが[Bing](https://Bing.com)で[SharePoint](https://sharepoint.com/)、 [Microsoft Office](https://Office.com)、および microsoft search の検索結果を表示するときに表示されるタブを示します。</span><span class="sxs-lookup"><span data-stu-id="12184-202">A search vertical refers to the tabs that are shown when a user views their search results in [SharePoint](https://sharepoint.com/), [Microsoft Office](https://Office.com), and Microsoft Search in [Bing](https://Bing.com).</span></span> <span data-ttu-id="12184-203">検索結果を絞り込んで検索結果の特定の種類だけが表示されるように、検索対象をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="12184-203">You can customize search verticals to narrow down results, so that only a certain type of search results is displayed.</span></span> <span data-ttu-id="12184-204">これらの業種は、検索結果ページの上部にタブとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="12184-204">These verticals appear as a tab on the top of the search results page.</span></span> <span data-ttu-id="12184-205">モダン検索結果の種類 (MRT) は、結果の表示方法を指定する UI です。</span><span class="sxs-lookup"><span data-stu-id="12184-205">A modern result type (MRT) is the UI that designates how results are presented.</span></span>

<span data-ttu-id="12184-206">独自の業種と結果の種類を作成することで、エンドユーザーは新しい接続から検索結果を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="12184-206">Create your own verticals and result types, so end users can view search results from new connections.</span></span> <span data-ttu-id="12184-207">この手順を行わないと、接続からのデータが検索結果ページに表示されません。</span><span class="sxs-lookup"><span data-stu-id="12184-207">Without this step, data from your connection won’t show up on the search results page.</span></span>

<span data-ttu-id="12184-208">業種および MRTs の作成方法の詳細については、「 [検索結果ページのカスタマイズ](customize-search-page.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12184-208">To learn more about how to create your verticals and MRTs, see [Search results page customization](customize-search-page.md).</span></span>

## <a name="how-do-i-know-the-connection-setup-worked"></a><span data-ttu-id="12184-209">接続セットアップが動作していることを確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="12184-209">How do I know the connection setup worked?</span></span>

<span data-ttu-id="12184-210">[管理センター](https://admin.microsoft.com)の [**コネクタ**] タブで、公開されている接続の一覧に移動します。</span><span class="sxs-lookup"><span data-stu-id="12184-210">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="12184-211">更新と削除を行う方法については、「 [コネクタの管理](manage-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12184-211">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
