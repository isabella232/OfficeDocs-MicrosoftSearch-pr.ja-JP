---
title: Microsoft Graph コネクタの概要
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
description: Microsoft Graph コネクタのMicrosoft Search
ms.openlocfilehash: 87645e32e274eb166d6ba008c4ac720667105a1f
ms.sourcegitcommit: 52129e0129a201ec056903b2461d012fda6d3636
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383485"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="41c9a-103">Microsoft Graph コネクタの概要</span><span class="sxs-lookup"><span data-stu-id="41c9a-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="41c9a-104">[Microsoft Search](./overview-microsoft-search.md)ユーザーを検索[Microsoft 365、すべての](https://www.microsoft.com/microsoft-365)データにインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="41c9a-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="41c9a-105">Microsoft Graphコネクタを使用すると、組織はサードパーティのデータをインデックス化して、結果に表示Microsoft Searchできます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="41c9a-106">この機能は、Microsoft 365 の生産性向上アプリと Microsoft の広範なエコシステムで検索可能な、コンテンツ ソースの種類を拡大しています。</span><span class="sxs-lookup"><span data-stu-id="41c9a-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="41c9a-107">サード パーティのデータは、オンプレミスまたはパブリック クラウドまたはプライベート クラウドでホストできます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="41c9a-108">この記事は、管理者がMicrosoft 365に回答できるリソースを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="41c9a-109">どのデータ ソースをデータ ソースに接続Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="41c9a-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="41c9a-110">接続を管理する方法</span><span class="sxs-lookup"><span data-stu-id="41c9a-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="41c9a-111">Microsoft Graphコネクタのライセンス要件と使用条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="41c9a-111">What are the license requirements and terms of use for Microsoft Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [<span data-ttu-id="41c9a-112">プレビュー機能とは</span><span class="sxs-lookup"><span data-stu-id="41c9a-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="41c9a-113">検索結果をカスタマイズおよび構成する方法</span><span class="sxs-lookup"><span data-stu-id="41c9a-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="41c9a-114">カスタム アプリケーションからコネクタ データを検索する方法</span><span class="sxs-lookup"><span data-stu-id="41c9a-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="41c9a-115">検索結果をカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="41c9a-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="41c9a-116">コネクタの制限事項</span><span class="sxs-lookup"><span data-stu-id="41c9a-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="41c9a-117">どのデータ ソースをデータ ソースに接続Microsoft Search?</span><span class="sxs-lookup"><span data-stu-id="41c9a-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="41c9a-118">Microsoft は 9 つのコネクタを提供し、エコシステム パートナーは 100 を超えるコネクタを作成しました。</span><span class="sxs-lookup"><span data-stu-id="41c9a-118">Microsoft provides 9 connectors and our ecosystem partners have created over 100 more connectors.</span></span> <span data-ttu-id="41c9a-119">独自のコネクタを作成できます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-119">You can also build your own connector.</span></span>

### <a name="microsoft-graph-connectors-by-microsoft"></a><span data-ttu-id="41c9a-120">Microsoft Graphコネクタ</span><span class="sxs-lookup"><span data-stu-id="41c9a-120">Microsoft Graph connectors by Microsoft</span></span>

<span data-ttu-id="41c9a-121">Microsoft によって作成されたコネクタを使用して、次のデータ ソースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-121">You can connect to the following data sources using connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="41c9a-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="41c9a-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="41c9a-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="41c9a-123">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="41c9a-124">Azure SQL および Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="41c9a-124">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="41c9a-125">大企業の Web サイト</span><span class="sxs-lookup"><span data-stu-id="41c9a-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="41c9a-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="41c9a-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="41c9a-127">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="41c9a-127">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="41c9a-128">Oracle SQL</span><span class="sxs-lookup"><span data-stu-id="41c9a-128">Oracle SQL</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="41c9a-129">Salesforce (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="41c9a-129">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="41c9a-130">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="41c9a-130">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="41c9a-131">[Microsoft Graph コネクタ ギャラリーには](https://www.microsoft.com/microsoft-search/connectors)、これらの各コネクタの簡単な説明が含まれている。</span><span class="sxs-lookup"><span data-stu-id="41c9a-131">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) contains a brief description of each of these connectors.</span></span> <span data-ttu-id="41c9a-132">これらのデータ ソースの 1 つをテナントに接続する準備が整っている場合は、[](configure-connector.md)データ ソースに適用される [Microsoft によるセットアップ コネクタ] セクションのセットアップの概要と他の記事を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="41c9a-132">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="microsoft-graph-connectors-by-our-partners"></a><span data-ttu-id="41c9a-133">Microsoft Graphパートナーによるコネクタ</span><span class="sxs-lookup"><span data-stu-id="41c9a-133">Microsoft Graph connectors by our partners</span></span>

<span data-ttu-id="41c9a-134">[Microsoft Graph コネクタ](https://www.microsoft.com/microsoft-search/connectors)ギャラリーには、パートナーによって作成された各コネクタの簡単な説明と、各パートナーの Web サイトへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="41c9a-134">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) includes a brief description of each of the connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="41c9a-135">詳細については、各パートナーに直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="41c9a-135">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-microsoft-graph-connector"></a><span data-ttu-id="41c9a-136">独自の Microsoft Graph コネクタを構築する</span><span class="sxs-lookup"><span data-stu-id="41c9a-136">Build your own Microsoft Graph connector</span></span>

<span data-ttu-id="41c9a-137">必要に応じて、独自のコネクタを構築できます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-137">You can build your own connector if you prefer.</span></span> <span data-ttu-id="41c9a-138">コネクタの構築の詳細については、「Build [your first custom Microsoft Graph コネクタ」を参照してください](/graph/connecting-external-content-build-quickstart)。</span><span class="sxs-lookup"><span data-stu-id="41c9a-138">For more information on building connectors, see  [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="41c9a-139">接続を管理する方法</span><span class="sxs-lookup"><span data-stu-id="41c9a-139">How do I manage my connections?</span></span>

<span data-ttu-id="41c9a-140">接続は、[コネクタ] タブ[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)の [コネクタ] タブから[管理Microsoft 365 管理センター。](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="41c9a-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="41c9a-141">接続の管理の詳細については、「接続の管理 [」を参照してください](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="41c9a-141">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a><span data-ttu-id="41c9a-142">コネクタのライセンス要件と使用条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="41c9a-142">What are the license requirements and terms of use for connectors?</span></span>

<span data-ttu-id="41c9a-143">組織内のユーザーがMicrosoft 365データOffice 365を表示するには、有効なライセンスまたはライセンスと十分なコネクタ クォータが必要です。</span><span class="sxs-lookup"><span data-stu-id="41c9a-143">You need a valid Microsoft 365 or Office 365 license and sufficient connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="41c9a-144">詳細については、「ライセンス要件 [と価格設定」および](licensing.md) 「 [使用条件」を参照してください](terms-of-use.md)。</span><span class="sxs-lookup"><span data-stu-id="41c9a-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="41c9a-145">プレビュー機能とは</span><span class="sxs-lookup"><span data-stu-id="41c9a-145">What are the preview features?</span></span>

<span data-ttu-id="41c9a-146">Microsoft Graphおよび Microsoft Search API は一般に使用できるが、プレビュー中のいくつかの機能があります。</span><span class="sxs-lookup"><span data-stu-id="41c9a-146">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="41c9a-147">プレビューのコネクタと機能のセットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="41c9a-147">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="41c9a-148">Azure DevOps コネクタ</span><span class="sxs-lookup"><span data-stu-id="41c9a-148">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="41c9a-149">Salesforce コネクタ</span><span class="sxs-lookup"><span data-stu-id="41c9a-149">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="41c9a-150">[ソース ACL を使用](servicenow-connector.md) する検索アクセス許可を持つ ServiceNow コネクタ</span><span class="sxs-lookup"><span data-stu-id="41c9a-150">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="41c9a-151">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="41c9a-151">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="41c9a-152">垂直の複数の接続</span><span class="sxs-lookup"><span data-stu-id="41c9a-152">Multiple connections in a vertical</span></span>](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="41c9a-153">検索結果をカスタマイズおよび構成する方法</span><span class="sxs-lookup"><span data-stu-id="41c9a-153">How do I customize and configure search results?</span></span>

<span data-ttu-id="41c9a-154">検索結果をカスタマイズおよび構成するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="41c9a-154">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="41c9a-155">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41c9a-155">See the following articles to learn more:</span></span>

* [<span data-ttu-id="41c9a-156">業界および結果の種類を管理する</span><span class="sxs-lookup"><span data-stu-id="41c9a-156">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="41c9a-157">検索結果のレイアウトを管理する</span><span class="sxs-lookup"><span data-stu-id="41c9a-157">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="41c9a-158">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="41c9a-158">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="41c9a-159">カスタム フィルターを管理する</span><span class="sxs-lookup"><span data-stu-id="41c9a-159">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="41c9a-160">カスタム アプリケーションからコネクタ データを検索する方法</span><span class="sxs-lookup"><span data-stu-id="41c9a-160">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="41c9a-161">カスタム データのインデックスが作成された後、開発者は、この [データを照会できます](/graph/search-concept-custom-types)。</span><span class="sxs-lookup"><span data-stu-id="41c9a-161">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="41c9a-162">任意のアプリケーションでデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-162">You can view your data in any application.</span></span> <span data-ttu-id="41c9a-163">詳細については、「Microsoft Microsoft Search API の概要[」を参照Graph。](/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="41c9a-163">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="41c9a-164">検索結果をカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="41c9a-164">How do I customize search results?</span></span>

<span data-ttu-id="41c9a-165">次の手順は、この記事で推奨される検索結果をカスタマイズする方法をカスタマイズし、検索結果[を構成する方法です。](#how-do-i-customize-and-configure-search-results)</span><span class="sxs-lookup"><span data-stu-id="41c9a-165">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="41c9a-166">検索結果のカスタマイズの詳細については、「[検索結果のカスタマイズ] ページ [」を参照してください](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="41c9a-166">To learn more about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="41c9a-167">コネクタの制限事項は何ですか?</span><span class="sxs-lookup"><span data-stu-id="41c9a-167">What are the connector limitations?</span></span>

* <span data-ttu-id="41c9a-168">Microsoft で **構築された** コネクタを発行すると、接続が作成されるのに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="41c9a-168">When you **publish** a Microsoft-built connector, it can take a few minutes for the connection to be created.</span></span> <span data-ttu-id="41c9a-169">その間、接続の状態は保留中として表示されます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-169">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="41c9a-170">取り込みスループットは、1 秒あたり約 4 つのアイテムで調整されます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-170">Ingestion throughput is throttled at approximately four items per second.</span></span>

* <span data-ttu-id="41c9a-171">スキーマの更新はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="41c9a-171">There is no support for schema updates.</span></span> <span data-ttu-id="41c9a-172">接続セットアップを作成した後、スキーマを更新する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="41c9a-172">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="41c9a-173">接続の削除と再作成のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="41c9a-173">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="41c9a-174">接続の制限があります。</span><span class="sxs-lookup"><span data-stu-id="41c9a-174">There is a connection limit.</span></span> <span data-ttu-id="41c9a-175">各テナントは、最大 10 の接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="41c9a-175">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="41c9a-176">接続を作成した後で、接続を編集または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="41c9a-176">You cannot edit or change a connection after it has been created.</span></span> <span data-ttu-id="41c9a-177">詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41c9a-177">If you need to change any details, you must delete and recreate the connection.</span></span>
