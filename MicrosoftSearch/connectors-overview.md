---
title: コネクタの概要
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft 検索用の Microsoft Graph のコネクタの概要
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367525"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="1a1be-103">Microsoft Graph コネクタの概要</span><span class="sxs-lookup"><span data-stu-id="1a1be-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="1a1be-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) では、ユーザーが検索できるように、 [microsoft 365](https://www.microsoft.com/microsoft-365) のすべてのデータのインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="1a1be-105">Microsoft Graph コネクタを使用すると、組織はサードパーティのデータにインデックスを作成して、Microsoft の検索結果に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="1a1be-106">これにより、Microsoft 365 プロダクティビティアプリと Microsoft の広範なエコシステムで検索可能なコンテンツソースの種類が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="1a1be-107">サードパーティのデータは、オンプレミスまたはパブリッククラウドまたはプライベートクラウドでホストできます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="1a1be-108">この記事の残りの部分では、Microsoft 365 管理者が、次の質問に回答するために avaiable されているリソースを見つけるのを支援します。</span><span class="sxs-lookup"><span data-stu-id="1a1be-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are avaiable to answer the following questions:</span></span>

* [<span data-ttu-id="1a1be-109">Microsoft Search に接続できるデータソース</span><span class="sxs-lookup"><span data-stu-id="1a1be-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="1a1be-110">接続を管理するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="1a1be-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="1a1be-111">グラフコネクタのライセンス要件と使用条件について</span><span class="sxs-lookup"><span data-stu-id="1a1be-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="1a1be-112">検索結果をカスタマイズして構成するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="1a1be-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="1a1be-113">カスタムアプリケーションからコネクタデータを検索するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="1a1be-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="1a1be-114">Microsoft Graph のコネクタと Microsoft 検索 Api は、一般公開されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="1a1be-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="1a1be-115">最初のロールアウトは、対象となるリリース用に構成された顧客に対して行われます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="1a1be-116">テナントで Graph connector を使用する場合は、ユーザーと管理者が [対象となるリリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)にオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a1be-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="1a1be-117">Microsoft Search に接続できるデータソース</span><span class="sxs-lookup"><span data-stu-id="1a1be-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="1a1be-118">Microsoft は10個のグラフコネクタを提供しており、エコシステムパートナーは100を超える追加の Graph コネクタを作成しています。</span><span class="sxs-lookup"><span data-stu-id="1a1be-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="1a1be-119">独自の Graph connector を構築することもできます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="1a1be-120">Microsoft によるグラフコネクタ</span><span class="sxs-lookup"><span data-stu-id="1a1be-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="1a1be-121">Microsoft によって作成された Graph コネクタを使用して、次のデータソースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="1a1be-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="1a1be-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="1a1be-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="1a1be-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="1a1be-124">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="1a1be-124">Azure SQL</span></span>
* [<span data-ttu-id="1a1be-125">大企業の Web サイト</span><span class="sxs-lookup"><span data-stu-id="1a1be-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="1a1be-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="1a1be-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="1a1be-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a1be-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="1a1be-128">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="1a1be-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="1a1be-129">Oracle (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1a1be-129">Oracle (preview)</span></span>
* [<span data-ttu-id="1a1be-130">Salesforce (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="1a1be-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="1a1be-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="1a1be-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="1a1be-132">[グラフコネクタギャラリー](connectors-gallery.md)には、これらのグラフコネクタの簡単な説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a1be-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="1a1be-133">これらのデータソースのいずれかをテナントに接続する準備が整っている場合は、「セットアップの [概要](configure-connector.md) 」および「Microsoft が設定したコネクタ」セクションにある、データソースに適用されるその他の記事を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="1a1be-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="1a1be-134">パートナーによるグラフコネクタ</span><span class="sxs-lookup"><span data-stu-id="1a1be-134">Graph connectors by our partners</span></span>

<span data-ttu-id="1a1be-135">[Microsoft graph のコネクタギャラリー](connectors-gallery.md)には、パートナーによって作成された各グラフコネクタの簡単な説明と、各パートナーの web サイトへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a1be-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="1a1be-136">詳細については、各パートナーに直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="1a1be-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="1a1be-137">独自の Graph connector を構築する</span><span class="sxs-lookup"><span data-stu-id="1a1be-137">Build your own Graph connector</span></span>

<span data-ttu-id="1a1be-138">独自の Graph connector の構築を計画している場合は、詳細について「 [Microsoft graph の Microsoft SEARCH API の概要](https://docs.microsoft.com/graph/search-concept-overview) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a1be-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="1a1be-139">接続を管理するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="1a1be-139">How do I manage my connections?</span></span>

<span data-ttu-id="1a1be-140">[Microsoft 365 管理センター](https://admin.microsoft.com/)の [[コネクタ] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)から、接続を管理できます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="1a1be-141">詳細については [、「接続を管理](manage-connector.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a1be-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="1a1be-142">グラフコネクタのライセンス要件と使用条件について</span><span class="sxs-lookup"><span data-stu-id="1a1be-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="1a1be-143">検索結果のコネクタのデータを表示するには、組織内のユーザーに対して有効な Microsoft 365 または Office 365 のライセンスと十分なグラフコネクタクォータが必要です。</span><span class="sxs-lookup"><span data-stu-id="1a1be-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="1a1be-144">詳細については、「[ライセンス要件と](licensing.md)[使用条件](terms-of-use.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a1be-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="1a1be-145">検索結果をカスタマイズして構成するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="1a1be-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="1a1be-146">検索結果をカスタマイズして構成するには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="1a1be-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="1a1be-147">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a1be-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="1a1be-148">業界および結果の種類を管理する</span><span class="sxs-lookup"><span data-stu-id="1a1be-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="1a1be-149">検索結果のレイアウトを管理する</span><span class="sxs-lookup"><span data-stu-id="1a1be-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="1a1be-150">検索結果クラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="1a1be-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="1a1be-151">カスタムフィルターを管理する</span><span class="sxs-lookup"><span data-stu-id="1a1be-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="1a1be-152">カスタムアプリケーションからコネクタデータを検索するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="1a1be-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="1a1be-153">カスタムデータのインデックスを作成すると、開発者は [このデータをクエリ](https://docs.microsoft.com/graph/search-concept-custom-types)できます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="1a1be-154">任意のアプリケーションでデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="1a1be-154">You can view your data in any application.</span></span> <span data-ttu-id="1a1be-155">詳細については、microsoft [Graph の Microsoft SEARCH API の概要](https://docs.microsoft.com/graph/search-concept-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1a1be-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>
