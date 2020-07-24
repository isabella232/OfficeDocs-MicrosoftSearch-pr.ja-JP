---
title: コネクタの概要
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: ecedd135336f37da26cee71be06dd421cdb95f61
ms.sourcegitcommit: f2323c43fc732890213223efac32006df5b92c28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2020
ms.locfileid: "45387996"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="c7b74-103">Microsoft Graph コネクタの概要</span><span class="sxs-lookup"><span data-stu-id="c7b74-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="c7b74-104">Microsoft Search では、ユーザーが検索できるように、 [microsoft 365](https://www.microsoft.com/microsoft-365)のすべてのデータのインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-104">Microsoft Search indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="c7b74-105">Microsoft Graph コネクタを使用すると、サードパーティーデータのインデックスを作成して、Microsoft の検索結果に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-105">With Microsoft Graph connectors, your organization can index third-party data to appear in Microsoft Search results.</span></span> <span data-ttu-id="c7b74-106">サードパーティのデータは、オンプレミスまたはパブリッククラウドまたはプライベートクラウドでホストできます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-106">The third-party data can be hosted on-premises or in the public or private clouds.</span></span> <span data-ttu-id="c7b74-107">コネクタは、Microsoft 365 プロダクティビティアプリと Microsoft の広範なエコシステムで検索可能なコンテンツソースの種類を拡張します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-107">Connectors expand the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7b74-108">**免責事項**: microsoft Graph のコネクタと Microsoft Search api (クエリとインデックス) は現在、対象となるリリースのテナントで利用可能なプレビュー状態になっています。</span><span class="sxs-lookup"><span data-stu-id="c7b74-108">**DISCLAIMER**: Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status available for tenants in Targeted release.</span></span> <span data-ttu-id="c7b74-109">Microsoft Search でコネクタを使用したり、コネクタを作成したりするには、[対象となるリリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)にオプトインします。</span><span class="sxs-lookup"><span data-stu-id="c7b74-109">To use connectors with Microsoft Search or to build connectors, opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span> <span data-ttu-id="c7b74-110">プレビューの詳細については、「[コネクタプレビュープログラム](connectors-preview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-110">To learn more about the preview, see [connectors preview program](connectors-preview.md).</span></span>

## <a name="architecture"></a><span data-ttu-id="c7b74-111">アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c7b74-111">Architecture</span></span>

<span data-ttu-id="c7b74-112">Microsoft Graph プラットフォームの次のアーキテクチャ図は、 [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search)クライアントでのコンテンツインデックスを使用してコネクタコンテンツをユーザーの結果にどのように流し込むかを示しています。</span><span class="sxs-lookup"><span data-stu-id="c7b74-112">The following architectural diagram of the Microsoft Graph platform shows how connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients.</span></span> <span data-ttu-id="c7b74-113">この記事では、Microsoft Graph コネクタデータフロープロセスの主な構成要素について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-113">This article explains each of the key building blocks in the Microsoft Graph connectors data flow process.</span></span>

![図: 社内およびクラウドベースのデータは、コネクタによって取得され、Microsoft Search API によってインデックスが作成され、Microsoft Search サービスが結果をユーザーに配信します。](media/highlevel-connectors_FINAL.png)

<span data-ttu-id="c7b74-115">API は、データソースごとに1つの接続をインスタンス化します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-115">The API instantiates one connection per data source.</span></span> <span data-ttu-id="c7b74-116">その後、API はデータをインデックス処理して格納します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-116">Then the API indexes and stores the data.</span></span> <span data-ttu-id="c7b74-117">確立された接続は Microsoft Search とやり取りされるので、ユーザーは検索結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-117">Established connections interact with Microsoft Search, so users can get search results.</span></span>

<span data-ttu-id="c7b74-118">Microsoft 365[管理センター](https://admin.microsoft.com)では、microsoft によって作成されたすべてのコネクタを構成できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-118">You can configure all the Microsoft-built connectors in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="c7b74-119">管理センターを使用すると、簡単なユーザーインターフェイスでコネクタを簡単に構成できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-119">The admin center simplifies configuring your connector with a simple user interface.</span></span>

<span data-ttu-id="c7b74-120">データソースへの**接続**を作成するには、管理者がデータとコンテンツリポジトリ全体への認証されたアクセスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="c7b74-120">To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository.</span></span> <span data-ttu-id="c7b74-121">データは、インデックス作成のために graph connector サービスに送られます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-121">The data is fed to the graph connector service for indexing.</span></span>

## <a name="available-connectors"></a><span data-ttu-id="c7b74-122">利用可能なコネクタ</span><span class="sxs-lookup"><span data-stu-id="c7b74-122">Available connectors</span></span>

<span data-ttu-id="c7b74-123">現在、マイクロソフトが提供しているコネクタが6つあり、エコシステムパートナーから100以上のコネクタを利用できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-123">There are currently 6 Microsoft-built connectors, and over 100 connectors are available from our ecosystem partners.</span></span>

<span data-ttu-id="c7b74-124">エコシステムパートナーの1つからコネクタをプレビューするには、そのパートナーに直接連絡します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-124">To preview connectors from one of our ecosystem partners, contact them directly.</span></span> <span data-ttu-id="c7b74-125">詳細については、 [Microsoft Graph のコネクタギャラリー](connectors-gallery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-125">For more information, see the [Microsoft Graph connectors gallery](connectors-gallery.md).</span></span>

<span data-ttu-id="c7b74-126">[独自のコネクタを作成](https://docs.microsoft.com/graph/search-concept-overview)することもできます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-126">You can also [build your own connector](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

### <a name="connectors-by-microsoft"></a><span data-ttu-id="c7b74-127">Microsoft 提供のコネクター</span><span class="sxs-lookup"><span data-stu-id="c7b74-127">Connectors by Microsoft</span></span>

<span data-ttu-id="c7b74-128">Microsoft Graph コネクタプレビューリリースには、6つの Microsoft が作成したコネクタが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c7b74-128">The Microsoft Graph connectors preview release includes 6 Microsoft-built connectors.</span></span> <span data-ttu-id="c7b74-129">[管理センター](https://admin.microsoft.com)で設定し、 [Microsoft が作成](configure-connector.md)したコネクタをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-129">You can set them up in the [admin center](https://admin.microsoft.com) and learn how to [Set up your Microsoft-built connector](configure-connector.md).</span></span>

<span data-ttu-id="c7b74-130">次のセクションでは、これらの Microsoft が作成したコネクタについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-130">The following sections provide brief descriptions for these Microsoft-built connectors.</span></span> <span data-ttu-id="c7b74-131">各コネクタのリンクされた記事に詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-131">You can get more information in the linked articles for each connector.</span></span>

- <span data-ttu-id="c7b74-132">**[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**。</span><span class="sxs-lookup"><span data-stu-id="c7b74-132">**[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**.</span></span> <span data-ttu-id="c7b74-133">この Microsoft Graph コネクタを使用すると、組織内のユーザーは Azure Blob コンテナーに格納されているファイルとコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-133">With this Microsoft Graph connector, users in your organization can search for files and content stored in Azure Blob containers.</span></span> <span data-ttu-id="c7b74-134">Azure Data Lake Storage Gen2 connector は、指定した Azure Data Lake Storage Gen2 アカウント内の階層が有効なフォルダーにもインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-134">The Azure Data Lake Storage Gen2 connector also indexes hierarchy-enabled folders in Azure Data Lake Storage Gen2 accounts that you specify.</span></span>
<span data-ttu-id="c7b74-135">詳細については、「 [Azure Data Lake Storage Gen2 connector](azure-data-lake-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-135">Learn more about the [Azure Data Lake Storage Gen2 connector](azure-data-lake-connector.md).</span></span>

- <span data-ttu-id="c7b74-136">**[Azure DevOps](https://azure.microsoft.com/services/devops)**。</span><span class="sxs-lookup"><span data-stu-id="c7b74-136">**[Azure DevOps](https://azure.microsoft.com/services/devops)**.</span></span> <span data-ttu-id="c7b74-137">この Microsoft Graph コネクタを使用すると、組織内のユーザーは Azure DevOps インスタンスから作業項目を検索できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-137">With this Microsoft Graph connector, users in your organization can search for work items from your Azure DevOps instance.</span></span>
<span data-ttu-id="c7b74-138">詳細については、「 [Azure DevOps connector](azure-devops-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-138">Learn more about the [Azure DevOps connector](azure-devops-connector.md).</span></span>

- <span data-ttu-id="c7b74-139">**[AZURE SQL](https://azure.microsoft.com/services/sql-database)**。</span><span class="sxs-lookup"><span data-stu-id="c7b74-139">**[Azure SQL](https://azure.microsoft.com/services/sql-database)**.</span></span> <span data-ttu-id="c7b74-140">この Microsoft Graph コネクタを使用すると、組織内のユーザーは Azure SQL データベースからデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-140">With this Microsoft Graph connector, users in your organization can search for data from your Azure SQL database.</span></span>
<span data-ttu-id="c7b74-141">詳細については、「 [AZURE SQL connector](MSSQL-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-141">Learn more about the [Azure SQL connector](MSSQL-connector.md).</span></span>

- <span data-ttu-id="c7b74-142">**エンタープライズ web サイト**。</span><span class="sxs-lookup"><span data-stu-id="c7b74-142">**Enterprise websites**.</span></span> <span data-ttu-id="c7b74-143">この Microsoft Graph コネクタを使用すると、組織内のユーザーは、SharePoint 以外のエンタープライズ web サイト内のページを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-143">With this Microsoft Graph connector, users in your organization can search over pages in any non-SharePoint enterprise website.</span></span>
<span data-ttu-id="c7b74-144">詳細については、「[エンタープライズ web サイトコネクタ](enterprise-web-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-144">Learn more about the [Enterprise websites connector](enterprise-web-connector.md).</span></span>

- <span data-ttu-id="c7b74-145">**[Mediawiki](https://www.mediawiki.org/wiki/MediaWiki)**。</span><span class="sxs-lookup"><span data-stu-id="c7b74-145">**[MediaWiki](https://www.mediawiki.org/wiki/MediaWiki)**.</span></span> <span data-ttu-id="c7b74-146">この Microsoft Graph コネクタを使用すると、ユーザーは、組織が MediaWiki を使用して作成した wiki サイトで、サポート技術情報の記事を検索できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-146">With this Microsoft Graph connector, users can search for knowledge-base articles on wiki sites your organization creates with MediaWiki.</span></span>
<span data-ttu-id="c7b74-147">詳細については、「 [Mediawiki コネクタ](mediawiki-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-147">Learn more about the [MediaWiki connector](mediawiki-connector.md).</span></span>

- <span data-ttu-id="c7b74-148">**[MICROSOFT SQL server](https://www.microsoft.com/sql-server/sql-server-2017)**。</span><span class="sxs-lookup"><span data-stu-id="c7b74-148">**[Microsoft SQL server](https://www.microsoft.com/sql-server/sql-server-2017)**.</span></span> <span data-ttu-id="c7b74-149">この Microsoft Graph コネクタを使用すると、組織内のユーザーはオンプレミスの SQL server データベースのデータを検索できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-149">With this Microsoft Graph connector, users in your organization can search for data in on-premises SQL server databases.</span></span>
<span data-ttu-id="c7b74-150">詳細については、「 [MICROSOFT SQL server connector](MSSQL-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-150">Learn more about the [Microsoft SQL server connector](MSSQL-connector.md).</span></span>

- <span data-ttu-id="c7b74-151">**[ServiceNow](https://www.servicenow.com)**</span><span class="sxs-lookup"><span data-stu-id="c7b74-151">**[ServiceNow](https://www.servicenow.com)**.</span></span> <span data-ttu-id="c7b74-152">この Microsoft Graph コネクタを使用すると、組織内のユーザーは ServiceNow インスタンスからサポート技術情報の記事を検索できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-152">With this Microsoft Graph connector, users in your organization can search for knowledge-base articles from your ServiceNow instance.</span></span>
<span data-ttu-id="c7b74-153">[ServiceNow コネクタ](servicenow-connector.md)の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-153">Learn more about the [ServiceNow connector](servicenow-connector.md).</span></span>

### <a name="connectors-from-our-partners"></a><span data-ttu-id="c7b74-154">パートナーからのコネクタ</span><span class="sxs-lookup"><span data-stu-id="c7b74-154">Connectors from our partners</span></span>

<span data-ttu-id="c7b74-155">エコシステムパートナーからのプレビューには、100を超えるコネクタが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c7b74-155">There are over 100 connectors available for preview from our ecosystem partners.</span></span> <span data-ttu-id="c7b74-156">エコシステムパートナーの1つからコネクタをプレビューするには、そのパートナーに直接連絡します。</span><span class="sxs-lookup"><span data-stu-id="c7b74-156">To preview connectors from one of our ecosystem partners, contact them directly.</span></span>
<span data-ttu-id="c7b74-157">パートナーからのコネクタの詳細については、 [Microsoft Graph のコネクタギャラリー](connectors-gallery.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-157">Learn more about connectors from our partners in the [Microsoft Graph connectors gallery](connectors-gallery.md).</span></span>

### <a name="build-your-own-connector"></a><span data-ttu-id="c7b74-158">独自のコネクタを作成する</span><span class="sxs-lookup"><span data-stu-id="c7b74-158">Build your own connector</span></span>

<span data-ttu-id="c7b74-159">カスタムデータ型またはファイルにインデックスを作成するために、開発者は[Microsoft Graph](https://developer.microsoft.com/graph/)でコネクタを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-159">To index custom data types or files, developers can create connectors in [Microsoft Graph](https://developer.microsoft.com/graph/).</span></span> <span data-ttu-id="c7b74-160">コネクタは、[接続を作成](https://docs.microsoft.com/graph/search-index-manage-connections)し、Microsoft 検索インデックスにアイテムをプッシュするアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="c7b74-160">A connector is an application that [creates a connection](https://docs.microsoft.com/graph/search-index-manage-connections) and pushes items into the Microsoft Search index.</span></span> <span data-ttu-id="c7b74-161">詳細については、microsoft [Graph でアプリの Microsoft 検索機能を拡張するための概要](https://docs.microsoft.com/graph/search-concept-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-161">For more information, see the [Overview for extending the Microsoft Search experience for apps on Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

### <a name="search-results-with-your-custom-built-connector"></a><span data-ttu-id="c7b74-162">カスタム作成コネクタを使用した検索結果</span><span class="sxs-lookup"><span data-stu-id="c7b74-162">Search results with your custom-built connector</span></span>

<span data-ttu-id="c7b74-163">カスタムデータのインデックスを作成すると、開発者は[このデータをクエリ](https://docs.microsoft.com/graph/search-concept-custom-types)できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-163">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="c7b74-164">任意のアプリケーションでデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c7b74-164">You can view your data in any application.</span></span> <span data-ttu-id="c7b74-165">詳細については、microsoft [Graph でアプリの Microsoft 検索機能を拡張するための概要](https://docs.microsoft.com/graph/search-concept-overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7b74-165">For more information, see the [Overview for extending the Microsoft Search experience for apps on Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="license-requirements"></a><span data-ttu-id="c7b74-166">ライセンス要件</span><span class="sxs-lookup"><span data-stu-id="c7b74-166">License requirements</span></span>

<span data-ttu-id="c7b74-167">検索結果のコネクタのデータを表示するには、次の Microsoft 365 または Office 365 のサブスクリプションのいずれかをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7b74-167">To view data from connectors in your search results, users must have one of the following Microsoft 365 or Office 365 subscriptions:</span></span>

- [<span data-ttu-id="c7b74-168">Microsoft 365 または Office 365 Enterprise E3 または E5</span><span class="sxs-lookup"><span data-stu-id="c7b74-168">Microsoft 365 or Office 365 Enterprise E3 or E5</span></span>](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)

- [<span data-ttu-id="c7b74-169">Microsoft 365 または Office 365 エデュケーション A3 または A5</span><span class="sxs-lookup"><span data-stu-id="c7b74-169">Microsoft 365 or Office 365 Education A3 or A5</span></span>](https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans?activetab=tab:primaryr1)
