---
title: Microsoft Graph コネクタの概要
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
description: Microsoft Search 用 Microsoft Graph コネクタの概要
ms.openlocfilehash: 13127d092fe4e624ed448037d83f16f83ddc560a
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084877"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="868b8-103">Microsoft Graph コネクタの概要</span><span class="sxs-lookup"><span data-stu-id="868b8-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="868b8-104">[Microsoft Search は](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) 、 [すべての Microsoft 365 データのインデックスを作成して](https://www.microsoft.com/microsoft-365) 、ユーザーを検索可能にしています。</span><span class="sxs-lookup"><span data-stu-id="868b8-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="868b8-105">Microsoft Graph コネクタを使用すると、組織は Microsoft Search の結果に表示されるサードパーティのデータにインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="868b8-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="868b8-106">この機能は、Microsoft 365 生産性アプリと広範な Microsoft エコシステムで検索可能なコンテンツ ソースの種類を拡張します。</span><span class="sxs-lookup"><span data-stu-id="868b8-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="868b8-107">サード パーティのデータは、オンプレミスまたはパブリック クラウドまたはプライベート クラウドでホストできます。</span><span class="sxs-lookup"><span data-stu-id="868b8-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="868b8-108">この記事は、Microsoft 365 管理者が次の質問に回答できるリソースを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="868b8-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="868b8-109">Microsoft Search に接続できるデータ ソースは何ですか?</span><span class="sxs-lookup"><span data-stu-id="868b8-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="868b8-110">接続を管理する方法</span><span class="sxs-lookup"><span data-stu-id="868b8-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="868b8-111">Graph コネクタのライセンス要件と使用条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="868b8-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="868b8-112">プレビュー機能とは</span><span class="sxs-lookup"><span data-stu-id="868b8-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="868b8-113">検索結果をカスタマイズおよび構成する方法</span><span class="sxs-lookup"><span data-stu-id="868b8-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="868b8-114">カスタム アプリケーションからコネクタ データを検索する方法</span><span class="sxs-lookup"><span data-stu-id="868b8-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="868b8-115">Microsoft Graph コネクタと Microsoft Search API が一般提供されています。</span><span class="sxs-lookup"><span data-stu-id="868b8-115">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="868b8-116">最初のロールアウトは、対象となるリリース用に構成されたユーザーに対して行います。</span><span class="sxs-lookup"><span data-stu-id="868b8-116">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="868b8-117">テナントで Graph コネクタを使用する場合、ユーザーと管理者は対象指定リリースにオプトイン [する必要があります](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="868b8-117">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="868b8-118">Microsoft Search に接続できるデータ ソースは何ですか?</span><span class="sxs-lookup"><span data-stu-id="868b8-118">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="868b8-119">Microsoft は 9 つの Graph コネクタを提供し、エコシステム パートナーは 100 を超える Graph コネクタを作成しています。</span><span class="sxs-lookup"><span data-stu-id="868b8-119">Microsoft provides 9 Graph connectors and our ecosystem partners have created over 100 more Graph connectors.</span></span> <span data-ttu-id="868b8-120">独自の Graph コネクタを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="868b8-120">You can also build your own Graph connector.</span></span>

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="868b8-121">Microsoft 提供の Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="868b8-121">Graph connectors by Microsoft</span></span>

<span data-ttu-id="868b8-122">Microsoft によって作成された Graph コネクタを使用して、次のデータ ソースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="868b8-122">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="868b8-123">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="868b8-123">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="868b8-124">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="868b8-124">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="868b8-125">Azure SQL および Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="868b8-125">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="868b8-126">大企業の Web サイト</span><span class="sxs-lookup"><span data-stu-id="868b8-126">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="868b8-127">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="868b8-127">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="868b8-128">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="868b8-128">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="868b8-129">Oracle SQL (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="868b8-129">Oracle SQL (preview)</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="868b8-130">Salesforce (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="868b8-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="868b8-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="868b8-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="868b8-132">Graph [コネクタ ギャラリーには、](connectors-gallery.md) これらの Graph コネクタの簡単な説明が含まれている。</span><span class="sxs-lookup"><span data-stu-id="868b8-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="868b8-133">これらのデータ ソースの 1 つをテナントに接続する準備ができている場合は、セットアップの[](configure-connector.md)概要と、データ ソースに適用される Microsoft によるセットアップ コネクタに関するその他の記事を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="868b8-133">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="868b8-134">パートナーによるグラフ コネクタ</span><span class="sxs-lookup"><span data-stu-id="868b8-134">Graph connectors by our partners</span></span>

<span data-ttu-id="868b8-135">[Microsoft Graph コネクタ](connectors-gallery.md)ギャラリーには、パートナーによって作成された各 Graph コネクタの簡単な説明と、各パートナーの Web サイトへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="868b8-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief description of each of the Graph connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="868b8-136">詳細については、各パートナーに直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="868b8-136">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="868b8-137">独自の Graph コネクタを作成する</span><span class="sxs-lookup"><span data-stu-id="868b8-137">Build your own Graph connector</span></span>

<span data-ttu-id="868b8-138">必要に応じて、独自の Graph コネクタを作成できます。</span><span class="sxs-lookup"><span data-stu-id="868b8-138">You can build your own Graph connector if you prefer.</span></span> <span data-ttu-id="868b8-139">Graph コネクタの構築の詳細については、Microsoft Graph の Microsoft Search API の概要 [を参照してください](https://docs.microsoft.com/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="868b8-139">For more information on building Graph connectors, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="868b8-140">接続を管理する方法</span><span class="sxs-lookup"><span data-stu-id="868b8-140">How do I manage my connections?</span></span>

<span data-ttu-id="868b8-141">[接続は、Microsoft 365](https://admin.microsoft.com/)管理センター[の](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[コネクタ] タブから管理できます。</span><span class="sxs-lookup"><span data-stu-id="868b8-141">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="868b8-142">接続の管理の詳細については、「接続の管理」 [を参照してください](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="868b8-142">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="868b8-143">Graph コネクタのライセンス要件と使用条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="868b8-143">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="868b8-144">有効な Microsoft 365 または Office 365 ライセンスと、組織内のユーザーが検索結果でコネクタからのデータを表示するのに十分な Graph Connectors クォータが必要です。</span><span class="sxs-lookup"><span data-stu-id="868b8-144">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="868b8-145">詳細については、「ライセンス要件 [と価格と使用](licensing.md) 条件」 [を参照してください](terms-of-use.md)。</span><span class="sxs-lookup"><span data-stu-id="868b8-145">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="868b8-146">プレビュー機能とは</span><span class="sxs-lookup"><span data-stu-id="868b8-146">What are the preview features?</span></span>

<span data-ttu-id="868b8-147">Microsoft Graph コネクタと Microsoft Search API が一般提供される現在ではありますが、プレビューにはいくつかの機能があります。</span><span class="sxs-lookup"><span data-stu-id="868b8-147">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="868b8-148">プレビューのコネクタと機能のセットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="868b8-148">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="868b8-149">Azure DevOps コネクタ</span><span class="sxs-lookup"><span data-stu-id="868b8-149">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="868b8-150">Salesforce コネクタ</span><span class="sxs-lookup"><span data-stu-id="868b8-150">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="868b8-151">[ソース ACL を](servicenow-connector.md) 使用する検索アクセス許可を持つ ServiceNow コネクタ</span><span class="sxs-lookup"><span data-stu-id="868b8-151">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="868b8-152">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="868b8-152">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="868b8-153">検索結果をカスタマイズおよび構成する方法</span><span class="sxs-lookup"><span data-stu-id="868b8-153">How do I customize and configure search results?</span></span>

<span data-ttu-id="868b8-154">検索結果をカスタマイズおよび構成する方法は多数あります。</span><span class="sxs-lookup"><span data-stu-id="868b8-154">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="868b8-155">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="868b8-155">See the following articles to learn more:</span></span>

* [<span data-ttu-id="868b8-156">業界および結果の種類を管理する</span><span class="sxs-lookup"><span data-stu-id="868b8-156">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="868b8-157">検索結果のレイアウトを管理する</span><span class="sxs-lookup"><span data-stu-id="868b8-157">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="868b8-158">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="868b8-158">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="868b8-159">カスタム フィルターを管理する</span><span class="sxs-lookup"><span data-stu-id="868b8-159">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="868b8-160">カスタム アプリケーションからコネクタ データを検索する方法</span><span class="sxs-lookup"><span data-stu-id="868b8-160">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="868b8-161">カスタム データのインデックスが作成された後、開発者は、この [データに対してクエリを実行できます](https://docs.microsoft.com/graph/search-concept-custom-types)。</span><span class="sxs-lookup"><span data-stu-id="868b8-161">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="868b8-162">データは任意のアプリケーションで表示できます。</span><span class="sxs-lookup"><span data-stu-id="868b8-162">You can view your data in any application.</span></span> <span data-ttu-id="868b8-163">詳細については、Microsoft Graph の Microsoft Search API の [概要を参照してください](https://docs.microsoft.com/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="868b8-163">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="next-steps"></a><span data-ttu-id="868b8-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="868b8-164">Next steps</span></span>

<span data-ttu-id="868b8-165">この記事で推奨されている方法で検索結果をカスタマイズし、構成する方法 [を確認します](#how-do-i-customize-and-configure-search-results)。</span><span class="sxs-lookup"><span data-stu-id="868b8-165">Make sure you customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="868b8-166">検索結果のカスタマイズの詳細については、「検索結果のカスタマイズ」 [ページを参照してください](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。</span><span class="sxs-lookup"><span data-stu-id="868b8-166">To learn more about customizing search results, see [Customize the search results page](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).</span></span>

## <a name="limitations"></a><span data-ttu-id="868b8-167">制限事項</span><span class="sxs-lookup"><span data-stu-id="868b8-167">Limitations</span></span>

* <span data-ttu-id="868b8-168">Microsoft **が作成** したコネクタを発行すると、接続が作成されるのに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="868b8-168">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="868b8-169">その間、接続の状態は保留中として表示されます。</span><span class="sxs-lookup"><span data-stu-id="868b8-169">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="868b8-170">[Microsoft 365 管理](https://admin.microsoft.com)センターでは、接続の公開後 **の検索スキーマ** の編集はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="868b8-170">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="868b8-171">検索スキーマを編集するには、接続を削除してから新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="868b8-171">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="868b8-172">取り込みスループットは、1 秒あたり約 4 アイテムで調整されます。</span><span class="sxs-lookup"><span data-stu-id="868b8-172">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="868b8-173">スキーマの更新はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="868b8-173">There is no support for schema updates.</span></span> <span data-ttu-id="868b8-174">接続セットアップを作成した後、スキーマを更新する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="868b8-174">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="868b8-175">接続を削除して作成し、もう一度作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="868b8-175">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="868b8-176">接続の制限があります。</span><span class="sxs-lookup"><span data-stu-id="868b8-176">There is a connections limit.</span></span> <span data-ttu-id="868b8-177">各テナントは、最大 10 の接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="868b8-177">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="868b8-178">接続の編集サポートは利用できません。</span><span class="sxs-lookup"><span data-stu-id="868b8-178">Edit support for connection is not available.</span></span> <span data-ttu-id="868b8-179">接続が作成されると、その接続を編集または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="868b8-179">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="868b8-180">詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="868b8-180">If you need to change any details, you must delete and recreate the connection.</span></span>
