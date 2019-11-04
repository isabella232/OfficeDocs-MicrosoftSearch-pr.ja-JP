---
title: Microsoft 検索ページをカスタマイズする
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 検索垂直を追加して検索結果をカスタマイズする
ms.openlocfilehash: 87b394847281e43683f2ed9dfd42d19aa103d3e2
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949932"
---
# <a name="customize-the-microsoft-search-page"></a><span data-ttu-id="cdca2-103">Microsoft 検索ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="cdca2-103">Customize the Microsoft Search page</span></span>

<span data-ttu-id="cdca2-104">検索の業種と検索結果の種類を作成することで、ユーザーが**SharePoint**で検索したときに表示される検索結果をカスタマイズしたり、 **Bing で Microsoft search**を**Office.com**することができます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-104">By creating search verticals and result types you can customize the search results that are shown to users when they search in **SharePoint**, **Office.com** and **Microsoft Search in Bing** .</span></span> <span data-ttu-id="cdca2-105">各業種では、ユーザーが表示するアクセス許可が付与されている情報を簡単に見つけられるようにします。</span><span class="sxs-lookup"><span data-stu-id="cdca2-105">Verticals make it easier for users to find the information they’ve got permission to see.</span></span>  <span data-ttu-id="cdca2-106">たとえば、マーケティング部門のユーザーのために、サードパーティ製のソフトウェアからマーケティング分析データの検索を縦に作成できます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-106">For example, you can create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="cdca2-107">また、検索結果の種類を定義し、このデータのレイアウトをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="cdca2-108">次のレベルで、業種と結果の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-108">You can create verticals and result types  at these levels:</span></span> 

- <span data-ttu-id="cdca2-109">組織レベル–縦型を組織レベルで追加すると、ユーザーが SharePoint のスタートページから Office.com および Bing.com で検索を行うときに、検索結果ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-109">Organization level – When you add a vertical at the organization level, it appears on the search results page when users search from their SharePoint start page, on Office.com and on Bing.com.</span></span> 
- <span data-ttu-id="cdca2-110">サイトレベル–たとえば、顧客サービスの従業員が、自分の部署の SharePoint サイトから直接 "重大度 1" インシデントを検索できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-110">Site level – For example, you might want to allow your customer service employees to search for “Severity 1” incidents directly from their department’s SharePoint site.</span></span> 

## <a name="whats-a-search-vertical"></a><span data-ttu-id="cdca2-111">検索垂直かどうか</span><span class="sxs-lookup"><span data-stu-id="cdca2-111">What’s a search vertical?</span></span>

<span data-ttu-id="cdca2-112">Microsoft 検索結果ページの一番上には、タブの行があり、これらは検索の各業種に該当します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-112">At the top of the Microsoft search results page there is a row of tabs, these are search verticals.</span></span> <span data-ttu-id="cdca2-113">検索垂直には、特定の種類の結果または特定のコンテンツ (たとえば、ファイルまたはニュース) だけが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-113">A search vertical only shows results of a certain type or from certain content, for example only files or news.</span></span> <span data-ttu-id="cdca2-114">既定では、Microsoft Search はすべての業種、人、ファイル、サイト、およびニュースを表示します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-114">By default Microsoft Search shows the verticals All, People, Files, Sites, and News.</span></span>  

<span data-ttu-id="cdca2-115">組織に関連する検索業種を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-115">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="cdca2-116">これらは、SharePoint、Office.com、および Bing の Microsoft 検索結果ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-116">These will appear on the Microsoft search results page in SharePoint, Office.com, and Bing.</span></span>  <span data-ttu-id="cdca2-117">たとえば、各グループに必要な情報の種類に基づいて、マーケティング関連のコンテンツ用に1つの垂直線を作成し、もう1つを販売することができます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-117">For example, you could create one vertical for  marketing related content and another for sales, based on the type of information that each group would want to have.</span></span> <span data-ttu-id="cdca2-118">すべての業種を追加して、コネクタ経由でインデックスが作成されたコンテンツからの結果のみを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-118">You can add verticals to show results only from content indexed via Connectors.</span></span>  

<span data-ttu-id="cdca2-119">**免責事項:** 各業種および結果の種類は、Microsoft コネクタプレビューの一部として現在プレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="cdca2-119">**DISCLAIMER:** Verticals and result types are currently in preview as a part of Microsoft Connectors preview.</span></span> <span data-ttu-id="cdca2-120">SharePoint 内にあるコンテンツまたは FileShare コネクタによってインデックスが作成されたコンテンツに対して、垂直方向を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdca2-120">You cannot create a vertical for content residing in SharePoint or from content indexed by the FileShare connector.</span></span> <span data-ttu-id="cdca2-121">プレビューの詳細については、「[コネクタプレビュー](connectors-preview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cdca2-121">To find out more about the preview, see [Connectors Preview](connectors-preview.md).</span></span> <span data-ttu-id="cdca2-122">プレビューに参加するには、最初に[Microsoft Graph Connector preview のサインアップフォーム](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdca2-122">To participate in the preview, you must first submit the [Microsoft Graph Connectors Preview Signup form](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="cdca2-123">検討事項</span><span class="sxs-lookup"><span data-stu-id="cdca2-123">Things to consider...</span></span>

<span data-ttu-id="cdca2-124">開始する前に、コネクタにインデックスが作成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cdca2-124">Before you start, make sure the connector has been indexed.</span></span> <span data-ttu-id="cdca2-125">ファイルサイズに応じて、最大48時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cdca2-125">It can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="cdca2-126">SharePoint 内にあるコンテンツまたは FileShare コネクタによってインデックスが作成されたコンテンツに対して、垂直方向を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="cdca2-126">You can’t create a vertical for content residing in SharePoint or from content indexed by the FileShare connector .</span></span> <span data-ttu-id="cdca2-127">コンテンツにインデックスを作成する方法について説明します (コネクタのドキュメントへのリンク)。</span><span class="sxs-lookup"><span data-stu-id="cdca2-127">Learn how to index content(Link to Connector documentation).</span></span>

<span data-ttu-id="cdca2-128">最高レベルでは、垂直方向を追加するための3つの主要な手順があります。</span><span class="sxs-lookup"><span data-stu-id="cdca2-128">At a high-level, there are three main steps for adding a vertical.</span></span> 

1. <span data-ttu-id="cdca2-129">垂直方向の作成-この手順では、検索するコンテンツの縦の名前、コンテンツソース、および範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-129">Create the vertical – In this step you will define the vertical’s name, content source, and scope of the content to search.</span></span> 
2. <span data-ttu-id="cdca2-130">この垂直方向の結果がどのように表示されるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-130">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="cdca2-131">垂直リストページから、垂直 (表示する) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="cdca2-131">Enable the vertical (to be displayed) from the vertical list page.</span></span>   

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="cdca2-132">手順 1: 検索垂直を作成する</span><span class="sxs-lookup"><span data-stu-id="cdca2-132">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="cdca2-133">ウィザードを開始すると、縦書きの名前、コンテンツソース、検索するコンテンツの範囲を定義するための手順がガイドされます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-133">Once you start the wizard, you'll be guided through the steps to define the vertical's name, content source and scope of the content that it will search.</span></span> <span data-ttu-id="cdca2-134">垂直は無効な状態で作成されます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-134">The vertical is created in a disabled state.</span></span> <span data-ttu-id="cdca2-135">後で垂直にすることができます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-135">You will enable the vertical later.</span></span>

<span data-ttu-id="cdca2-136">[キーワードクエリ言語 (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)の限定されたセットを使用して範囲を絞り込むことができます。ページには、使用可能なプロパティの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-136">You can use a limited set of the [Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow down the scope, and the page shows lists the properties available to you.</span></span> <span data-ttu-id="cdca2-137">KQL を作成するには、ブール演算子と共に free text-キーワードおよびプロパティ制限を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cdca2-137">We recommend using free text-keywords and property restrictions with boolean operators for creating the KQL</span></span> 

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="cdca2-138">組織レベルで垂直線を作成する</span><span class="sxs-lookup"><span data-stu-id="cdca2-138">Create a vertical at the organization level</span></span>

<span data-ttu-id="cdca2-139">SharePoint home、Bing、または Office.com で、Microsoft Search で垂直方向を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-139">To create the vertical on Microsoft Search in SharePoint home, Bing or Office.com, follow these steps:</span></span>

1. <span data-ttu-id="cdca2-140">Microsoft 365 管理センターで、[ **設定** ] [> **microsoft Search** > ] の各オプションに移動**します。**</span><span class="sxs-lookup"><span data-stu-id="cdca2-140">In the Microsoft 365 admin center go to **Settings** > **Microsoft Search** > **Verticals**.</span></span>
1. <span data-ttu-id="cdca2-141">開始するには、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-141">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="cdca2-142">サイトレベルで垂直方向のを作成する</span><span class="sxs-lookup"><span data-stu-id="cdca2-142">Create a vertical at the site level</span></span>

1. <span data-ttu-id="cdca2-143">垂直方向を作成する SharePoint サイトで、[**設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-143">On the SharePoint site where you want to create the vertical, go to **Settings**.</span></span>
1. <span data-ttu-id="cdca2-144">[**サイト情報**] を選択し、[**すべてのサイト設定**] を表示します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-144">Select **Site information**, and then **View all site settings**.</span></span>
1. <span data-ttu-id="cdca2-145">[ **Microsoft search** ] セクションを探し、[**このサイトコレクションの Microsoft Search を構成する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-145">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="cdca2-146">ナビゲーションウィンドウで、[ **ユーザー設定の操作**] に移動し、[**垂直**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-146">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
1. <span data-ttu-id="cdca2-147">垂直方向を追加するには、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-147">To add a vertical, select **Add**.</span></span> <br>
<span data-ttu-id="cdca2-148">または</span><span class="sxs-lookup"><span data-stu-id="cdca2-148">OR</span></span> <br><span data-ttu-id="cdca2-149">垂直方向を編集するには、一覧から縦に選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-149">To edit a vertical, select it in the list.</span></span>

<span data-ttu-id="cdca2-150">各業種は無効な状態で作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="cdca2-150">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="cdca2-151">ユーザーが各業種を表示できるようにするには、それらを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cdca2-151">You'll still need to enable them before users can see the verticals.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="cdca2-152">手順 2: 検索結果の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="cdca2-152">STEP 2: Create the result types</span></span>

<span data-ttu-id="cdca2-153">結果の種類を使用してレイアウトを設計することで、結果を垂直に表示する方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-153">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="cdca2-154">結果のレイアウトを使用すると、検索結果に重要な情報を直接表示することができます。したがって、ユーザーが探しているものが見つかったかどうかを確認するために、各結果をクリックする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cdca2-154">The result layout let you show important information directly in the search results, so that users don't have to click on each result to see if they've found what they're looking for.</span></span>

<span data-ttu-id="cdca2-p111">検索結果の種類とは、検索結果のタイプの違いに応じて表示方法を変えるルールのことです。このルールは、次のような構成になっています。</span><span class="sxs-lookup"><span data-stu-id="cdca2-p111">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways. It consists of the following:</span></span>

- <span data-ttu-id="cdca2-157">検索結果のコンテンツソースなど、各検索結果を比較する*1 つまたは複数の条件*。</span><span class="sxs-lookup"><span data-stu-id="cdca2-157">*One or more conditions* to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="cdca2-158">条件に一致する検索結果に使用する*結果レイアウト*。</span><span class="sxs-lookup"><span data-stu-id="cdca2-158">A *result layout* to use for search results that meet the conditions.</span></span> <span data-ttu-id="cdca2-159">結果レイアウトは、条件を満たすすべての結果が検索結果ページに表示され、動作する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-159">The result layout controls the way in which all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="cdca2-160">**結果を垂直に表示するには、少なくとも1つの結果の種類を作成する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="cdca2-160">**You must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="cdca2-161">垂直方向に複数の検索結果の種類を作成できます。これにより、さまざまな種類の結果に異なるレイアウトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-161">You can create multiple result types for each vertical, this allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="cdca2-162">たとえば、"Severity 1" インシデントをカスタマイズして、より目立つ色を設定したり、"重大度 3" インシデントと比較してより大きなフォントを設定したりできます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-162">For example, you can customize “Severity 1” incidents to have more prominent colors and a larger font compared to “Severity 3” incidents.</span></span> 

 <span data-ttu-id="cdca2-163">ウィザードを開始すると、検索結果の種類の名前、コンテンツソース、および条件を定義するための手順がガイドされます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-163">Once you start the wizard, you will be guided through the steps to define the name, content source and conditions for the result type.</span></span> <span data-ttu-id="cdca2-164">リストビューから検索結果の種類の優先度を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cdca2-164">You can define the priority of the result type from the list view.</span></span> 
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="cdca2-165">組織レベルで結果の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="cdca2-165">Create a result type at the organization level</span></span>

1. <span data-ttu-id="cdca2-166">Microsoft 365 管理センターで、[**microsoft Search**の**設定** > ] に移動し、[**結果の種類**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-166">In the Microsoft 365 admin center, go to **Setting** > **Microsoft Search**, and then select **Result type**.</span></span>
1. <span data-ttu-id="cdca2-167">**検索結果の種類**を追加するには、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-167">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="cdca2-168">検索結果の種類を編集するには、関連するリストで結果の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-168">To edit a result type, select the result type in the relevant list.</span></span>
 
### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="cdca2-169">サイトレベルで結果の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="cdca2-169">Create a results type at the site level</span></span>

1. <span data-ttu-id="cdca2-170">検索結果の種類を作成する SharePoint サイトで、[**設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-170">On the SharePoint site where you want to create the result type, go to **Settings**.</span></span>
1. <span data-ttu-id="cdca2-171">[**サイト情報**] を選択し、[**すべてのサイト設定**] を表示します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-171">Select **Site information**, and then **View all site settings**.</span></span> 
1. <span data-ttu-id="cdca2-172">[Microsoft Search] セクションを探し、[**このサイトコレクションの Microsoft search を構成する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-172">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="cdca2-173">ナビゲーションウィンドウで、[ **ユーザー設定の操作**] に移動し、[結果の種類] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-173">In the navigation pane, go to **Custom experience**, and then select Result type tab.</span></span>
1. <span data-ttu-id="cdca2-174">検索結果の種類を追加するには、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-174">To add a result type, select **Add**.</span></span> <br> <span data-ttu-id="cdca2-175">または</span><span class="sxs-lookup"><span data-stu-id="cdca2-175">OR</span></span> <br><span data-ttu-id="cdca2-176">検索結果の種類を編集するには、リストで結果の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-176">To edit a result type, select the result type in the list.</span></span>

### <a name="view-the-vertical-after-enabling"></a><span data-ttu-id="cdca2-177">垂直方向の表示を有効にした後</span><span class="sxs-lookup"><span data-stu-id="cdca2-177">View the vertical after enabling</span></span>

<span data-ttu-id="cdca2-178">垂直方向を有効にした後は、表示する前にしばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cdca2-178">After you enable the vertical, it might take a while before you can view it.</span></span>
<span data-ttu-id="cdca2-179">これを有効にした後で待機する場合は、 *cacheClear = true*を SHAREPOINT の URL に追加して、Office.com をすぐに表示するようにします。</span><span class="sxs-lookup"><span data-stu-id="cdca2-179">If you want to wait after enabling it, you can append *cacheClear=true* to the URL in SharePoint and Office.com to view the vertical immediately.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="cdca2-180">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="cdca2-180">Troubleshooting</span></span>

<span data-ttu-id="cdca2-181">発生する可能性のある一般的な問題と、それらを修正するためのアクションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="cdca2-181">Here's a list of common issues you might encounter and actions for fixing them.</span></span>


|<span data-ttu-id="cdca2-182">Error</span><span class="sxs-lookup"><span data-stu-id="cdca2-182">Error</span></span>  |<span data-ttu-id="cdca2-183">Action</span><span class="sxs-lookup"><span data-stu-id="cdca2-183">Action</span></span>  |
|---------|---------|
|<span data-ttu-id="cdca2-184">垂直方向に「問題が発生しました」というエラーが表示される</span><span class="sxs-lookup"><span data-stu-id="cdca2-184">I see a 'Something went wrong' error on the vertical</span></span>|   <span data-ttu-id="cdca2-185">セットアップを完了するには、垂直および結果の種類の両方が必要です。</span><span class="sxs-lookup"><span data-stu-id="cdca2-185">Both vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="cdca2-186">同じコンテンツソースに対して両方の作成が完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cdca2-186">Make sure you have created both for the same content source.</span></span>      |
|<span data-ttu-id="cdca2-187">作成したものの、結果のレイアウトが表示されないのはなぜですか?</span><span class="sxs-lookup"><span data-stu-id="cdca2-187">Why don't I see my result layout although I have created one?</span></span> | <span data-ttu-id="cdca2-188">これらの設定は通常キャッシュされるため、検索結果の種類を使用するのに数分かかります。</span><span class="sxs-lookup"><span data-stu-id="cdca2-188">It takes a few minutes for result types to be used as these settings are generally cached.</span></span> <span data-ttu-id="cdca2-189">数分待ってから再試行してください</span><span class="sxs-lookup"><span data-stu-id="cdca2-189">Wait for a few minutes and try again</span></span>        |
|<span data-ttu-id="cdca2-190">[垂直または結果の種類] ページにコンテンツソースが表示されない</span><span class="sxs-lookup"><span data-stu-id="cdca2-190">I don't see any content sources on the vertical or result type page</span></span>     |      <span data-ttu-id="cdca2-191">コネクタとインデックスデータを構成していることを確認する</span><span class="sxs-lookup"><span data-stu-id="cdca2-191">Make sure you have configured connectors and indexed data</span></span>   |



## <a name="next-steps"></a><span data-ttu-id="cdca2-192">次のステップ</span><span class="sxs-lookup"><span data-stu-id="cdca2-192">Next steps</span></span>
[<span data-ttu-id="cdca2-193">手順 3: 結果のレイアウトをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="cdca2-193">STEP 3: Customize the results layout</span></span>](customize-results-layout.md)
