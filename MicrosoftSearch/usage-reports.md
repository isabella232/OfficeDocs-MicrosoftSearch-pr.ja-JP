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
ms.openlocfilehash: ad349e60794f219fa757861081b12a33c6806091
ms.sourcegitcommit: 25b82bce1eaec5803111161b04ee9fd9e82a0bd8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50072241"
---
# <a name="microsoft-search-usage-reports"></a><span data-ttu-id="c9d36-103">Microsoft Search 利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="c9d36-103">Microsoft Search Usage Reports</span></span>

<span data-ttu-id="c9d36-104">検索利用状況レポートを使用すると、検索が組織でどのように機能しているのかをより深く理解できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-104">Search usage reports enable you to gain more understanding of how search is functioning in your organization.</span></span> <span data-ttu-id="c9d36-105">これらのレポートから生成された分析情報は、コンテンツ[](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find)を見つけやすくし、ユーザーにとってより便利で楽しいエクスペリエンスを提供するアクションを実行するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-105">The insights generated from these reports will help you [make content easy to find](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) and take actions that will make search a more useful and delightful experience for your users.</span></span>

<span data-ttu-id="c9d36-106">[Microsoft Search の利用状況レポートには](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights)、SharePoint Home から実行された検索から生成されたグラフとテーブル、および検索ボックスOffice.comが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-106">The [Microsoft Search usage reports](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) include graphs and tables generated from searches that are executed from SharePoint Home and Office.com search boxes.</span></span> <span data-ttu-id="c9d36-107">過去 31 日間のデータ、1 日あたりのデータ、または前年の月単位のデータを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-107">You can see data from the past 31 days, per day, or monthly for the previous year.</span></span> <span data-ttu-id="c9d36-108">これらのレポートは展開中なので、履歴データの収集に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c9d36-108">These reports are just rolling out so it will take time to accrue the historical data.</span></span>

<span data-ttu-id="c9d36-109">このページの以前のバージョンには、Web サイトの Bing で Microsoft Search に対して実行された検索のデータBing.com。</span><span class="sxs-lookup"><span data-stu-id="c9d36-109">A previous version of this page included data from searches executed for Microsoft Search in Bing on Bing.com.</span></span> <span data-ttu-id="c9d36-110">そのデータは間もなくこれらのレポートに統合されますが、現時点では、ページの下部にあるリンクをクリックして **Bing** の上位クエリとインプレッション分布を表示することで、これらのレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-110">That data will be integrated into these reports soon, but for now, you can still see those reports by clicking the link at the bottom of the page to **View Bing's top queries and impression distribution**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c9d36-111">![検索利用状況レポート ダッシュボード](media/usage-reports/usage_reports_v2.png)</span><span class="sxs-lookup"><span data-stu-id="c9d36-111">![Search usage reports dashboard](media/usage-reports/usage_reports_v2.png)</span></span>

## <a name="overview-of-search-reports"></a><span data-ttu-id="c9d36-112">検索レポートの概要</span><span class="sxs-lookup"><span data-stu-id="c9d36-112">Overview of search reports</span></span>

| <span data-ttu-id="c9d36-113">レポート</span><span class="sxs-lookup"><span data-stu-id="c9d36-113">Report</span></span> | <span data-ttu-id="c9d36-114">説明</span><span class="sxs-lookup"><span data-stu-id="c9d36-114">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="c9d36-115">クエリ ボリューム</span><span class="sxs-lookup"><span data-stu-id="c9d36-115">Query Volume</span></span>|<span data-ttu-id="c9d36-116">このレポートには、実行された検索クエリの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-116">This report shows the number of search queries performed.</span></span> <span data-ttu-id="c9d36-117">このレポートを使用して、検索クエリの量の傾向を特定し、検索アクティビティの高い期間と低い期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="c9d36-117">Use this report to identify search query volume trends and to determine periods of high and low search activity.</span></span>|
|<span data-ttu-id="c9d36-118">よく使用されるクエリ</span><span class="sxs-lookup"><span data-stu-id="c9d36-118">Top Queries</span></span>|<span data-ttu-id="c9d36-119">このレポートには、最も人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-119">This report shows the most popular search queries.</span></span> <span data-ttu-id="c9d36-120">このレポートを使用して、ユーザーが検索している情報の種類を把握します。</span><span class="sxs-lookup"><span data-stu-id="c9d36-120">Use this report to understand what types of information your users are searching for.</span></span>|
|<span data-ttu-id="c9d36-121">破棄されたクエリ</span><span class="sxs-lookup"><span data-stu-id="c9d36-121">Abandoned Queries</span></span>|<span data-ttu-id="c9d36-122">このレポートには、低クリックスルーを受け取る一般的な検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-122">This report shows popular search queries that receive low click-through.</span></span> <span data-ttu-id="c9d36-123">このレポートを使用して、ユーザー満足度の低い可能性のある検索クエリを特定し、コンテンツの検出可能性を改善します。</span><span class="sxs-lookup"><span data-stu-id="c9d36-123">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="c9d36-124">その後、ブックマークのような回答を作成するか、Graph コネクタを介して新しいコンテンツを取り込むのが正しいアクションかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-124">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|
|<span data-ttu-id="c9d36-125">結果のクエリなし</span><span class="sxs-lookup"><span data-stu-id="c9d36-125">No Results Queries</span></span>|<span data-ttu-id="c9d36-126">このレポートには、結果を返さなかった人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-126">This report shows popular search queries that returned no results.</span></span> <span data-ttu-id="c9d36-127">このレポートを使用して、ユーザー満足度の低い可能性のある検索クエリを特定し、コンテンツの検出可能性を改善します。</span><span class="sxs-lookup"><span data-stu-id="c9d36-127">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="c9d36-128">その後、ブックマークのような回答を作成するか、Graph コネクタを使用して新しいコンテンツを取り込むのが適切なアクションかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-128">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|

## <a name="viewing-reports"></a><span data-ttu-id="c9d36-129">レポートの表示</span><span class="sxs-lookup"><span data-stu-id="c9d36-129">Viewing reports</span></span>

<span data-ttu-id="c9d36-130">[利用状況レポート] ページに移動すると、すべてのレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-130">When you navigate to the usage reports page, all the reports are available to view.</span></span> <span data-ttu-id="c9d36-131">日付フィルターを使用して、表示する特定の日または月を選択できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-131">You can use the date filter to pick a specific day or month to view.</span></span>

<span data-ttu-id="c9d36-132">レポートをダウンロードすると、広範な時間からレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-132">Downloading a report will allow you to see reports from a broader range of time.</span></span> <span data-ttu-id="c9d36-133">ダウンロード矢印をクリックし、 **過去 31 日間または過去** 12 か月 **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="c9d36-133">Click on the download arrow and select **past 31 days** or **past 12 months**.</span></span> <span data-ttu-id="c9d36-134">レポートは Excel スプレッドシートとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-134">The report downloads as an Excel spreadsheet.</span></span> <span data-ttu-id="c9d36-135">過去 31 日間を選択した場合、スプレッドシートには日ごとに個別のタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-135">If you selected past 31 days, the spreadsheet will have an individual tab for each day.</span></span> <span data-ttu-id="c9d36-136">過去 12 か月間のダウンロードでは、各月のタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-136">The past 12 months download will have a tab for each month.</span></span>

<span data-ttu-id="c9d36-137">Bing の上位クエリとインプレッション分布レポートを表示するには、ページ上のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c9d36-137">To view Bing’s top queries and impression distribution reports click on the link on the page.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c9d36-138">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="c9d36-138">Frequently asked questions</span></span>

<span data-ttu-id="c9d36-139">**過去 31 日間または過去 12 か月を選択した場合、特定の日または特定の月を選択する必要がある理由を説明します。**</span><span class="sxs-lookup"><span data-stu-id="c9d36-139">**When I select past 31 days or past 12 months, why do I then have to choose a specific day or specific month.**</span></span>

<span data-ttu-id="c9d36-140">Microsoft Search 利用状況レポートのカレンダー ビューは、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="c9d36-140">The calendar view, today, in Microsoft search usage reports is a two-step process.</span></span> <span data-ttu-id="c9d36-141">最初にドロップダウンから日付範囲 (過去 31 日間または過去 12 か月) を選択し、開始日または月を選択します。</span><span class="sxs-lookup"><span data-stu-id="c9d36-141">First select the date range from the dropdown (past 31 days or past 12 months) and then select the start day or month.</span></span>

<span data-ttu-id="c9d36-142">上位、破棄、および失敗したクエリ テーブルには、選択した日または月の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-142">The top, abandoned, and failed query tables show results from either the day or the month you choose.</span></span>

<span data-ttu-id="c9d36-143">**過去 7 日間、過去 30 日間などの集計データがいつ表示されます。Bing の上位クエリ レポートのように**</span><span class="sxs-lookup"><span data-stu-id="c9d36-143">**When will I see aggregate data for past 7 days, past 30 days, etc... like Bing’s top queries reports?**</span></span>

<span data-ttu-id="c9d36-144">この種の集計を検討し、これらのレポートの将来のバージョンのデータ範囲フィルター処理を簡略化しています。</span><span class="sxs-lookup"><span data-stu-id="c9d36-144">We are considering this type of aggregation and simplifying the data range filtering for future versions of these reports.</span></span>

<span data-ttu-id="c9d36-145">**別のアプリ (ソース) による使用状況レポートの内訳が表示できない理由**</span><span class="sxs-lookup"><span data-stu-id="c9d36-145">**Why can’t I see a breakdown of usage reports by different apps (sources)?**</span></span>

<span data-ttu-id="c9d36-146">現在、ソースによるフィルター処理は使用できません。</span><span class="sxs-lookup"><span data-stu-id="c9d36-146">Currently, filtering by source is not available.</span></span> <span data-ttu-id="c9d36-147">レポートは、SharePoint Home からの検索と検索を組み合Office.com。</span><span class="sxs-lookup"><span data-stu-id="c9d36-147">The reports combine searches from SharePoint Home and Office.com.</span></span> <span data-ttu-id="c9d36-148">次のリリースには、各アプリケーションに固有の指標を確認できるソース フィルターが含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-148">Our next release will include source filtering so you can see metrics specific to each application.</span></span>

<span data-ttu-id="c9d36-149">**利用状況レポートのその他のフィルター処理は予定されていますか?**</span><span class="sxs-lookup"><span data-stu-id="c9d36-149">**What other filtering for usage reports is coming?**</span></span>

<span data-ttu-id="c9d36-150">組織のより詳細なレベルで検索の使用状況を意味する追加のフィルターに取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="c9d36-150">We are working on additional filters that will help make sense of search usage at a more granular level of your organization.</span></span> <span data-ttu-id="c9d36-151">たとえば、特定の地域または部門のクエリ ボリュームを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-151">For example, you will be able to see query volume for a specific geography or department.</span></span>

<span data-ttu-id="c9d36-152">**Bing の Microsoft Search レポートが別のページに表示される理由**</span><span class="sxs-lookup"><span data-stu-id="c9d36-152">**Why is the Microsoft Search in Bing reports on a separate page?**</span></span>

<span data-ttu-id="c9d36-153">Office 365 アプリケーションの検索を Microsoft Search にモダン化するには、レポート生成を含め、以前はさまざまなシステムに参加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d36-153">Modernizing search in Office 365 applications to Microsoft Search has required us to join previously disparate systems, including the reports generation.</span></span> <span data-ttu-id="c9d36-154">これには時間がかかるので、Bing データの統合を完了するまで待機するよりも、これらのレポートを今すぐ取り出す方が重要だと感じていました。</span><span class="sxs-lookup"><span data-stu-id="c9d36-154">This takes time and we felt it was more important to get these reports out now versus waiting until we could complete the integration of the Bing data.</span></span> <span data-ttu-id="c9d36-155">統合が完了すると、すべての検索エンドポイントのデータが同じレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="c9d36-155">Once we complete the integration, the data from all search endpoints will be included in the same reports.</span></span>
