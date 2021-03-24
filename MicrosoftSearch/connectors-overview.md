---
title: Microsoft Graph Connectors の概要
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
description: Microsoft Search 用 Microsoft Graph コネクタの概要
ms.openlocfilehash: 77f145f58cf06e49f88af25bcb4d28cfa7d2bd56
ms.sourcegitcommit: 08a7086185d28df14b06d1f7fdfbb1637288f7a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51042576"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="576ce-103">Microsoft Graph コネクタの概要</span><span class="sxs-lookup"><span data-stu-id="576ce-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="576ce-104">[Microsoft Search は](./overview-microsoft-search.md) 、 [すべての Microsoft 365](https://www.microsoft.com/microsoft-365) データにインデックスを作成して、ユーザーを検索可能にしています。</span><span class="sxs-lookup"><span data-stu-id="576ce-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="576ce-105">Microsoft Graph コネクタを使用すると、組織はサード パーティのデータにインデックスを付け、Microsoft 検索結果に表示できます。</span><span class="sxs-lookup"><span data-stu-id="576ce-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="576ce-106">この機能は、Microsoft 365 生産性向上アプリと広範な Microsoft エコシステムで検索可能なコンテンツ ソースの種類を拡張します。</span><span class="sxs-lookup"><span data-stu-id="576ce-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="576ce-107">サード パーティのデータは、オンプレミスまたはパブリック クラウドまたはプライベート クラウドでホストできます。</span><span class="sxs-lookup"><span data-stu-id="576ce-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="576ce-108">この記事は、Microsoft 365 管理者が次の質問に答えるリソースを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="576ce-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="576ce-109">Microsoft Search に接続できるデータ ソース</span><span class="sxs-lookup"><span data-stu-id="576ce-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="576ce-110">接続を管理する方法</span><span class="sxs-lookup"><span data-stu-id="576ce-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="576ce-111">Graph コネクタのライセンス要件と使用条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="576ce-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="576ce-112">プレビュー機能とは</span><span class="sxs-lookup"><span data-stu-id="576ce-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="576ce-113">検索結果をカスタマイズおよび構成する方法</span><span class="sxs-lookup"><span data-stu-id="576ce-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="576ce-114">カスタム アプリケーションからコネクタ データを検索する方法</span><span class="sxs-lookup"><span data-stu-id="576ce-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="576ce-115">検索結果をカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="576ce-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="576ce-116">コネクタの制限事項</span><span class="sxs-lookup"><span data-stu-id="576ce-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="576ce-117">Microsoft Graph コネクタと Microsoft Search API が一般提供されています。</span><span class="sxs-lookup"><span data-stu-id="576ce-117">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="576ce-118">最初のロールアウトは、ターゲットリリース用に構成された顧客に対して行います。</span><span class="sxs-lookup"><span data-stu-id="576ce-118">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="576ce-119">テナントで Graph コネクタを使用する場合は、ユーザーと管理者がターゲット リリースをオプトイン [する必要があります](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="576ce-119">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="576ce-120">Microsoft Search に接続できるデータ ソース</span><span class="sxs-lookup"><span data-stu-id="576ce-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="576ce-121">Microsoft は 9 つのグラフ コネクタを提供し、エコシステム パートナーは 100 を超える Graph コネクタを作成しました。</span><span class="sxs-lookup"><span data-stu-id="576ce-121">Microsoft provides 9 Graph connectors and our ecosystem partners have created over 100 more Graph connectors.</span></span> <span data-ttu-id="576ce-122">独自の Graph コネクタを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="576ce-122">You can also build your own Graph connector.</span></span>

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="576ce-123">Microsoft 提供の Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="576ce-123">Graph connectors by Microsoft</span></span>

<span data-ttu-id="576ce-124">Microsoft によって作成された Graph コネクタを使用して、次のデータ ソースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="576ce-124">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="576ce-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="576ce-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="576ce-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="576ce-126">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="576ce-127">Azure SQL および Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="576ce-127">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="576ce-128">大企業の Web サイト</span><span class="sxs-lookup"><span data-stu-id="576ce-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="576ce-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="576ce-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="576ce-130">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="576ce-130">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="576ce-131">Oracle SQL (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="576ce-131">Oracle SQL (preview)</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="576ce-132">Salesforce (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="576ce-132">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="576ce-133">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="576ce-133">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="576ce-134">Graph [コネクタ ギャラリーには、](connectors-gallery.md) これらの各 Graph コネクタの簡単な説明が含まれている。</span><span class="sxs-lookup"><span data-stu-id="576ce-134">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="576ce-135">これらのデータ ソースの 1 つをテナントに接続する準備が整っている場合は、[](configure-connector.md)データ ソースに適用される [Microsoft によるセットアップ コネクタ] セクションのセットアップの概要と他の記事を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="576ce-135">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="576ce-136">パートナーによるグラフ コネクタ</span><span class="sxs-lookup"><span data-stu-id="576ce-136">Graph connectors by our partners</span></span>

<span data-ttu-id="576ce-137">[Microsoft Graph コネクタ ギャラリーには](connectors-gallery.md)、パートナーによって作成された各 Graph コネクタの簡単な説明と、各パートナーの Web サイトへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="576ce-137">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief description of each of the Graph connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="576ce-138">詳細については、各パートナーに直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="576ce-138">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="576ce-139">独自の Graph コネクタを作成する</span><span class="sxs-lookup"><span data-stu-id="576ce-139">Build your own Graph connector</span></span>

<span data-ttu-id="576ce-140">必要に応じて、独自の Graph コネクタを作成できます。</span><span class="sxs-lookup"><span data-stu-id="576ce-140">You can build your own Graph connector if you prefer.</span></span> <span data-ttu-id="576ce-141">Graph コネクタの構築の詳細については、「Microsoft Graph の Microsoft Search API の概要 [」を参照してください](/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="576ce-141">For more information on building Graph connectors, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="576ce-142">接続を管理する方法</span><span class="sxs-lookup"><span data-stu-id="576ce-142">How do I manage my connections?</span></span>

<span data-ttu-id="576ce-143">接続は[、Microsoft 365](https://admin.microsoft.com/)[管理センターの](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[コネクタ] タブから管理できます。</span><span class="sxs-lookup"><span data-stu-id="576ce-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="576ce-144">接続の管理の詳細については、「接続の管理 [」を参照してください](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="576ce-144">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="576ce-145">Graph コネクタのライセンス要件と使用条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="576ce-145">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="576ce-146">有効な Microsoft 365 または Office 365 ライセンスと、組織内のユーザーが検索結果でコネクタからのデータを表示するのに十分な Graph Connectors クォータが必要です。</span><span class="sxs-lookup"><span data-stu-id="576ce-146">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="576ce-147">詳細については、「ライセンス要件 [と価格設定」および](licensing.md) 「 [使用条件」を参照してください](terms-of-use.md)。</span><span class="sxs-lookup"><span data-stu-id="576ce-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="576ce-148">プレビュー機能とは</span><span class="sxs-lookup"><span data-stu-id="576ce-148">What are the preview features?</span></span>

<span data-ttu-id="576ce-149">Microsoft Graph コネクタと Microsoft Search API は一般に利用可能ですが、プレビュー中のいくつかの機能があります。</span><span class="sxs-lookup"><span data-stu-id="576ce-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="576ce-150">プレビューのコネクタと機能のセットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="576ce-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="576ce-151">Azure DevOps コネクタ</span><span class="sxs-lookup"><span data-stu-id="576ce-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="576ce-152">Salesforce コネクタ</span><span class="sxs-lookup"><span data-stu-id="576ce-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="576ce-153">[ソース ACL を使用](servicenow-connector.md) する検索アクセス許可を持つ ServiceNow コネクタ</span><span class="sxs-lookup"><span data-stu-id="576ce-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="576ce-154">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="576ce-154">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="576ce-155">検索結果をカスタマイズおよび構成する方法</span><span class="sxs-lookup"><span data-stu-id="576ce-155">How do I customize and configure search results?</span></span>

<span data-ttu-id="576ce-156">検索結果をカスタマイズおよび構成するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="576ce-156">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="576ce-157">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="576ce-157">See the following articles to learn more:</span></span>

* [<span data-ttu-id="576ce-158">業界および結果の種類を管理する</span><span class="sxs-lookup"><span data-stu-id="576ce-158">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="576ce-159">検索結果のレイアウトを管理する</span><span class="sxs-lookup"><span data-stu-id="576ce-159">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="576ce-160">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="576ce-160">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="576ce-161">カスタム フィルターを管理する</span><span class="sxs-lookup"><span data-stu-id="576ce-161">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="576ce-162">カスタム アプリケーションからコネクタ データを検索する方法</span><span class="sxs-lookup"><span data-stu-id="576ce-162">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="576ce-163">カスタム データのインデックスが作成された後、開発者は、この [データを照会できます](/graph/search-concept-custom-types)。</span><span class="sxs-lookup"><span data-stu-id="576ce-163">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="576ce-164">任意のアプリケーションでデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="576ce-164">You can view your data in any application.</span></span> <span data-ttu-id="576ce-165">詳細については、「Microsoft Graph の [Microsoft Search API の概要」を参照してください](/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="576ce-165">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="576ce-166">検索結果をカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="576ce-166">How do I customize search results?</span></span>

<span data-ttu-id="576ce-167">次の手順は、この記事で推奨される検索結果をカスタマイズする方法をカスタマイズし、検索結果[を構成する方法です。](#how-do-i-customize-and-configure-search-results)</span><span class="sxs-lookup"><span data-stu-id="576ce-167">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="576ce-168">検索結果のカスタマイズの詳細については、「[検索結果のカスタマイズ] ページ [」を参照してください](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="576ce-168">To learn more about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="576ce-169">コネクタの制限事項は何ですか?</span><span class="sxs-lookup"><span data-stu-id="576ce-169">What are the connector limitations?</span></span>

* <span data-ttu-id="576ce-170">Microsoft で **構築された** コネクタを発行すると、接続が作成されるのに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="576ce-170">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="576ce-171">その間、接続の状態は保留中として表示されます。</span><span class="sxs-lookup"><span data-stu-id="576ce-171">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="576ce-172">[Microsoft 365 管理センター](https://admin.microsoft.com)では、接続が公開された後の検索 **スキーマ** の編集はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="576ce-172">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="576ce-173">検索スキーマを編集するには、接続を削除してから、新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="576ce-173">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="576ce-174">取り込みスループットは、1 秒あたり約 4 つのアイテムで調整されます。</span><span class="sxs-lookup"><span data-stu-id="576ce-174">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="576ce-175">スキーマの更新はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="576ce-175">There is no support for schema updates.</span></span> <span data-ttu-id="576ce-176">接続セットアップを作成した後、スキーマを更新する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="576ce-176">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="576ce-177">接続の削除と再作成のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="576ce-177">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="576ce-178">接続の制限があります。</span><span class="sxs-lookup"><span data-stu-id="576ce-178">There is a connection limit.</span></span> <span data-ttu-id="576ce-179">各テナントは、最大 10 の接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="576ce-179">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="576ce-180">接続の編集サポートは利用できません。</span><span class="sxs-lookup"><span data-stu-id="576ce-180">Edit support for connection is not available.</span></span> <span data-ttu-id="576ce-181">接続が作成されると、その接続を編集または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="576ce-181">Once the connection has been created, you can't edit or change it.</span></span> <span data-ttu-id="576ce-182">詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="576ce-182">If you need to change any details, you must delete and recreate the connection.</span></span>