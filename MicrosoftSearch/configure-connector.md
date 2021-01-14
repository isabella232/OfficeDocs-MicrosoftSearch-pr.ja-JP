---
title: Microsoft Search 用に Microsoft が構築したコネクタを構成する
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
description: Microsoft Search 用に Microsoft が構築したコネクタを構成する
ms.openlocfilehash: 61a7d444ddc4c290b5098c327faa8e70f0ef1049
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847548"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a><span data-ttu-id="a66af-103">Microsoft による Graph コネクタのセットアップの概要</span><span class="sxs-lookup"><span data-stu-id="a66af-103">Setup overview for Graph connectors by Microsoft</span></span> 

<span data-ttu-id="a66af-104">この記事では [、Microsoft 365](https://admin.microsoft.com) 管理センターを使用して Microsoft が Graph コネクタをセットアップするために必要な基本的なプロセスを要約します。</span><span class="sxs-lookup"><span data-stu-id="a66af-104">This article summarizes the basic process required to use the [Microsoft 365 admin center](https://admin.microsoft.com) to setup any of the Graph connectors by Microsoft.</span></span> <span data-ttu-id="a66af-105">基本的なプロセスには、次の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a66af-105">The basic process includes the following steps:</span></span>  
<!---Add links to each section in the doc--->

1. <span data-ttu-id="a66af-106">Microsoft 365 管理センターで Graph コネクタを追加します。</span><span class="sxs-lookup"><span data-stu-id="a66af-106">Add a Graph connector in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="a66af-107">接続の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a66af-107">Name the connection.</span></span>
3. <span data-ttu-id="a66af-108">接続設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="a66af-108">Configure the connection settings.</span></span>
4. <span data-ttu-id="a66af-109">検索アクセス許可を管理します。</span><span class="sxs-lookup"><span data-stu-id="a66af-109">Manage search permissions.</span></span>
5. <span data-ttu-id="a66af-110">プロパティ ラベルを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a66af-110">Assign property labels.</span></span>
6. <span data-ttu-id="a66af-111">スキーマを管理します。</span><span class="sxs-lookup"><span data-stu-id="a66af-111">Manage schema.</span></span>
7. <span data-ttu-id="a66af-112">更新設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="a66af-112">Choose refresh settings.</span></span>
8. <span data-ttu-id="a66af-113">接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="a66af-113">Review the connection.</span></span>

<span data-ttu-id="a66af-114">セットアップ プロセスは、Microsoft のすべての Graph コネクタで非常に似ていますが、まったく同じではありません。</span><span class="sxs-lookup"><span data-stu-id="a66af-114">It is important to note that the setup process is very similar for all the Graph connectors by Microsoft but is not exactly the same.</span></span> <span data-ttu-id="a66af-115">**この記事を読むだけでなく、データ ソースのコネクタ固有の情報も必ずお読みください。**</span><span class="sxs-lookup"><span data-stu-id="a66af-115">**In addition to reading this article, be sure to read the connector-specific information for your data source.**</span></span>  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a66af-116">手順 1: Microsoft 365 管理センターで Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="a66af-116">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a66af-117">Microsoft が作成したコネクタを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a66af-117">Complete the following steps to configure any of the Microsoft-built connectors.</span></span>

1. <span data-ttu-id="a66af-118">[Microsoft 365 管理センターで管理者アカウントにサインインする](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="a66af-118">Sign into your admin account in the [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
2. <span data-ttu-id="a66af-119">ナビゲーション ウィンドウで、[設定] **を選択し**、[検索とインテリジェンス] **&します**。</span><span class="sxs-lookup"><span data-stu-id="a66af-119">In the navigation pane, select **Settings**, and then select **Search & intelligence**.</span></span> <span data-ttu-id="a66af-120">[コネクタ [] タブを選択します](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)。</span><span class="sxs-lookup"><span data-stu-id="a66af-120">Select the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).</span></span>
3. <span data-ttu-id="a66af-121">**[+追加]** を選択し、使用可能なオプションのメニューから選択したデータ ソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="a66af-121">Select **+Add**, and then select the data source of your choice from the menu of available options.</span></span>

![利用可能なデータ ソースは、ADLS Gen2、Enterprise Web サイト、Microsoft SQL サーバー、Azure SQL、Oracle SQL データベース、ServiceNow、ファイル共有、Azure DevOps、MediaWiki です。](media/add-connector.png)

><span data-ttu-id="a66af-123">[!注:] 各テナントに最大 10 個の Graph 接続を追加できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-123">[!Note:] You can add a maximum of ten Graph connections to each tenant.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="a66af-124">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="a66af-124">Step 2: Name the connection</span></span>
<span data-ttu-id="a66af-125">次の属性を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a66af-125">You will need to specify these attributes:</span></span> 

* <span data-ttu-id="a66af-126">名前</span><span class="sxs-lookup"><span data-stu-id="a66af-126">Name</span></span>  
* <span data-ttu-id="a66af-127">接続 ID</span><span class="sxs-lookup"><span data-stu-id="a66af-127">Connection ID</span></span> 
* <span data-ttu-id="a66af-128">説明 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a66af-128">Description (optional)</span></span> 

<span data-ttu-id="a66af-129">接続 ID は、コネクタの暗黙的なプロパティを作成します。</span><span class="sxs-lookup"><span data-stu-id="a66af-129">The connection ID creates implicit properties for your connector.</span></span> <span data-ttu-id="a66af-130">英数字のみを含む必要があります。最大 32 文字です。</span><span class="sxs-lookup"><span data-stu-id="a66af-130">It must contain only alphanumeric characters and be a maximum of 32 characters.</span></span> 

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="a66af-131">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a66af-131">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="a66af-132">接続設定を構成するプロセスは、データ ソースの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a66af-132">The process to configure the Connection settings varies based on the type of data source.</span></span> <span data-ttu-id="a66af-133">セットアップ プロセスでこの手順を完了するには、テナントに追加するデータ ソースの種類に関するコネクタ固有の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a66af-133">See the Connector-specific information for the type of data source you want to add to your tenant to complete this step in the setup process.</span></span>  

<span data-ttu-id="a66af-134">オンプレミスのデータ ソースへの接続の詳細については、「オンプレミス のデータ ゲートウェイをインストールする」 [を参照してください](https://aka.ms/configuregateway)。</span><span class="sxs-lookup"><span data-stu-id="a66af-134">To learn more about connecting to an on-premises data source, see [Install an on-premises data gateway](https://aka.ms/configuregateway).</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="a66af-135">手順 4: 検索権限を管理する</span><span class="sxs-lookup"><span data-stu-id="a66af-135">Step 4: Manage search permissions</span></span>

<span data-ttu-id="a66af-136">アクセス制御リスト (ACL) は、組織内のユーザーがデータの各アイテムにアクセスできるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="a66af-136">Access Control Lists (ACLs) determine which users in your organization can access each item of data.</span></span>  

<span data-ttu-id="a66af-137">Microsoft SQL [や](MSSQL-connector.md) Azure Data [Lake Storage Gen2](azure-data-lake-connector.md) のような一部のコネクタは [、Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) ACL をネイティブにサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a66af-137">Some connectors like [Microsoft SQL](MSSQL-connector.md) and [Azure Data Lake Storage Gen2](azure-data-lake-connector.md) natively support [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) ACLs.</span></span>

<span data-ttu-id="a66af-138">[ServiceNow、Azure DevOps、Salesforce](servicenow-connector.md)などの他[](salesforce-connector.md)のコネクタは、Azure 以外のユーザーとグループAD同期をサポートします。 [](azure-devops-connector.md)</span><span class="sxs-lookup"><span data-stu-id="a66af-138">Other connectors like [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md), and [Salesforce](salesforce-connector.md) support syncing of non-Azure AD users and groups.</span></span>  

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="a66af-139">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a66af-139">Step 5: Assign property labels</span></span>
<span data-ttu-id="a66af-140">セマンティック ラベルは、[プロパティ ラベルの割り当て] ページでソース プロパティに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="a66af-140">You can assign semantic labels to your source properties on the "Assign property labels" page.</span></span> <span data-ttu-id="a66af-141">ラベルは、意味を提供する Microsoft によって提供される既知のタグです。</span><span class="sxs-lookup"><span data-stu-id="a66af-141">Labels are well known tags provided by Microsoft that provide semantic meaning.</span></span> <span data-ttu-id="a66af-142">Microsoft は、拡張検索、ユーザー カード、インテリジェント検出などの Microsoft 365 エクスペリエンスにコネクタ データを統合できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-142">They allow Microsoft to integrate your connector data into Microsoft 365 experiences such as enhanced search, people cards, intelligent discovery, and more.</span></span>  

<span data-ttu-id="a66af-143">次の表に、現在サポートされているラベルとその説明を示します。</span><span class="sxs-lookup"><span data-stu-id="a66af-143">The following table lists the currently supported labels and their descriptions.</span></span>  

<span data-ttu-id="a66af-144">ラベル</span><span class="sxs-lookup"><span data-stu-id="a66af-144">Label</span></span> | <span data-ttu-id="a66af-145">説明</span><span class="sxs-lookup"><span data-stu-id="a66af-145">Description</span></span>
--- | ---  
<span data-ttu-id="a66af-146">**title**</span><span class="sxs-lookup"><span data-stu-id="a66af-146">**title**</span></span> | <span data-ttu-id="a66af-147">検索やその他のエクスペリエンスに表示するアイテムのタイトル</span><span class="sxs-lookup"><span data-stu-id="a66af-147">The title for the item that you want shown in search and other experiences</span></span> 
<span data-ttu-id="a66af-148">**url**</span><span class="sxs-lookup"><span data-stu-id="a66af-148">**url**</span></span> | <span data-ttu-id="a66af-149">ソース システム内のアイテムのターゲット URL</span><span class="sxs-lookup"><span data-stu-id="a66af-149">The target url of the item in the source system</span></span> 
<span data-ttu-id="a66af-150">**createdBy**</span><span class="sxs-lookup"><span data-stu-id="a66af-150">**createdBy**</span></span> | <span data-ttu-id="a66af-151">アイテムを作成したユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="a66af-151">Name of the person who created the item</span></span> 
<span data-ttu-id="a66af-152">**lastModifiedBy**</span><span class="sxs-lookup"><span data-stu-id="a66af-152">**lastModifiedBy**</span></span> | <span data-ttu-id="a66af-153">アイテムを最近編集したユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="a66af-153">Name of the person who most recently edited the item</span></span> 
<span data-ttu-id="a66af-154">**authors**</span><span class="sxs-lookup"><span data-stu-id="a66af-154">**authors**</span></span> | <span data-ttu-id="a66af-155">アイテムに参加/共同作業を行ったユーザーの名前</span><span class="sxs-lookup"><span data-stu-id="a66af-155">Name of the people who participated/collaborated on the item</span></span> 
<span data-ttu-id="a66af-156">**createdDateTime**</span><span class="sxs-lookup"><span data-stu-id="a66af-156">**createdDateTime**</span></span> | <span data-ttu-id="a66af-157">アイテムが作成されたのはいつか</span><span class="sxs-lookup"><span data-stu-id="a66af-157">When was the item created</span></span> 
<span data-ttu-id="a66af-158">**lastModifiedDateTime**</span><span class="sxs-lookup"><span data-stu-id="a66af-158">**lastModifiedDateTime**</span></span> | <span data-ttu-id="a66af-159">アイテムが最近編集されたのはいつか</span><span class="sxs-lookup"><span data-stu-id="a66af-159">When was the item most recently edited</span></span> 
<span data-ttu-id="a66af-160">**fileName**</span><span class="sxs-lookup"><span data-stu-id="a66af-160">**fileName**</span></span> | <span data-ttu-id="a66af-161">ファイル アイテムの名前</span><span class="sxs-lookup"><span data-stu-id="a66af-161">Name of the file item</span></span> 
<span data-ttu-id="a66af-162">**FileExtension**</span><span class="sxs-lookup"><span data-stu-id="a66af-162">**fileExtension**</span></span> | <span data-ttu-id="a66af-163">.pdf や .word などのファイルアイテムの種類</span><span class="sxs-lookup"><span data-stu-id="a66af-163">Type of file item such as .pdf or .word</span></span> 

<span data-ttu-id="a66af-164">このページのプロパティは、データ ソースに基づいて事前に選択されますが、特定のラベルに適した別のプロパティがある場合は、この選択を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-164">The properties on this page are pre-selected based on your data source, but you can change this selection if there is a different property that is better suited for a particular label.</span></span>  

<span data-ttu-id="a66af-165">ラベルの **タイトルは** 最も重要なラベルです。</span><span class="sxs-lookup"><span data-stu-id="a66af-165">The label **title** is the most important label.</span></span> <span data-ttu-id="a66af-166">接続が **結果クラスター エクスペリエンス** に参加するには、このラベルにプロパティが割り当てられている必要 [があります。](result-cluster.md)</span><span class="sxs-lookup"><span data-stu-id="a66af-166">It is **strongly recommended** that you have a property assigned to this label in order for your connection to participate in the [result cluster experience](result-cluster.md).</span></span>

<span data-ttu-id="a66af-167">ラベルを正しくマッピングしないと、検索エクスペリエンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="a66af-167">Incorrectly mapping labels will cause a deteriorated search experience.</span></span> <span data-ttu-id="a66af-168">一部のラベルにはプロパティが割り当てられていない場合でも問題ありません。</span><span class="sxs-lookup"><span data-stu-id="a66af-168">It is okay for some labels to not have a property assigned to it.</span></span>  

## <a name="step-6-manage-schema"></a><span data-ttu-id="a66af-169">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="a66af-169">Step 6: Manage schema</span></span>

### <a name="content-property"></a><span data-ttu-id="a66af-170">Content プロパティ</span><span class="sxs-lookup"><span data-stu-id="a66af-170">Content property</span></span>

<span data-ttu-id="a66af-171">オプションのドロップダウン メニューから [コンテンツ プロパティ] を選択するか、存在する場合は既定値のままにしてください。</span><span class="sxs-lookup"><span data-stu-id="a66af-171">It is strongly recommended that you select a \*\*Content Property" from the drop-down menu of options, or keep the default if one is present.</span></span> <span data-ttu-id="a66af-172">このプロパティは、コンテンツのフルテキスト インデックス作成、検索結果ページ スニペットの生成、 [結果クラスター](result-cluster.md) への参加、言語検出、HTML/テキストのサポート、ランク付けと関連性、クエリの生成に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a66af-172">This property is used for full-text indexing of content, search results page snippet generation, [result cluster](result-cluster.md) participation, language detection, HTML/text support, ranking and relevance, and query formulation.</span></span>

<span data-ttu-id="a66af-173">コンテンツ プロパティを選択すると、結果の種類を作成するときに、システム生成プロパティ **ResultSnippet** [を使用できます](customize-results-layout.md)。</span><span class="sxs-lookup"><span data-stu-id="a66af-173">If you select a content property, you will have the option of using the system-generated property **ResultSnippet** when you [create your result type](customize-results-layout.md).</span></span> <span data-ttu-id="a66af-174">このプロパティは、クエリ時にコンテンツ プロパティから生成される動的スニペットのプレースホルダーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="a66af-174">This property serves as a placeholder for the dynamic snippets that are generated from the content property at query time.</span></span> <span data-ttu-id="a66af-175">このプロパティを結果の種類で使用すると、検索結果にスニペットが生成されます。</span><span class="sxs-lookup"><span data-stu-id="a66af-175">If you use this property in your result type, snippets will be generated in your search results.</span></span>

### <a name="creating-aliases-for-source-properties"></a><span data-ttu-id="a66af-176">ソース プロパティのエイリアスの作成</span><span class="sxs-lookup"><span data-stu-id="a66af-176">Creating aliases for source properties</span></span>

<span data-ttu-id="a66af-177">[スキーマの管理] ページの [エイリアス] 列で、プロパティにエイリアスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-177">You can add aliases to your properties under the "Alias" column on the "Manage schema" page.</span></span> <span data-ttu-id="a66af-178">エイリアスは、プロパティの表示名です。</span><span class="sxs-lookup"><span data-stu-id="a66af-178">Aliases are friendly names for your properties.</span></span> <span data-ttu-id="a66af-179">クエリやフィルターの作成で使用されます。</span><span class="sxs-lookup"><span data-stu-id="a66af-179">They are used in queries and in the creation of filters.</span></span> <span data-ttu-id="a66af-180">また、同じ名前を持つ複数の接続からソース プロパティを正規化するためにも使用されます。</span><span class="sxs-lookup"><span data-stu-id="a66af-180">They are also used to normalize source properties from multiple connections such that they have the same name.</span></span> <span data-ttu-id="a66af-181">この方法で、複数の接続を持つ垂直に対して 1 つのフィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-181">That way you can create a single filter for a vertical with multiple connections.</span></span> <span data-ttu-id="a66af-182">詳細 [については、「検索結果のカスタマイズ」ページ](customize-search-page.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a66af-182">See [Customize the search results page](customize-search-page.md) for more information.</span></span>  

### <a name="search-schema-attributes"></a><span data-ttu-id="a66af-183">検索スキーマの属性</span><span class="sxs-lookup"><span data-stu-id="a66af-183">Search schema attributes</span></span>

<span data-ttu-id="a66af-184">検索スキーマ属性を設定して、各ソース プロパティの検索機能を制御できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-184">You can set the search schema attributes to control search functionality of each source property.</span></span> <span data-ttu-id="a66af-185">検索スキーマは、検索結果ページに表示される結果と、エンド ユーザーが表示およびアクセスできる情報を決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a66af-185">A search schema helps determine what results display on the search results page and what information end users can view and access.</span></span>

<span data-ttu-id="a66af-186">検索スキーマの属性には **、検索可能、\*\*\*\*クエリ可能、\*\*\*\*取得可能、** 絞り込み **可能な属性が含まれます**。</span><span class="sxs-lookup"><span data-stu-id="a66af-186">Search schema attributes include **searchable**, **queryable**, **retrievable**, and **refinable**.</span></span> <span data-ttu-id="a66af-187">次の表に、Microsoft Graph コネクタがサポートする各属性とその機能を示します。</span><span class="sxs-lookup"><span data-stu-id="a66af-187">The following table lists each of the attributes that Microsoft Graph connectors support and explains their functions.</span></span>

<span data-ttu-id="a66af-188">検索スキーマ属性</span><span class="sxs-lookup"><span data-stu-id="a66af-188">Search schema attribute</span></span> | <span data-ttu-id="a66af-189">関数</span><span class="sxs-lookup"><span data-stu-id="a66af-189">Function</span></span> | <span data-ttu-id="a66af-190">例</span><span class="sxs-lookup"><span data-stu-id="a66af-190">Example</span></span>
--- | --- | ---
<span data-ttu-id="a66af-191">SEARCHABLE</span><span class="sxs-lookup"><span data-stu-id="a66af-191">SEARCHABLE</span></span> | <span data-ttu-id="a66af-192">プロパティのテキスト コンテンツを検索可能にする。</span><span class="sxs-lookup"><span data-stu-id="a66af-192">Makes the text content of a property searchable.</span></span> <span data-ttu-id="a66af-193">プロパティの内容は、フルテキスト インデックスに含まれます。</span><span class="sxs-lookup"><span data-stu-id="a66af-193">Property contents are included in the full-text index.</span></span> | <span data-ttu-id="a66af-194">プロパティが title **の場合**、 **エンタープライズ** のクエリは、任意のテキストまたはタイトルに **Enterprise** という単語を含む回答を返します。</span><span class="sxs-lookup"><span data-stu-id="a66af-194">If the property is **title**, a query for **Enterprise** returns answers that contain the word **Enterprise** in any text or title.</span></span>
<span data-ttu-id="a66af-195">QUERYABLE</span><span class="sxs-lookup"><span data-stu-id="a66af-195">QUERYABLE</span></span> | <span data-ttu-id="a66af-196">特定のプロパティの一致をクエリで検索します。</span><span class="sxs-lookup"><span data-stu-id="a66af-196">Searches by query for a match for a particular property.</span></span> <span data-ttu-id="a66af-197">その後、クエリでプログラムまたは動詞を使用してプロパティ名を指定できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-197">The property name can then be specified in the query either programmatically or verbatim.</span></span> |  <span data-ttu-id="a66af-198">Title プロパティ **がクエリ** 可能な場合、クエリ **Title: Enterprise** がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a66af-198">If the **Title** property is queryable, then the query **Title: Enterprise** is supported.</span></span> 
<span data-ttu-id="a66af-199">取得可能</span><span class="sxs-lookup"><span data-stu-id="a66af-199">RETRIEVABLE</span></span> | <span data-ttu-id="a66af-200">検索結果の種類で使用できるのは、取得可能なプロパティのみであり、検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="a66af-200">Only retrievable properties can be used in the result type and display in the search result.</span></span> |
<span data-ttu-id="a66af-201">絞り込み可能</span><span class="sxs-lookup"><span data-stu-id="a66af-201">REFINABLE</span></span> | <span data-ttu-id="a66af-202">絞り込み可能なプロパティは、Microsoft Search の結果ページで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-202">Refinable properties can be used as in the Microsoft Search results page.</span></span> | <span data-ttu-id="a66af-203">接続のセットアップ中に [](custom-filters.md)プロパティが絞り込み可能とマークされている場合、組織内のユーザーは検索結果ページで **lastModifiedDateTime** でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-203">Users in your organization can [filter](custom-filters.md) by **lastModifiedDateTime** in the search results page if the property is marked refinable during connection setup</span></span>

<span data-ttu-id="a66af-204">ファイル共有コネクタを除くすべてのコネクタでは、カスタム型を手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a66af-204">For all connectors except the File share connector, custom types must be set manually.</span></span> <span data-ttu-id="a66af-205">各フィールドの検索機能をアクティブにするには、プロパティのリストにマップされた検索スキーマが必要です。</span><span class="sxs-lookup"><span data-stu-id="a66af-205">To activate search capabilities for each field, you need a search schema mapped to a list of properties.</span></span> <span data-ttu-id="a66af-206">接続ウィザードは、選択したソース プロパティのセットに基づいて検索スキーマを自動的に選択します。</span><span class="sxs-lookup"><span data-stu-id="a66af-206">The connection wizard automatically selects a search schema based on the set of source properties you choose.</span></span> <span data-ttu-id="a66af-207">このスキーマを変更するには、検索スキーマ ページの各プロパティと属性のチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a66af-207">You can modify this schema by selecting the check boxes for each property and attribute in the search schema page.</span></span>

![コネクタのスキーマは、クエリ関数、検索関数、および取得関数を追加または削除することでカスタマイズできます。](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a><span data-ttu-id="a66af-209">検索スキーマ設定の制限事項と推奨事項</span><span class="sxs-lookup"><span data-stu-id="a66af-209">Restrictions and recommendations for search schema settings</span></span>

* <span data-ttu-id="a66af-210">コンテンツ **プロパティ** は検索のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="a66af-210">The **content** property is searchable only.</span></span> <span data-ttu-id="a66af-211">ドロップダウンで選択すると、このプロパティを取得可能またはクエリ可能 **と** マーク **することはできません**。</span><span class="sxs-lookup"><span data-stu-id="a66af-211">Once selected in the dropdown, this property cannot be marked **retrievable** or **queryable**.</span></span>

* <span data-ttu-id="a66af-212">コンテンツ プロパティを使用して検索結果が表示される場合、パフォーマンスに重大な問題 **が発生** します。</span><span class="sxs-lookup"><span data-stu-id="a66af-212">Significant performance issues occur when search results render with the **content** property.</span></span> <span data-ttu-id="a66af-213">たとえば [、ServiceNow](https://www.servicenow.com) **ナレッジ** ベースの記事のテキスト コンテンツ フィールドがあります。</span><span class="sxs-lookup"><span data-stu-id="a66af-213">An example is the **Text** content field for a [ServiceNow](https://www.servicenow.com) knowledge-base article.</span></span>

* <span data-ttu-id="a66af-214">検索結果で取得可能とマークされているプロパティのみ、モダン検索結果の種類 (MRT) の作成に使用できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-214">Only properties marked as retrievable render in the search results and can be used to create modern result types (MRTs).</span></span>

* <span data-ttu-id="a66af-215">検索可能とマークできるのは文字列プロパティのみです。</span><span class="sxs-lookup"><span data-stu-id="a66af-215">Only string properties can be marked searchable.</span></span>

> [!NOTE]
> <span data-ttu-id="a66af-216">接続を作成した後は **、スキーマを** 変更できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-216">After you create a connection, you **can't** modify the schema.</span></span> <span data-ttu-id="a66af-217">これを行うには、接続を削除し、新しい接続を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a66af-217">To do that, you need to delete your connection and create a new one.</span></span>

## <a name="step-7-refresh-settings"></a><span data-ttu-id="a66af-218">手順 7: 設定を更新する</span><span class="sxs-lookup"><span data-stu-id="a66af-218">Step 7: Refresh settings</span></span>

<span data-ttu-id="a66af-219">更新間隔は、データ ソースと Microsoft Search の間でデータが同期される頻度を決定します。</span><span class="sxs-lookup"><span data-stu-id="a66af-219">The refresh interval determines how often your data is synced between the data source and Microsoft Search.</span></span> <span data-ttu-id="a66af-220">データ ソースの種類ごとに、データの変更頻度と変更の種類に基づいて、最適な更新スケジュールのセットが異なります。</span><span class="sxs-lookup"><span data-stu-id="a66af-220">Each type of data source has a different set of optimal refresh schedules based on how often data is modified and the type of modifications.</span></span>

<span data-ttu-id="a66af-221">更新間隔には、完全更新と増分更新の2種類がありますが、一部のデータ ソースでは増分更新を使用できません。</span><span class="sxs-lookup"><span data-stu-id="a66af-221">There are two types of refresh intervals, which are **Full refresh** and **Incremental refresh**, but incremental refreshes are not available for some data sources.</span></span>

<span data-ttu-id="a66af-222">完全な更新では、検索エンジンは、以前のクロールに関係なく、コンテンツ ソース内のすべてのアイテムを処理し、インデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="a66af-222">With a full refresh, the search engine processes and indexes every item in the content source, regardless of previous crawls.</span></span> <span data-ttu-id="a66af-223">完全な更新は、次の状況に最適です。</span><span class="sxs-lookup"><span data-stu-id="a66af-223">A full refresh works best for these situations:</span></span>

* <span data-ttu-id="a66af-224">データの削除を検出する。</span><span class="sxs-lookup"><span data-stu-id="a66af-224">Detecting deletions of data.</span></span>
* <span data-ttu-id="a66af-225">エラーが原因で、増分更新でコンテンツの更新に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="a66af-225">The incremental refresh failed to update content due to errors.</span></span>
* <span data-ttu-id="a66af-226">ACL が変更されました。</span><span class="sxs-lookup"><span data-stu-id="a66af-226">ACLs were modified.</span></span>
* <span data-ttu-id="a66af-227">クロール ルールが変更されました。</span><span class="sxs-lookup"><span data-stu-id="a66af-227">Crawl rules were modified.</span></span>
* <span data-ttu-id="a66af-228">接続のスキーマが更新された場合 (スキーマの更新はまだサポートされていません)</span><span class="sxs-lookup"><span data-stu-id="a66af-228">When schema for the connection has been updated (schema updates are not yet supported)</span></span>

<span data-ttu-id="a66af-229">増分更新 **では、** 検索エンジンは前回成功したクロール以降に作成または変更されたアイテムのみを処理してインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-229">With an **Incremental refresh**, the search engine can process and index only the items that were created or modified since the last successful crawl.</span></span> <span data-ttu-id="a66af-230">したがって、コンテンツ ソース内のすべてのデータのインデックスが再作成されるのではありません。</span><span class="sxs-lookup"><span data-stu-id="a66af-230">Therefore, not all the data in the content source is re-indexed.</span></span> <span data-ttu-id="a66af-231">増分更新は、コンテンツ、メタデータ、アクセス許可、その他の更新を検出する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="a66af-231">Incremental refreshes work best to detect content, metadata, permission, and other updates.</span></span>

<span data-ttu-id="a66af-232">変更されていないアイテムは処理されないので、増分更新は完全な更新よりもずっと高速です。</span><span class="sxs-lookup"><span data-stu-id="a66af-232">Incremental refreshes are much faster than full refreshes because unchanged items aren’t processed.</span></span> <span data-ttu-id="a66af-233">ただし、増分更新を実行する場合でも、コンテンツ ソースと検索インデックスの間の正確なデータ同期を維持するために、定期的に完全な更新を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a66af-233">However, if you choose to run incremental refreshes, you will still need to run full refreshes periodically to maintain an accurate data sync between the content source and the search index.</span></span>

![増分クロールとフル クロールの間隔の設定で、[15 分の増分] と [1 週間のフル クロール] が表示されます。](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a><span data-ttu-id="a66af-235">手順 8: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="a66af-235">Step 8: Review connection</span></span>

<span data-ttu-id="a66af-236">接続を完了する前に、必要に応じて構成全体を確認し、設定を編集できます。</span><span class="sxs-lookup"><span data-stu-id="a66af-236">You can review your entire configuration and edit settings as needed before completing the connection.</span></span> <span data-ttu-id="a66af-237">**データ ソースのコネクタ固有の情報をまだ読み込んでいなき場合は、必ずお読みください。**</span><span class="sxs-lookup"><span data-stu-id="a66af-237">**Be sure to read the connector-specific information for your data source if you have not already done so.**</span></span> <span data-ttu-id="a66af-238">接続 **を完了する準備ができたら** 、[更新の完了] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a66af-238">Select **Finish updating** when you are ready to complete the connection.</span></span>

## <a name="how-do-i-know-the-connection-setup-worked"></a><span data-ttu-id="a66af-239">接続セットアップの動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="a66af-239">How do I know the connection setup worked?</span></span>

<span data-ttu-id="a66af-240">管理センターの [コネクタ] タブで、公開されている接続の一覧に[移動します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a66af-240">Go to the list of your published connections under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="a66af-241">更新と削除を行う方法については、「コネクタの管理」 [を参照してください](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="a66af-241">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>
