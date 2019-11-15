---
title: Q&A の管理
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: 回答を個別に検索して更新するか、利用可能な Microsoft Search のツールを使用して一括ですべての回答を編集します
ms.openlocfilehash: 903aab52e8d51e45588a390b5ccdccbaae2cf04a
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626776"
---
# <a name="manage-qas"></a><span data-ttu-id="3750b-103">Q&A の管理</span><span class="sxs-lookup"><span data-stu-id="3750b-103">Manage Q&As</span></span>

<span data-ttu-id="3750b-104">Q&A の作成は、ブックマークの作成と似ています。</span><span class="sxs-lookup"><span data-stu-id="3750b-104">Creating a Q&A is similar to creating bookmarks.</span></span> <span data-ttu-id="3750b-105">Q&A では、Web ページへのリンクを提供するだけではなく、ユーザーの質問に回答することができます。</span><span class="sxs-lookup"><span data-stu-id="3750b-105">Q&A allows you to answer the user's question instead of just providing a link to webpage.</span></span> <span data-ttu-id="3750b-106">利用可能なツールを使用して、回答をリッチ テキスト形式にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3750b-106">You can format the answer in rich text using the available tools.</span></span> <span data-ttu-id="3750b-107">ブックマークと Q&A が同じキーワードを共有している場合は、ブックマークの結果が最初に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3750b-107">If a Bookmark and a Q&A share the same keyword, the Bookmark result is shown first.</span></span> <span data-ttu-id="3750b-108">ブックマークと同様に、Q&A インデックスは Q&A が追加または変更された直後に更新されます。</span><span class="sxs-lookup"><span data-stu-id="3750b-108">Like Bookmarks, the Q&A index is refreshed immediately after a Q&A is added or changed.</span></span> 

## <a name="add-or-edit-a-single-qa"></a><span data-ttu-id="3750b-109">1 つの Q&A を追加または編集する</span><span class="sxs-lookup"><span data-stu-id="3750b-109">Add or edit a single Q&A</span></span>
1. <span data-ttu-id="3750b-110">**Microsoft 365 管理センター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="3750b-110">Go to **Microsoft 365 admin center**.</span></span>
1. <span data-ttu-id="3750b-111">ナビゲーション ウィンドウで、**[設定]** に移動して、**[Microsoft Search]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3750b-111">In the navigation pane, go to **Settings** and select **Microsoft Search**.</span></span>
1. <span data-ttu-id="3750b-112">**[Q&A]** タブを選択します。既定では、最初のタブ (**ブックマーク**) が選択されています。</span><span class="sxs-lookup"><span data-stu-id="3750b-112">Select **Q&A** tab. By default, the first tab (**Bookmarks**) is selected.</span></span>
1. <span data-ttu-id="3750b-113">Q&A を追加するには、**[新規追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3750b-113">To add a Q&A, select **Add new**.</span></span>
<span data-ttu-id="3750b-114">Q&A を編集するには、関連する Q&A の一覧で Q&A を選択します。</span><span class="sxs-lookup"><span data-stu-id="3750b-114">To edit a Q&A, select the Q&A in the relevant Q&A list.</span></span>
1. <span data-ttu-id="3750b-115">情報を追加または編集すると、プレビューが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="3750b-115">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="3750b-116">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="3750b-116">Save your changes.</span></span>

### <a name="supported-html-tags"></a><span data-ttu-id="3750b-117">サポートされている HTML タグ</span><span class="sxs-lookup"><span data-stu-id="3750b-117">Supported HTML tags</span></span>
<span data-ttu-id="3750b-118">回答 (説明) に既存の HTML コンテンツを使用したり、HTML タグを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="3750b-118">You can use existing HTML content or add HTML tags to your answer (description).</span></span> <span data-ttu-id="3750b-119">サポート対象外のタグは無視されます。</span><span class="sxs-lookup"><span data-stu-id="3750b-119">Unsupported tags are ignored.</span></span>  
<span data-ttu-id="3750b-120">次の HTML タグがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3750b-120">The following HTML tags are supported:</span></span>
- <span data-ttu-id="3750b-121">blockquote</span><span class="sxs-lookup"><span data-stu-id="3750b-121">blockquote</span></span>
- <span data-ttu-id="3750b-122">div</span><span class="sxs-lookup"><span data-stu-id="3750b-122">div</span></span>
- <span data-ttu-id="3750b-123">em</span><span class="sxs-lookup"><span data-stu-id="3750b-123">em</span></span>
- <span data-ttu-id="3750b-124">h1、h2、h3、h4</span><span class="sxs-lookup"><span data-stu-id="3750b-124">h1, h2, h3, and h4</span></span>
- <span data-ttu-id="3750b-125">ol、ul、li</span><span class="sxs-lookup"><span data-stu-id="3750b-125">ol, ul, and li</span></span>
- <span data-ttu-id="3750b-126">p</span><span class="sxs-lookup"><span data-stu-id="3750b-126">p</span></span>
- <span data-ttu-id="3750b-127">pre</span><span class="sxs-lookup"><span data-stu-id="3750b-127">pre</span></span>
- <span data-ttu-id="3750b-128">span</span><span class="sxs-lookup"><span data-stu-id="3750b-128">span</span></span>
- <span data-ttu-id="3750b-129">strong</span><span class="sxs-lookup"><span data-stu-id="3750b-129">strong</span></span>
- <span data-ttu-id="3750b-130">table、thead、tbody、tr、th、td</span><span class="sxs-lookup"><span data-stu-id="3750b-130">table, thead, tbody, tr, th, and td</span></span>
- <span data-ttu-id="3750b-131">u</span><span class="sxs-lookup"><span data-stu-id="3750b-131">u</span></span>
- <span data-ttu-id="3750b-132">a</span><span class="sxs-lookup"><span data-stu-id="3750b-132">a</span></span>
- <span data-ttu-id="3750b-133">code</span><span class="sxs-lookup"><span data-stu-id="3750b-133">code</span></span>
- <span data-ttu-id="3750b-134">br</span><span class="sxs-lookup"><span data-stu-id="3750b-134">br</span></span>
- <span data-ttu-id="3750b-135">hr</span><span class="sxs-lookup"><span data-stu-id="3750b-135">hr</span></span>
- <span data-ttu-id="3750b-136">img</span><span class="sxs-lookup"><span data-stu-id="3750b-136">img</span></span>

## <a name="bulk-add-or-edit-qas"></a><span data-ttu-id="3750b-137">Q&A を一括して追加または編集する</span><span class="sxs-lookup"><span data-stu-id="3750b-137">Bulk add or edit Q&As</span></span>
<span data-ttu-id="3750b-138">管理者は、インポート機能とエクスポート機能を使用して、Q&A の一括作成または一括編集が行えます。</span><span class="sxs-lookup"><span data-stu-id="3750b-138">Administrators can use the Import and Export features to bulk create or edit Q&A.</span></span> <span data-ttu-id="3750b-139">これは、管理者が多数の Q&A を追加または編集する必要がある場合に便利な機能です。</span><span class="sxs-lookup"><span data-stu-id="3750b-139">This is a useful feature when administrators need to add or edit a large number of Q&A.</span></span> 

<span data-ttu-id="3750b-140">インポート/エクスポート機能を使用して、次のことが実行できます。</span><span class="sxs-lookup"><span data-stu-id="3750b-140">Use the import/export feature to:</span></span>
1. <span data-ttu-id="3750b-141">Q&A の一括追加 - Q&A テンプレート ファイルに詳細を追加して、インポートします。</span><span class="sxs-lookup"><span data-stu-id="3750b-141">Bulk add Q&A - Add details in the Q&A template file, and then import it.</span></span>
1. <span data-ttu-id="3750b-142">Q&A の一括編集 - Q&A を .csv ファイルにエクスポートし、エクスポートされた .csv ファイルの Q&A の詳細を編集してから、.csv ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="3750b-142">Bulk edit Q&A - Export Q&A to a .csv file, then edit the Q&A details in the exported .csv file, and then import the .csv file.</span></span>
1. <span data-ttu-id="3750b-143">Q&A のバックアップ - Q&A を .csv ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="3750b-143">Backup Q&A - Export Q&A to a .csv file.</span></span>

<span data-ttu-id="3750b-144">Q&A をインポートまたはエクスポートするには:</span><span class="sxs-lookup"><span data-stu-id="3750b-144">To import or export Q&A:</span></span>
1. <span data-ttu-id="3750b-145">[Q&A] タブの右上隅にある **[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3750b-145">In the upper-right corner of the Q&A tab, select **Import**.</span></span> <span data-ttu-id="3750b-146">.csv ファイル内の既存の Q&A をすべてダウンロードするには、**[エクスポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3750b-146">Select **Export** to download all the existing Q&A in a .csv file.</span></span>
1. <span data-ttu-id="3750b-147">右側のウィンドウで、.csv ファイルを使用してインポートするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="3750b-147">In the right pane, choose the option to import using a .csv file.</span></span>
<span data-ttu-id="3750b-148">必要なフィールドと詳細の一覧については、テンプレート ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3750b-148">Download the template file for a list of the required fields and details.</span></span> 
1. <span data-ttu-id="3750b-149">テンプレート ファイルの Q&A の詳細を追加または編集して、コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="3750b-149">Add or edit Q&A details in the template file and save it on your computer.</span></span> 
1. <span data-ttu-id="3750b-150">**[Q&A のインポート]** ウィンドウで、**[参照]** を選び、インポートする .csv ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="3750b-150">In the **Import Q&A** pane, select **Browse**, and then the .csv file that you want to import.</span></span>
1. <span data-ttu-id="3750b-151">**[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="3750b-151">Select **Import**.</span></span>

<span data-ttu-id="3750b-152">以下に、テンプレート ファイルに関する重要な点をいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="3750b-152">Here are some important points regarding the template file:</span></span>
- <span data-ttu-id="3750b-153">次のフィールドのデータは決して編集しないでください: *ID*、*最終更新日時*、*最終更新者*</span><span class="sxs-lookup"><span data-stu-id="3750b-153">Never edit data in these fields: *Id*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="3750b-154">既存のブックマークの *ID* を含めると、インポート ファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="3750b-154">If you include the *Id* of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="3750b-155">同じタイトルまたは URL を持つ既存のブックマークがある場合は、そのブックマークはインポート ファイル内の情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="3750b-155">If there is an existing bookmark with the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="3750b-156">テンプレート ファイルのすべてのフィールドが必要なわけではなく、ブックマークの状態によって必要なフィールドは変わります。</span><span class="sxs-lookup"><span data-stu-id="3750b-156">Not all fields in the template file are required and required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="3750b-157">状態フィールドに基づいて、ブックマークは、下書き、おすすめ、スケジュール済みとして保存されるか、自動的に公開されます。</span><span class="sxs-lookup"><span data-stu-id="3750b-157">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>
- <span data-ttu-id="3750b-158">複数の組織を管理するパートナーは、1つの組織からブックマークをエクスポートして、別の組織にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="3750b-158">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="3750b-159">ただし、インポートする前に *ID* 列のデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3750b-159">But you must remove the data in the *Id* column before you import.</span></span>

<span data-ttu-id="3750b-160">**注:** テンプレート ファイルにエラーがある場合は、Q&A をインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="3750b-160">**Note:** You cannot import Q&A if there are any errors in the template file.</span></span> <span data-ttu-id="3750b-161">エラーを回避するには、インポート ファイルが正しく書式設定されていて、必要な情報がすべて含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3750b-161">To prevent errors, make sure your import file is properly formatted and include all the required information.</span></span> 

<span data-ttu-id="3750b-162">エラーを回避する方法の詳細については、「[インポート エラーを回避する](manage-bookmarks.md#prevent-import-errors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3750b-162">For more information on how to prevent error, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>