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
description: Microsoft Search 管理ポータルのインポートツールを使用して、多くの場所を一度に追加する
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901810"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="fbcec-103">場所の一括作成</span><span class="sxs-lookup"><span data-stu-id="fbcec-103">Bulk create locations</span></span>

<span data-ttu-id="fbcec-104">.csv テンプレートをダウンロードして使用し、場所を一括で作成、編集、および保存します。</span><span class="sxs-lookup"><span data-stu-id="fbcec-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="fbcec-105">[場所] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbcec-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="fbcec-106">[**ダウンロード場所テンプレート (.csv)] を**クリックする</span><span class="sxs-lookup"><span data-stu-id="fbcec-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="fbcec-107">.csv ファイルを保存して開きます。</span><span class="sxs-lookup"><span data-stu-id="fbcec-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="fbcec-108">場所のコンテンツを追加してファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="fbcec-108">Add the location content and save the file</span></span>

    <span data-ttu-id="fbcec-109">.csv ファイルを csv utf-8 ファイルとして保存する必要があります。他のファイルの種類やエンコードにより、インポートエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbcec-109">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="fbcec-110">[場所] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbcec-110">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="fbcec-111">[場所のインポート] ウィンドウで、[**参照**] をクリックし、インポートする .csv ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="fbcec-111">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="fbcec-112">[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbcec-112">Click **Import**</span></span>

<span data-ttu-id="fbcec-113">[インポート] および [エクスポート場所] テンプレートのフィールドは同じです。</span><span class="sxs-lookup"><span data-stu-id="fbcec-113">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="fbcec-114">編集をエクスポート、一括編集、およびインポートするか、空のテンプレートで開始して新しい場所を一括作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fbcec-114">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="fbcec-115">既存の場所を一括編集するには、管理ポータルからそれらをエクスポートし、必要な編集を行ってからインポートします。</span><span class="sxs-lookup"><span data-stu-id="fbcec-115">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="fbcec-116">インポートエラーを回避する</span><span class="sxs-lookup"><span data-stu-id="fbcec-116">Prevent import errors</span></span>  
<span data-ttu-id="fbcec-117">必要なデータが不足しているか無効な場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbcec-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="fbcec-118">エラーによっては、修正する必要がある行と列に関する詳細情報を含むログファイルが生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="fbcec-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="fbcec-119">必要な編集を行ってから、もう一度ファイルをインポートしてみてください。</span><span class="sxs-lookup"><span data-stu-id="fbcec-119">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fbcec-120">すべてのエラーが解決されるまで、場所を作成または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="fbcec-120">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="fbcec-121">エラーが発生しないようにするために、インポートファイルの形式が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fbcec-121">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="fbcec-122">インポートテンプレートに含まれていたヘッダー行を含みます。</span><span class="sxs-lookup"><span data-stu-id="fbcec-122">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="fbcec-123">インポートテンプレートに含まれていたすべての列を含みます。</span><span class="sxs-lookup"><span data-stu-id="fbcec-123">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="fbcec-124">列の順序はインポートテンプレートと同じです。</span><span class="sxs-lookup"><span data-stu-id="fbcec-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="fbcec-125">これらの列は空にすることができます。 Id、last modified、last modified By、および Lat/Long</span><span class="sxs-lookup"><span data-stu-id="fbcec-125">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="fbcec-126">このフィールドが空の場合、アドレスに基づいて lat/long を決定します</span><span class="sxs-lookup"><span data-stu-id="fbcec-126">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="fbcec-127">[状態] 列を空にすることはできません。この情報は必須です。</span><span class="sxs-lookup"><span data-stu-id="fbcec-127">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="fbcec-128">[状態] フィールドに基づいて、場所が下書き、提案済み、スケジュール済み、または自動的に公開されるように保存されます。</span><span class="sxs-lookup"><span data-stu-id="fbcec-128">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="fbcec-129">また、既存の場所の Id を指定すると、インポートファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="fbcec-129">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="fbcec-130">複数のテナントを持つ組織では、あるテナントから場所をエクスポートして別のテナントにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="fbcec-130">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another.</span></span> <span data-ttu-id="fbcec-131">ただし、インポートする前に、[Id] 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbcec-131">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="fbcec-132">必須および推奨フィールドの詳細については、「[場所を追加](add-a-location.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbcec-132">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

