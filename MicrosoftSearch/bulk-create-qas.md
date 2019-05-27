---
title: Q&A の一括作成
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
description: Microsoft Search 管理ポータルのインポート ツールを使用して、よく寄せられる質問への回答をすばやく追加します
ms.openlocfilehash: f535cb7ae843def536976cb1f05c8601de592cbb
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968307"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="6b125-103">Q&A の一括作成</span><span class="sxs-lookup"><span data-stu-id="6b125-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b125-104">Bing の Microsoft Search の設定は、Microsoft 365 管理センターで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6b125-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6b125-105">まず、管理センターで[検索管理者を割り当てる](https://docs.microsoft.com/ja-JP/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)ことから作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="6b125-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="6b125-106">.csv テンプレートをダウンロードして使用し、Q&A を一括作成または一括編集します。</span><span class="sxs-lookup"><span data-stu-id="6b125-106">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="6b125-107">これは、編集や更新が必要な Q&A を一括で下書き保存する簡単な方法でもあります。</span><span class="sxs-lookup"><span data-stu-id="6b125-107">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="6b125-108">既存の Q&A を一括編集するには、管理ポータルからエクスポートし、必要な編集を行ってからインポートします。</span><span class="sxs-lookup"><span data-stu-id="6b125-108">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="6b125-109">[Q&A] セクションの右上部分で、[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b125-109">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="6b125-110">[**Q&A テンプレート (.csv) をダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b125-110">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="6b125-111">.csv ファイルを保存して開きます</span><span class="sxs-lookup"><span data-stu-id="6b125-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="6b125-112">Q&A のコンテンツと設定を追加して、ファイルを保存します</span><span class="sxs-lookup"><span data-stu-id="6b125-112">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="6b125-113">この .csv ファイルは、CSV UTF-8 ファイルとして保存する必要があります。その他のファイルの種類やエンコーディングでは、インポート エラーが発生する可能性があります</span><span class="sxs-lookup"><span data-stu-id="6b125-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="6b125-114">[Q&A] セクションの右上部分で、**[インポート]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="6b125-114">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="6b125-115">[Q&A のインポート] ウィンドウで、**[参照]** をクリックしてインポートする .csv ファイルに移動します</span><span class="sxs-lookup"><span data-stu-id="6b125-115">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="6b125-116">**[インポート]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="6b125-116">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="6b125-117">インポート エラーを回避する</span><span class="sxs-lookup"><span data-stu-id="6b125-117">Prevent import errors</span></span>      
<span data-ttu-id="6b125-118">必要なデータが存在しないか無効な場合は、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6b125-118">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="6b125-119">エラーによっては、修正の必要がある行や列に関する詳細情報が記載されたログ ファイルが生成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b125-119">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="6b125-120">必要な編集を行い、ファイルのインポートを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="6b125-120">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="6b125-121">すべてのエラーが解決されるまで、Q&A の作成または編集はできません。</span><span class="sxs-lookup"><span data-stu-id="6b125-121">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="6b125-122">エラーが発生しないように、インポート ファイルが正しく書式設定されていることに加えて、次の事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6b125-122">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="6b125-123">インポート テンプレートに存在していたヘッダー行が含まれていること</span><span class="sxs-lookup"><span data-stu-id="6b125-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="6b125-124">インポート テンプレートに存在していたすべての列が含まれていること</span><span class="sxs-lookup"><span data-stu-id="6b125-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="6b125-125">列の順序がインポート テンプレートと同じであること</span><span class="sxs-lookup"><span data-stu-id="6b125-125">The column order is the same as the import template</span></span>
- <span data-ttu-id="6b125-126">空にできる列は、「Id」、「最終更新日時」、「最終更新者」です</span><span class="sxs-lookup"><span data-stu-id="6b125-126">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="6b125-127">「状態」列は空にできません (この情報は必須です)</span><span class="sxs-lookup"><span data-stu-id="6b125-127">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="6b125-128">状態フィールドに基づいて、Q&A は、下書き、おすすめ、スケジュール済みとして保存されるか、自動的に公開されます。</span><span class="sxs-lookup"><span data-stu-id="6b125-128">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="6b125-129">また、既存の Q&A の Id を含めると、インポート ファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="6b125-129">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="6b125-130">複数のテナントを持つ組織の場合は、テナントからエクスポートした Q&A を別のテナントにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="6b125-130">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="6b125-131">ただし、インポートする前に Id 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b125-131">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="6b125-132">必須フィールドと推奨フィールドの詳細については、「[Q&A の作成](create-qas.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6b125-132">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

