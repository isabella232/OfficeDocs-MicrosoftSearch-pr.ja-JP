---
title: Microsoft Search 用の Microsoft Graphコネクタを構成する
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
description: Microsoft によるGraphコネクタのセットアップの概要
ms.openlocfilehash: ef94d530af63d8b8b33dfae3c4b411164ef31feb
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720945"
---
<!-- Previous ms.author: monaray -->

<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a><span data-ttu-id="01889-103">Microsoft によるGraphコネクタのセットアップの概要</span><span class="sxs-lookup"><span data-stu-id="01889-103">Setup overview for Graph connectors by Microsoft</span></span> 

<span data-ttu-id="01889-104">この記事では、Microsoft が管理センターで Graph コネクタをセットアップするために必要Microsoft 365[を示します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="01889-104">This article shows the basic process required to set up the Graph connectors **by Microsoft** in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="01889-105">基本的なプロセスには、以下のステップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="01889-105">The basic process includes the following steps:</span></span>  
<!---Add links to each section in the doc--->

1. [<span data-ttu-id="01889-106">管理センター GraphコネクタをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="01889-106">Add a Graph connector in the Microsoft 365 admin center</span></span>](#step-1-add-a-graph-connector-in-the-microsoft-365-admin-center)
2. [<span data-ttu-id="01889-107">接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="01889-107">Name the connection</span></span>](#step-2-name-the-connection)
3. [<span data-ttu-id="01889-108">接続設定の構成</span><span class="sxs-lookup"><span data-stu-id="01889-108">Configure the connection settings</span></span>](#step-3-configure-the-connection-settings)
4. [<span data-ttu-id="01889-109">検索のアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="01889-109">Manage search permissions</span></span>](#step-4-manage-search-permissions)
5. [<span data-ttu-id="01889-110">プロパティ ラベルの割り当て</span><span class="sxs-lookup"><span data-stu-id="01889-110">Assign property labels</span></span>](#step-5-assign-property-labels)
6. [<span data-ttu-id="01889-111">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="01889-111">Manage schema</span></span>](#step-6-manage-schema)
7. [<span data-ttu-id="01889-112">更新設定</span><span class="sxs-lookup"><span data-stu-id="01889-112">Refresh settings</span></span>](#step-7-refresh-settings)
8. [<span data-ttu-id="01889-113">接続の確認</span><span class="sxs-lookup"><span data-stu-id="01889-113">Review connection</span></span>](#step-8-review-connection)

<span data-ttu-id="01889-114">この記事には、トラブルシューティング、制限事項、および次の手順に関する情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="01889-114">This article also includes information about troubleshooting, limitations, and next steps:</span></span>

* [<span data-ttu-id="01889-115">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="01889-115">Troubleshooting</span></span>](#troubleshooting)
* [<span data-ttu-id="01889-116">限界事項</span><span class="sxs-lookup"><span data-stu-id="01889-116">Limitations</span></span>](#limitations)
* [<span data-ttu-id="01889-117">次の手順</span><span class="sxs-lookup"><span data-stu-id="01889-117">Next steps</span></span>](#next-steps)

> [!NOTE]
> <span data-ttu-id="01889-118">セットアップ プロセスは、Microsoft のすべてのGraph似ていますが、まったく同じではありません。</span><span class="sxs-lookup"><span data-stu-id="01889-118">The setup process is similar for all the Graph connectors by Microsoft but is not exactly the same.</span></span> <span data-ttu-id="01889-119">**この記事を読むだけでなく、必ずデータ ソースのコネクタ固有の情報を読んでください。**</span><span class="sxs-lookup"><span data-stu-id="01889-119">**In addition to reading this article, be sure to read the connector-specific information for your data source.**</span></span>  

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="01889-120">手順 1: 管理センター GraphコネクタをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="01889-120">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="01889-121">以下の手順を実行して、Microsoft が構築したコネクタGraphします。</span><span class="sxs-lookup"><span data-stu-id="01889-121">Complete the following steps to configure any of the Microsoft-built Graph connectors:</span></span>

1. <span data-ttu-id="01889-122">管理センターで管理者アカウント[にサインインMicrosoft 365します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="01889-122">Sign into your admin account in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

2. <span data-ttu-id="01889-123">ナビゲーション ウィンドウで、[検索] を選択 **設定** し、[検索] を選択&**します**。</span><span class="sxs-lookup"><span data-stu-id="01889-123">In the navigation pane, select **Settings**, and then select **Search & intelligence**.</span></span> <span data-ttu-id="01889-124">[コネクタ] [タブを選択します](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。</span><span class="sxs-lookup"><span data-stu-id="01889-124">Select the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).</span></span>

3. <span data-ttu-id="01889-125">**[+追加]** を選択し、使用可能なオプションのメニューから選択したデータ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="01889-125">Select **+Add**, and then select the data source of your choice from the menu of available options.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01889-126">![使用できるデータ ソースは、ADLS Gen2、Enterprise Web サイト、Microsoft SQL サーバー、Azure SQL、Oracle SQL データベース、ServiceNow、ファイル共有、Azure DevOps、および MediaWiki です。](media/add-connector.png)</span><span class="sxs-lookup"><span data-stu-id="01889-126">![Data sources available include: ADLS Gen2, Enterprise websites, Microsoft SQL server, Azure SQL, Oracle SQL database, ServiceNow, File share, Azure DevOps, and MediaWiki.](media/add-connector.png)</span></span>

> [!NOTE]
> <span data-ttu-id="01889-127">各テナントに最大 10 個Graph接続を追加できます。</span><span class="sxs-lookup"><span data-stu-id="01889-127">You can add a maximum of ten Graph connections to each tenant.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="01889-128">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="01889-128">Step 2: Name the connection</span></span>

<span data-ttu-id="01889-129">次の属性を指定します。</span><span class="sxs-lookup"><span data-stu-id="01889-129">Specify these attributes:</span></span>

* <span data-ttu-id="01889-130">Name (必須)</span><span class="sxs-lookup"><span data-stu-id="01889-130">Name (required)</span></span>
* <span data-ttu-id="01889-131">接続 ID (必須)</span><span class="sxs-lookup"><span data-stu-id="01889-131">Connection ID (required)</span></span>
* <span data-ttu-id="01889-132">説明 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="01889-132">Description (optional)</span></span>

<span data-ttu-id="01889-133">接続 ID は、コネクタの暗黙的なプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="01889-133">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="01889-134">英数字のみを含み、最大 32 文字にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01889-134">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span>

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="01889-135">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="01889-135">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="01889-136">接続設定を構成するプロセスは、データ ソースの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="01889-136">The process to configure the connection settings varies based on the type of data source.</span></span> <span data-ttu-id="01889-137">セットアップ プロセスでこの手順を完了するには、テナントに追加するデータ ソースの種類に関するコネクタ固有の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01889-137">See the Connector-specific information for the type of data source you want to add to your tenant to complete this step in the setup process.</span></span>  

<span data-ttu-id="01889-138">オンプレミス データ ソースへの接続の詳細については、「オンプレミス データ ゲートウェイのインストール [」を参照してください](/data-integration/gateway/service-gateway-install)。</span><span class="sxs-lookup"><span data-stu-id="01889-138">To learn more about connecting to an on-premises data source, see [Install an on-premises data gateway](/data-integration/gateway/service-gateway-install).</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="01889-139">手順 4: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="01889-139">Step 4: Manage search permissions</span></span>

<span data-ttu-id="01889-140">アクセス制御リスト (ACL) は、組織内のユーザーがデータの各アイテムにアクセスできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="01889-140">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span>  

<span data-ttu-id="01889-141">Microsoft SQL[および Azure](MSSQL-connector.md) Data Lake Storage [Gen2](azure-data-lake-connector.md)のような一部のコネクタは、Azure Active Directory [(Azure AD)](/azure/active-directory/) ACL をネイティブにサポートします。</span><span class="sxs-lookup"><span data-stu-id="01889-141">Some connectors like [Microsoft SQL](MSSQL-connector.md) and [Azure Data Lake Storage Gen2](azure-data-lake-connector.md) natively support [Azure Active Directory (Azure AD)](/azure/active-directory/) ACLs.</span></span>

<span data-ttu-id="01889-142">[ServiceNow、Azure DevOps、Salesforce](servicenow-connector.md)[などの](azure-devops-connector.md)他のコネクタは[、Azure](salesforce-connector.md)以外のユーザーとグループAD同期をサポートします。</span><span class="sxs-lookup"><span data-stu-id="01889-142">Other connectors like [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md), and [Salesforce](salesforce-connector.md) support syncing of non-Azure AD users and groups.</span></span>  

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="01889-143">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="01889-143">Step 5: Assign property labels</span></span>

<span data-ttu-id="01889-144">セマンティック ラベルは、[プロパティ ラベルの割り当て] ページでソース プロパティに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="01889-144">You can assign semantic labels to your source properties on the "Assign property labels" page.</span></span> <span data-ttu-id="01889-145">ラベルは、意味的な意味を提供する Microsoft によって提供される既知のタグです。</span><span class="sxs-lookup"><span data-stu-id="01889-145">Labels are well-known tags provided by Microsoft that provide semantic meaning.</span></span> <span data-ttu-id="01889-146">これらの機能を使用すると、Microsoft は、拡張検索、Microsoft 365、インテリジェント検出など、さまざまなエクスペリエンスにコネクタ データを統合できます。</span><span class="sxs-lookup"><span data-stu-id="01889-146">They allow Microsoft to integrate your connector data into Microsoft 365 experiences such as enhanced search, people cards, intelligent discovery, and more.</span></span>  

<span data-ttu-id="01889-147">次の表に、現在サポートされているラベルとその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="01889-147">The following table lists the currently supported labels and their descriptions.</span></span>  

<span data-ttu-id="01889-148">ラベル</span><span class="sxs-lookup"><span data-stu-id="01889-148">Label</span></span> | <span data-ttu-id="01889-149">説明</span><span class="sxs-lookup"><span data-stu-id="01889-149">Description</span></span>
--- | ---  
<span data-ttu-id="01889-150">**title**</span><span class="sxs-lookup"><span data-stu-id="01889-150">**title**</span></span> | <span data-ttu-id="01889-151">検索やその他のエクスペリエンスに表示するアイテムのタイトル</span><span class="sxs-lookup"><span data-stu-id="01889-151">The title for the item that you want shown in search and other experiences</span></span>
<span data-ttu-id="01889-152">**url**</span><span class="sxs-lookup"><span data-stu-id="01889-152">**url**</span></span> | <span data-ttu-id="01889-153">ソース システム内のアイテムのターゲット URL</span><span class="sxs-lookup"><span data-stu-id="01889-153">The target url of the item in the source system</span></span>
<span data-ttu-id="01889-154">**createdBy**</span><span class="sxs-lookup"><span data-stu-id="01889-154">**createdBy**</span></span> | <span data-ttu-id="01889-155">アイテムを作成したユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="01889-155">Name of the person who created the item</span></span>
<span data-ttu-id="01889-156">**lastModifiedBy**</span><span class="sxs-lookup"><span data-stu-id="01889-156">**lastModifiedBy**</span></span> | <span data-ttu-id="01889-157">アイテムを最近編集したユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="01889-157">Name of the person who most recently edited the item</span></span>
<span data-ttu-id="01889-158">**authors**</span><span class="sxs-lookup"><span data-stu-id="01889-158">**authors**</span></span> | <span data-ttu-id="01889-159">アイテムに参加/共同作業を行ったユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="01889-159">Name of the people who participated/collaborated on the item</span></span>
<span data-ttu-id="01889-160">**createdDateTime**</span><span class="sxs-lookup"><span data-stu-id="01889-160">**createdDateTime**</span></span> | <span data-ttu-id="01889-161">アイテムが作成されたのは、いつ</span><span class="sxs-lookup"><span data-stu-id="01889-161">When was the item created</span></span>
<span data-ttu-id="01889-162">**lastModifiedDateTime**</span><span class="sxs-lookup"><span data-stu-id="01889-162">**lastModifiedDateTime**</span></span> | <span data-ttu-id="01889-163">アイテムが最近編集された場合</span><span class="sxs-lookup"><span data-stu-id="01889-163">When was the item most recently edited</span></span>
<span data-ttu-id="01889-164">**fileName**</span><span class="sxs-lookup"><span data-stu-id="01889-164">**fileName**</span></span> | <span data-ttu-id="01889-165">ファイル アイテムの名前</span><span class="sxs-lookup"><span data-stu-id="01889-165">Name of the file item</span></span>
<span data-ttu-id="01889-166">**FileExtension**</span><span class="sxs-lookup"><span data-stu-id="01889-166">**fileExtension**</span></span> | <span data-ttu-id="01889-167">ファイル アイテムの種類 (.pdf .word など)</span><span class="sxs-lookup"><span data-stu-id="01889-167">Type of file item such as .pdf or .word</span></span>

<span data-ttu-id="01889-168">このページのプロパティは、データ ソースに基づいて事前に選択されますが、特定のラベルに適した別のプロパティがある場合は、この選択を変更できます。</span><span class="sxs-lookup"><span data-stu-id="01889-168">The properties on this page are pre-selected based on your data source, but you can change this selection if there's a different property that is better suited for a particular label.</span></span>  

<span data-ttu-id="01889-169">ラベル タイトル **は、** 最も重要なラベルです。</span><span class="sxs-lookup"><span data-stu-id="01889-169">The label **title** is the most important label.</span></span> <span data-ttu-id="01889-170">接続が **結果クラスター エクスペリエンス** に参加するには、このラベルにプロパティが割り当てられている必要 [があります。](result-cluster.md)</span><span class="sxs-lookup"><span data-stu-id="01889-170">It's **strongly recommended** you have a property assigned to this label in order for your connection to participate in the [result cluster experience](result-cluster.md).</span></span>

<span data-ttu-id="01889-171">ラベルを正しくマッピングしないと、検索エクスペリエンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="01889-171">Incorrectly mapping labels will cause a deteriorated search experience.</span></span> <span data-ttu-id="01889-172">一部のラベルにプロパティが割り当てられていない場合は問題ありません。</span><span class="sxs-lookup"><span data-stu-id="01889-172">It's okay for some labels to not have a property assigned to it.</span></span>  

## <a name="step-6-manage-schema"></a><span data-ttu-id="01889-173">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="01889-173">Step 6: Manage schema</span></span>

### <a name="content-property"></a><span data-ttu-id="01889-174">Content プロパティ</span><span class="sxs-lookup"><span data-stu-id="01889-174">Content property</span></span>

<span data-ttu-id="01889-175">オプションのドロップダウン メニューから **コンテンツ** プロパティを選択するか、存在する場合は既定値のままにしてください。</span><span class="sxs-lookup"><span data-stu-id="01889-175">It's recommended you select a **Content Property** from the drop-down menu of options, or keep the default if one is present.</span></span> <span data-ttu-id="01889-176">このプロパティは、コンテンツのフルテキスト インデックス作成、検索結果ページ スニペットの生成、[](result-cluster.md)結果クラスターへの参加、言語の検出、HTML/テキストのサポート、ランク付けと関連性、およびクエリの作成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="01889-176">This property is used for full-text indexing of content, search results page snippet generation, [result cluster](result-cluster.md) participation, language detection, HTML/text support, ranking and relevance, and query formulation.</span></span>

<span data-ttu-id="01889-177">コンテンツ プロパティを選択すると、結果の種類を作成するときに、システム生成プロパティ **ResultSnippet** を [使用できます](customize-results-layout.md)。</span><span class="sxs-lookup"><span data-stu-id="01889-177">If you select a content property, you will have the option of using the system-generated property **ResultSnippet** when you [create your result type](customize-results-layout.md).</span></span> <span data-ttu-id="01889-178">このプロパティは、クエリ時に content プロパティから生成される動的スニペットのプレースホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="01889-178">This property serves as a placeholder for the dynamic snippets that are generated from the content property at query time.</span></span> <span data-ttu-id="01889-179">このプロパティを結果の種類で使用すると、検索結果にスニペットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="01889-179">If you use this property in your result type, snippets will be generated in your search results.</span></span>

### <a name="creating-aliases-for-source-properties"></a><span data-ttu-id="01889-180">ソース プロパティのエイリアスの作成</span><span class="sxs-lookup"><span data-stu-id="01889-180">Creating aliases for source properties</span></span>

<span data-ttu-id="01889-181">[スキーマの管理] ページの [エイリアス] 列の下のプロパティにエイリアスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="01889-181">You can add aliases to your properties under the "Alias" column on the "Manage schema" page.</span></span> <span data-ttu-id="01889-182">エイリアスは、プロパティの表示名であり、クエリやフィルターの作成にも使用されます。</span><span class="sxs-lookup"><span data-stu-id="01889-182">Aliases are friendly names for your properties, and also used in queries and in the creation of filters.</span></span> <span data-ttu-id="01889-183">また、同じ名前を持つ複数の接続からソース プロパティを正規化するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="01889-183">They're also used to normalize source properties from multiple connections such that they have the same name.</span></span> <span data-ttu-id="01889-184">この方法で、複数の接続を持つ垂直の 1 つのフィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="01889-184">That way you can create a single filter for a vertical with multiple connections.</span></span> <span data-ttu-id="01889-185">詳細については、「検索結果ページを [カスタマイズする」を参照してください](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="01889-185">For more information, see [Customize the search results page](customize-search-page.md).</span></span>  

### <a name="search-schema-attributes"></a><span data-ttu-id="01889-186">スキーマ属性の検索</span><span class="sxs-lookup"><span data-stu-id="01889-186">Search schema attributes</span></span>

<span data-ttu-id="01889-187">検索スキーマ属性を設定して、各ソース プロパティの検索機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="01889-187">You can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="01889-188">検索スキーマは、検索結果ページに表示される結果と、エンド ユーザーが表示およびアクセスできる情報を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01889-188">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="01889-189">検索スキーマ属性には、クエリ、 **検索**、 **取得**、絞り込 **み** などのオプション **があります**。</span><span class="sxs-lookup"><span data-stu-id="01889-189">Search schema attributes include options to **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="01889-190">次の表に、Microsoft がコネクタでサポートする各Graphを示し、その機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="01889-190">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="01889-191">検索スキーマ属性</span><span class="sxs-lookup"><span data-stu-id="01889-191">Search schema attribute</span></span> | <span data-ttu-id="01889-192">機能</span><span class="sxs-lookup"><span data-stu-id="01889-192">Function</span></span> | <span data-ttu-id="01889-193">例</span><span class="sxs-lookup"><span data-stu-id="01889-193">Example</span></span>
--- | --- | ---
<span data-ttu-id="01889-194">SEARCH</span><span class="sxs-lookup"><span data-stu-id="01889-194">SEARCH</span></span> | <span data-ttu-id="01889-195">プロパティのテキスト コンテンツを検索可能にする。</span><span class="sxs-lookup"><span data-stu-id="01889-195">Makes the text content of a property searchable.</span></span> <span data-ttu-id="01889-196">プロパティの内容は、フルテキスト インデックスに含まれます。</span><span class="sxs-lookup"><span data-stu-id="01889-196">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="01889-197">プロパティが **title** の場合は、テキスト **または** Enterpriseの単語を含む **Enterpriseを返** します。</span><span class="sxs-lookup"><span data-stu-id="01889-197">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="01889-198">QUERY</span><span class="sxs-lookup"><span data-stu-id="01889-198">QUERY</span></span> | <span data-ttu-id="01889-199">特定のプロパティの一致をクエリで検索します。</span><span class="sxs-lookup"><span data-stu-id="01889-199">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="01889-200">その後、クエリでプロパティ名をプログラムまたは動詞で指定できます。</span><span class="sxs-lookup"><span data-stu-id="01889-200">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="01889-201">Title プロパティ **をクエリ** できる場合は、**クエリ Title: Enterprise** サポートされます。</span><span class="sxs-lookup"><span data-stu-id="01889-201">If the **Title** property can be queried, then the query **Title: Enterprise** is supported.</span></span>
<span data-ttu-id="01889-202">RETRIEVE</span><span class="sxs-lookup"><span data-stu-id="01889-202">RETRIEVE</span></span> | <span data-ttu-id="01889-203">検索可能なプロパティのみを結果の種類で使用し、検索結果に表示できます。</span><span class="sxs-lookup"><span data-stu-id="01889-203">Only retrievable properties can be used in the result type and display in the search result.</span></span> |
<span data-ttu-id="01889-204">REFINE</span><span class="sxs-lookup"><span data-stu-id="01889-204">REFINE</span></span> | <span data-ttu-id="01889-205">絞り込みオプションは、Microsoft 検索結果ページと同様に使用できます。</span><span class="sxs-lookup"><span data-stu-id="01889-205">The refine option can be used as in the Microsoft Search results page.</span></span> | <span data-ttu-id="01889-206">接続のセットアップ中に[](custom-filters.md)絞り込みプロパティがマークされている場合、組織内のユーザーは検索結果ページの URL でフィルター処理できます</span><span class="sxs-lookup"><span data-stu-id="01889-206">Users in your organization can [filter](custom-filters.md) by **URL** in the search results page if the refine property is marked during connection setup</span></span>

<span data-ttu-id="01889-207">ファイル共有コネクタを除くすべてのコネクタでは、ユーザー設定の種類を手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01889-207">For all connectors except the File share connector, custom types must be set manually.</span></span> <span data-ttu-id="01889-208">各フィールドの検索機能をアクティブにするには、プロパティの一覧にマップされた検索スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="01889-208">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="01889-209">接続ウィザードでは、選択したソース プロパティのセットに基づいて検索スキーマが自動的に選択されます。</span><span class="sxs-lookup"><span data-stu-id="01889-209">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="01889-210">このスキーマを変更するには、検索スキーマ ページの各プロパティと属性のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="01889-210">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="01889-211">![コネクタのスキーマは、クエリ、検索、および取得関数を追加または削除することでカスタマイズできます。](media/manageschema.png)</span><span class="sxs-lookup"><span data-stu-id="01889-211">![Schema for a connector can be customized by adding or removing Query, Search, and Retrieve functions.](media/manageschema.png)</span></span>

### <a name="restrictions-and-recommendations-for-search-schema-settings"></a><span data-ttu-id="01889-212">検索スキーマ設定の制限と推奨事項</span><span class="sxs-lookup"><span data-stu-id="01889-212">Restrictions and recommendations for search schema settings</span></span>

* <span data-ttu-id="01889-213">content **プロパティ** は検索可能です。</span><span class="sxs-lookup"><span data-stu-id="01889-213">The **content** property is searchable only.</span></span> <span data-ttu-id="01889-214">ドロップダウンで選択すると、このプロパティをオプションの取得またはクエリ **と一緒に** 使用 **することはできません**。</span><span class="sxs-lookup"><span data-stu-id="01889-214">Once selected in the dropdown, this property cannot be used with the options **retrieve** or **query**.</span></span>

* <span data-ttu-id="01889-215">検索結果が content プロパティでレンダリングされる場合、パフォーマンスに関する重大な **問題が発生** します。</span><span class="sxs-lookup"><span data-stu-id="01889-215">Significant performance issues occur when search results render with the **content** property.</span></span> <span data-ttu-id="01889-216">例として **、ServiceNow** ナレッジベース記事の [テキスト](https://www.servicenow.com) コンテンツ フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="01889-216">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>

* <span data-ttu-id="01889-217">検索結果で取得可能なレンダリングとしてマークされたプロパティのみであり、最新の結果の種類 (MRT) の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="01889-217">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>

* <span data-ttu-id="01889-218">検索可能とマークできるのは文字列プロパティのみです。</span><span class="sxs-lookup"><span data-stu-id="01889-218">Only string properties can be marked searchable.</span></span>

> [!NOTE]
> <span data-ttu-id="01889-219">接続を作成した後は **、スキーマを** 変更できます。</span><span class="sxs-lookup"><span data-stu-id="01889-219">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="01889-220">これを行うには、接続を削除して新しい接続を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01889-220">To do that, you need to delete your connection and create a new one.</span></span>

## <a name="step-7-refresh-settings"></a><span data-ttu-id="01889-221">手順 7: 設定の更新</span><span class="sxs-lookup"><span data-stu-id="01889-221">Step 7: Refresh settings</span></span>

<span data-ttu-id="01889-222">更新間隔は、データ ソースと Microsoft Search の間でデータを同期する頻度を決定します。</span><span class="sxs-lookup"><span data-stu-id="01889-222">The refresh interval determines how often your data is synced between the data source and Microsoft Search.</span></span> <span data-ttu-id="01889-223">データ ソースの種類ごとに、データの変更頻度と変更の種類に基づいて、最適な更新スケジュールのセットが異なります。</span><span class="sxs-lookup"><span data-stu-id="01889-223">Each type of data source has a different set of optimal refresh schedules based on how often data is modified and the type of modifications.</span></span>

<span data-ttu-id="01889-224">更新間隔には、完全更新と増分更新の2種類がありますが、一部のデータ ソースでは増分更新を使用できません。</span><span class="sxs-lookup"><span data-stu-id="01889-224">There are two types of refresh intervals, which are **Full refresh** and **Incremental refresh**, but incremental refreshes aren't available for some data sources.</span></span>

<span data-ttu-id="01889-225">完全な更新により、検索エンジンは、以前のクロールに関係なく、コンテンツ ソースで変更されたアイテムを処理してインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="01889-225">With a full refresh, the search engine processes and indexes the items that have changed in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="01889-226">完全な更新は、次の状況に最適です。</span><span class="sxs-lookup"><span data-stu-id="01889-226">A full refresh works best for these situations:</span></span>

* <span data-ttu-id="01889-227">データの削除を検出する。</span><span class="sxs-lookup"><span data-stu-id="01889-227">Detecting deletions of data.</span></span>
* <span data-ttu-id="01889-228">増分更新でエラーが検出され、失敗しました。</span><span class="sxs-lookup"><span data-stu-id="01889-228">The incremental refresh found errors, and failed.</span></span>
* <span data-ttu-id="01889-229">ACL が変更されました。</span><span class="sxs-lookup"><span data-stu-id="01889-229">ACLs were modified.</span></span>
* <span data-ttu-id="01889-230">クロール ルールが変更されました。</span><span class="sxs-lookup"><span data-stu-id="01889-230">Crawl rules were modified.</span></span>
* <span data-ttu-id="01889-231">接続のスキーマが更新されました (スキーマ更新はまだサポートされていません)。</span><span class="sxs-lookup"><span data-stu-id="01889-231">The schema for the connection has been updated (schema updates aren't yet supported).</span></span>

<span data-ttu-id="01889-232">増分更新 **を使用すると**、検索エンジンは、前回のクロールが成功した後に作成または変更されたアイテムのみを処理およびインデックス付けできます。</span><span class="sxs-lookup"><span data-stu-id="01889-232">With an **Incremental refresh**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="01889-233">その結果、コンテンツ ソース内のすべてのデータがインデックスを再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01889-233">As a result, not all the data in the content source is reindexed.</span></span> <span data-ttu-id="01889-234">増分更新は、コンテンツ、メタデータ、アクセス許可、その他の更新プログラムを検出する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="01889-234">Incremental refreshes work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="01889-235">変更されていないアイテムは処理されないので、増分更新は完全な更新よりもはるかに高速です。</span><span class="sxs-lookup"><span data-stu-id="01889-235">Incremental refreshes are much faster than full refreshes because unchanged items aren't processed.</span></span> <span data-ttu-id="01889-236">ただし、増分更新を実行する場合でも、コンテンツ ソースと検索インデックスの間で正しいデータ同期を維持するには、定期的に完全な更新を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01889-236">However, if you choose to run incremental refreshes, you still need to run full refreshes periodically to maintain correct data sync between the content source and the search index.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="01889-237">![増分クロールと 15 分の増分、1 週間のフル クロールを示すフル クロール間隔の設定。](media/refreshschedule.png)</span><span class="sxs-lookup"><span data-stu-id="01889-237">![Incremental crawl and full crawl interval settings showing Incremental at 15 minutes and Full crawl at 1 week.](media/refreshschedule.png)</span></span>

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a><span data-ttu-id="01889-238">手順 8: 接続の確認</span><span class="sxs-lookup"><span data-stu-id="01889-238">Step 8: Review connection</span></span>

<span data-ttu-id="01889-239">接続を完了する前に、必要に応じて構成全体を確認し、設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="01889-239">You can review your entire configuration and edit settings as needed before completing the connection.</span></span> <span data-ttu-id="01889-240">**まだデータ ソースのコネクタ固有の情報を読み取っていない場合は、必ずお読みください。**</span><span class="sxs-lookup"><span data-stu-id="01889-240">**Be sure to read the connector-specific information for your data source if you haven't already done so.**</span></span> <span data-ttu-id="01889-241">接続 **を完了する準備** ができたら、[更新の完了] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01889-241">Select **Finish updating** when you're ready to complete the connection.</span></span>

### <a name="confirm-if-the-connection-setup-worked"></a><span data-ttu-id="01889-242">接続のセットアップが機能した場合の確認</span><span class="sxs-lookup"><span data-stu-id="01889-242">Confirm if the connection setup worked</span></span>

<span data-ttu-id="01889-243">管理センターの [コネクタ] タブの下にある発行済み **接続の一** 覧に [移動します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="01889-243">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="01889-244">更新と削除を行う方法については、「コネクタの管理 [」を参照してください](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="01889-244">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="01889-245">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="01889-245">Troubleshooting</span></span>
<!---Insert troubleshooting recommendations for this data source-->
<span data-ttu-id="01889-246">データ ソースのコネクタ固有の情報を読み取る。</span><span class="sxs-lookup"><span data-stu-id="01889-246">Read the connector-specific information for your data source.</span></span> 

> [!NOTE]
> <span data-ttu-id="01889-247">コネクタ固有の記事の中には、この時点でのトラブルシューティングの推奨事項が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="01889-247">Not all connector-specific articles include troubleshooting recommendations at this point.</span></span>

## <a name="limitations"></a><span data-ttu-id="01889-248">制限事項</span><span class="sxs-lookup"><span data-stu-id="01889-248">Limitations</span></span>
<!---Insert limitations for this data source-->
<span data-ttu-id="01889-249">すべてのデータ ソースに適用される制限の詳細については[、「Microsoft Graphコネクタの概要」を参照](connectors-overview.md)してください。</span><span class="sxs-lookup"><span data-stu-id="01889-249">To learn about limitations that apply to all data sources see the [Overview of Microsoft Graph connectors](connectors-overview.md) article.</span></span>

<span data-ttu-id="01889-250">データ ソースのコネクタ固有の情報を参照して、その特定のコネクタに他の制限が適用されるGraphしてください。</span><span class="sxs-lookup"><span data-stu-id="01889-250">See the connector-specific information for your data source to find out if other limitations apply to that  particular Graph connector.</span></span>

## <a name="next-steps"></a><span data-ttu-id="01889-251">次の手順</span><span class="sxs-lookup"><span data-stu-id="01889-251">Next steps</span></span>

<span data-ttu-id="01889-252">接続を公開した後、検索結果ページをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="01889-252">After publishing the connection, you need to customize the search results page.</span></span> <span data-ttu-id="01889-253">検索結果のカスタマイズの詳細については、「検索結果のカスタマイズ [ページ」を参照してください](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="01889-253">To learn about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>