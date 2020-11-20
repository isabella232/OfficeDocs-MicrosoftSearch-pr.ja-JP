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
ms.openlocfilehash: 86ddf0387e3d00a005f25207a322c8470799b76b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367610"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a><span data-ttu-id="e0196-103">Microsoft によるグラフコネクタのセットアップの概要</span><span class="sxs-lookup"><span data-stu-id="e0196-103">Setup overview for Graph connectors by Microsoft</span></span> 

<span data-ttu-id="e0196-104">この記事では、microsoft [365 管理センター](https://admin.microsoft.com) を使用して、microsoft によってグラフコネクタをセットアップするために必要な基本手順の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="e0196-104">This article summarizes the basic process required to use the [Microsoft 365 admin center](https://admin.microsoft.com) to setup any of the Graph connectors by Microsoft.</span></span> <span data-ttu-id="e0196-105">基本的なプロセスには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e0196-105">The basic process includes the following steps:</span></span>  
<!---Add links to each section in the doc--->

1. <span data-ttu-id="e0196-106">Microsoft 365 管理センターで Graph connector を追加します。</span><span class="sxs-lookup"><span data-stu-id="e0196-106">Add a Graph connector in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="e0196-107">接続に名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0196-107">Name the connection.</span></span>
3. <span data-ttu-id="e0196-108">接続設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="e0196-108">Configure the connection settings.</span></span>
4. <span data-ttu-id="e0196-109">検索権限を管理します。</span><span class="sxs-lookup"><span data-stu-id="e0196-109">Manage search permissions.</span></span>
5. <span data-ttu-id="e0196-110">プロパティのラベルを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e0196-110">Assign property labels.</span></span>
6. <span data-ttu-id="e0196-111">スキーマを管理します。</span><span class="sxs-lookup"><span data-stu-id="e0196-111">Manage schema.</span></span>
7. <span data-ttu-id="e0196-112">[設定の更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0196-112">Choose refresh settings.</span></span>
8. <span data-ttu-id="e0196-113">接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="e0196-113">Review the connection.</span></span>

<span data-ttu-id="e0196-114">セットアッププロセスは、Microsoft によってすべての Graph コネクタでよく似ていますが、まったく同じではないことに注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0196-114">It is important to note that the setup process is very similar for all the Graph connectors by Microsoft but is not exactly the same.</span></span> <span data-ttu-id="e0196-115">**この記事を読むだけでなく、データソースのコネクタ固有の情報を必ずお読みください。**</span><span class="sxs-lookup"><span data-stu-id="e0196-115">**In addition to reading this article, be sure to read the connector-specific for your data source.**</span></span>  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e0196-116">手順 1: Microsoft 365 管理センターで Graph connector を追加する</span><span class="sxs-lookup"><span data-stu-id="e0196-116">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="e0196-117">Microsoft によって作成されたコネクタのいずれかを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0196-117">Complete the following steps to configure any of the Microsoft-built connectors.</span></span>

1. <span data-ttu-id="e0196-118">[Microsoft 365 管理センター](https://admin.microsoft.com)で管理者アカウントにサインインする</span><span class="sxs-lookup"><span data-stu-id="e0196-118">Sign into your admin account in the [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
2. <span data-ttu-id="e0196-119">ナビゲーションウィンドウで、[ **設定**] を選択し、[ **Search & 知能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0196-119">In the navigation pane, select **Settings**, and then select **Search & intelligence**.</span></span> <span data-ttu-id="e0196-120">[ [コネクタ] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0196-120">Select the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).</span></span>
3.  <span data-ttu-id="e0196-121">[ **+ 追加**] を選択し、使用可能なオプションのメニューから任意のデータソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0196-121">Select **+Add**, and then select the data source of your choice from the menu of available options.</span></span>

![使用可能なデータソースは次のとおりです。 ADLS Gen2、エンタープライズ web サイト、Microsoft SQL server、Azure SQL、Oracle SQL database、ServiceNow、ファイル共有、Azure DevOps、および MediaWiki。](media/add-connector.png)

><span data-ttu-id="e0196-123">[!注:] 各テナントに最大10個のグラフ接続を追加できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-123">[!Note:] You can add a maximum of ten Graph connections to each tenant.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="e0196-124">手順 2: 接続に名前を指定する</span><span class="sxs-lookup"><span data-stu-id="e0196-124">Step 2: Name the connection</span></span>
<span data-ttu-id="e0196-125">次の属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0196-125">You will need to specify these attributes:</span></span> 

* <span data-ttu-id="e0196-126">Name</span><span class="sxs-lookup"><span data-stu-id="e0196-126">Name</span></span>  
* <span data-ttu-id="e0196-127">接続 ID</span><span class="sxs-lookup"><span data-stu-id="e0196-127">Connection ID</span></span> 
* <span data-ttu-id="e0196-128">説明 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e0196-128">Description (optional)</span></span> 

<span data-ttu-id="e0196-129">接続 ID は、コネクタの暗黙的なプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0196-129">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="e0196-130">このファイルには、英数字のみが含まれ、最大32文字の文字が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0196-130">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span> 

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="e0196-131">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="e0196-131">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="e0196-132">接続設定を構成するプロセスは、データソースの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e0196-132">The process to configure the Connection settings varies based on the type of data source.</span></span> <span data-ttu-id="e0196-133">セットアッププロセスでこの手順を実行するには、テナントに追加するデータソースの種類に関するコネクタ固有の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0196-133">See the Connector-specific information for the type of data source you want to add to your tenant to complete this step in the setup process.</span></span>  

<span data-ttu-id="e0196-134">オンプレミスのデータソースへの接続の詳細については、「 [オンプレミスのデータゲートウェイをインストール](https://aka.ms/configuregateway)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0196-134">To learn more about connecting to an on-premises data source, see [Install an on-premises data gateway](https://aka.ms/configuregateway).</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="e0196-135">手順 4: 検索権限を管理する</span><span class="sxs-lookup"><span data-stu-id="e0196-135">Step 4: Manage search permissions</span></span>

<span data-ttu-id="e0196-136">アクセス制御リスト (Acl) は、組織内のどのユーザーがデータの各アイテムにアクセスできるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="e0196-136">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span>  

<span data-ttu-id="e0196-137">[MICROSOFT SQL](MSSQL-connector.md)および[Azure Data Lake Storage Gen2](azure-data-lake-connector.md)などの一部のコネクタでは、 [AZURE Active Directory (azure AD)](https://docs.microsoft.com/azure/active-directory/) acl がネイティブにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e0196-137">Some connectors like [Microsoft SQL](MSSQL-connector.md) and [Azure Data Lake Storage Gen2](azure-data-lake-connector.md) natively support [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) ACLs.</span></span>

<span data-ttu-id="e0196-138">[ServiceNow](servicenow-connector.md)、 [azure DevOps](azure-devops-connector.md)、および[Salesforce](salesforce-connector.md)などの他のコネクタは、非 Azure AD ユーザーとグループの同期をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e0196-138">Other connectors like [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md), and [Salesforce](salesforce-connector.md) support syncing of non-Azure AD users and groups.</span></span>  

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="e0196-139">手順 5: プロパティラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e0196-139">Step 5: Assign property labels</span></span>
<span data-ttu-id="e0196-140">[プロパティラベルの割り当て] ページでソースプロパティにセマンティックラベルを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e0196-140">You can assign semantic labels to your source properties on the "Assign property labels" page.</span></span> <span data-ttu-id="e0196-141">ラベルは、Microsoft によって提供される、意味的な意味を提供する既知のタグです。</span><span class="sxs-lookup"><span data-stu-id="e0196-141">Labels are well known tags provided by Microsoft that provide semantic meaning.</span></span> <span data-ttu-id="e0196-142">これにより、Microsoft は、拡張検索、people カード、インテリジェントな検出などの Microsoft 365 エクスペリエンスに、コネクタデータを統合することができます。</span><span class="sxs-lookup"><span data-stu-id="e0196-142">They allow Microsoft to integrate your connector data into Microsoft 365 experiences such as enhanced search, people cards, intelligent discovery, and more.</span></span>  

<span data-ttu-id="e0196-143">次の表に、現在サポートされているラベルとその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="e0196-143">The following table lists the currently supported labels and their descriptions.</span></span>  

<span data-ttu-id="e0196-144">ラベル</span><span class="sxs-lookup"><span data-stu-id="e0196-144">Label</span></span> | <span data-ttu-id="e0196-145">説明</span><span class="sxs-lookup"><span data-stu-id="e0196-145">Description</span></span>
--- | ---  
<span data-ttu-id="e0196-146">**title**</span><span class="sxs-lookup"><span data-stu-id="e0196-146">**title**</span></span> | <span data-ttu-id="e0196-147">検索やその他のエクスペリエンスに表示するアイテムのタイトル</span><span class="sxs-lookup"><span data-stu-id="e0196-147">The title for the item that you want shown in search and other experiences</span></span> 
<span data-ttu-id="e0196-148">**url**</span><span class="sxs-lookup"><span data-stu-id="e0196-148">**url**</span></span> | <span data-ttu-id="e0196-149">ソースシステム内のアイテムのターゲット url</span><span class="sxs-lookup"><span data-stu-id="e0196-149">The target url of the item in the source system</span></span> 
<span data-ttu-id="e0196-150">**createdBy**</span><span class="sxs-lookup"><span data-stu-id="e0196-150">**createdBy**</span></span> | <span data-ttu-id="e0196-151">アイテムを作成したユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="e0196-151">Name of the person who created the item</span></span> 
<span data-ttu-id="e0196-152">**lastModifiedBy**</span><span class="sxs-lookup"><span data-stu-id="e0196-152">**lastModifiedBy**</span></span> | <span data-ttu-id="e0196-153">アイテムを最後に編集したユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="e0196-153">Name of the person who most recently edited the item</span></span> 
<span data-ttu-id="e0196-154">**authors**</span><span class="sxs-lookup"><span data-stu-id="e0196-154">**authors**</span></span> | <span data-ttu-id="e0196-155">アイテムに共同作業しているユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="e0196-155">Name of the people who participated/collaborated on the item</span></span> 
<span data-ttu-id="e0196-156">**createdDateTime**</span><span class="sxs-lookup"><span data-stu-id="e0196-156">**createdDateTime**</span></span> | <span data-ttu-id="e0196-157">アイテムが作成された日時</span><span class="sxs-lookup"><span data-stu-id="e0196-157">When was the item created</span></span> 
<span data-ttu-id="e0196-158">**lastModifiedDateTime**</span><span class="sxs-lookup"><span data-stu-id="e0196-158">**lastModifiedDateTime**</span></span> | <span data-ttu-id="e0196-159">アイテムが最後に編集されたのはいつですか</span><span class="sxs-lookup"><span data-stu-id="e0196-159">When was the item most recently edited</span></span> 
<span data-ttu-id="e0196-160">**fileName**</span><span class="sxs-lookup"><span data-stu-id="e0196-160">**fileName**</span></span> | <span data-ttu-id="e0196-161">ファイルアイテムの名前</span><span class="sxs-lookup"><span data-stu-id="e0196-161">Name of the file item</span></span> 
<span data-ttu-id="e0196-162">**FileExtension**</span><span class="sxs-lookup"><span data-stu-id="e0196-162">**fileExtension**</span></span> | <span data-ttu-id="e0196-163">.Pdf または word などのファイル項目の種類</span><span class="sxs-lookup"><span data-stu-id="e0196-163">Type of file item such as .pdf or .word</span></span> 

<span data-ttu-id="e0196-164">このページのプロパティは、データソースに基づいてあらかじめ選択されていますが、特定のラベルにより適した別のプロパティがある場合は、この選択を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-164">The properties on this page are pre-selected based on your data source, but you can change this selection if there is a different property that is better suited for a particular label.</span></span>  

<span data-ttu-id="e0196-165">ラベル **タイトル** は、最も重要なラベルです。</span><span class="sxs-lookup"><span data-stu-id="e0196-165">The label **title** is the most important label.</span></span> <span data-ttu-id="e0196-166">このラベルには、[結果のクラスター環境](result-cluster.md)に参加するためにプロパティを割り当てることを **強くお勧め** します。</span><span class="sxs-lookup"><span data-stu-id="e0196-166">It is **strongly recommended** that you have a property assigned to this label in order for your connection to participate in the [result cluster experience](result-cluster.md).</span></span>

<span data-ttu-id="e0196-167">ラベルを誤ってマッピングすると、deteriorated の検索機能が発生します。</span><span class="sxs-lookup"><span data-stu-id="e0196-167">Incorrectly mapping labels will cause a deteriorated search experience.</span></span> <span data-ttu-id="e0196-168">プロパティを割り当てられていないラベルもあります。</span><span class="sxs-lookup"><span data-stu-id="e0196-168">It is okay for some labels to not have a property assigned to it.</span></span>  

## <a name="step-6-manage-schema"></a><span data-ttu-id="e0196-169">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="e0196-169">Step 6: Manage schema</span></span>

### <a name="content-property"></a><span data-ttu-id="e0196-170">Content プロパティ</span><span class="sxs-lookup"><span data-stu-id="e0196-170">Content property</span></span>

<span data-ttu-id="e0196-171">[オプション] ドロップダウンメニューから [\* \* Content Property] を選択することを強くお勧めします。または、存在する場合は既定値をそのまま使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e0196-171">It is strongly recommended that you select a \*\*Content Property" from the drop-down menu of options, or keep the default if one is present.</span></span> <span data-ttu-id="e0196-172">このプロパティは、コンテンツのフルテキストインデックス作成、検索結果のページスニペット生成、 [結果のクラスター](result-cluster.md) 参加、言語の検出、HTML/テキストのサポート、ランク付けと関連性、およびクエリ formulation に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0196-172">This property is used for full-text indexing of content, search results page snippet generation, [result cluster](result-cluster.md) participation, language detection, HTML/text support, ranking and relevance, and query formulation.</span></span>

<span data-ttu-id="e0196-173">コンテンツプロパティを選択した場合は、[結果の種類を作成](customize-results-layout.md)するときにシステム生成されたプロパティ **resultsnippet** を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="e0196-173">If you select a content property, you will have the option of using the system-generated property **ResultSnippet** when you [create your result type](customize-results-layout.md).</span></span> <span data-ttu-id="e0196-174">このプロパティは、クエリ時に content プロパティから生成される動的スニペットのプレースホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="e0196-174">This property serves as a placeholder for the dynamic snippets that are generated from the content property at query time.</span></span> <span data-ttu-id="e0196-175">結果の種類でこのプロパティを使用すると、検索結果にスニペットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="e0196-175">If you use this property in your result type, snippets will be generated in your search results.</span></span>

### <a name="creating-aliases-for-source-properties"></a><span data-ttu-id="e0196-176">ソースプロパティのエイリアスを作成する</span><span class="sxs-lookup"><span data-stu-id="e0196-176">Creating aliases for source properties</span></span>

<span data-ttu-id="e0196-177">[スキーマの管理] ページの [エイリアス] 列の下にあるプロパティにエイリアスを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e0196-177">You can add aliases to your properties under the "Alias" column on the "Manage schema" page.</span></span> <span data-ttu-id="e0196-178">エイリアスは、プロパティのフレンドリ名です。</span><span class="sxs-lookup"><span data-stu-id="e0196-178">Aliases are friendly names for your properties.</span></span> <span data-ttu-id="e0196-179">クエリとフィルターの作成で使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0196-179">They are used in queries and in the creation of filters.</span></span> <span data-ttu-id="e0196-180">また、同じ名前を持つ複数の接続からソースプロパティを正規化するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="e0196-180">They are also used to normalize source properties from multiple connections such that they have the same name.</span></span> <span data-ttu-id="e0196-181">これにより、複数の接続を持つ垂直方向の単一のフィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-181">That way you can create a single filter for a vertical with multiple connections.</span></span> <span data-ttu-id="e0196-182">詳細について [は、「検索結果ページのカスタマイズ](customize-search-page.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0196-182">See [Customize the search results page](customize-search-page.md) for more information.</span></span>  

### <a name="search-schema-attributes"></a><span data-ttu-id="e0196-183">検索スキーマの属性</span><span class="sxs-lookup"><span data-stu-id="e0196-183">Search schema attributes</span></span>

<span data-ttu-id="e0196-184">検索スキーマの属性を設定して、各 source プロパティの検索機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-184">You can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="e0196-185">検索スキーマは、検索結果ページに表示される結果と、エンドユーザーが表示およびアクセスできる情報を決定するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e0196-185">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="e0196-186">検索スキーマの属性に **は、検索** 可能、**クエリ\*\*\*\*可能、取得可能、\*\*\*\*絞り込み可能な** があります。</span><span class="sxs-lookup"><span data-stu-id="e0196-186">Search schema attributes include **searchable**, **queryable**, **retrievable**, and **refinable**.</span></span> <span data-ttu-id="e0196-187">次の表に、Microsoft Graph コネクタがサポートしている各属性とその機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0196-187">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="e0196-188">検索スキーマの属性</span><span class="sxs-lookup"><span data-stu-id="e0196-188">Search schema attribute</span></span> | <span data-ttu-id="e0196-189">関数</span><span class="sxs-lookup"><span data-stu-id="e0196-189">Function</span></span> | <span data-ttu-id="e0196-190">例</span><span class="sxs-lookup"><span data-stu-id="e0196-190">Example</span></span>
--- | --- | ---
<span data-ttu-id="e0196-191">サーチ</span><span class="sxs-lookup"><span data-stu-id="e0196-191">SEARCHABLE</span></span> | <span data-ttu-id="e0196-192">プロパティのテキストコンテンツを検索可能にします。</span><span class="sxs-lookup"><span data-stu-id="e0196-192">Makes the text content of a property searchable.</span></span> <span data-ttu-id="e0196-193">プロパティの内容は、フルテキストインデックスに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e0196-193">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="e0196-194">プロパティが **title** の場合、 **エンタープライズ** のクエリは、テキストまたはタイトルに " **enterprise** " が含まれている回答を返します。</span><span class="sxs-lookup"><span data-stu-id="e0196-194">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="e0196-195">クエリ可能</span><span class="sxs-lookup"><span data-stu-id="e0196-195">QUERYABLE</span></span> | <span data-ttu-id="e0196-196">クエリによって特定のプロパティの一致が検索されます。</span><span class="sxs-lookup"><span data-stu-id="e0196-196">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="e0196-197">プロパティ名は、プログラムまたは逐語的にクエリで指定できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-197">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="e0196-198">**Title** プロパティがクエリ可能な場合は、クエリ **タイトル: Enterprise** がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e0196-198">If the **Title** property is queryable, then the query **Title: Enterprise** is supported.</span></span> 
<span data-ttu-id="e0196-199">だっ</span><span class="sxs-lookup"><span data-stu-id="e0196-199">RETRIEVABLE</span></span> | <span data-ttu-id="e0196-200">検索結果の種類には取得可能なプロパティのみを使用し、検索結果に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e0196-200">Only retrievable properties can be used in the result type and display in the search result.</span></span> |
<span data-ttu-id="e0196-201">絞り込み可能な</span><span class="sxs-lookup"><span data-stu-id="e0196-201">REFINABLE</span></span> | <span data-ttu-id="e0196-202">絞り込み可能なプロパティは、Microsoft 検索結果ページと同じように使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-202">Refinable properties can be used as in the Microsoft Search results page.</span></span> | <span data-ttu-id="e0196-203">組織内のユーザーは、接続の設定中に絞り込み可能なというマークが付けられている場合、検索結果ページの **lastModifiedDateTime** によって [フィルター処理](custom-filters.md)できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-203">Users in your organization can [filter](custom-filters.md) by **lastModifiedDateTime** in the search results page if the property is marked refinable during connection setup</span></span>

<span data-ttu-id="e0196-204">ファイル共有コネクタを除くすべてのコネクタについては、カスタムの種類を手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0196-204">For all connectors except the File share connector, custom types must be set manually.</span></span> <span data-ttu-id="e0196-205">各フィールドの検索機能をアクティブにするには、プロパティのリストにマップされた検索スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0196-205">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="e0196-206">接続ウィザードは、選択したソースプロパティのセットに基づいて検索スキーマを自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="e0196-206">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="e0196-207">このスキーマを変更するには、[検索スキーマ] ページで各プロパティと属性のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e0196-207">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

![コネクタのスキーマは、クエリ、検索、および取得機能を追加または削除することでカスタマイズできます。](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a><span data-ttu-id="e0196-209">検索スキーマ設定の制限事項と推奨事項</span><span class="sxs-lookup"><span data-stu-id="e0196-209">Restrictions and recommendations for search schema settings</span></span>

* <span data-ttu-id="e0196-210">**コンテンツ** プロパティは検索可能でのみあります。</span><span class="sxs-lookup"><span data-stu-id="e0196-210">The **content** property is searchable only.</span></span> <span data-ttu-id="e0196-211">ドロップダウンで選択すると、このプロパティを取得または **クエリ\*\*\*\*可能とし** てマークすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e0196-211">Once selected in the dropdown, this property cannot be marked **retrievable** or **queryable**.</span></span>

* <span data-ttu-id="e0196-212">**コンテンツ** プロパティを使用して検索結果が表示される場合、パフォーマンスの著しい問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="e0196-212">Significant performance issues occur when search results render with the **content** property.</span></span> <span data-ttu-id="e0196-213">この例は、 [ServiceNow](https://www.servicenow.com)ナレッジベースの記事の **テキスト** コンテンツフィールドです。</span><span class="sxs-lookup"><span data-stu-id="e0196-213">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>

* <span data-ttu-id="e0196-214">検索結果には、取得可能としてマークされたプロパティのみが表示され、モダンの検索結果の種類 (MRTs) を作成するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-214">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>

* <span data-ttu-id="e0196-215">検索可能としてマークできるのは、文字列のプロパティだけです。</span><span class="sxs-lookup"><span data-stu-id="e0196-215">Only string properties can be marked searchable.</span></span>

> [!NOTE]
> <span data-ttu-id="e0196-216">接続を作成した後、スキーマを変更する **ことはできません** 。</span><span class="sxs-lookup"><span data-stu-id="e0196-216">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="e0196-217">そのためには、接続を削除して、新しい接続を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0196-217">To do that, you need to delete your connection and create a new one.</span></span>

## <a name="step-7-refresh-settings"></a><span data-ttu-id="e0196-218">手順 7: 設定を更新する</span><span class="sxs-lookup"><span data-stu-id="e0196-218">Step 7: Refresh settings</span></span>

<span data-ttu-id="e0196-219">更新間隔によって、データソースと Microsoft Search の間でデータが同期される頻度が決まります。</span><span class="sxs-lookup"><span data-stu-id="e0196-219">The refresh interval determines how often your data is synced between the data source and Microsoft Search.</span></span> <span data-ttu-id="e0196-220">データソースの種類によって、データが変更される頻度と変更の種類に基づいて、最適な更新スケジュールのセットが異なります。</span><span class="sxs-lookup"><span data-stu-id="e0196-220">Each type of data source has a different set of optimal refresh schedules based on how often data is modified and the type of modifications.</span></span>

<span data-ttu-id="e0196-221">更新間隔には、 **完全更新** と **増分更新** の2種類がありますが、一部のデータソースでは増分更新を使用できません。</span><span class="sxs-lookup"><span data-stu-id="e0196-221">There are two types of refresh intervals, which are **Full refresh** and **Incremental refresh**, but incremental refreshes are not available for some data sources.</span></span>

<span data-ttu-id="e0196-222">完全更新では、検索エンジンは、以前のクロールに関係なく、コンテンツソース内のすべてのアイテムを処理してインデックスを付けます。</span><span class="sxs-lookup"><span data-stu-id="e0196-222">With a full refresh, the search engine processes and indexes every item in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="e0196-223">完全更新は、次のような状況で最適に機能します。</span><span class="sxs-lookup"><span data-stu-id="e0196-223">A full refresh works best for these situations:</span></span>

* <span data-ttu-id="e0196-224">データの削除を検出します。</span><span class="sxs-lookup"><span data-stu-id="e0196-224">Detecting deletions of data.</span></span>
* <span data-ttu-id="e0196-225">増分更新で、エラーのためにコンテンツを更新できませんでした。</span><span class="sxs-lookup"><span data-stu-id="e0196-225">The incremental refresh failed to update content due to errors.</span></span>
* <span data-ttu-id="e0196-226">Acl が変更されました。</span><span class="sxs-lookup"><span data-stu-id="e0196-226">ACLs were modified.</span></span>
* <span data-ttu-id="e0196-227">クロールルールが変更されました。</span><span class="sxs-lookup"><span data-stu-id="e0196-227">Crawl rules were modified.</span></span>
* <span data-ttu-id="e0196-228">接続のスキーマが更新された場合 (スキーマの更新はまだサポートされていません)</span><span class="sxs-lookup"><span data-stu-id="e0196-228">When schema for the connection has been updated (schema updates are not yet supported)</span></span>

<span data-ttu-id="e0196-229">**増分更新** では、検索エンジンは、最後に成功したクロール以降に作成または変更されたアイテムのみを処理してインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e0196-229">With an **Incremental refresh**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="e0196-230">そのため、コンテンツソース内のすべてのデータが再インデックス化されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="e0196-230">Therefore, not all the data in the content source is re-indexed.</span></span> <span data-ttu-id="e0196-231">増分更新は、コンテンツ、メタデータ、アクセス許可、その他の更新プログラムを検出するのに最適です。</span><span class="sxs-lookup"><span data-stu-id="e0196-231">Incremental refreshes work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="e0196-232">変更されていないアイテムは処理されないため、増分更新は完全な更新よりもはるかに高速です。</span><span class="sxs-lookup"><span data-stu-id="e0196-232">Incremental refreshes are much faster than full refreshes because unchanged items aren’t processed.</span></span> <span data-ttu-id="e0196-233">ただし、増分更新を実行することを選択した場合でも、コンテンツソースと検索インデックス間で正確なデータ同期を維持するために、完全更新を定期的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0196-233">However, if you choose to run incremental refreshes, you will still need to run full refreshes periodically to maintain an accurate data sync between the content source and the search index.</span></span>

![増分クロールとフルクロール間隔の設定は、増分は15分で、フルクロールは1週間で表示されます。](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a><span data-ttu-id="e0196-235">手順 8: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="e0196-235">Step 8: Review connection</span></span>

<span data-ttu-id="e0196-236">接続を完了する前に、構成全体を確認し、必要に応じて設定を編集することができます。</span><span class="sxs-lookup"><span data-stu-id="e0196-236">You can review your entire configuration and edit settings as needed before completing the connection.</span></span> <span data-ttu-id="e0196-237">**まだデータソースのコネクタ固有の情報を確認していない場合は、必ず読み取ります。**</span><span class="sxs-lookup"><span data-stu-id="e0196-237">**Be sure to read the connector-specific information for your data source if you have not already done so.**</span></span> <span data-ttu-id="e0196-238">接続を完了する準備ができたら、[ **更新の完了** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0196-238">Select **Finish updating** when you are ready to complete the connection.</span></span>

## <a name="how-do-i-know-the-connection-setup-worked"></a><span data-ttu-id="e0196-239">接続セットアップが動作していることを確認するには、どうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="e0196-239">How do I know the connection setup worked?</span></span>

<span data-ttu-id="e0196-240">[管理センター](https://admin.microsoft.com)の [**コネクタ**] タブで、公開されている接続の一覧に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0196-240">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="e0196-241">更新と削除を行う方法については、「 [コネクタの管理](manage-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0196-241">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
