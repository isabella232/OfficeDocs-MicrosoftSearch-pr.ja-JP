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
description: Microsoft Search 管理ポータルのインポート ツールを使用して、一度に多数の場所を追加
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968293"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="3907f-103">場所の一括作成</span><span class="sxs-lookup"><span data-stu-id="3907f-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3907f-104">Bing の Microsoft Search の設定は、Microsoft 365 管理センターで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3907f-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3907f-105">まず、管理センターで[検索管理者を割り当てる](https://docs.microsoft.com/ja-JP/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)ことから作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="3907f-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="3907f-106">場所の情報を一括作成、編集、および保存するには、.csv テンプレートをダウンロードして使用します。</span><span class="sxs-lookup"><span data-stu-id="3907f-106">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="3907f-107">[場所] セクションの右上にある **[インポート]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="3907f-107">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="3907f-108">**[場所テンプレート (.csv) のダウンロード]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="3907f-108">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="3907f-109">.csv ファイルを保存して開きます</span><span class="sxs-lookup"><span data-stu-id="3907f-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="3907f-110">場所の内容を追加してファイルを保存します</span><span class="sxs-lookup"><span data-stu-id="3907f-110">Add the location content and save the file</span></span>

    <span data-ttu-id="3907f-111">この .csv ファイルは、CSV UTF-8 ファイルとして保存する必要があります。その他のファイルの種類やエンコーディングでは、インポート エラーが発生する可能性があります</span><span class="sxs-lookup"><span data-stu-id="3907f-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="3907f-112">[場所] セクションの右上にある **[インポート]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="3907f-112">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="3907f-113">[場所のインポート] ウィンドウで、**[参照]** をクリックしてインポートする .csv ファイルに移動します</span><span class="sxs-lookup"><span data-stu-id="3907f-113">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="3907f-114">**[インポート]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="3907f-114">Click **Import**.</span></span>

<span data-ttu-id="3907f-115">場所のインポートおよびエクスポート テンプレートのフィールドは同じです。</span><span class="sxs-lookup"><span data-stu-id="3907f-115">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="3907f-116">場所の情報をエクスポートして一括編集し、編集したものをインポートするか、空のテンプレートから開始して新しい場所を一括作成します。</span><span class="sxs-lookup"><span data-stu-id="3907f-116">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="3907f-117">既存の場所を一括編集するには、管理ポータルから場所の情報をエクスポートして、必要な編集を加えてからインポートします。</span><span class="sxs-lookup"><span data-stu-id="3907f-117">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="3907f-118">インポート エラーを回避する</span><span class="sxs-lookup"><span data-stu-id="3907f-118">Prevent import errors</span></span>  
<span data-ttu-id="3907f-119">必要なデータが存在しないか無効な場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3907f-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="3907f-120">エラーによっては、修正の必要がある行や列に関する詳細情報が記載されたログ ファイルが生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="3907f-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="3907f-121">必要な編集を行い、ファイルのインポートを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="3907f-121">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3907f-122">すべてのエラーが解決されるまで、場所の作成または編集はできません。</span><span class="sxs-lookup"><span data-stu-id="3907f-122">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="3907f-123">エラーが発生しないように、インポート ファイルが正しく書式設定されていることに加えて、次の事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="3907f-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="3907f-124">インポート テンプレートに存在していたヘッダー行が含まれていること</span><span class="sxs-lookup"><span data-stu-id="3907f-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="3907f-125">インポート テンプレートに存在していたすべての列が含まれていること</span><span class="sxs-lookup"><span data-stu-id="3907f-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="3907f-126">列の順序がインポート テンプレートと同じであること</span><span class="sxs-lookup"><span data-stu-id="3907f-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="3907f-127">空にできる列は、「Id」、「最終更新日時」、「最終更新者」、および「緯度/経度」です</span><span class="sxs-lookup"><span data-stu-id="3907f-127">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="3907f-128">このフィールドが空の場合は、住所に基づいて緯度/経度の決定が試行されます</span><span class="sxs-lookup"><span data-stu-id="3907f-128">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="3907f-129">「状態」列は空にできません (この情報は必須です)</span><span class="sxs-lookup"><span data-stu-id="3907f-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="3907f-130">状態フィールドに基づいて、場所の情報は、下書き、おすすめ、スケジュール済みとして保存されるか、自動的に公開されます。</span><span class="sxs-lookup"><span data-stu-id="3907f-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="3907f-131">また、既存の場所の Id を含めると、インポート ファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="3907f-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="3907f-132">複数のテナントを持つ組織の場合は、テナントからエクスポートした場所の情報を別のテナントにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="3907f-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="3907f-133">ただし、インポートする前に Id 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3907f-133">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="3907f-134">必須フィールドと推奨フィールドの詳細については、「[場所の追加](add-a-location.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3907f-134">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

