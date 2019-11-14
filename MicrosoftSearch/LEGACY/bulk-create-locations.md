---
title: 場所の一括作成
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
ROBOTS: NoIndex
description: Microsoft Search 管理ポータルのインポートツールを使用して、多くの場所を一度に追加する
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311769"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="0f259-103">場所の一括作成</span><span class="sxs-lookup"><span data-stu-id="0f259-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f259-104">この記事は、Bing 管理ポータルの Microsoft Search に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0f259-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="0f259-105">ポータルを Microsoft 365 管理センターに移動していますので、後で Bing ポータルの Microsoft Search は削除されます。</span><span class="sxs-lookup"><span data-stu-id="0f259-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="0f259-106">Microsoft 365 管理センターを使用して作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f259-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="0f259-107">[Microsoft Search の概要](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="0f259-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="0f259-108">.Csv テンプレートをダウンロードして使用し、場所を一括で作成、編集、および保存します。</span><span class="sxs-lookup"><span data-stu-id="0f259-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="0f259-109">[場所] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f259-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="0f259-110">[**ダウンロード場所テンプレート (.csv)] を**クリックする</span><span class="sxs-lookup"><span data-stu-id="0f259-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="0f259-111">.csv ファイルを保存して開きます</span><span class="sxs-lookup"><span data-stu-id="0f259-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="0f259-112">場所のコンテンツを追加してファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="0f259-112">Add the location content and save the file</span></span>

    <span data-ttu-id="0f259-113">この .csv ファイルは、CSV UTF-8 ファイルとして保存する必要があります。その他のファイルの種類やエンコーディングでは、インポート エラーが発生する可能性があります</span><span class="sxs-lookup"><span data-stu-id="0f259-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="0f259-114">[場所] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f259-114">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="0f259-115">[場所のインポート] ウィンドウで、[**参照**] をクリックし、インポートする .csv ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="0f259-115">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="0f259-116">**[インポート]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="0f259-116">Click **Import**</span></span>

<span data-ttu-id="0f259-117">[インポート] および [エクスポート場所] テンプレートのフィールドは同じです。</span><span class="sxs-lookup"><span data-stu-id="0f259-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="0f259-118">編集をエクスポート、一括編集、およびインポートするか、空のテンプレートで開始して新しい場所を一括作成することができます。</span><span class="sxs-lookup"><span data-stu-id="0f259-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="0f259-119">既存の場所を一括編集するには、管理ポータルからそれらをエクスポートし、必要な編集を行ってからインポートします。</span><span class="sxs-lookup"><span data-stu-id="0f259-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="0f259-120">インポート エラーを回避する</span><span class="sxs-lookup"><span data-stu-id="0f259-120">Prevent import errors</span></span>  
<span data-ttu-id="0f259-121">必要なデータが存在しないか無効な場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="0f259-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="0f259-122">エラーによっては、修正の必要がある行や列に関する詳細情報が記載されたログ ファイルが生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0f259-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="0f259-123">必要な編集を行い、ファイルのインポートを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="0f259-123">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f259-124">すべてのエラーが解決されるまで、場所を作成または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="0f259-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="0f259-125">エラーが発生しないように、インポート ファイルが正しく書式設定されていることに加えて、次の事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0f259-125">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="0f259-126">インポート テンプレートに存在していたヘッダー行が含まれていること</span><span class="sxs-lookup"><span data-stu-id="0f259-126">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="0f259-127">インポート テンプレートに存在していたすべての列が含まれていること</span><span class="sxs-lookup"><span data-stu-id="0f259-127">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="0f259-128">列の順序がインポート テンプレートと同じであること</span><span class="sxs-lookup"><span data-stu-id="0f259-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="0f259-129">これらの列は空にすることができます。 Id、Last Modified、Last Modified By、および Lat/Long</span><span class="sxs-lookup"><span data-stu-id="0f259-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="0f259-130">このフィールドが空の場合、アドレスに基づいて lat/long を決定します</span><span class="sxs-lookup"><span data-stu-id="0f259-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="0f259-131">「状態」列は空にできません (この情報は必須です)</span><span class="sxs-lookup"><span data-stu-id="0f259-131">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="0f259-132">[状態] フィールドに基づいて、場所が下書き、提案済み、スケジュール済み、または自動的に公開されるように保存されます。</span><span class="sxs-lookup"><span data-stu-id="0f259-132">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="0f259-133">また、既存の場所の Id を指定すると、インポートファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="0f259-133">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="0f259-134">複数の組織を管理するパートナーは、1つの組織からの場所をエクスポートして、別の組織にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f259-134">For partners who manage multiple organizations, you can export your locations from one org and import them into another.</span></span> <span data-ttu-id="0f259-135">ただし、インポートする前に Id 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f259-135">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="0f259-136">必須および推奨フィールドの詳細については、「[場所を追加](add-a-location.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f259-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

