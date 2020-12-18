---
title: 検索使用状況レポート
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の利用状況レポートを確認する
ms.openlocfilehash: 04de0de08423eff1368bc2b77e48d3fc8add038d
ms.sourcegitcommit: 1d6fcf180f427abf3d8bfa4b8b6129e39f60ceb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712613"
---
# <a name="microsoft-search-usage-reports"></a><span data-ttu-id="fdd02-103">Microsoft Search 利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="fdd02-103">Microsoft Search Usage Reports</span></span>

<span data-ttu-id="fdd02-104">検索利用状況レポートを使用すると、検索が組織でどのように機能しているのかをより深く理解できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-104">Search usage reports enable you to gain more understanding of how search is functioning in your organization.</span></span> <span data-ttu-id="fdd02-105">これらのレポートから生成された分析情報は、コンテンツ[](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find)を見つけやすくし、ユーザーにとってより便利で楽しいエクスペリエンスを提供するアクションを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-105">The insights generated from these reports will help you [make content easy to find](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) and take actions that will make search a more useful and delightful experience for your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fdd02-106">Microsoft Search 利用状況レポートは現在プレビュー中で、対象指定リリースの管理者に展開されています。</span><span class="sxs-lookup"><span data-stu-id="fdd02-106">Microsoft Search usage reports are currently in preview and rolling out to admins in Targeted Release.</span></span> <span data-ttu-id="fdd02-107">これらのレポートを表示するには、管理者アカウントが対象のリリース リングに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdd02-107">Ensure your admin account is in the targeted release ring to see these reports.</span></span>

<span data-ttu-id="fdd02-108">[Microsoft Search の利用状況レポートには](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights)、SharePoint Home から実行された検索から生成されたグラフとテーブル、および検索ボックスOffice.comが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-108">The [Microsoft Search usage reports](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) include graphs and tables generated from searches that are executed from SharePoint Home and Office.com search boxes.</span></span> <span data-ttu-id="fdd02-109">過去 31 日間のデータ、1 日あたりのデータ、または前年の月単位のデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-109">You can see data from the past 31 days, per day, or monthly for the previous year.</span></span> <span data-ttu-id="fdd02-110">これらのレポートは展開中なので、履歴データの収集に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="fdd02-110">These reports are just rolling out so it will take time to accrue the historical data.</span></span>

<span data-ttu-id="fdd02-111">このページの以前のバージョンには、Web サイトの Bing で Microsoft Search に対して実行された検索のデータBing.com。</span><span class="sxs-lookup"><span data-stu-id="fdd02-111">A previous version of this page included data from searches executed for Microsoft Search in Bing on Bing.com.</span></span> <span data-ttu-id="fdd02-112">そのデータは間もなくこれらのレポートに統合されますが、現時点では、ページの下部にあるリンクをクリックして **Bing** の上位クエリとインプレッション分布を表示することで、これらのレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-112">That data will be integrated into these reports soon, but for now, you can still see those reports by clicking the link at the bottom of the page to **View Bing's top queries and impression distribution**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fdd02-113">![検索利用状況レポート ダッシュボード](media/usage-reports/usage_reports_v2.png)</span><span class="sxs-lookup"><span data-stu-id="fdd02-113">![Search usage reports dashboard](media/usage-reports/usage_reports_v2.png)</span></span>


## <a name="overview-of-search-reports"></a><span data-ttu-id="fdd02-114">検索レポートの概要</span><span class="sxs-lookup"><span data-stu-id="fdd02-114">Overview of search reports</span></span>

| <span data-ttu-id="fdd02-115">レポート</span><span class="sxs-lookup"><span data-stu-id="fdd02-115">Report</span></span> | <span data-ttu-id="fdd02-116">説明</span><span class="sxs-lookup"><span data-stu-id="fdd02-116">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="fdd02-117">クエリ ボリューム</span><span class="sxs-lookup"><span data-stu-id="fdd02-117">Query Volume</span></span>|<span data-ttu-id="fdd02-118">このレポートには、実行された検索クエリの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-118">This report shows the number of search queries performed.</span></span> <span data-ttu-id="fdd02-119">このレポートを使用して、検索クエリの量の傾向を特定し、検索アクティビティの高い期間と低い期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="fdd02-119">Use this report to identify search query volume trends and to determine periods of high and low search activity.</span></span>|
|<span data-ttu-id="fdd02-120">よく使用されるクエリ</span><span class="sxs-lookup"><span data-stu-id="fdd02-120">Top Queries</span></span>|<span data-ttu-id="fdd02-121">このレポートには、最も人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-121">This report shows the most popular search queries.</span></span> <span data-ttu-id="fdd02-122">このレポートを使用して、ユーザーが検索している情報の種類を把握します。</span><span class="sxs-lookup"><span data-stu-id="fdd02-122">Use this report to understand what types of information your users are searching for.</span></span>|
|<span data-ttu-id="fdd02-123">破棄されたクエリ</span><span class="sxs-lookup"><span data-stu-id="fdd02-123">Abandoned Queries</span></span>|<span data-ttu-id="fdd02-124">このレポートには、低クリックスルーを受け取る人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-124">This report shows popular search queries that receive low click-through.</span></span> <span data-ttu-id="fdd02-125">このレポートを使用して、ユーザー満足度の低い可能性のある検索クエリを特定し、コンテンツの検出可能性を改善します。</span><span class="sxs-lookup"><span data-stu-id="fdd02-125">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="fdd02-126">その後、ブックマークのような回答を作成するか、Graph コネクタを使用して新しいコンテンツを取り込むのが適切なアクションかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-126">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|
|<span data-ttu-id="fdd02-127">結果のクエリなし</span><span class="sxs-lookup"><span data-stu-id="fdd02-127">No Results Queries</span></span>|<span data-ttu-id="fdd02-128">このレポートには、結果を返さなかった人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-128">This report shows popular search queries that returned no results.</span></span> <span data-ttu-id="fdd02-129">このレポートを使用して、ユーザー満足度の低い可能性のある検索クエリを特定し、コンテンツの検出可能性を改善します。</span><span class="sxs-lookup"><span data-stu-id="fdd02-129">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="fdd02-130">その後、ブックマークのような回答を作成するか、Graph コネクタを介して新しいコンテンツを取り込むのが正しいアクションかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-130">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|

## <a name="viewing-reports"></a><span data-ttu-id="fdd02-131">レポートの表示</span><span class="sxs-lookup"><span data-stu-id="fdd02-131">Viewing reports</span></span>

<span data-ttu-id="fdd02-132">[利用状況レポート] ページに移動すると、すべてのレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-132">When you navigate to the usage reports page, all the reports are available to view.</span></span> <span data-ttu-id="fdd02-133">日付フィルターを使用して、表示する特定の日または月を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-133">You can use the date filter to pick a specific day or month to view.</span></span>

<span data-ttu-id="fdd02-134">レポートをダウンロードすると、広範な時間からレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-134">Downloading a report will allow you to see reports from a broader range of time.</span></span> <span data-ttu-id="fdd02-135">ダウンロード矢印をクリックし、 **過去 31 日間または過去** 12 か月 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fdd02-135">Click on the download arrow and select **past 31 days** or **past 12 months**.</span></span> <span data-ttu-id="fdd02-136">レポートは Excel スプレッドシートとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-136">The report downloads as an Excel spreadsheet.</span></span> <span data-ttu-id="fdd02-137">過去 31 日間を選択した場合、スプレッドシートには日ごとに個別のタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-137">If you selected past 31 days, the spreadsheet will have an individual tab for each day.</span></span> <span data-ttu-id="fdd02-138">過去 12 か月間のダウンロードでは、各月のタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-138">The past 12 months download will have a tab for each month.</span></span>

<span data-ttu-id="fdd02-139">Bing の上位クエリとインプレッション分布レポートを表示するには、ページ上のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdd02-139">To view Bing’s top queries and impression distribution reports click on the link on the page.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="fdd02-140">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="fdd02-140">Frequently asked questions</span></span>

<span data-ttu-id="fdd02-141">**過去 31 日間または過去 12 か月を選択した場合、特定の日または特定の月を選択する必要がある理由を説明します。**</span><span class="sxs-lookup"><span data-stu-id="fdd02-141">**When I select past 31 days or past 12 months, why do I then have to choose a specific day or specific month.**</span></span>

<span data-ttu-id="fdd02-142">Microsoft Search 利用状況レポートのカレンダー ビューは、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="fdd02-142">The calendar view, today, in Microsoft search usage reports is a two-step process.</span></span> <span data-ttu-id="fdd02-143">最初にドロップダウンから日付範囲 (過去 31 日間または過去 12 か月) を選択し、開始日または月を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdd02-143">First select the date range from the dropdown (past 31 days or past 12 months) and then select the start day or month.</span></span>

<span data-ttu-id="fdd02-144">上位、破棄、および失敗したクエリ テーブルには、選択した日または月の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-144">The top, abandoned, and failed query tables show results from either the day or the month you choose.</span></span>

<span data-ttu-id="fdd02-145">**過去 7 日間、過去 30 日間などの集計データがいつ表示されます。Bing の上位クエリ レポートのように**</span><span class="sxs-lookup"><span data-stu-id="fdd02-145">**When will I see aggregate data for past 7 days, past 30 days, etc... like Bing’s top queries reports?**</span></span>

<span data-ttu-id="fdd02-146">この種の集計を検討し、これらのレポートの将来のバージョンのデータ範囲フィルター処理を簡略化しています。</span><span class="sxs-lookup"><span data-stu-id="fdd02-146">We are considering this type of aggregation and simplifying the data range filtering for future versions of these reports.</span></span>

<span data-ttu-id="fdd02-147">**さまざまなアプリ (ソース) による利用状況レポートの内訳が表示できない理由**</span><span class="sxs-lookup"><span data-stu-id="fdd02-147">**Why can’t I see a breakdown of usage reports by different apps (sources)?**</span></span>

<span data-ttu-id="fdd02-148">現在、ソースによるフィルター処理は使用できません。</span><span class="sxs-lookup"><span data-stu-id="fdd02-148">Currently, filtering by source is not available.</span></span> <span data-ttu-id="fdd02-149">レポートは、SharePoint Home からの検索と検索を組み合Office.com。</span><span class="sxs-lookup"><span data-stu-id="fdd02-149">The reports combine searches from SharePoint Home and Office.com.</span></span> <span data-ttu-id="fdd02-150">次のリリースには、各アプリケーションに固有の指標を確認できるソース フィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-150">Our next release will include source filtering so you can see metrics specific to each application.</span></span>

<span data-ttu-id="fdd02-151">**利用状況レポートのその他のフィルター処理は予定されていますか?**</span><span class="sxs-lookup"><span data-stu-id="fdd02-151">**What other filtering for usage reports is coming?**</span></span>

<span data-ttu-id="fdd02-152">組織のより詳細なレベルで検索の使用を意味する追加のフィルターに取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="fdd02-152">We are working on additional filters that will help make sense of search usage at a more granular level of your organization.</span></span> <span data-ttu-id="fdd02-153">たとえば、特定の地域または部門のクエリ ボリュームを表示できます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-153">For example, you will be able to see query volume for a specific geography or department.</span></span>

<span data-ttu-id="fdd02-154">**Bing の Microsoft Search レポートが別のページに表示される理由**</span><span class="sxs-lookup"><span data-stu-id="fdd02-154">**Why is the Microsoft Search in Bing reports on a separate page?**</span></span>

<span data-ttu-id="fdd02-155">Office 365 アプリケーションの検索を Microsoft Search にモダン化するには、レポート生成を含め、以前はさまざまなシステムに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fdd02-155">Modernizing search in Office 365 applications to Microsoft Search has required us to join previously disparate systems, including the reports generation.</span></span> <span data-ttu-id="fdd02-156">これには時間がかかるので、Bing データの統合を完了するまで待機するよりも、これらのレポートを今すぐ取り出す方が重要だと感じていました。</span><span class="sxs-lookup"><span data-stu-id="fdd02-156">This takes time and we felt it was more important to get these reports out now versus waiting until we could complete the integration of the Bing data.</span></span> <span data-ttu-id="fdd02-157">統合が完了すると、すべての検索エンドポイントのデータが同じレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="fdd02-157">Once we complete the integration, the data from all search endpoints will be included in the same reports.</span></span>
