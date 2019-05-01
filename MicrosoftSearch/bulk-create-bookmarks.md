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
description: Microsoft Search 管理ポータルのインポートツールを使用して、多数のブックマークを一度に作成する
ms.openlocfilehash: 7c134784f0ca0d4cc84d5bce3a98f7e75aa6f441
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508620"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="3ec15-103">ブックマークの一括作成</span><span class="sxs-lookup"><span data-stu-id="3ec15-103">Bulk create bookmarks</span></span>

<span data-ttu-id="3ec15-104">.csv テンプレートをダウンロードして使用し、ブックマークを一括作成、編集、および保存します。</span><span class="sxs-lookup"><span data-stu-id="3ec15-104">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="3ec15-105">既存のブックマークを一括編集するには、管理ポータルからそれらをエクスポートし、必要な編集を行ってからインポートします。</span><span class="sxs-lookup"><span data-stu-id="3ec15-105">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="3ec15-106">[ブックマーク] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ec15-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="3ec15-107">[**ブックマークテンプレートをダウンロードする (.csv)] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="3ec15-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="3ec15-108">.csv ファイルを保存して開きます。</span><span class="sxs-lookup"><span data-stu-id="3ec15-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="3ec15-109">ブックマークの内容と設定を追加し、ファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="3ec15-109">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="3ec15-110">.csv ファイルを csv utf-8 ファイルとして保存する必要があります。他のファイルの種類やエンコードにより、インポートエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3ec15-110">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="3ec15-111">[ブックマーク] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ec15-111">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="3ec15-112">[ブックマークのインポート] ウィンドウで、[**参照**] をクリックして、インポートする .csv ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="3ec15-112">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="3ec15-113">[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3ec15-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="3ec15-114">インポートエラーを回避する</span><span class="sxs-lookup"><span data-stu-id="3ec15-114">Prevent import errors</span></span>      
<span data-ttu-id="3ec15-115">必要なデータが不足しているか無効な場合は、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ec15-115">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="3ec15-116">エラーによっては、修正する必要がある行と列に関する詳細情報を含むログファイルが生成されることがあります。</span><span class="sxs-lookup"><span data-stu-id="3ec15-116">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="3ec15-117">必要な編集を行ってから、もう一度ファイルをインポートしてみてください。</span><span class="sxs-lookup"><span data-stu-id="3ec15-117">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="3ec15-118">すべてのエラーが解決されるまで、ブックマークを作成または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ec15-118">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="3ec15-119">エラーが発生しないようにするために、インポートファイルの形式が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3ec15-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="3ec15-120">インポートテンプレートに含まれていたヘッダー行を含みます。</span><span class="sxs-lookup"><span data-stu-id="3ec15-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="3ec15-121">インポートテンプレートに含まれていたすべての列を含みます。</span><span class="sxs-lookup"><span data-stu-id="3ec15-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="3ec15-122">列の順序はインポートテンプレートと同じです。</span><span class="sxs-lookup"><span data-stu-id="3ec15-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="3ec15-123">これらの列は空にすることができます。 Id、last modified、および last modified By</span><span class="sxs-lookup"><span data-stu-id="3ec15-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="3ec15-124">[状態] 列を空にすることはできません。この情報は必須です。</span><span class="sxs-lookup"><span data-stu-id="3ec15-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="3ec15-125">[状態] フィールドに基づいて、ブックマークが下書きとして保存されるか、提案されるか、スケジュールが設定されるか、または自動的に公開されるようになります。</span><span class="sxs-lookup"><span data-stu-id="3ec15-125">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="3ec15-126">また、既存のブックマークの Id を含めると、そのブックマークはインポートファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="3ec15-126">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="3ec15-127">複数のテナントを持つ組織では、1つのテナントからブックマークをエクスポートして、別のテナントにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="3ec15-127">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="3ec15-128">ただし、インポートする前に、[Id] 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ec15-128">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="3ec15-129">必須および推奨フィールドの詳細については、「 [Create bookmarks](create-bookmarks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ec15-129">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
