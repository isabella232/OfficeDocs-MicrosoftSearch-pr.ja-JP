---
title: 検索利用状況レポート
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
description: Microsoft 検索の利用状況レポートを確認する
ms.openlocfilehash: 96599ad18cb45feb53b3a786730a3ce506f49600
ms.sourcegitcommit: 13e52d6c66c811cc7612197ba5d8cc3598309314
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586371"
---
# <a name="microsoft-search-usage-reports"></a><span data-ttu-id="65fd3-103">Microsoft 検索の利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="65fd3-103">Microsoft Search Usage Reports</span></span>

<span data-ttu-id="65fd3-104">検索利用状況レポートを使用すると、組織内での検索の機能をより深く理解できます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-104">Search usage reports enable you to gain more understanding of how search is functioning in your organization.</span></span> <span data-ttu-id="65fd3-105">これらのレポートから生成された洞察は、 [コンテンツを検索](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) して、ユーザーにとってより便利で delightful のような操作を実行するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-105">The insights generated from these reports will help you [make content easy to find](https://docs.microsoft.com/microsoftsearch/make-content-easy-to-find) and take actions that will make search a more useful and delightful experience for your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65fd3-106">Microsoft 検索利用状況レポートは現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="65fd3-106">Microsoft Search usage reports are currently in preview.</span></span>

<span data-ttu-id="65fd3-107">[Microsoft 検索使用状況レポート](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights)には、SharePoint ホームおよび Office.com 検索ボックスから実行される検索から生成されたグラフとテーブルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="65fd3-107">The [Microsoft Search usage reports](https://admin.microsoft.com/Adminportal/Home?#/MicrosoftSearch/insights) include graphs and tables generated from searches that are executed from SharePoint Home and Office.com search boxes.</span></span> <span data-ttu-id="65fd3-108">前月の過去31日間、1日、または毎月のデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-108">You can see data from the past 31 days, per day, or monthly for the previous year.</span></span> <span data-ttu-id="65fd3-109">これらのレポートは、履歴データの見越計上に時間がかかるように、ロールアウトされています。</span><span class="sxs-lookup"><span data-stu-id="65fd3-109">These reports are just rolling out so it will take time to accrue the historical data.</span></span>

<span data-ttu-id="65fd3-110">このページの以前のバージョンには、Bing.com で Bing で Microsoft Search に対して実行された検索からのデータが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="65fd3-110">A previous version of this page included data from searches executed for Microsoft Search in Bing on Bing.com.</span></span> <span data-ttu-id="65fd3-111">そのデータはすぐにこれらのレポートに統合されますが、現時点では、ページの下部にあるリンクをクリックして **Bing の上位のクエリとインプレッション配布を表示** することで、これらのレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-111">That data will be integrated into these reports soon, but for now, you can still see those reports by clicking the link at the bottom of the page to **View Bing's top queries and impression distribution**.</span></span>

![検索利用状況レポートダッシュボード](media/usage-reports/usage_reports_v2.png)

## <a name="overview-of-search-reports"></a><span data-ttu-id="65fd3-113">検索レポートの概要</span><span class="sxs-lookup"><span data-stu-id="65fd3-113">Overview of search reports</span></span>

|<span data-ttu-id="65fd3-114">**レポート**</span><span class="sxs-lookup"><span data-stu-id="65fd3-114">**Report**</span></span>|<span data-ttu-id="65fd3-115">**説明**</span><span class="sxs-lookup"><span data-stu-id="65fd3-115">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65fd3-116">クエリボリューム</span><span class="sxs-lookup"><span data-stu-id="65fd3-116">Query Volume</span></span>|<span data-ttu-id="65fd3-117">このレポートには、実行された検索クエリの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-117">This report shows the number of search queries performed.</span></span> <span data-ttu-id="65fd3-118">このレポートを使用して、検索クエリのボリュームの傾向を特定し、検索アクティビティの高および低期間を特定します。</span><span class="sxs-lookup"><span data-stu-id="65fd3-118">Use this report to identify search query volume trends and to determine periods of high and low search activity.</span></span>|
|<span data-ttu-id="65fd3-119">よく使用されるクエリ</span><span class="sxs-lookup"><span data-stu-id="65fd3-119">Top Queries</span></span>|<span data-ttu-id="65fd3-120">このレポートには、最も人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-120">This report shows the most popular search queries.</span></span> <span data-ttu-id="65fd3-121">このレポートを使用して、ユーザーが検索している情報の種類を把握します。</span><span class="sxs-lookup"><span data-stu-id="65fd3-121">Use this report to understand what types of information your users are searching for.</span></span>|
|<span data-ttu-id="65fd3-122">破棄したクエリ</span><span class="sxs-lookup"><span data-stu-id="65fd3-122">Abandoned Queries</span></span>|<span data-ttu-id="65fd3-123">このレポートには、クリックスルーを低頻度で受信する人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-123">This report shows popular search queries that receive low click-through.</span></span> <span data-ttu-id="65fd3-124">このレポートを使用して、ユーザー満足度の低い可能性のある検索クエリを特定し、コンテンツの検出可能性を改善します。</span><span class="sxs-lookup"><span data-stu-id="65fd3-124">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="65fd3-125">その後で、ブックマークなどの回答を作成するか、グラフコネクタを使用して新しいコンテンツを取り込むするかを決定できます。これは、適切な操作です。</span><span class="sxs-lookup"><span data-stu-id="65fd3-125">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|
|<span data-ttu-id="65fd3-126">結果なしのクエリ</span><span class="sxs-lookup"><span data-stu-id="65fd3-126">No Results Queries</span></span>|<span data-ttu-id="65fd3-127">このレポートには、結果を返さなかった人気の高い検索クエリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-127">This report shows popular search queries that returned no results.</span></span> <span data-ttu-id="65fd3-128">このレポートを使用して、ユーザー満足度の低い可能性のある検索クエリを特定し、コンテンツの検出可能性を改善します。</span><span class="sxs-lookup"><span data-stu-id="65fd3-128">Use this report to identify search queries that might create user dissatisfaction and to improve the discoverability of content.</span></span> <span data-ttu-id="65fd3-129">その後で、ブックマークなどの回答を作成するか、グラフコネクタを使用して新しいコンテンツを取り込むするかを決定できます。これは、適切な操作です。</span><span class="sxs-lookup"><span data-stu-id="65fd3-129">You can then determine if creating an answer, like a Bookmark, or ingesting new content through a Graph connector is the right action.</span></span>|

## <a name="viewing-reports"></a><span data-ttu-id="65fd3-130">レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="65fd3-130">Viewing reports</span></span>

<span data-ttu-id="65fd3-131">[利用状況レポート] ページに移動すると、すべてのレポートを表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="65fd3-131">When you navigate to the usage reports page, all the reports are available to view.</span></span> <span data-ttu-id="65fd3-132">日付フィルターを使用して、表示する特定の日または月を選択できます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-132">You can use the date filter to pick a specific day or month to view.</span></span>

<span data-ttu-id="65fd3-133">レポートをダウンロードすることにより、より幅広い期間のレポートを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-133">Downloading a report will allow you to see reports from a broader range of time.</span></span> <span data-ttu-id="65fd3-134">ダウンロードする矢印をクリックし、[ **過去31日間** ] または [ **過去12か月**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="65fd3-134">Click on the download arrow and select **past 31 days** or **past 12 months**.</span></span> <span data-ttu-id="65fd3-135">レポートは、Excel スプレッドシートとしてダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-135">The report downloads as an Excel spreadsheet.</span></span> <span data-ttu-id="65fd3-136">過去31日間を選択した場合、スプレッドシートには、各日の個別のタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-136">If you selected past 31 days, the spreadsheet will have am individual tab for each day.</span></span> <span data-ttu-id="65fd3-137">過去12か月間のダウンロードには、毎月1つのタブが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-137">The past 12 months download will have a tab for each month.</span></span>

<span data-ttu-id="65fd3-138">Bing の上位のクエリおよびインプレッション配布レポートを表示するには、ページ上のリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="65fd3-138">To view Bing’s top queries and impression distribution reports click on the link on the page.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="65fd3-139">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="65fd3-139">Frequently asked questions</span></span>

<span data-ttu-id="65fd3-140">**過去31日間または過去12か月を選択したときに、それぞれ特定の日または特定の月を選択する必要があるのはなぜですか。**</span><span class="sxs-lookup"><span data-stu-id="65fd3-140">**When I select past 31 days or past 12 months, why do I then have to choose a specific day or specific month respectively.**</span></span>

<span data-ttu-id="65fd3-141">Microsoft search 利用状況レポートの今日の予定表ビューは、2段階のプロセスです。</span><span class="sxs-lookup"><span data-stu-id="65fd3-141">The calendar view today in Microsoft search usage reports is a two-step process.</span></span> <span data-ttu-id="65fd3-142">最初にドロップダウンから日付範囲 (過去31日間または過去12か月) を選択してから、開始日または月を選択します。</span><span class="sxs-lookup"><span data-stu-id="65fd3-142">first select the date range from the dropdown (past 31 days or past 12 months) and then select the start day or month.</span></span>

<span data-ttu-id="65fd3-143">Top、放棄、および failed のクエリテーブルでは、選択した日または月の結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-143">The top, abandoned, and failed query tables show results from either the day or the month you choose.</span></span>

<span data-ttu-id="65fd3-144">**どのような場合に過去7日間、過去30日間の集計データが表示されます。 Bing の上位クエリレポートのようになりますか?**</span><span class="sxs-lookup"><span data-stu-id="65fd3-144">**When will I see aggregate data for past 7 days, past 30 days, etc. like Bing’s top queries reports?**</span></span>

<span data-ttu-id="65fd3-145">この種の集約を検討しており、今後のバージョンのレポートでデータ範囲フィルター処理を簡素化しています。</span><span class="sxs-lookup"><span data-stu-id="65fd3-145">We are considering this type of aggregation and simplifying the data range filtering for future versions of these reports.</span></span>

<span data-ttu-id="65fd3-146">**利用状況レポートの内訳を異なるアプリ (ソース) ごとに表示できないのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="65fd3-146">**Why can’t I see a breakdown of usage reports by different apps (sources)?**</span></span>

<span data-ttu-id="65fd3-147">現在、ソースによるフィルターは使用できません。</span><span class="sxs-lookup"><span data-stu-id="65fd3-147">Currently, filtering by source is not available.</span></span> <span data-ttu-id="65fd3-148">これらのレポートは、SharePoint Home と Office.com の検索を組み合わせたものです。</span><span class="sxs-lookup"><span data-stu-id="65fd3-148">The reports combine searches from SharePoint Home and Office.com.</span></span> <span data-ttu-id="65fd3-149">次のリリースにはソースフィルターが組み込まれているため、各アプリケーションに固有の測定値を確認できます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-149">Our next release will include source filtering so you can see metrics specific to each application.</span></span>

<span data-ttu-id="65fd3-150">**利用状況レポートに関するその他のフィルター処理**</span><span class="sxs-lookup"><span data-stu-id="65fd3-150">**What other filtering for usage reports is coming?**</span></span>

<span data-ttu-id="65fd3-151">組織のより詳細なレベルでの検索の使用法を理解するために役立つ追加のフィルターを使用しています。</span><span class="sxs-lookup"><span data-stu-id="65fd3-151">We are working on additional filters that will help make sense of search usage at a more granular level of your organization.</span></span> <span data-ttu-id="65fd3-152">たとえば、特定の地域または部署のクエリボリュームを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-152">For example, you will be able to see query volume for a specific geography or department.</span></span>

<span data-ttu-id="65fd3-153">**Bing レポートでの Microsoft 検索が別のページにあるのはなぜですか?**</span><span class="sxs-lookup"><span data-stu-id="65fd3-153">**Why are the Microsoft Search in Bing reports on a separate page?**</span></span>

<span data-ttu-id="65fd3-154">モダン化 search in Office 365 applications for Microsoft Search では、レポートの生成を含む以前に分散したシステムに参加する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="65fd3-154">Modernizing search in Office 365 applications to Microsoft Search has required us to join previously disparate systems, including the reports generation.</span></span> <span data-ttu-id="65fd3-155">これには時間がかかるので、Bing データの統合が完了するまで待機することによって、今まで以上のレポートを取得することが重要であると考えています。</span><span class="sxs-lookup"><span data-stu-id="65fd3-155">This takes time and we felt it was more important to get these reports out now versus waiting until we could complete the integration of the Bing data.</span></span> <span data-ttu-id="65fd3-156">統合が完了すると、すべての検索エンドポイントのデータが同じレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="65fd3-156">Once we complete the integration, the data from all search endpoints will be included in the same reports.</span></span>
