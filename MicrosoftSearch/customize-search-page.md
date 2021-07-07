---
title: Microsoft Search ページをカスタマイズする
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 検索カテゴリを追加し、検索結果をカスタマイズする
ms.openlocfilehash: 6b6f0593a668e9c2c5c7fc5a62f7b5dd4a43a8bb
ms.sourcegitcommit: ea6905626de67090141039565282e4e0c53b43ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314021"
---
# <a name="customize-the-search-results-page"></a><span data-ttu-id="57b04-103">検索結果ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="57b04-103">Customize the search results page</span></span>

<span data-ttu-id="57b04-104">検索カテゴリと結果タイプを作成して、ユーザーが Microsoft [SharePoint](https://sharepoint.com/)、[Microsoft Office](https://office.com)、および [Bing](https://bing.com) の Microsoft Search で検索したときに表示される検索結果をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="57b04-104">You can create search verticals and result types to customize the search results that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="57b04-105">バーティカルを使用すると、ユーザーは表示を許可されている情報を簡単に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="57b04-105">Verticals make it easier for users to find the information that they have permission to see.</span></span> <span data-ttu-id="57b04-106">たとえば、マーケティング部門のユーザー向けに、サードパーティ ソフトウェアからのマーケティング分析データの検索カテゴリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-106">For example, you could create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="57b04-107">結果の種類を定義し、このデータのレイアウトをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="57b04-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="57b04-108">次のレベルで、バーティカルと結果タイプを作成できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-108">You can create verticals and result types at these levels:</span></span>

- <span data-ttu-id="57b04-109">**組織レベル** – 組織レベルで業種を追加することで、ユーザーが [SharePoint](https://sharepoint.com/) スタートページ、[Office](https://office.com)、または [Bing](https://bing.com) から検索すると、検索結果ページに表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="57b04-109">**Organization level** – When you add a vertical at the organization level, it appears on the search results page when users search from their [SharePoint](https://sharepoint.com/) start page, on [Office](https://office.com), or on [Bing](https://bing.com).</span></span>
- <span data-ttu-id="57b04-110">**サイトレベル** – たとえば、カスタマーサービスの従業員が部門の SharePoint サイトから直接、*重大度 1* のインシデントを検索できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="57b04-110">**Site level** – For example, you might want to enable your customer service employees to search for *Severity 1* incidents directly from their department’s SharePoint site.</span></span>

## <a name="search-verticals-explained"></a><span data-ttu-id="57b04-111">検索バーティカルの説明</span><span class="sxs-lookup"><span data-stu-id="57b04-111">Search verticals explained</span></span>

<span data-ttu-id="57b04-112">Microsoft Search 結果ページの上部には、タブが表示される行があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-112">At the top of the Microsoft Search results page, there's a row of tabs.</span></span> <span data-ttu-id="57b04-113">これらは検索バーティカルです。</span><span class="sxs-lookup"><span data-stu-id="57b04-113">These are the search verticals.</span></span> <span data-ttu-id="57b04-114">検索バーティカルには、特定のタイプまたは特定のコンテンツの結果のみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-114">A search vertical only shows results of a certain type or from certain content.</span></span> <span data-ttu-id="57b04-115">例として、**ファイル** または **ニュース** があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-115">Examples are **Files** or **News**.</span></span> <span data-ttu-id="57b04-116">既定では、Microsoft Search には、[**すべて**]、[**人物**]、[**ファイル**]、[**サイト**]、および [**ニュース**] のカテゴリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-116">By default, Microsoft Search shows the verticals **All**, **People**, **Files**, **Sites**, and **News**.</span></span>  

<span data-ttu-id="57b04-117">組織に関連する検索カテゴリを追加できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-117">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="57b04-118">これらの結果は、[SharePoint](https://sharepoint.com/)、[Office](https://Office.com)、[Bing](https://bing.com) の Microsoft Search 結果ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-118">These will appear on the Microsoft Search results page in [SharePoint](https://sharepoint.com/), [Office](https://Office.com), and [Bing](https://bing.com).</span></span> <span data-ttu-id="57b04-119">たとえば、各グループが必要とする情報のタイプに基づいて、マーケティング関連のコンテンツ用のバーティカルと販売用のバーティカルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-119">For example, you could create a vertical for marketing-related content and another for sales, based on the type of information that each group needs.</span></span> <span data-ttu-id="57b04-120">バーティカルを追加して、コネクタを介してインデックス付けされたコンテンツからの結果のみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-120">You can add verticals to show results only from content indexed via connectors.</span></span>  

### <a name="multiple-connections-in-a-vertical"></a><span data-ttu-id="57b04-121">垂直の複数の接続</span><span class="sxs-lookup"><span data-stu-id="57b04-121">Multiple connections in a vertical</span></span>

<span data-ttu-id="57b04-122">複数のコネクタ ソースからの検索結果を垂直方向の検索で表示できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-122">A search vertical can now surface results from multiple connector sources.</span></span> <span data-ttu-id="57b04-123">これにより、検索結果ページを設計する柔軟性が向上します。</span><span class="sxs-lookup"><span data-stu-id="57b04-123">This provides greater flexibility in designing your search result page.</span></span> <span data-ttu-id="57b04-124">垂直セットアップの既存の管理エクスペリエンスでは、"コンテンツ ソース" ステップで複数の接続を選択できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-124">The existing administrative experience of vertical setup allows you to select multiple connections in the "Content Source" step.</span></span>
<span data-ttu-id="57b04-125">可能な限り多くのセマンティック ラベルを正確に任命すると、このエクスペリエンスが強化されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-125">If you accurately appoint as many semantic labels as possible, this experience will be enhanced.</span></span> <span data-ttu-id="57b04-126">スキーマの定義と取り込み時にセマンティック ラベルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-126">You can add semantic labels upon schema definition and ingestion.</span></span>

<span data-ttu-id="57b04-127">[セ](configure-connector.md#step-5-assign-property-labels) マンティック ラベルを作成および管理する方法に関する追加情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="57b04-127">[Here](configure-connector.md#step-5-assign-property-labels) is additional information on how to create and manage semantic labels.</span></span>

> [!NOTE]
> <span data-ttu-id="57b04-128">垂直の複数の接続が現在プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="57b04-128">Multiple connections in a vertical is currently in preview.</span></span> <span data-ttu-id="57b04-129">プレビューの詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。</span><span class="sxs-lookup"><span data-stu-id="57b04-129">For more information about preview, see [Connectors preview features](connectors-overview.md#what-are-the-preview-features).</span></span>

### <a name="things-you-should-know"></a><span data-ttu-id="57b04-130">知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-130">Things you should know</span></span>

1. <span data-ttu-id="57b04-131">接続は、1 つの垂直の下でのみコンテンツ ソースとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-131">A connection can be added as a content source only under one vertical.</span></span> <span data-ttu-id="57b04-132">複数の垂直で接続を再利用できません。</span><span class="sxs-lookup"><span data-stu-id="57b04-132">Reusing connections under multiple verticals is not allowed.</span></span>
2. <span data-ttu-id="57b04-133">複数の接続ソースが追加されている検索バーティカルのクエリを設定する必要がある場合は、一般的なソース プロパティを使用してこのようなクエリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-133">If you need to set up a query for a search vertical where multiple connection sources have been added, common source properties should be used to create a such a query.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="57b04-134">考慮事項</span><span class="sxs-lookup"><span data-stu-id="57b04-134">Things to consider</span></span>

<span data-ttu-id="57b04-135">開始する前に、コネクタにインデックスが付けられていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="57b04-135">Before you start, make sure that the connector has been indexed.</span></span> <span data-ttu-id="57b04-136">ファイルサイズによって、これには最大48時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-136">This can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="57b04-137">[SharePoint](https://sharepoint.com/) に存在するコンテンツのバーティカルを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="57b04-137">You can’t create a vertical for content that resides in [SharePoint](https://sharepoint.com/).</span></span>

<span data-ttu-id="57b04-138">バーティカルを追加するには、次の3つの基本的な手順があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-138">There are three basic steps to add a vertical:</span></span>

1. <span data-ttu-id="57b04-139">バーティカルを作成します。</span><span class="sxs-lookup"><span data-stu-id="57b04-139">Create the vertical.</span></span> <span data-ttu-id="57b04-140">このステップでは、検索するコンテンツのバーティカルの名前、コンテンツソース、および範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="57b04-140">In this step, you define the vertical’s name, content source, and scope of the content to search.</span></span>
2. <span data-ttu-id="57b04-141">このバーティカルの結果がどのようになるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="57b04-141">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="57b04-142">バーティカル リストページからバーティカル (表示する) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="57b04-142">Enable the vertical (to be displayed) from the vertical list page.</span></span>

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="57b04-143">手順 1: 検索バーティカルを作成する</span><span class="sxs-lookup"><span data-stu-id="57b04-143">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="57b04-144">ウィザードを開始すると、業種の名前、コンテンツソース、および検索するコンテンツの範囲を定義する手順がガイドされます。</span><span class="sxs-lookup"><span data-stu-id="57b04-144">After you start the wizard, you're guided through the steps to define the vertical's name, content source, and scope of the content to search.</span></span> <span data-ttu-id="57b04-145">バーティカルは無効な状態で作成されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-145">The vertical is created in a disabled state.</span></span> <span data-ttu-id="57b04-146">後ほど有効にします。</span><span class="sxs-lookup"><span data-stu-id="57b04-146">You'll enable it later.</span></span>

<span data-ttu-id="57b04-147">限定された[キーワードクエリ言語 (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) のセットを使用して、範囲を狭めることができます。</span><span class="sxs-lookup"><span data-stu-id="57b04-147">You can use a limited set of [Keyword Query Language (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow the scope.</span></span> <span data-ttu-id="57b04-148">このページには、利用可能なプロパティが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-148">This page lists the properties that are available.</span></span> <span data-ttu-id="57b04-149">KQL を作成するには、ブール演算子と一緒にフリーテキスト キーワードとプロパティ制限を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57b04-149">We recommend that you use free-text keywords and property restrictions with boolean operators for creating the KQL.</span></span>
<span data-ttu-id="57b04-150">KQL では、プロファイル クエリ [変数を使用](#profile-query-variables) して垂直方向の結果を微調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="57b04-150">KQL also supports the use of [profile query variables](#profile-query-variables) to fine-tune results under the vertical.</span></span>

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="57b04-151">組織レベルで業種を作成する</span><span class="sxs-lookup"><span data-stu-id="57b04-151">Create a vertical at the organization level</span></span>

<span data-ttu-id="57b04-152">[SharePoint](https://sharepoint.com/) ホーム、[Office](https://office.com)、または[Bing](https://bing.com)で Microsoft Search にカテゴリを作成するには、次の手順を実行します。 </span><span class="sxs-lookup"><span data-stu-id="57b04-152">To create the vertical on Microsoft Search in [SharePoint](https://sharepoint.com/) home, [Office](https://office.com), or [Bing](https://bing.com), follow these steps:</span></span>

1. <span data-ttu-id="57b04-153">[バーティ [Microsoft 365 管理センター](https://admin.microsoft.com)に [**移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)。</span><span class="sxs-lookup"><span data-stu-id="57b04-153">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="57b04-154">[追加 **] を** 選択して開始します。</span><span class="sxs-lookup"><span data-stu-id="57b04-154">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="57b04-155">サイトレベルでカテゴリを作成する</span><span class="sxs-lookup"><span data-stu-id="57b04-155">Create a vertical at the site level</span></span>

1. <span data-ttu-id="57b04-156">バーティカルにする [SharePoint](https://sharepoint.com/) サイトで、**[設定]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="57b04-156">On the [SharePoint](https://sharepoint.com/) site where you want the vertical, go to **Settings**.</span></span>
2. <span data-ttu-id="57b04-157">[**サイト情報**]、[**すべてのサイト設定を表示**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="57b04-157">Select **Site information** and then **View all site settings**.</span></span>
3. <span data-ttu-id="57b04-158">**[Microsoft Search]** セクションを探し、**[このサイトコレクションの Microsoft 検索の構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="57b04-158">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="57b04-159">ナビゲーション ウィンドウで、[カスタム エクスペリエンス] **に移動** し、[垂直] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="57b04-159">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
5. <span data-ttu-id="57b04-160">垂直を追加するには、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="57b04-160">To add a vertical, select **Add**.</span></span>
  <span data-ttu-id="57b04-161">または、バーティカルを編集するには、リストから業種を選択します。</span><span class="sxs-lookup"><span data-stu-id="57b04-161">Or, to edit a vertical, select it in the list.</span></span>

<span data-ttu-id="57b04-162">バーティカルは無効な状態で作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="57b04-162">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="57b04-163">ユーザーに表示する前に、これらを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-163">They must be enabled before users can see them.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="57b04-164">ステップ 2: 検索結果の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="57b04-164">STEP 2: Create the result types</span></span>

<span data-ttu-id="57b04-165">検索結果の種類を使用してレイアウトをデザインすることにより、検索結果がバーティカルにどのように表示されるかを定義できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-165">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="57b04-166">結果のレイアウトを使用すると、重要な情報を検索結果に直接表示できるため、ユーザーはユーザーは各結果を選択して、探しているものが見つかったかどうかを確認する必要がありません。</span><span class="sxs-lookup"><span data-stu-id="57b04-166">The result layout lets you show important information directly in the search results, so users don't have to select each result to see if they found what they're looking for.</span></span>

### <a name="default-search-result-layout"></a><span data-ttu-id="57b04-167">既定の検索結果レイアウト</span><span class="sxs-lookup"><span data-stu-id="57b04-167">Default search result layout</span></span>

<span data-ttu-id="57b04-168">コネクタの構成時にラベルとコンテンツ プロパティがソースプロパティに正しくマップされている場合、Connector コンテンツの既定の検索結果レイアウトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-168">A default search result layout will be shown for Connector content if **labels** and **content** property have been mapped correctly to the source properties at the time of configuring the connector.</span></span> <span data-ttu-id="57b04-169">ラベル タイトル **は、** 最も重要なラベルです。</span><span class="sxs-lookup"><span data-stu-id="57b04-169">The label **title** is the most important label.</span></span> <span data-ttu-id="57b04-170">既定の **検索結果レイアウトを** 使用するには、このラベルにプロパティが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-170">It is **strongly recommended** that you have a property assigned to this label to use default search result layout.</span></span>

### <a name="create-your-own-result-type"></a><span data-ttu-id="57b04-171">独自の結果の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="57b04-171">Create your own result type</span></span>

<span data-ttu-id="57b04-172">独自の検索結果レイアウトを作成し、結果の種類を作成して既定の検索結果レイアウトを上書 **きすることができます**。</span><span class="sxs-lookup"><span data-stu-id="57b04-172">You can decide to create your own search result layout and override the default search result layout by creating a **result type**.</span></span> <span data-ttu-id="57b04-173">検索結果の種類とは、検索結果のタイプの違いに応じて表示方法を変えるルールのことです。</span><span class="sxs-lookup"><span data-stu-id="57b04-173">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways.</span></span> <span data-ttu-id="57b04-174">このルールは、次のような構成になっています。</span><span class="sxs-lookup"><span data-stu-id="57b04-174">It consists of the following:</span></span>

- <span data-ttu-id="57b04-175">検索結果のコンテンツソースなど、各検索結果を比較するための **1 つ以上の条件**。</span><span class="sxs-lookup"><span data-stu-id="57b04-175">**One or more conditions** to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="57b04-176">条件を満たす検索結果に使用する **結果レイアウト**。</span><span class="sxs-lookup"><span data-stu-id="57b04-176">A **result layout** to use for search results that meet the conditions.</span></span> <span data-ttu-id="57b04-177">結果のレイアウトは、条件を満たすすべての結果が検索結果ページに表示および動作する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="57b04-177">The resulting layout controls the way that all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="57b04-178">**既定の検索結果レイアウトを表示するために適切なマッピングが行われない場合は、垂直方向に表示する結果の種類を少なくとも 1 つ作成する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="57b04-178">**If appropriate mapping is not done to show default search result layout, You must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="57b04-179">業種ごとに複数の結果タイプを作成できます。これにより、さまざまなタイプの結果にさまざまなレイアウトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-179">You can create multiple result types for each vertical, which allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="57b04-180">たとえば、*重大度 1* のインシデントをカスタマイズして、*重大度 3* のインシデントと比較してより目立つ色と大きなフォントを使用できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-180">For example, you can customize *Severity 1* incidents to have more prominent colors and a larger font compared to *Severity 3* incidents.</span></span>

<span data-ttu-id="57b04-181">ウィザードを開始すると、結果タイプの名前、コンテンツソース、および条件を定義する手順がガイドされます。</span><span class="sxs-lookup"><span data-stu-id="57b04-181">After you start the wizard, you're guided through the steps to define the name, content source, and conditions for the result type.</span></span> <span data-ttu-id="57b04-182">リストビューから結果タイプの優先度を定義できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-182">You can define the priority of the result type from the list view.</span></span>
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="57b04-183">Create a result type at the organization level</span><span class="sxs-lookup"><span data-stu-id="57b04-183">Create a result type at the organization level</span></span>

1. <span data-ttu-id="57b04-184">[Microsoft 365 管理センター](https://admin.microsoft.com)で、[[結果の種類]**に移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)。</span><span class="sxs-lookup"><span data-stu-id="57b04-184">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).</span></span>
2. <span data-ttu-id="57b04-185">結果の種類を **追加するには、[追加**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="57b04-185">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="57b04-186">結果タイプを編集するには、関連するリストで結果タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="57b04-186">To edit a result type, select the result type in the relevant list.</span></span>

### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="57b04-187">サイトレベルで結果タイプを作成する</span><span class="sxs-lookup"><span data-stu-id="57b04-187">Create a results type at the site level</span></span>

1. <span data-ttu-id="57b04-188">結果タイプを作成する [SharePoint](https://sharepoint.com/) サイトで、**[設定]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="57b04-188">On the [SharePoint](https://sharepoint.com/) site where you want to create the result type, go to **Settings**.</span></span>
2. <span data-ttu-id="57b04-189">[**サイト情報**]、[**すべてのサイト設定を表示**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="57b04-189">Select **Site information** and then **View all site settings**.</span></span>
3. <span data-ttu-id="57b04-190">[Microsoft Search] セクションを探し、**[このサイトコレクションのMicrosoft Searchの構成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="57b04-190">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="57b04-191">ナビゲーション ウィンドウで、[カスタム エクスペリエンス] に移動 **し、[** 結果の種類 **] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="57b04-191">In the navigation pane, go to **Custom experience**, and select **Result type** tab.</span></span>
5. <span data-ttu-id="57b04-192">結果の種類を追加するには、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="57b04-192">To add a result type, select **Add**.</span></span>  <span data-ttu-id="57b04-193">または、結果タイプを編集するには、リストから結果タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="57b04-193">Or, to edit a result type, select the result type in the list.</span></span>

## <a name="step-3-view-the-vertical-after-its-enabled"></a><span data-ttu-id="57b04-194">手順 3: 垂直を有効にした後に表示する</span><span class="sxs-lookup"><span data-stu-id="57b04-194">STEP 3: View the vertical after it's enabled</span></span>

<span data-ttu-id="57b04-195">垂直を有効にした後、表示するには数時間かかります。</span><span class="sxs-lookup"><span data-stu-id="57b04-195">After you enable the vertical, it will take a few hours before you can view it.</span></span> <span data-ttu-id="57b04-196">有効にした後で待ちたくない場合は、[SharePoint](https://sharepoint.com/) と [Office](https://office.com) の URL に **cacheClear=true** を追加して、カテゴリをすぐに表示できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-196">If you don't want to wait after enabling it, you can append **cacheClear=true** to the URL in [SharePoint](https://sharepoint.com/) and [Office](https://office.com) to view the vertical immediately.</span></span> <span data-ttu-id="57b04-197">たとえば [Bing、&](https://bing.com)**を**[作業] 垂直 URL に追加して、垂直をすぐに表示します。</span><span class="sxs-lookup"><span data-stu-id="57b04-197">For [Bing](https://bing.com), append **&features=uncachedVerticals** to the Work vertical URL to view the verticals immediately.</span></span>

> [!NOTE]
> <span data-ttu-id="57b04-198">モバイル Web ブラウザーから表示された場合、追加された[SharePointとOffice](https://sharepoint.com/)[に表示](https://office.com)されません。</span><span class="sxs-lookup"><span data-stu-id="57b04-198">Added verticals will not be visible on [SharePoint](https://sharepoint.com/) and [Office](https://office.com) when viewed from mobile web browsers.</span></span>

## <a name="profile-query-variables"></a><span data-ttu-id="57b04-199">プロファイル クエリ変数</span><span class="sxs-lookup"><span data-stu-id="57b04-199">Profile query variables</span></span>

<span data-ttu-id="57b04-200">クエリ変数は、垂直のクエリへの入力として動的データを提供するために、垂直の KQL クエリ セクションで使用されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-200">Query variables are used in the KQL query section of a vertical to provide dynamic data as an input to the query of a vertical.</span></span> <span data-ttu-id="57b04-201">プロファイル クエリ変数を使用して、サインインしているユーザーに対して検索結果をコンテキストに合った状態にできます。</span><span class="sxs-lookup"><span data-stu-id="57b04-201">You can use profile query variables to make the search results contextual to the signed-in user.</span></span> <span data-ttu-id="57b04-202">プロファイル クエリ変数は、サインインしているユーザーのプロファイルから値をフェッチ [します](/graph/api/resources/profile?view=graph-rest-beta)。</span><span class="sxs-lookup"><span data-stu-id="57b04-202">Profile query variables fetch values from the signed-in user’s [profile](/graph/api/resources/profile?view=graph-rest-beta).</span></span>

<span data-ttu-id="57b04-203">たとえば、サインインしているユーザーが割り当てられたサポート チケットを検索できる垂直の "チケット" を作成する場合は、管理ページの垂直方向の作成中に[クエリ] セクションで次のクエリを指定できます。</span><span class="sxs-lookup"><span data-stu-id="57b04-203">For example, if you want to create a “Tickets” vertical where a signed-in user can search for support tickets assigned to them, you can specify the following query under the "Query" section during the vertical creation in the administration page.</span></span>  

<span data-ttu-id="57b04-204">**AssignedTo:{Profile.accounts.userPrincipalName}**</span><span class="sxs-lookup"><span data-stu-id="57b04-204">**AssignedTo:{Profile.accounts.userPrincipalName}**</span></span>

<span data-ttu-id="57b04-205">これにより、検索結果を絞り込み、割り当て先が検索を実行しているユーザーであるアイテムのみを表示します。</span><span class="sxs-lookup"><span data-stu-id="57b04-205">This will narrow down the search results to show only those items where the assignee is the user performing the search.</span></span>

<span data-ttu-id="57b04-206">[プロファイル リソースは](https://graph.microsoft.com/graph/api/resources/profile?view=graph-rest-beta) 、プロパティをコレクションとして公開します。</span><span class="sxs-lookup"><span data-stu-id="57b04-206">[Profile resource](https://graph.microsoft.com/graph/api/resources/profile?view=graph-rest-beta) exposes properties as collections.</span></span> <span data-ttu-id="57b04-207">たとえば、電子メール アドレスに関連する情報は、電子メールのコレクション、職位のコレクションとしての作業位置などによって公開されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-207">For example, information related to email addresses is exposed through email collection, work positions as positions collection, and so on.</span></span> <span data-ttu-id="57b04-208">ソースの種類として AAD を持つユーザー プロファイルで使用可能なすべてのプロパティは、クエリ変数として公開されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-208">All properties available in the user profile, which have AAD as the source type, are exposed as Query variables.</span></span>

<span data-ttu-id="57b04-209">以下に示すように、電子メール コレクションで使用できる電子メール アドレスが 3 つ含まれます。</span><span class="sxs-lookup"><span data-stu-id="57b04-209">Consider a user who has 3 email addresses available in the email collection, as shown below.</span></span>

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- <span data-ttu-id="57b04-210">クエリ **MyProperty: {Profile.emails.address}** は MyProperty: "Megan.Bowen@contoso.com" に解決されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-210">The query **MyProperty: {Profile.emails.address}** will resolve to MyProperty: “Megan.Bowen@contoso.com”.</span></span>  

- <span data-ttu-id="57b04-211">address 属性のすべての値を解決するには、複数値の拡張構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-211">If you wish to resolve all the values of the address attribute, you have to use the multi-value expansion syntax.</span></span> <span data-ttu-id="57b04-212">クエリ **{|MyProperty:{Profile.emails.address}}** は ((MyProperty:"Megan.Bowen@contoso.com") OR (MyProperty: "meganb@hotmail.com") OR (MyProperty:"meganb@outlook.com")) に解決されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-212">The query **{|MyProperty:{Profile.emails.address}}** will resolve to ((MyProperty:"Megan.Bowen@contoso.com") OR (MyProperty: "meganb@hotmail.com") OR (MyProperty:"meganb@outlook.com"))</span></span>  

<span data-ttu-id="57b04-213">"|" 演算子は、複数値変数の解決に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57b04-213">The “|” operator should be used for resolving multi-value variables.</span></span> <span data-ttu-id="57b04-214">プロファイルの展開に関するその他の例については、以下の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="57b04-214">For more examples on profile expansion refer to the table below.</span></span>

| #         | <span data-ttu-id="57b04-215">構文</span><span class="sxs-lookup"><span data-stu-id="57b04-215">Syntax</span></span> |  <span data-ttu-id="57b04-216">戻り値</span><span class="sxs-lookup"><span data-stu-id="57b04-216">Value returned</span></span>  |
| --------- | ------ | --- |
| <span data-ttu-id="57b04-217">1</span><span class="sxs-lookup"><span data-stu-id="57b04-217">1</span></span>    | <span data-ttu-id="57b04-218">MyProperty:{Profile.emails.address}</span><span class="sxs-lookup"><span data-stu-id="57b04-218">MyProperty:{Profile.emails.address}</span></span>  |   <span data-ttu-id="57b04-219">"Megan.Bowen@contoso.com"</span><span class="sxs-lookup"><span data-stu-id="57b04-219">"Megan.Bowen@contoso.com"</span></span>  |
| <span data-ttu-id="57b04-220">2</span><span class="sxs-lookup"><span data-stu-id="57b04-220">2</span></span> | <span data-ttu-id="57b04-221">MyProperty:{Profile.emails}</span><span class="sxs-lookup"><span data-stu-id="57b04-221">MyProperty:{Profile.emails}</span></span>   |    <span data-ttu-id="57b04-222">{Profile.emails} 電子メールはオブジェクトなので、これは解決できません。</span><span class="sxs-lookup"><span data-stu-id="57b04-222">{Profile.emails} This will not resolve because emails are an object.</span></span>|
| <span data-ttu-id="57b04-223">3</span><span class="sxs-lookup"><span data-stu-id="57b04-223">3</span></span>    | <span data-ttu-id="57b04-224">{?MyProperty:{Profile.emails}}</span><span class="sxs-lookup"><span data-stu-id="57b04-224">{?MyProperty:{Profile.emails}}</span></span>  |  <span data-ttu-id="57b04-225">メールはオブジェクトなので、これは解決しない。</span><span class="sxs-lookup"><span data-stu-id="57b04-225">This will not resolve because emails is an object.</span></span> <span data-ttu-id="57b04-226">"?</span><span class="sxs-lookup"><span data-stu-id="57b04-226">The “?”</span></span> <span data-ttu-id="57b04-227">演算子は、解決しないクエリ変数を無視します。</span><span class="sxs-lookup"><span data-stu-id="57b04-227">operator ignores query variables that do not resolve.</span></span> <span data-ttu-id="57b04-228">この変数は、クエリ スタックの下にさらに渡されると削除されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-228">This variable will be removed when passed further down the query stack.</span></span>   |
| <span data-ttu-id="57b04-229">4 </span><span class="sxs-lookup"><span data-stu-id="57b04-229">4</span></span> | <span data-ttu-id="57b04-230">{&#124;MyProperty: {Profile.emails.source.Type}}</span><span class="sxs-lookup"><span data-stu-id="57b04-230">{&#124;MyProperty: {Profile.emails.source.Type}}</span></span>    |  <span data-ttu-id="57b04-231">((MyProperty:"official") OR (MyProperty:"non-official") OR (MyProperty:"personal"))</span><span class="sxs-lookup"><span data-stu-id="57b04-231">((MyProperty:"official") OR (MyProperty:"non-official") OR (MyProperty:"personal"))</span></span>    |

> [!NOTE]
>
> - <span data-ttu-id="57b04-232">プロファイル クエリ変数は、コネクタをコンテンツ ソースとして使用するカスタム [バー](connectors-overview.md) ティカルでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="57b04-232">Profile query variables are only supported for custom verticals using a [connector](connectors-overview.md) as a content source.</span></span>
> - <span data-ttu-id="57b04-233">プロファイル クエリ変数は、垂直セットアップ プロセスの "Query" [セクションで定義されます](customize-search-page.md#step-1-create-the-search-vertical)。</span><span class="sxs-lookup"><span data-stu-id="57b04-233">Profile query variables are defined on the “Query” section of the [vertical set up process](customize-search-page.md#step-1-create-the-search-vertical).</span></span>
> - <span data-ttu-id="57b04-234">プロファイル クエリ変数は現在プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="57b04-234">Profile query variables is currently in preview.</span></span> <span data-ttu-id="57b04-235">プレビューの詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。</span><span class="sxs-lookup"><span data-stu-id="57b04-235">For more information about preview, see [Connectors preview features](connectors-overview.md#what-are-the-preview-features).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="57b04-236">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="57b04-236">Troubleshooting</span></span>

<span data-ttu-id="57b04-237">発生する可能性のある一般的な問題とそれらを修正するためのアクションのリストを次に示します。</span><span class="sxs-lookup"><span data-stu-id="57b04-237">Here's a list of common issues you might encounter and actions to fix them.</span></span>

|<span data-ttu-id="57b04-238">Error</span><span class="sxs-lookup"><span data-stu-id="57b04-238">Error</span></span>  |<span data-ttu-id="57b04-239">アクション</span><span class="sxs-lookup"><span data-stu-id="57b04-239">Action</span></span>  |
|---------|---------|
| <span data-ttu-id="57b04-240">バーティカルに「問題が発生しました」というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="57b04-240">I see a "Something went wrong" error message on the vertical.</span></span> | <span data-ttu-id="57b04-241">セットアップを完了するには、バーティカル タイプと結果タイプの両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="57b04-241">Both the vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="57b04-242">両方を、同じコンテンツソースに対して作成したことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="57b04-242">Make sure you have created both for the same content source.</span></span> |
| <span data-ttu-id="57b04-243">結果のレイアウトを作成しましたが、表示されません。</span><span class="sxs-lookup"><span data-stu-id="57b04-243">I don't see my result layout, although I created one.</span></span> | <span data-ttu-id="57b04-244">これらの設定は通常キャッシュされるため、数分かかります。</span><span class="sxs-lookup"><span data-stu-id="57b04-244">It takes a few minutes because these settings are generally cached.</span></span> <span data-ttu-id="57b04-245">数分待ってから、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="57b04-245">Wait for a few minutes and try again.</span></span>        |
| <span data-ttu-id="57b04-246">バーティカル ページまたは結果タイプのページにコンテンツ ソースが表示されません。</span><span class="sxs-lookup"><span data-stu-id="57b04-246">I don't see any content sources on the vertical or result type page.</span></span> | <span data-ttu-id="57b04-247">コネクタとインデックス付きデータが構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="57b04-247">Make sure you have configured connectors and indexed data.</span></span>   |

## <a name="next-steps"></a><span data-ttu-id="57b04-248">次のステップ</span><span class="sxs-lookup"><span data-stu-id="57b04-248">Next steps</span></span>

[<span data-ttu-id="57b04-249">結果のレイアウトをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="57b04-249">Customize the results layout</span></span>](customize-results-layout.md)
