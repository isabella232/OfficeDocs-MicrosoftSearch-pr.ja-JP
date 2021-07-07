---
title: 検索使用状況レポート
ms.author: ankmis
author: jeffkizn
manager: parulm
ms.topic: article
ms.service: mssearch
audience: Admin
ms.audience: Admin
ms.date: 07/02/2021
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 使用状況Microsoft Search確認する
ms.openlocfilehash: 83a2d895ac251affdd5e1c9ea3b0d0fffcecc5a4
ms.sourcegitcommit: 36a699554bfe9debdb9a33e942597cceb575666b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2021
ms.locfileid: "53285560"
---
# <a name="microsoft-search-usage-reports"></a><span data-ttu-id="41753-103">Microsoft Search利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="41753-103">Microsoft Search Usage Reports</span></span>

<span data-ttu-id="41753-104">検索利用状況レポートを使用すると、組織内での検索の機能を理解できます。</span><span class="sxs-lookup"><span data-stu-id="41753-104">Search usage reports enable you to gain more understanding of how search is functioning in your organization.</span></span> <span data-ttu-id="41753-105">これらのレポートから生成された分析情報は、コンテンツ[](./make-content-easy-to-find.md)を簡単に見つけてアクションを実行し、ユーザーにとって検索をより便利で楽しいエクスペリエンスにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="41753-105">The insights generated from these reports will help you [make content easy to find](./make-content-easy-to-find.md) and take actions that will make search a more useful and delightful experience for your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41753-106">Microsoft Searchレポートは現在プレビュー中です</span><span class="sxs-lookup"><span data-stu-id="41753-106">Microsoft Search usage reports are currently in preview</span></span>

<span data-ttu-id="41753-107">Microsoft Search[使用状況](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights)レポートには、SharePoint Home、Office.com、および Bing 検索ボックスで Microsoft Search から実行される検索から生成されたグラフとテーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="41753-107">The [Microsoft Search usage reports](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) include graphs and tables generated from searches that are executed from SharePoint Home, Office.com, and Microsoft Search in Bing search boxes.</span></span> <span data-ttu-id="41753-108">過去 31 日、1 日、または前の年の月次のデータを確認できます。</span><span class="sxs-lookup"><span data-stu-id="41753-108">You can see data from the past 31 days, per day, or monthly for the previous year.</span></span> <span data-ttu-id="41753-109">これらのレポートは展開されているだけなので、履歴データの発生に時間がかかっています。</span><span class="sxs-lookup"><span data-stu-id="41753-109">These reports are just rolling out so it will take time to accrue the historical data.</span></span>

<span data-ttu-id="41753-110">このページの以前のバージョンには、Microsoft Search.com のBing検索Bing含まれていました。</span><span class="sxs-lookup"><span data-stu-id="41753-110">A previous version of this page included data from searches executed only for Microsoft Search in Bing on Bing.com.</span></span> <span data-ttu-id="41753-111">このデータは、これらのレポートに統合されました。ページの下部にあるリンクをクリックして、ページのトップ クエリとインプレッション配布Bingを表示 **できます。**</span><span class="sxs-lookup"><span data-stu-id="41753-111">That data is now integrated into these reports; you can still see the old page by clicking the link at the bottom of the page to **View Bing's top queries and impression distribution**.</span></span> <span data-ttu-id="41753-112">このリンクと古いページは近日削除されます。</span><span class="sxs-lookup"><span data-stu-id="41753-112">This link and the old page will be removed soon.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41753-113">![使用状況レポートのダッシュボードの検索](media/usage-reports/usage_reports_v2.png)</span><span class="sxs-lookup"><span data-stu-id="41753-113">![Search usage reports dashboard](media/usage-reports/usage_reports_v2.png)</span></span>

## <a name="overview-of-search-reports"></a><span data-ttu-id="41753-114">検索レポートの概要</span><span class="sxs-lookup"><span data-stu-id="41753-114">Overview of search reports</span></span>

| <span data-ttu-id="41753-115">レポート</span><span class="sxs-lookup"><span data-stu-id="41753-115">Report</span></span> | <span data-ttu-id="41753-116">説明</span><span class="sxs-lookup"><span data-stu-id="41753-116">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="41753-117">クエリ ボリューム</span><span class="sxs-lookup"><span data-stu-id="41753-117">Query Volume</span></span>|<span data-ttu-id="41753-118">このレポートには、実行された検索クエリの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41753-118">This report shows the number of search queries performed.</span></span> <span data-ttu-id="41753-119">このレポートを使用して、検索クエリのボリュームの傾向を特定し、検索アクティビティの高い期間と低い期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="41753-119">Use this report to identify search query volume trends and to determine periods of high and low search activity.</span></span>|
|<span data-ttu-id="41753-120">よく使用されるクエリ</span><span class="sxs-lookup"><span data-stu-id="41753-120">Top Queries</span></span>|<span data-ttu-id="41753-121">このレポートには、最も人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41753-121">This report shows the most popular search queries.</span></span> <span data-ttu-id="41753-122">クエリは、結果をクリックして少なくとも 3 回検索すると、このレポートに追加されます。</span><span class="sxs-lookup"><span data-stu-id="41753-122">A query is added to this report when it is searched at least three times with a click on a result.</span></span> <span data-ttu-id="41753-123">このレポートを使用して、ユーザーが検索している情報の種類を把握します。</span><span class="sxs-lookup"><span data-stu-id="41753-123">Use this report to understand what types of information your users are searching for.</span></span>|
|<span data-ttu-id="41753-124">破棄されたクエリ</span><span class="sxs-lookup"><span data-stu-id="41753-124">Abandoned Queries</span></span>|<span data-ttu-id="41753-125">このレポートには、低クリックスルーを受け取る一般的な検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41753-125">This report shows popular search queries that receive low click-through.</span></span> <span data-ttu-id="41753-126">このレポートを使用して、ユーザー満足度の低い可能性のある検索クエリを特定し、コンテンツの検出可能性を改善します。</span><span class="sxs-lookup"><span data-stu-id="41753-126">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="41753-127">その後、ブックマークのような回答を作成するか、新しいコンテンツを新しいコネクタを介して取り込Graphが正しいアクションかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="41753-127">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|
|<span data-ttu-id="41753-128">結果クエリなし</span><span class="sxs-lookup"><span data-stu-id="41753-128">No Results Queries</span></span>|<span data-ttu-id="41753-129">このレポートには、結果を返さなかった人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="41753-129">This report shows popular search queries that returned no results.</span></span> <span data-ttu-id="41753-130">このレポートを使用して、ユーザー満足度の低い可能性のある検索クエリを特定し、コンテンツの検出可能性を改善します。</span><span class="sxs-lookup"><span data-stu-id="41753-130">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="41753-131">その後、ブックマークのような回答を作成するか、新しいコンテンツを新しいコネクタを介して取り込Graphが正しいアクションかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="41753-131">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|

>[!NOTE]
><span data-ttu-id="41753-132">現在、ブックマークのような回答で満たされたクエリが放棄されたクエリとしてカウントされる既知の問題があります。</span><span class="sxs-lookup"><span data-stu-id="41753-132">There is currently a known issue where queries satisfied by an answer like a Bookmark are counted as an abandoned query.</span></span>

## <a name="viewing-reports"></a><span data-ttu-id="41753-133">レポートの表示</span><span class="sxs-lookup"><span data-stu-id="41753-133">Viewing reports</span></span>

<span data-ttu-id="41753-134">[利用状況レポート] ページに移動すると、すべてのレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="41753-134">When you navigate to the usage reports page, all the reports are available to view.</span></span> <span data-ttu-id="41753-135">日付フィルターを使用して、表示する特定の日または月を選択できます。</span><span class="sxs-lookup"><span data-stu-id="41753-135">You can use the date filter to pick a specific day or month to view.</span></span>

<span data-ttu-id="41753-136">レポートをダウンロードすると、より広範な時間からレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="41753-136">Downloading a report will allow you to see reports from a broader range of time.</span></span> <span data-ttu-id="41753-137">ダウンロード矢印をクリックして、 **過去 31** 日または過去 **12 か月を選択します**。</span><span class="sxs-lookup"><span data-stu-id="41753-137">Click on the download arrow and select **past 31 days** or **past 12 months**.</span></span> <span data-ttu-id="41753-138">レポートは、スプレッドシートとしてExcelされます。</span><span class="sxs-lookup"><span data-stu-id="41753-138">The report downloads as an Excel spreadsheet.</span></span> <span data-ttu-id="41753-139">過去 31 日間を選択した場合、スプレッドシートには各日の個別のタブがあります。</span><span class="sxs-lookup"><span data-stu-id="41753-139">If you selected past 31 days, the spreadsheet will have an individual tab for each day.</span></span> <span data-ttu-id="41753-140">過去 12 か月のダウンロードには、各月のタブがあります。</span><span class="sxs-lookup"><span data-stu-id="41753-140">The past 12 months download will have a tab for each month.</span></span>

<span data-ttu-id="41753-141">ユーザーのBingとインプレッション配布レポートを表示するには、ページのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="41753-141">To view Bing’s top queries and impression distribution reports click on the link on the page.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="41753-142">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="41753-142">Frequently asked questions</span></span>

<span data-ttu-id="41753-143">**過去 31 日間または過去 12 か月を選択した場合、特定の日または特定の月を選択する必要がある理由。**</span><span class="sxs-lookup"><span data-stu-id="41753-143">**When I select past 31 days or past 12 months, why do I then have to choose a specific day or specific month.**</span></span>

<span data-ttu-id="41753-144">今日の Microsoft 検索利用状況レポートの予定表ビューは、2 段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="41753-144">The calendar view, today, in Microsoft search usage reports is a two-step process.</span></span> <span data-ttu-id="41753-145">最初にドロップダウン (過去 31 日または過去 12 か月) から日付範囲を選択し、開始日または月を選択します。</span><span class="sxs-lookup"><span data-stu-id="41753-145">First select the date range from the dropdown (past 31 days or past 12 months) and then select the start day or month.</span></span>

<span data-ttu-id="41753-146">上位、破棄、および失敗したクエリ テーブルには、選択した日または月の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="41753-146">The top, abandoned, and failed query tables show results from either the day or the month you choose.</span></span>

<span data-ttu-id="41753-147">**過去 7 日間、過去 30 日間の集計データが表示される場合などです。Bingのトップ クエリ レポートのように?**</span><span class="sxs-lookup"><span data-stu-id="41753-147">**When will I see aggregate data for past 7 days, past 30 days, and so on...like Bing’s top queries reports?**</span></span>

<span data-ttu-id="41753-148">この種類の集約を検討し、将来のバージョンのこれらのレポートのデータ範囲フィルター処理を簡略化しています。</span><span class="sxs-lookup"><span data-stu-id="41753-148">We are considering this type of aggregation and simplifying the data range filtering for future versions of these reports.</span></span>

<span data-ttu-id="41753-149">**異なるアプリ (ソース) による利用状況レポートの内訳が表示できない理由**</span><span class="sxs-lookup"><span data-stu-id="41753-149">**Why can’t I see a breakdown of usage reports by different apps (sources)?**</span></span>

<span data-ttu-id="41753-150">現在、ソースによるフィルター処理は使用できません。</span><span class="sxs-lookup"><span data-stu-id="41753-150">Currently, filtering by source is not available.</span></span> <span data-ttu-id="41753-151">レポートは、ホーム と SharePoint.com からのOfficeを組み合わせます。</span><span class="sxs-lookup"><span data-stu-id="41753-151">The reports combine searches from SharePoint Home and Office.com.</span></span> <span data-ttu-id="41753-152">次のリリースでは、ソース フィルターが含まれるので、各アプリケーションに固有の指標を確認できます。</span><span class="sxs-lookup"><span data-stu-id="41753-152">Our next release will include source filtering so you can see metrics specific to each application.</span></span>

<span data-ttu-id="41753-153">**利用状況レポートのその他のフィルター処理が予定されていますか?**</span><span class="sxs-lookup"><span data-stu-id="41753-153">**What other filtering for usage reports is coming?**</span></span>

<span data-ttu-id="41753-154">組織のより詳細なレベルで検索の使用状況を知るのに役立つ追加のフィルターに取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="41753-154">We are working on additional filters that will help make sense of search usage at a more granular level of your organization.</span></span> <span data-ttu-id="41753-155">たとえば、特定の地域または部署のクエリ ボリュームを表示できます。</span><span class="sxs-lookup"><span data-stu-id="41753-155">For example, you will be able to see query volume for a specific geography or department.</span></span>
