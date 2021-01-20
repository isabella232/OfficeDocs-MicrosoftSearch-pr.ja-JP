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
description: Microsoft Search 用 Microsoft Graph コネクタの概要
ms.openlocfilehash: a45a007bbb2774caaaac90fc1549c8ba634b0580
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905957"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="97641-103">Microsoft Graph コネクタの概要</span><span class="sxs-lookup"><span data-stu-id="97641-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="97641-104">[Microsoft Search は](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) 、 [すべての Microsoft 365 データのインデックスを作成して](https://www.microsoft.com/microsoft-365) 、ユーザーを検索可能にしています。</span><span class="sxs-lookup"><span data-stu-id="97641-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="97641-105">Microsoft Graph コネクタを使用すると、組織は Microsoft Search の結果に表示されるサードパーティのデータにインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="97641-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="97641-106">これにより、Microsoft 365 生産性アプリと広範な Microsoft エコシステムで検索できるコンテンツ ソースの種類が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="97641-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="97641-107">サード パーティのデータは、オンプレミスまたはパブリック クラウドまたはプライベート クラウドでホストできます。</span><span class="sxs-lookup"><span data-stu-id="97641-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="97641-108">この記事の残りの部分は、Microsoft 365 管理者が次の質問に回答できるリソースを見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="97641-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="97641-109">Microsoft Search に接続できるデータ ソースは何ですか?</span><span class="sxs-lookup"><span data-stu-id="97641-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="97641-110">接続を管理する方法</span><span class="sxs-lookup"><span data-stu-id="97641-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="97641-111">Graph コネクタのライセンス要件と使用条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="97641-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="97641-112">プレビュー機能とは</span><span class="sxs-lookup"><span data-stu-id="97641-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="97641-113">検索結果をカスタマイズおよび構成する方法</span><span class="sxs-lookup"><span data-stu-id="97641-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="97641-114">カスタム アプリケーションからコネクタ データを検索する方法</span><span class="sxs-lookup"><span data-stu-id="97641-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="97641-115">Microsoft Graph コネクタと Microsoft Search API が一般提供されています。</span><span class="sxs-lookup"><span data-stu-id="97641-115">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="97641-116">最初のロールアウトは、2021 年 2 月まで続く予定です。</span><span class="sxs-lookup"><span data-stu-id="97641-116">The first rollout is scheduled to last until February 2021.</span></span> <span data-ttu-id="97641-117">それまでは、対象指定リリースにオプトインしたテナントと[](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)ユーザーだけが Graph コネクタを使用できます。</span><span class="sxs-lookup"><span data-stu-id="97641-117">Until then, only tenants and users who have opted into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) will be able to use Graph connectors.</span></span> <span data-ttu-id="97641-118">すべてのテナントへのロールアウトが完了すると、コネクタ コンテンツからのインデックス クォータ使用率は課金の対象になります。</span><span class="sxs-lookup"><span data-stu-id="97641-118">Upon rollout completion to all tenants, index quota utilization from connectors content will become subject to billing.</span></span> <span data-ttu-id="97641-119">詳細 [については、「ライセンス要件と価格」](licensing.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97641-119">See [Licensing requirements and pricing](licensing.md) for more information.</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="97641-120">Microsoft Search に接続できるデータ ソースは何ですか?</span><span class="sxs-lookup"><span data-stu-id="97641-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="97641-121">Microsoft は 10 個の Graph コネクタを提供し、エコシステム パートナーは 100 を超える追加の Graph コネクタを作成しています。</span><span class="sxs-lookup"><span data-stu-id="97641-121">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="97641-122">独自の Graph コネクタを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="97641-122">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="97641-123">Microsoft 提供の Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="97641-123">Graph connectors by Microsoft</span></span>

<span data-ttu-id="97641-124">Microsoft によって作成された Graph コネクタを使用して、次のデータ ソースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="97641-124">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="97641-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="97641-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="97641-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="97641-126">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="97641-127">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="97641-127">Azure SQL</span></span>
* [<span data-ttu-id="97641-128">大企業の Web サイト</span><span class="sxs-lookup"><span data-stu-id="97641-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="97641-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="97641-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="97641-130">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="97641-130">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="97641-131">ファイル共有</span><span class="sxs-lookup"><span data-stu-id="97641-131">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="97641-132">Oracle (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="97641-132">Oracle (preview)</span></span>
* [<span data-ttu-id="97641-133">Salesforce (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="97641-133">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="97641-134">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="97641-134">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="97641-135">Graph [コネクタ ギャラリーには、](connectors-gallery.md) これらの各 Graph コネクタの簡単な説明が含まれている。</span><span class="sxs-lookup"><span data-stu-id="97641-135">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="97641-136">これらのデータ ソースの 1 つをテナントに接続する準備ができている場合は、セットアップ[](configure-connector.md)の概要と、データ ソースに適用される Microsoft によるセットアップ コネクタに関するその他の記事を必ずお読みください。</span><span class="sxs-lookup"><span data-stu-id="97641-136">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="97641-137">パートナーによるグラフ コネクタ</span><span class="sxs-lookup"><span data-stu-id="97641-137">Graph connectors by our partners</span></span>

<span data-ttu-id="97641-138">[Microsoft Graph コネクタ](connectors-gallery.md)ギャラリーには、パートナーによって作成された各 Graph コネクタの簡単な説明と、各パートナーの Web サイトへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="97641-138">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="97641-139">詳細については、各パートナーに直接お問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="97641-139">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="97641-140">独自の Graph コネクタを作成する</span><span class="sxs-lookup"><span data-stu-id="97641-140">Build your own Graph connector</span></span>

<span data-ttu-id="97641-141">独自の Graph コネクタを構築する予定の場合は [、Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) の Microsoft Search API の概要を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97641-141">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="97641-142">接続を管理する方法</span><span class="sxs-lookup"><span data-stu-id="97641-142">How do I manage my connections?</span></span>

<span data-ttu-id="97641-143">[接続は、Microsoft 365](https://admin.microsoft.com/)管理センター[の](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[コネクタ] タブから管理できます。</span><span class="sxs-lookup"><span data-stu-id="97641-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="97641-144">詳細 [については、「接続の管理](manage-connector.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97641-144">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="97641-145">Graph コネクタのライセンス要件と使用条件は何ですか?</span><span class="sxs-lookup"><span data-stu-id="97641-145">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="97641-146">有効な Microsoft 365 または Office 365 ライセンスと、組織内のユーザーが検索結果でコネクタからのデータを表示するのに十分な Graph Connectors クォータが必要です。</span><span class="sxs-lookup"><span data-stu-id="97641-146">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="97641-147">詳細については、「ライセンス要件 [と価格と使用](licensing.md) 条件」 [を参照してください](terms-of-use.md)。</span><span class="sxs-lookup"><span data-stu-id="97641-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="97641-148">プレビュー機能とは</span><span class="sxs-lookup"><span data-stu-id="97641-148">What are the preview features?</span></span>

<span data-ttu-id="97641-149">Microsoft Graph コネクタと Microsoft Search API が一般提供される現在ではありますが、プレビューにはいくつかの機能があります。</span><span class="sxs-lookup"><span data-stu-id="97641-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="97641-150">プレビューのコネクタと機能のセットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="97641-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="97641-151">Azure DevOps コネクタ</span><span class="sxs-lookup"><span data-stu-id="97641-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="97641-152">Salesforce コネクタ</span><span class="sxs-lookup"><span data-stu-id="97641-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="97641-153">[ソース ACL を使用](servicenow-connector.md) する検索アクセス許可を持つ ServiceNow コネクタ</span><span class="sxs-lookup"><span data-stu-id="97641-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="97641-154">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="97641-154">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="97641-155">検索結果をカスタマイズおよび構成する方法</span><span class="sxs-lookup"><span data-stu-id="97641-155">How do I customize and configure search results?</span></span>

<span data-ttu-id="97641-156">検索結果をカスタマイズおよび構成するには、さまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="97641-156">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="97641-157">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="97641-157">See the following articles to learn more:</span></span>

* [<span data-ttu-id="97641-158">業界および結果の種類を管理する</span><span class="sxs-lookup"><span data-stu-id="97641-158">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="97641-159">検索結果のレイアウトを管理する</span><span class="sxs-lookup"><span data-stu-id="97641-159">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="97641-160">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="97641-160">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="97641-161">カスタム フィルターを管理する</span><span class="sxs-lookup"><span data-stu-id="97641-161">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="97641-162">カスタム アプリケーションからコネクタ データを検索する方法</span><span class="sxs-lookup"><span data-stu-id="97641-162">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="97641-163">カスタム データのインデックスが作成された後、開発者は、この [データに対してクエリを実行できます](https://docs.microsoft.com/graph/search-concept-custom-types)。</span><span class="sxs-lookup"><span data-stu-id="97641-163">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="97641-164">データは、任意のアプリケーションで表示できます。</span><span class="sxs-lookup"><span data-stu-id="97641-164">You can view your data in any application.</span></span> <span data-ttu-id="97641-165">詳細については、Microsoft Graph の Microsoft Search API の [概要を参照してください](https://docs.microsoft.com/graph/search-concept-overview)。</span><span class="sxs-lookup"><span data-stu-id="97641-165">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="limitations"></a><span data-ttu-id="97641-166">制限事項</span><span class="sxs-lookup"><span data-stu-id="97641-166">Limitations</span></span>

* <span data-ttu-id="97641-167">Microsoft **が作成** したコネクタを発行すると、接続が作成されるのに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="97641-167">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="97641-168">その間、接続の状態は保留中として表示されます。</span><span class="sxs-lookup"><span data-stu-id="97641-168">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="97641-169">[Microsoft 365 管理](https://admin.microsoft.com)センターでは、接続の公開後 **の検索スキーマ** の編集はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97641-169">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="97641-170">検索スキーマを編集するには、接続を削除してから新しい接続を作成します。</span><span class="sxs-lookup"><span data-stu-id="97641-170">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="97641-171">取り込みスループットは、1 秒あたり約 4 アイテムで調整されます。</span><span class="sxs-lookup"><span data-stu-id="97641-171">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="97641-172">スキーマの更新はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="97641-172">There is no support for schema updates.</span></span> <span data-ttu-id="97641-173">接続セットアップを作成した後、スキーマを更新する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="97641-173">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="97641-174">接続を削除して作成し、もう一度作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97641-174">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="97641-175">接続の制限があります。</span><span class="sxs-lookup"><span data-stu-id="97641-175">There is a connections limit.</span></span> <span data-ttu-id="97641-176">各テナントは、最大 10 の接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="97641-176">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="97641-177">接続の編集サポートは利用できません。</span><span class="sxs-lookup"><span data-stu-id="97641-177">Edit support for connection is not available.</span></span> <span data-ttu-id="97641-178">接続が作成されると、その接続を編集または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="97641-178">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="97641-179">詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="97641-179">If you need to change any details, you must delete and recreate the connection.</span></span>
