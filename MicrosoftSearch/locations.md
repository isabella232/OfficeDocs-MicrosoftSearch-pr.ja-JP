---
title: 場所
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 2379e72c-a7da-4e3f-932a-12d431a0a284
description: Microsoft Search の作業結果に組織の場所の情報を含めるすべての方法についての概要
ms.openlocfilehash: bcda64315f85b9770f47d1b6c08fd90296063487
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968461"
---
# <a name="locations"></a><span data-ttu-id="d0ff9-103">場所</span><span class="sxs-lookup"><span data-stu-id="d0ff9-103">Locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d0ff9-104">Bing の Microsoft Search の設定は、Microsoft 365 管理センターで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d0ff9-105">まず、管理センターで[検索管理者を割り当てる](https://docs.microsoft.com/ja-JP/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)ことから作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
## <a name="add-locations"></a><span data-ttu-id="d0ff9-106">場所の追加</span><span class="sxs-lookup"><span data-stu-id="d0ff9-106">Add federated locations</span></span>

<span data-ttu-id="d0ff9-107">場所の情報は、ユーザーが組織の建物やオフィスなどの作業空間の住所を調べて、地図で位置を特定する際に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-107">Find addresses and locate your organization's buildings, offices, and other workspaces on a map</span></span> <span data-ttu-id="d0ff9-108">ユーザーは Bing 地図を使用して、道順を調べたり、近所に何があるかを確認したりできます。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-108">They can also use Bing Maps to get directions, see what's nearby, and more.</span></span>
  
- [<span data-ttu-id="d0ff9-109">場所の追加</span><span class="sxs-lookup"><span data-stu-id="d0ff9-109">Add a location</span></span>](add-a-location.md)
    
    <span data-ttu-id="d0ff9-110">建物、オフィス、キャンパスなどの作業空間を追加します</span><span class="sxs-lookup"><span data-stu-id="d0ff9-110">Add a building, office, campus, or other workspace</span></span>
    
- [<span data-ttu-id="d0ff9-111">場所の一括作成</span><span class="sxs-lookup"><span data-stu-id="d0ff9-111">Bulk create locations</span></span>](bulk-create-locations.md)
    
    <span data-ttu-id="d0ff9-112">場所の情報を .csv ファイルに追加して、一括でインポートします</span><span class="sxs-lookup"><span data-stu-id="d0ff9-112">Add locations to a .csv file and bulk import them</span></span>
    
## <a name="manage-locations"></a><span data-ttu-id="d0ff9-113">場所の管理</span><span class="sxs-lookup"><span data-stu-id="d0ff9-113">Manage locations</span></span>

<span data-ttu-id="d0ff9-114">場所の状態、フィルタリング ツール、および一括エクスポート/インポート ツールを使用して、住所と地名を含む[場所の情報を検索および更新](manage-locations.md)します</span><span class="sxs-lookup"><span data-stu-id="d0ff9-114">Use the location status, filtering tools, and bulk export/import tools to [find and update locations](manage-locations.md), including address and location name</span></span>
  
## <a name="location-status"></a><span data-ttu-id="d0ff9-115">場所の状態</span><span class="sxs-lookup"><span data-stu-id="d0ff9-115">Location status</span></span>

<span data-ttu-id="d0ff9-116">管理ポータルでは、現在の状態ごとに場所の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-116">In the Admin portal, you can view locations by their current status:</span></span>
  
- <span data-ttu-id="d0ff9-117">公開済み</span><span class="sxs-lookup"><span data-stu-id="d0ff9-117">Published</span></span>
    
    <span data-ttu-id="d0ff9-118">公開済みの場所の情報は、承認されたユーザーがキーワードを検索すると、Bing の検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-118">Published locations appear in Bing search results when an authorized user searches for a keyword.</span></span>
    
- <span data-ttu-id="d0ff9-119">下書き</span><span class="sxs-lookup"><span data-stu-id="d0ff9-119">Draft</span></span>
    
    <span data-ttu-id="d0ff9-120">場所の情報は、公開する準備ができていない場合、下書きとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-120">If a location isn't ready to publish, save it as a draft.</span></span> <span data-ttu-id="d0ff9-121">下書きの場所は、Bing に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-121">Draft locations will not appear on Bing.</span></span>
    
- <span data-ttu-id="d0ff9-122">スケジュール済み</span><span class="sxs-lookup"><span data-stu-id="d0ff9-122">Scheduled</span></span>
    
    <span data-ttu-id="d0ff9-123">スケジュール済みの場所の情報は、将来の日付で自動的に公開されます。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-123">Scheduled locations are automatically published on a future date.</span></span>
    
- <span data-ttu-id="d0ff9-124">期限切れ</span><span class="sxs-lookup"><span data-stu-id="d0ff9-124">Expired</span></span>
    
    <span data-ttu-id="d0ff9-125">期限切れの場所の情報は、その期限切れ日に基づいて、公開されたコンテンツから自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-125">Expired locations were automatically removed from published content based on their expiration dates.</span></span>
    
- <span data-ttu-id="d0ff9-126">おすすめ</span><span class="sxs-lookup"><span data-stu-id="d0ff9-126">Suggested Meetings</span></span>
    
    <span data-ttu-id="d0ff9-127">おすすめの場所の情報は、ユーザーからのフィードバックに基づいています。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-127">Suggested locations are based on feedback from users.</span></span> <span data-ttu-id="d0ff9-128">Microsoft からの既定の候補が表示されることもあります。</span><span class="sxs-lookup"><span data-stu-id="d0ff9-128">You may also see default suggestions from Microsoft.</span></span>

  

