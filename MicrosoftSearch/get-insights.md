---
title: Microsoft Search Insights ダッシュボードレポート
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: ebce7fdc-e89b-473c-8131-67e659bb3f73
description: Microsoft Search の insights ダッシュボードから測定値を分析し、コンテンツを管理する
ms.openlocfilehash: d75622ad8c414f225615ea14082c8197e2947dd4
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626875"
---
# <a name="microsoft-search-insights-dashboard-reports"></a><span data-ttu-id="df72d-103">Microsoft Search Insights ダッシュボードレポート</span><span class="sxs-lookup"><span data-stu-id="df72d-103">Microsoft Search Insights dashboard reports</span></span>

<span data-ttu-id="df72d-104">Microsoft Search insights ダッシュボードを使用して、発行された回答の Bing データを管理できます。</span><span class="sxs-lookup"><span data-stu-id="df72d-104">You can use the Microsoft Search insights dashboard to manage the Bing data for your published answers.</span></span> <span data-ttu-id="df72d-105">これは、ユーザーがコンテンツを簡単に[見つけられるよう](make-content-easy-to-find.md)にするために必要な手順の1つにすぎません。</span><span class="sxs-lookup"><span data-stu-id="df72d-105">This is just one of the steps needed to [make content easy to find](make-content-easy-to-find.md) for your users.</span></span>

<span data-ttu-id="df72d-106">Microsoft 365 管理センターで最初に Microsoft Search に移動すると、Insights ダッシュボードにが入力されます。</span><span class="sxs-lookup"><span data-stu-id="df72d-106">When you first go to Microsoft Search in the Microsoft 365 admin center, you'll enter on the Insights dashboard.</span></span>

![Insights-dashboard](media/Insights-dashboard.png)

<span data-ttu-id="df72d-108">ここでは、insights ダッシュボードで使用可能なレポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="df72d-108">Here are the reports that are available on the insights dashboard.</span></span>

> [!NOTE]
> <span data-ttu-id="df72d-109">レポート内のデータは、Bing データのみを表します。</span><span class="sxs-lookup"><span data-stu-id="df72d-109">The data in the reports only represents Bing data.</span></span>

## <a name="top-queries"></a><span data-ttu-id="df72d-110">よく使用されるクエリ</span><span class="sxs-lookup"><span data-stu-id="df72d-110">Top queries</span></span>

<span data-ttu-id="df72d-111">このレポートでは、ユーザーが実行する上位の 2000 Bing 検索クエリについての詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="df72d-111">This report gives details about the top 2000 Bing search queries that users run.</span></span> <span data-ttu-id="df72d-112">クエリを**上位のクエリ**に表示するには、クエリは少なくとも3回のクリックを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="df72d-112">For a query to appear in **Top queries**, the query must get at least three clicks.</span></span>

![上位のクエリは、テーブルの見出しと共にレポートします。クエリ、クエリの合計数、およびクリックの頻度です。](media/Insights-topqueries.png)

<span data-ttu-id="df72d-114">ユーザーが検索しているものを見つけないことを意味するのは、クリックスルーレート (CTR) です。</span><span class="sxs-lookup"><span data-stu-id="df72d-114">A low click-through rate (CTR) means that users aren’t finding what they’re looking for.</span></span>

<span data-ttu-id="df72d-115">回答の種類に基づいてフィルター処理することで、レポートのさまざまなビューを選択できます。</span><span class="sxs-lookup"><span data-stu-id="df72d-115">You can choose different views of the report by filtering on the type of answer.</span></span> <span data-ttu-id="df72d-116">たとえば、ブックマークの上位のクエリを表示する場合は、レポートの右上隅にあるドロップダウンを選択し、[**ブックマーク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df72d-116">For example if you just want to view the top queries for Bookmarks, select the drop-down in the upper-right corner of the report, and then select **Bookmarks**.</span></span> <span data-ttu-id="df72d-117">既定では、**すべて**の応答の種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df72d-117">By default, **All** answer types are shown.</span></span>

![ブックマーク、ユーザー、Q&A、ファイル、グループ、場所、会話、サイトによって上位のクエリレポートをフィルター処理する](media/Insights-topqueries-dropdown.png)

## <a name="impression-distribution"></a><span data-ttu-id="df72d-119">インプレッションの分布</span><span class="sxs-lookup"><span data-stu-id="df72d-119">Impression distribution</span></span>

<span data-ttu-id="df72d-120">このレポートでは、さまざまな回答に関して Bing でのインプレッション分布が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df72d-120">This report shows impression distribution in Bing over time for various answers.</span></span> <span data-ttu-id="df72d-121">ブックマーク、ユーザー、Q&A、ファイル、場所、ファイルサイト、グループ、会話などがあります。</span><span class="sxs-lookup"><span data-stu-id="df72d-121">Examples are bookmarks, people, Q&A, files, locations, file sites, groups, and conversations.</span></span> 

![期間として90日が選択されたインプレッションレポート。](media/Insights-impressions.png)

<span data-ttu-id="df72d-123">インプレッション配布は、指定された期間中にユーザーが検索する内容を管理者が理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="df72d-123">Impression Distribution can help admins understand what users look for during a specified period.</span></span>
