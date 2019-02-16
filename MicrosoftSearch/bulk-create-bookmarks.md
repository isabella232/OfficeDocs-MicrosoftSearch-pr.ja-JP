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
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068404"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="4e931-103">ブックマークの一括作成</span><span class="sxs-lookup"><span data-stu-id="4e931-103">Bulk create bookmarks</span></span>

<span data-ttu-id="4e931-p101">.csv テンプレートをダウンロードして使用し、ブックマークを一括作成、編集、および保存します。既存のブックマークを一括編集するには、管理ポータルからそれらをエクスポートし、必要な編集を行ってからインポートします。</span><span class="sxs-lookup"><span data-stu-id="4e931-p101">Download and use the .csv template to bulk create, edit, and save bookmarks. To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="4e931-106">[ブックマーク] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e931-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="4e931-107">[**ブックマークテンプレートをダウンロードする (.csv)] をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="4e931-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="4e931-108">.csv ファイルを保存して開きます。</span><span class="sxs-lookup"><span data-stu-id="4e931-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="4e931-109">ブックマークの内容と設定を追加し、ファイルを保存する</span><span class="sxs-lookup"><span data-stu-id="4e931-109">Add the bookmark content and settings and save the file</span></span>
    
5. <span data-ttu-id="4e931-110">[ブックマーク] セクションの右上隅にある [**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e931-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="4e931-111">[ブックマークのインポート] ウィンドウで、[**参照**] をクリックして、インポートする .csv ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="4e931-111">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="4e931-112">[**インポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e931-112">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="4e931-113">インポートエラーを回避する</span><span class="sxs-lookup"><span data-stu-id="4e931-113">Prevent import errors</span></span>      
<span data-ttu-id="4e931-p102">必要なデータが不足しているか無効な場合は、エラーが表示されます。エラーによっては、修正する必要がある行と列に関する詳細情報を含むログファイルが生成されることがあります。必要な編集を行ってから、もう一度ファイルをインポートしてみてください。</span><span class="sxs-lookup"><span data-stu-id="4e931-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="4e931-117">すべてのエラーが解決されるまで、ブックマークを作成または編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="4e931-117">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="4e931-118">エラーが発生しないようにするために、インポートファイルの形式が正しいことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4e931-118">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="4e931-119">インポートテンプレートに含まれていたヘッダー行を含みます。</span><span class="sxs-lookup"><span data-stu-id="4e931-119">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="4e931-120">インポートテンプレートに含まれていたすべての列を含みます。</span><span class="sxs-lookup"><span data-stu-id="4e931-120">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="4e931-121">列の順序はインポートテンプレートと同じです。</span><span class="sxs-lookup"><span data-stu-id="4e931-121">The column order is the same as the import template</span></span>
- <span data-ttu-id="4e931-122">これらの列は空にすることができます。 Id、last modified、および last modified By</span><span class="sxs-lookup"><span data-stu-id="4e931-122">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="4e931-123">[状態] 列を空にすることはできません。この情報は必須です。</span><span class="sxs-lookup"><span data-stu-id="4e931-123">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="4e931-124">[状態] フィールドに基づいて、ブックマークが下書きとして保存されるか、提案されるか、スケジュールが設定されるか、または自動的に公開されるようになります。</span><span class="sxs-lookup"><span data-stu-id="4e931-124">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="4e931-125">また、既存のブックマークの Id を含めると、そのブックマークはインポートファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="4e931-125">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="4e931-p103">複数のテナントを持つ組織では、1つのテナントからブックマークをエクスポートして、別のテナントにインポートできます。ただし、インポートする前に、[Id] 列のすべてのデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e931-p103">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="4e931-128">必須および推奨フィールドの詳細については、「 [Create bookmarks](create-bookmarks.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e931-128">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
