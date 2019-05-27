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
description: Microsoft Search 管理ポータルのインポート ツールを使用して、一度に多くのブックマークを作成します
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968351"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="89786-103">ブックマークの一括作成</span><span class="sxs-lookup"><span data-stu-id="89786-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89786-104">Bing の Microsoft Search の設定は、Microsoft 365 管理センターで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="89786-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="89786-105">まず、管理センターで[検索管理者を割り当てる](https://docs.microsoft.com/ja-JP/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)ことから作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="89786-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="89786-106">ブックマークを一括作成、編集、および保存するには、.csv テンプレートをダウンロードして使用します。</span><span class="sxs-lookup"><span data-stu-id="89786-106">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="89786-107">既存のブックマークを一括編集するには、管理ポータルからブックマークをエクスポートし、必要な編集を行ってからインポートします。</span><span class="sxs-lookup"><span data-stu-id="89786-107">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="89786-108">[ブックマーク] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89786-108">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="89786-109">[**ブックマーク テンプレート (.csv) のダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89786-109">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="89786-110">.csv ファイルを保存して開きます。</span><span class="sxs-lookup"><span data-stu-id="89786-110">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="89786-111">ブックマークの内容と設定を追加して、ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="89786-111">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="89786-112">この .csv ファイルは、CSV UTF-8 ファイルとして保存する必要があります。その他のファイルの種類やエンコーディングでは、インポート エラーが発生する可能性があります</span><span class="sxs-lookup"><span data-stu-id="89786-112">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="89786-113">[ブックマーク] セクションの右上隅にある **[インポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="89786-113">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="89786-114">[ブックマークのインポート] ウィンドウで、**[参照]** をクリックして、インポートする .csv ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="89786-114">In the Import bookmarks pane, select **Browse** and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="89786-115">**[インポート]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="89786-115">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="89786-116">インポート エラーを回避する</span><span class="sxs-lookup"><span data-stu-id="89786-116">Prevent import errors</span></span>      
<span data-ttu-id="89786-117">必要なデータが存在しないか無効な場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="89786-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="89786-118">エラーによっては、修正の必要がある行や列に関する詳細情報が記載されたログ ファイルが生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="89786-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="89786-119">必要な編集を行い、ファイルのインポートを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="89786-119">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="89786-120">すべてのエラーが解決されるまで、いずれのブックマークも作成または編集できません。</span><span class="sxs-lookup"><span data-stu-id="89786-120">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="89786-121">エラーが発生しないように、インポート ファイルが正しく書式設定されていることに加えて、次の事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="89786-121">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="89786-122">インポート テンプレートに存在していたヘッダー行が含まれていること</span><span class="sxs-lookup"><span data-stu-id="89786-122">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="89786-123">インポート テンプレートに存在していたすべての列が含まれていること</span><span class="sxs-lookup"><span data-stu-id="89786-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="89786-124">列の順序がインポート テンプレートと同じであること</span><span class="sxs-lookup"><span data-stu-id="89786-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="89786-125">空にできる列は、「Id」、「最終更新日時」、「最終更新者」です</span><span class="sxs-lookup"><span data-stu-id="89786-125">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="89786-126">「状態」列は空にできません (この情報は必須です)</span><span class="sxs-lookup"><span data-stu-id="89786-126">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="89786-127">状態フィールドに基づいて、ブックマークは、下書き、おすすめ、スケジュール済みとして保存されるか、自動的に公開されます。</span><span class="sxs-lookup"><span data-stu-id="89786-127">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="89786-128">また、既存のフックマークの Id を含めると、インポート ファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="89786-128">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="89786-129">複数のテナントを持つ組織の場合は、テナントからエクスポートしたブックマークを別のテナントにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="89786-129">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="89786-130">ただし、インポートする前に Id 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89786-130">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="89786-131">必須フィールドと推奨フィールドの詳細については、「[ブックマークの作成](create-bookmarks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89786-131">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
