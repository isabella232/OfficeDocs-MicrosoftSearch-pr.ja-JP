---
title: 一括作成 Q&As
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
description: Microsoft Search 管理ポータルのインポートツールでよく寄せられる質問への回答をすばやく追加する
ms.openlocfilehash: 53f1d167948f6b621ad139620553df51b0cb91c2
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068396"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="70eb1-103">一括作成 Q&As</span><span class="sxs-lookup"><span data-stu-id="70eb1-103">Bulk create Q&As</span></span>

<span data-ttu-id="70eb1-p101">.csv テンプレートをダウンロードして使用し、Q&As を一括作成または一括編集します。また、追加の編集や更新が必要な下書き Q&As を一括保存する簡単な方法でもあります。既存の Q&As を一括編集する必要がある場合は、管理ポータルからそれらをエクスポートしてから、必要な編集を行ってからインポートします。</span><span class="sxs-lookup"><span data-stu-id="70eb1-p101">Download and use the .csv template to bulk create or bulk edit Q&As. It's also a simple way to bulk save draft Q&As that need additional edits or updates. If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="70eb1-107">[Q&As] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70eb1-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="70eb1-108">[ **Q&A テンプレート (.csv) をダウンロード**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70eb1-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="70eb1-109">.csv ファイルを保存して開きます。</span><span class="sxs-lookup"><span data-stu-id="70eb1-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="70eb1-110">Q&A のコンテンツと設定を追加し、ファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="70eb1-110">Add the Q&A content and settings and save the file</span></span>
    
5. <span data-ttu-id="70eb1-111">[Q&As] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70eb1-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="70eb1-112">[Q&As のインポート] ウィンドウで、[**参照**] をクリックし、インポートする .csv ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="70eb1-112">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="70eb1-113">[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="70eb1-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="70eb1-114">インポートエラーを回避する</span><span class="sxs-lookup"><span data-stu-id="70eb1-114">Prevent import errors</span></span>      
<span data-ttu-id="70eb1-p102">必要なデータが不足しているか無効な場合は、エラーが表示されます。エラーによっては、修正する必要がある行と列に関する詳細情報を含むログファイルが生成されることがあります。必要な編集を行ってから、もう一度ファイルをインポートしてみてください。</span><span class="sxs-lookup"><span data-stu-id="70eb1-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="70eb1-118">すべてのエラーが解決されるまで、Q&As を作成または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="70eb1-118">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="70eb1-119">エラーが発生しないようにするために、インポートファイルの形式が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="70eb1-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="70eb1-120">インポートテンプレートに含まれていたヘッダー行を含みます。</span><span class="sxs-lookup"><span data-stu-id="70eb1-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="70eb1-121">インポートテンプレートに含まれていたすべての列を含みます。</span><span class="sxs-lookup"><span data-stu-id="70eb1-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="70eb1-122">列の順序はインポートテンプレートと同じです。</span><span class="sxs-lookup"><span data-stu-id="70eb1-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="70eb1-123">これらの列は空にすることができます。 Id、last modified、および last modified By</span><span class="sxs-lookup"><span data-stu-id="70eb1-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="70eb1-124">[状態] 列を空にすることはできません。この情報は必須です。</span><span class="sxs-lookup"><span data-stu-id="70eb1-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="70eb1-125">[状態] フィールドに基づいて、Q&As が下書きとして保存されるか、提案され、スケジュールされるか、または自動的に公開されるようになります。</span><span class="sxs-lookup"><span data-stu-id="70eb1-125">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="70eb1-126">また、既存の Q&A の Id を指定すると、インポートファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="70eb1-126">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="70eb1-p103">複数のテナントを持つ組織では、Q&As を1つのテナントからエクスポートして、別のテナントにインポートできます。ただし、インポートする前に、[Id] 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="70eb1-p103">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="70eb1-129">必須および推奨フィールドの詳細については、「 [Create Q&As](create-qas.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="70eb1-129">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

