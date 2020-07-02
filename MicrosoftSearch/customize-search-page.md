---
title: Microsoft 検索ページをカスタマイズする
ms.author: jypal6
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
description: 検索垂直を追加して検索結果をカスタマイズする
ms.openlocfilehash: 60ab3423db0a86982df9c4332f0f22267c49dc04
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996060"
---
# <a name="customize-the-search-results-page"></a><span data-ttu-id="252d2-103">検索結果ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="252d2-103">Customize the search results page</span></span>

<span data-ttu-id="252d2-104">検索の業種と結果の種類を作成して、 [Bing](https://bing.com)で microsoft [SharePoint](https://sharepoint.com/)、 [microsoft Office](https://office.com)、microsoft search を検索するときにユーザーに表示される検索結果をカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="252d2-104">You can create search verticals and result types to customize the search results that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), [Microsoft Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="252d2-105">各業種では、ユーザーが表示するアクセス許可を持っている情報を簡単に見つけられるようにします。</span><span class="sxs-lookup"><span data-stu-id="252d2-105">Verticals make it easier for users to find the information that they have permission to see.</span></span> <span data-ttu-id="252d2-106">たとえば、マーケティング部門のユーザーのために、サードパーティ製のソフトウェアからマーケティング分析データの検索を縦に作成できます。</span><span class="sxs-lookup"><span data-stu-id="252d2-106">For example, you could create a search vertical for marketing analysis data from third-party software for your users in the marketing department.</span></span> <span data-ttu-id="252d2-107">また、検索結果の種類を定義し、このデータのレイアウトをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="252d2-107">You can also define result types and customize the layout for this data.</span></span>  

<span data-ttu-id="252d2-108">次のレベルで、業種と結果の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="252d2-108">You can create verticals and result types at these levels:</span></span>

- <span data-ttu-id="252d2-109">**組織レベル**–組織レベルで垂直を追加すると、ユーザーが[SharePoint](https://sharepoint.com/)のスタートページ、 [Office](https://office.com)、または[Bing](https://bing.com)で検索したときに、検索結果ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="252d2-109">**Organization level** – When you add a vertical at the organization level, it appears on the search results page when users search from their [SharePoint](https://sharepoint.com/) start page, on [Office](https://office.com), or on [Bing](https://bing.com).</span></span>
- <span data-ttu-id="252d2-110">**サイトレベル**–たとえば、顧客サービスの従業員が、部門の SharePoint サイトから直接、*重要度 1*のインシデントを検索できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="252d2-110">**Site level** – For example, you might want to enable your customer service employees to search for *Severity 1* incidents directly from their department’s SharePoint site.</span></span>

## <a name="search-verticals-explained"></a><span data-ttu-id="252d2-111">検索業種の説明</span><span class="sxs-lookup"><span data-stu-id="252d2-111">Search verticals explained</span></span>

<span data-ttu-id="252d2-112">Microsoft 検索結果ページの上部には、タブの行があります。</span><span class="sxs-lookup"><span data-stu-id="252d2-112">At the top of the Microsoft Search results page, there's a row of tabs.</span></span> <span data-ttu-id="252d2-113">これらは検索業界です。</span><span class="sxs-lookup"><span data-stu-id="252d2-113">These are the search verticals.</span></span> <span data-ttu-id="252d2-114">検索垂直では、特定の種類の結果または特定のコンテンツのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="252d2-114">A search vertical only shows results of a certain type or from certain content.</span></span> <span data-ttu-id="252d2-115">例としては、**ファイル**または**ニュース**があります。</span><span class="sxs-lookup"><span data-stu-id="252d2-115">Examples are **Files** or **News**.</span></span> <span data-ttu-id="252d2-116">Microsoft Search では、既定で、**すべて**の業種、**人**、**ファイル**、**サイト**、および**ニュース**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="252d2-116">By default, Microsoft Search shows the verticals **All**, **People**, **Files**, **Sites**, and **News**.</span></span>  

<span data-ttu-id="252d2-117">組織に関連する検索業種を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="252d2-117">You can add search verticals that are relevant to your organization.</span></span> <span data-ttu-id="252d2-118">これらは、 [SharePoint](https://sharepoint.com/)、 [Office](https://Office.com)、および[Bing](https://bing.com)の Microsoft 検索結果ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="252d2-118">These will appear on the Microsoft Search results page in [SharePoint](https://sharepoint.com/), [Office](https://Office.com), and [Bing](https://bing.com).</span></span> <span data-ttu-id="252d2-119">たとえば、各グループに必要な情報の種類に基づいて、マーケティング関連のコンテンツを縦にまとめ、売り上げに対して別のものを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="252d2-119">For example, you could create a vertical for marketing-related content and another for sales, based on the type of information that each group needs.</span></span> <span data-ttu-id="252d2-120">すべての業種を追加して、コネクタ経由でインデックスが作成されたコンテンツからの結果のみを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="252d2-120">You can add verticals to show results only from content indexed via connectors.</span></span>  

>[!NOTE]
> <span data-ttu-id="252d2-121">各業種および結果の種類は、Microsoft Graph のコネクタプレビューの一部として現在プレビュー段階にあります。</span><span class="sxs-lookup"><span data-stu-id="252d2-121">Verticals and result types are currently in preview as a part of the Microsoft Graph connectors preview.</span></span> <span data-ttu-id="252d2-122">プレビューの詳細については、「[コネクタプレビュー](connectors-preview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="252d2-122">For more about the preview, see [Connectors preview](connectors-preview.md).</span></span> <span data-ttu-id="252d2-123">プレビューに参加するには、最初に[Microsoft Graph Connector preview のサインアップフォーム](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="252d2-123">To participate in the preview, you must first submit the [Microsoft Graph Connectors Preview Signup form](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="252d2-124">考慮事項</span><span class="sxs-lookup"><span data-stu-id="252d2-124">Things to consider</span></span>

<span data-ttu-id="252d2-125">開始する前に、コネクタにインデックスが作成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="252d2-125">Before you start, make sure that the connector has been indexed.</span></span> <span data-ttu-id="252d2-126">これには、ファイルサイズに応じて、最大48時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="252d2-126">This can take up to 48 hours, depending on the file size.</span></span>

<span data-ttu-id="252d2-127">[SharePoint](https://sharepoint.com/)または[ファイル共有コネクタ](file-share-connector.md)によってインデックスが作成されたコンテンツに対して、垂直方向を作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="252d2-127">You can’t create a vertical for content that resides in [SharePoint](https://sharepoint.com/) or from content that's indexed by the [file share connector](file-share-connector.md).</span></span> <span data-ttu-id="252d2-128">[コンテンツにインデックス](configure-connector.md)を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="252d2-128">Learn how to [index content](configure-connector.md).</span></span>

<span data-ttu-id="252d2-129">垂直方向を追加するには、次の3つの基本的な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="252d2-129">There are three basic steps to add a vertical:</span></span>

1. <span data-ttu-id="252d2-130">垂直方向のを作成します。</span><span class="sxs-lookup"><span data-stu-id="252d2-130">Create the vertical.</span></span> <span data-ttu-id="252d2-131">この手順では、検索するコンテンツの縦の名前、コンテンツソース、および範囲を定義します。</span><span class="sxs-lookup"><span data-stu-id="252d2-131">In this step, you define the vertical’s name, content source, and scope of the content to search.</span></span>
2. <span data-ttu-id="252d2-132">この垂直方向の結果がどのように表示されるかを定義します。</span><span class="sxs-lookup"><span data-stu-id="252d2-132">Define what the results for this vertical will look like.</span></span>  
3. <span data-ttu-id="252d2-133">垂直リストページから、垂直 (表示する) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="252d2-133">Enable the vertical (to be displayed) from the vertical list page.</span></span>

## <a name="step-1-create-the-search-vertical"></a><span data-ttu-id="252d2-134">手順 1: 検索垂直を作成する</span><span class="sxs-lookup"><span data-stu-id="252d2-134">STEP 1: Create the search vertical</span></span>

<span data-ttu-id="252d2-135">ウィザードを開始したら、検索するコンテンツの縦の名前、コンテンツソース、および範囲を定義する手順に従って操作します。</span><span class="sxs-lookup"><span data-stu-id="252d2-135">After you start the wizard, you're guided through the steps to define the vertical's name, content source, and scope of the content to search.</span></span> <span data-ttu-id="252d2-136">垂直は無効な状態で作成されます。</span><span class="sxs-lookup"><span data-stu-id="252d2-136">The vertical is created in a disabled state.</span></span> <span data-ttu-id="252d2-137">後で有効にします。</span><span class="sxs-lookup"><span data-stu-id="252d2-137">You'll enable it later.</span></span>

<span data-ttu-id="252d2-138">限定された一連の[キーワードクエリ言語 (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)を使用して、範囲を絞ることができます。</span><span class="sxs-lookup"><span data-stu-id="252d2-138">You can use a limited set of [Keyword Query Language (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) to narrow the scope.</span></span> <span data-ttu-id="252d2-139">このページには、使用可能なプロパティの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="252d2-139">This page lists the properties that are available.</span></span> <span data-ttu-id="252d2-140">この KQL を作成するブール演算子では、freetext キーワードとプロパティ制限を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="252d2-140">We recommend that you use freetext keywords and property restrictions with boolean operators for creating the KQL.</span></span>

### <a name="create-a-vertical-at-the-organization-level"></a><span data-ttu-id="252d2-141">組織レベルで垂直線を作成する</span><span class="sxs-lookup"><span data-stu-id="252d2-141">Create a vertical at the organization level</span></span>

<span data-ttu-id="252d2-142">[SharePoint](https://sharepoint.com/) Home、 [Office](https://office.com)、または[Bing](https://bing.com)で Microsoft Search に垂直にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="252d2-142">To create the vertical on Microsoft Search in [SharePoint](https://sharepoint.com/) home, [Office](https://office.com), or [Bing](https://bing.com), follow these steps:</span></span>

1. <span data-ttu-id="252d2-143">Microsoft 365 [管理センター](https://admin.microsoft.com)で、[ **設定**] [   >  **microsoft Search**カスタマイズ] の各オプションに移動   >  **Customization**  >  [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)します。</span><span class="sxs-lookup"><span data-stu-id="252d2-143">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Customization** > [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="252d2-144">開始するには、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-144">Select **Add** to get started.</span></span>  

### <a name="create-a-vertical-at-the-site-level"></a><span data-ttu-id="252d2-145">サイトレベルで垂直方向のを作成する</span><span class="sxs-lookup"><span data-stu-id="252d2-145">Create a vertical at the site level</span></span>

1. <span data-ttu-id="252d2-146">垂直にする[SharePoint](https://sharepoint.com/)サイトで、[**設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="252d2-146">On the [SharePoint](https://sharepoint.com/) site where you want the vertical, go to **Settings**.</span></span>
1. <span data-ttu-id="252d2-147">[**サイト情報**] を選択し、[**すべてのサイト設定**] を表示します。</span><span class="sxs-lookup"><span data-stu-id="252d2-147">Select **Site information** and then **View all site settings**.</span></span>
1. <span data-ttu-id="252d2-148">[ **Microsoft search** ] セクションを探し、[**このサイトコレクションの Microsoft Search を構成する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-148">Look for the **Microsoft Search** section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="252d2-149">ナビゲーションウィンドウで、[ **ユーザー設定の操作**] に移動し、[**垂直**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-149">In the navigation pane, go to **Custom experience**, and then select the **Verticals** tab.</span></span>
1. <span data-ttu-id="252d2-150">垂直方向を追加するには、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-150">To add a vertical, select **Add**.</span></span>
  <span data-ttu-id="252d2-151">または、縦方向を編集するには、一覧から選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-151">Or, to edit a vertical, select it in the list.</span></span>

<span data-ttu-id="252d2-152">各業種は無効な状態で作成されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="252d2-152">Remember, verticals are created in a disabled state.</span></span> <span data-ttu-id="252d2-153">ユーザーが表示できるようにするには、それらを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="252d2-153">They must be enabled before users can see them.</span></span>

## <a name="step-2-create-the-result-types"></a><span data-ttu-id="252d2-154">手順 2: 検索結果の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="252d2-154">STEP 2: Create the result types</span></span>

<span data-ttu-id="252d2-155">結果の種類を使用してレイアウトを設計することで、結果を垂直に表示する方法を定義できます。</span><span class="sxs-lookup"><span data-stu-id="252d2-155">You can define how results are displayed in the vertical by designing the layout using result types.</span></span> <span data-ttu-id="252d2-156">結果レイアウトでは、重要な情報を検索結果に直接表示することができます。したがって、ユーザーが探しているものが見つかったかどうかを確認するために、各結果を選択する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="252d2-156">The result layout lets you show important information directly in the search results, so users don't have to select each result to see if they found what they're looking for.</span></span>

<span data-ttu-id="252d2-157">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways.</span><span class="sxs-lookup"><span data-stu-id="252d2-157">A search result type is a rule that causes distinct kinds of search results to be displayed in different ways.</span></span> <span data-ttu-id="252d2-158">It consists of the following:</span><span class="sxs-lookup"><span data-stu-id="252d2-158">It consists of the following:</span></span>

- <span data-ttu-id="252d2-159">検索結果のコンテンツソースなど、各検索結果を比較する**1 つまたは複数の条件**。</span><span class="sxs-lookup"><span data-stu-id="252d2-159">**One or more conditions** to compare each search result against, such as the content source of the search result.</span></span>  
- <span data-ttu-id="252d2-160">条件に一致する検索結果に使用する**結果レイアウト**。</span><span class="sxs-lookup"><span data-stu-id="252d2-160">A **result layout** to use for search results that meet the conditions.</span></span> <span data-ttu-id="252d2-161">結果レイアウトは、条件を満たすすべての結果が検索結果ページに表示され、動作する方法を制御します。</span><span class="sxs-lookup"><span data-stu-id="252d2-161">The result layout controls the way that all results that meet the conditions appear and behave on a search results page.</span></span>

<span data-ttu-id="252d2-162">**結果を垂直に表示するには、少なくとも1つの結果の種類を作成する必要があります。**</span><span class="sxs-lookup"><span data-stu-id="252d2-162">**You must create at least one result type for results to display on the vertical.**</span></span> <span data-ttu-id="252d2-163">垂直方向に複数の検索結果の種類を作成できます。これにより、さまざまな種類の結果に異なるレイアウトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="252d2-163">You can create multiple result types for each vertical, which allows you to use different layouts for different type of results.</span></span> <span data-ttu-id="252d2-164">たとえば、重大度*1*のインシデントをカスタマイズして、*重要度 3*のインシデントに比べて目立つ色とより大きいフォントを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="252d2-164">For example, you can customize *Severity 1* incidents to have more prominent colors and a larger font compared to *Severity 3* incidents.</span></span>

<span data-ttu-id="252d2-165">ウィザードを開始した後、検索結果の種類の名前、コンテンツソース、および条件を定義する手順について説明しています。</span><span class="sxs-lookup"><span data-stu-id="252d2-165">After you start the wizard, you're guided through the steps to define the name, content source, and conditions for the result type.</span></span> <span data-ttu-id="252d2-166">リストビューから検索結果の種類の優先度を定義できます。</span><span class="sxs-lookup"><span data-stu-id="252d2-166">You can define the priority of the result type from the list view.</span></span>
  
### <a name="create-a-result-type-at-the-organization-level"></a><span data-ttu-id="252d2-167">組織レベルで結果の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="252d2-167">Create a result type at the organization level</span></span>

1. <span data-ttu-id="252d2-168">[管理センター](https://admin.microsoft.com)で、[ **Setting**  >  **Microsoft Search**  >  の**カスタマイズ**の結果の種類の設定] に移動  >  [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)します。</span><span class="sxs-lookup"><span data-stu-id="252d2-168">In the [admin center](https://admin.microsoft.com), go to **Setting** > **Microsoft Search** > **Customizations** > [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).</span></span>
1. <span data-ttu-id="252d2-169">**検索結果の種類**を追加するには、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-169">To add a **Result type**, select **Add**.</span></span> <span data-ttu-id="252d2-170">検索結果の種類を編集するには、関連するリストで結果の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-170">To edit a result type, select the result type in the relevant list.</span></span>

### <a name="create-a-results-type-at-the-site-level"></a><span data-ttu-id="252d2-171">サイトレベルで結果の種類を作成する</span><span class="sxs-lookup"><span data-stu-id="252d2-171">Create a results type at the site level</span></span>

1. <span data-ttu-id="252d2-172">検索結果の種類を作成する[SharePoint](https://sharepoint.com/)サイトで、[**設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="252d2-172">On the [SharePoint](https://sharepoint.com/) site where you want to create the result type, go to **Settings**.</span></span>
1. <span data-ttu-id="252d2-173">[**サイト情報**] を選択し、[**すべてのサイト設定**] を表示します。</span><span class="sxs-lookup"><span data-stu-id="252d2-173">Select **Site information** and then **View all site settings**.</span></span>
1. <span data-ttu-id="252d2-174">[Microsoft Search] セクションを探し、[**このサイトコレクションの Microsoft search を構成する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-174">Look for the Microsoft Search section, and then select **Configure Microsoft Search for this site collection**.</span></span>
1. <span data-ttu-id="252d2-175">ナビゲーションウィンドウで、[ **ユーザー設定の操作**] に移動し、[**結果の種類**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-175">In the navigation pane, go to **Custom experience**, and select **Result type** tab.</span></span>
2. <span data-ttu-id="252d2-176">検索結果の種類を追加するには、[ **追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-176">To add a result type, select **Add**.</span></span>  <span data-ttu-id="252d2-177">または、結果の種類を編集するには、リストで結果の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="252d2-177">Or, to edit a result type, select the result type in the list.</span></span>

### <a name="view-the-vertical-after-its-enabled"></a><span data-ttu-id="252d2-178">有効になった縦の表示</span><span class="sxs-lookup"><span data-stu-id="252d2-178">View the vertical after it's enabled</span></span>

<span data-ttu-id="252d2-179">垂直方向を有効にした後は、表示する前にしばらく時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="252d2-179">After you enable the vertical, it might take a while before you can view it.</span></span> <span data-ttu-id="252d2-180">有効にした後に待機する必要がない場合は、 **cacheClear = true**を[SharePoint](https://sharepoint.com/)および[Office](https://office.com)の URL に追加して、すぐに垂直状態を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="252d2-180">If you don't want to wait after enabling it, you can append **cacheClear=true** to the URL in [SharePoint](https://sharepoint.com/) and [Office](https://office.com) to view the vertical immediately.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="252d2-181">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="252d2-181">Troubleshooting</span></span>

<span data-ttu-id="252d2-182">発生する可能性のある一般的な問題と、それらを修正するためのアクションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="252d2-182">Here's a list of common issues you might encounter and actions to fix them.</span></span>

|<span data-ttu-id="252d2-183">Error</span><span class="sxs-lookup"><span data-stu-id="252d2-183">Error</span></span>  |<span data-ttu-id="252d2-184">アクション</span><span class="sxs-lookup"><span data-stu-id="252d2-184">Action</span></span>  |
|---------|---------|
| <span data-ttu-id="252d2-185">垂直方向に "問題が発生しました" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="252d2-185">I see a "Something went wrong" error message on the vertical.</span></span> | <span data-ttu-id="252d2-186">セットアップを完了するには、垂直と結果の両方の種類が必要です。</span><span class="sxs-lookup"><span data-stu-id="252d2-186">Both the vertical and result types are needed to complete the setup.</span></span> <span data-ttu-id="252d2-187">同じコンテンツソースに対して両方の作成が完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="252d2-187">Make sure you have created both for the same content source.</span></span> |
| <span data-ttu-id="252d2-188">結果のレイアウトは表示されませんでしたが、作成しました。</span><span class="sxs-lookup"><span data-stu-id="252d2-188">I don't see my result layout, although I created one.</span></span> | <span data-ttu-id="252d2-189">これらの設定は一般的にキャッシュされるため、数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="252d2-189">It takes a few minutes because these settings are generally cached.</span></span> <span data-ttu-id="252d2-190">数分待ってから、もう一度実行してください。</span><span class="sxs-lookup"><span data-stu-id="252d2-190">Wait for a few minutes and try again.</span></span>        |
| <span data-ttu-id="252d2-191">[垂直または結果の種類] ページにコンテンツソースが表示されません。</span><span class="sxs-lookup"><span data-stu-id="252d2-191">I don't see any content sources on the vertical or result type page.</span></span> | <span data-ttu-id="252d2-192">コネクタとインデックスデータが構成されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="252d2-192">Make sure you have configured connectors and indexed data.</span></span>   |

## <a name="next-steps"></a><span data-ttu-id="252d2-193">次の手順</span><span class="sxs-lookup"><span data-stu-id="252d2-193">Next steps</span></span>

[<span data-ttu-id="252d2-194">手順 3: 結果のレイアウトをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="252d2-194">STEP 3: Customize the results layout</span></span>](customize-results-layout.md)
