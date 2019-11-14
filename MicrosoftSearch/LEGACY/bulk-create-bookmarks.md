---
title: ブックマークの一括作成
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Microsoft Search 管理ポータルのインポートツールを使用して、多数のブックマークを一度に作成する
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311785"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="31d46-103">ブックマークの一括作成</span><span class="sxs-lookup"><span data-stu-id="31d46-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31d46-104">この記事は、Bing 管理ポータルの Microsoft Search に適用されます。</span><span class="sxs-lookup"><span data-stu-id="31d46-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="31d46-105">ポータルを Microsoft 365 管理センターに移動していますので、後で Bing ポータルの Microsoft Search は削除されます。</span><span class="sxs-lookup"><span data-stu-id="31d46-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="31d46-106">Microsoft 365 管理センターを使用して作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31d46-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="31d46-107">[Microsoft Search の概要](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="31d46-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="31d46-108">.Csv テンプレートをダウンロードして使用し、ブックマークを一括作成、編集、および保存します。</span><span class="sxs-lookup"><span data-stu-id="31d46-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="31d46-109">既存のブックマークを一括編集するには、管理ポータルからそれらをエクスポートし、必要な編集を行ってからインポートします。</span><span class="sxs-lookup"><span data-stu-id="31d46-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="31d46-110">[ブックマーク] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31d46-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="31d46-111">[**ブックマークテンプレートをダウンロードする (.csv)] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="31d46-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="31d46-112">.csv ファイルを保存して開きます</span><span class="sxs-lookup"><span data-stu-id="31d46-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="31d46-113">ブックマークの内容と設定を追加し、ファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="31d46-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="31d46-114">この .csv ファイルは、CSV UTF-8 ファイルとして保存する必要があります。その他のファイルの種類やエンコーディングでは、インポート エラーが発生する可能性があります</span><span class="sxs-lookup"><span data-stu-id="31d46-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="31d46-115">[ブックマーク] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31d46-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="31d46-116">[ブックマークのインポート] ウィンドウで、[**参照**] をクリックして、インポートする .csv ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="31d46-116">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="31d46-117">**[インポート]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="31d46-117">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="31d46-118">インポート エラーを回避する</span><span class="sxs-lookup"><span data-stu-id="31d46-118">Prevent import errors</span></span>      
<span data-ttu-id="31d46-119">必要なデータが存在しないか無効な場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="31d46-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="31d46-120">エラーによっては、修正の必要がある行や列に関する詳細情報が記載されたログ ファイルが生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="31d46-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="31d46-121">必要な編集を行い、ファイルのインポートを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="31d46-121">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="31d46-122">すべてのエラーが解決されるまで、ブックマークを作成または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="31d46-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="31d46-123">エラーが発生しないように、インポート ファイルが正しく書式設定されていることに加えて、次の事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="31d46-123">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="31d46-124">インポート テンプレートに存在していたヘッダー行が含まれていること</span><span class="sxs-lookup"><span data-stu-id="31d46-124">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="31d46-125">インポート テンプレートに存在していたすべての列が含まれていること</span><span class="sxs-lookup"><span data-stu-id="31d46-125">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="31d46-126">列の順序がインポート テンプレートと同じであること</span><span class="sxs-lookup"><span data-stu-id="31d46-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="31d46-127">空にできる列は、「Id」、「最終更新日時」、「最終更新者」です</span><span class="sxs-lookup"><span data-stu-id="31d46-127">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="31d46-128">「状態」列は空にできません (この情報は必須です)</span><span class="sxs-lookup"><span data-stu-id="31d46-128">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="31d46-129">状態フィールドに基づいて、ブックマークは、下書き、おすすめ、スケジュール済みとして保存されるか、自動的に公開されます。</span><span class="sxs-lookup"><span data-stu-id="31d46-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="31d46-130">また、既存のブックマークの Id を含めると、そのブックマークはインポートファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="31d46-130">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="31d46-131">複数の組織を管理するパートナーは、1つの組織からブックマークをエクスポートして、別の組織にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="31d46-131">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="31d46-132">ただし、インポートする前に Id 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31d46-132">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="31d46-133">必須および推奨フィールドの詳細については、「 [Create bookmarks](create-bookmarks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31d46-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
