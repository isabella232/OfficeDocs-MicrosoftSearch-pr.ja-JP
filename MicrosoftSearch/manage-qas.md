---
title: Q&A の管理
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: 回答を個別に検索して更新したり、使用可能な Microsoft 検索ツールを使用して、Q&を一度にすべて編集したりできます。
ms.openlocfilehash: 78a6ee0ff14f3347b0b2e2a65cc1ee0f68500981
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996087"
---
# <a name="manage-qas"></a><span data-ttu-id="55171-103">Q&A の管理</span><span class="sxs-lookup"><span data-stu-id="55171-103">Manage Q&As</span></span>

<span data-ttu-id="55171-104">Q&A の作成は、ブックマークの作成と似ています。</span><span class="sxs-lookup"><span data-stu-id="55171-104">Creating a Q&A is similar to creating bookmarks.</span></span> <span data-ttu-id="55171-105">Q&、web ページへのリンクを提供するだけでなく、ユーザーの質問に答えることができます。</span><span class="sxs-lookup"><span data-stu-id="55171-105">Q&As allow you to answer the user's questions instead of just providing a link to a webpage.</span></span> <span data-ttu-id="55171-106">また、リッチテキスト形式で回答の書式を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="55171-106">You can also format the answer in rich text.</span></span> <span data-ttu-id="55171-107">ブックマークと Q&A が同じキーワードを共有している場合は、ブックマークの結果が最初に表示されます。</span><span class="sxs-lookup"><span data-stu-id="55171-107">If a bookmark and a Q&A share the same keyword, the bookmark result is shown first.</span></span> <span data-ttu-id="55171-108">ブックマークと同様に、q&のインデックスは、Q&A が追加または変更された直後に更新されます。</span><span class="sxs-lookup"><span data-stu-id="55171-108">Like bookmarks, the Q&A index is refreshed immediately after a Q&A is added or changed.</span></span>

## <a name="add-or-edit-a-single-qa"></a><span data-ttu-id="55171-109">1 つの Q&A を追加または編集する</span><span class="sxs-lookup"><span data-stu-id="55171-109">Add or edit a single Q&A</span></span>

1. <span data-ttu-id="55171-110">**Microsoft 365 管理センター**に移動します。</span><span class="sxs-lookup"><span data-stu-id="55171-110">Go to **Microsoft 365 admin center**.</span></span>
1. <span data-ttu-id="55171-111">ナビゲーションウィンドウで、[**設定**] の [  >  **Microsoft Search**  >  **アンサー**]  >  [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)に移動します。</span><span class="sxs-lookup"><span data-stu-id="55171-111">In the navigation pane, go to **Settings** > **Microsoft Search** > **Answers** > [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)</span></span>
1. <span data-ttu-id="55171-112">Q&A を追加するには、**[新規追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="55171-112">To add a Q&A, select **Add new**.</span></span>
<span data-ttu-id="55171-113">Q&A を編集するには、関連する Q&A の一覧で Q&A を選択します。</span><span class="sxs-lookup"><span data-stu-id="55171-113">To edit a Q&A, select the Q&A in the relevant Q&A list.</span></span> <span data-ttu-id="55171-114">情報を追加または編集すると、プレビューが自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="55171-114">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="55171-115">変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="55171-115">Save your changes.</span></span>

### <a name="supported-html-tags"></a><span data-ttu-id="55171-116">サポートされている HTML タグ</span><span class="sxs-lookup"><span data-stu-id="55171-116">Supported HTML tags</span></span>

<span data-ttu-id="55171-117">回答 (説明) に既存の HTML コンテンツを使用したり、HTML タグを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="55171-117">You can use existing HTML content or add HTML tags to your answer (description).</span></span> <span data-ttu-id="55171-118">サポート対象外のタグは無視されます。</span><span class="sxs-lookup"><span data-stu-id="55171-118">Unsupported tags are ignored.</span></span>

<span data-ttu-id="55171-119">次の HTML タグがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="55171-119">The following HTML tags are supported:</span></span>

- <span data-ttu-id="55171-120">blockquote</span><span class="sxs-lookup"><span data-stu-id="55171-120">blockquote</span></span>
- <span data-ttu-id="55171-121">div</span><span class="sxs-lookup"><span data-stu-id="55171-121">div</span></span>
- <span data-ttu-id="55171-122">em</span><span class="sxs-lookup"><span data-stu-id="55171-122">em</span></span>
- <span data-ttu-id="55171-123">h1、h2、h3、h4</span><span class="sxs-lookup"><span data-stu-id="55171-123">h1, h2, h3, and h4</span></span>
- <span data-ttu-id="55171-124">ol、ul、li</span><span class="sxs-lookup"><span data-stu-id="55171-124">ol, ul, and li</span></span>
- <span data-ttu-id="55171-125">p</span><span class="sxs-lookup"><span data-stu-id="55171-125">p</span></span>
- <span data-ttu-id="55171-126">pre</span><span class="sxs-lookup"><span data-stu-id="55171-126">pre</span></span>
- <span data-ttu-id="55171-127">span</span><span class="sxs-lookup"><span data-stu-id="55171-127">span</span></span>
- <span data-ttu-id="55171-128">strong</span><span class="sxs-lookup"><span data-stu-id="55171-128">strong</span></span>
- <span data-ttu-id="55171-129">table、thead、tbody、tr、th、td</span><span class="sxs-lookup"><span data-stu-id="55171-129">table, thead, tbody, tr, th, and td</span></span>
- <span data-ttu-id="55171-130">u</span><span class="sxs-lookup"><span data-stu-id="55171-130">u</span></span>
- <span data-ttu-id="55171-131">a</span><span class="sxs-lookup"><span data-stu-id="55171-131">a</span></span>
- <span data-ttu-id="55171-132">code</span><span class="sxs-lookup"><span data-stu-id="55171-132">code</span></span>
- <span data-ttu-id="55171-133">br</span><span class="sxs-lookup"><span data-stu-id="55171-133">br</span></span>
- <span data-ttu-id="55171-134">hr</span><span class="sxs-lookup"><span data-stu-id="55171-134">hr</span></span>
- <span data-ttu-id="55171-135">img</span><span class="sxs-lookup"><span data-stu-id="55171-135">img</span></span>

## <a name="add-or-edit-qas-using-browser-extensions"></a><span data-ttu-id="55171-136">ブラウザー拡張機能を使用して Q&を追加または編集する</span><span class="sxs-lookup"><span data-stu-id="55171-136">Add or edit Q&As using browser extensions</span></span>

<span data-ttu-id="55171-137">検索管理者は、ブラウザーの拡張機能を使用して検索コンテンツを簡単に作成できます。</span><span class="sxs-lookup"><span data-stu-id="55171-137">Search administrators can create search content easily by using browser extensions.</span></span> <span data-ttu-id="55171-138">ブラウザー拡張機能をインストールし、Q&A を生成するサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="55171-138">Install the browser extension, and then go to the site from which you want to generate a Q&A.</span></span> <span data-ttu-id="55171-139">その後、Q&A を作成し、ソースサイトへのリンクを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="55171-139">You can then create the Q&A and include a link to the source site.</span></span>

<span data-ttu-id="55171-140">現在、Microsoft Edge および Chrome ではブラウザー拡張機能を使用できます。</span><span class="sxs-lookup"><span data-stu-id="55171-140">Currently, browser extensions are available for Microsoft Edge and Chrome.</span></span>

- <span data-ttu-id="55171-141">エッジ (レガシ) の拡張機能をダウンロードするには、 [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)にアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="55171-141">To download extensions for Edge (Legacy), go to [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).</span></span>
- <span data-ttu-id="55171-142">拡張子クロムまたはエッジ (Chromium) をダウンロードするには、 [chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)に移動します。</span><span class="sxs-lookup"><span data-stu-id="55171-142">To download extensions Chrome or Edge (Chromium), go to the [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).</span></span>

## <a name="bulk-add-or-edit-qas"></a><span data-ttu-id="55171-143">Q&A を一括して追加または編集する</span><span class="sxs-lookup"><span data-stu-id="55171-143">Bulk add or edit Q&As</span></span>

<span data-ttu-id="55171-144">管理者は、インポートおよびエクスポート機能を使用して、Q&の一括作成または編集を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="55171-144">Administrators can use the Import and Export features to bulk create or edit Q&As.</span></span>

<span data-ttu-id="55171-145">インポート/エクスポート機能を使用して、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="55171-145">Use the Import/Export feature to:</span></span>

- <span data-ttu-id="55171-146">[一括追加] q&テンプレートファイルに&追加の詳細を追加して、インポートします。</span><span class="sxs-lookup"><span data-stu-id="55171-146">Bulk add Q&As - Add details in the Q&A template file, and then import it.</span></span>
- <span data-ttu-id="55171-147">一括編集 Q&エクスポート Q&.csv ファイルとして q&を編集し、エクスポートしたファイルの詳細を編集して、ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="55171-147">Bulk edit Q&As - Export Q&As to a .csv file, edit the Q&A details in the exported file, and then import the file.</span></span>
- <span data-ttu-id="55171-148">Q&をエクスポートし、.csv ファイルとして&としてバックアップします。</span><span class="sxs-lookup"><span data-stu-id="55171-148">Back up Q&As - Export Q&As to a .csv file.</span></span>

<span data-ttu-id="55171-149">Q&をインポートまたはエクスポートするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="55171-149">To import or export Q&As:</span></span>

1. <span data-ttu-id="55171-150">[Q&A] タブの右上隅にある **[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="55171-150">In the upper-right corner of the Q&A tab, select **Import**.</span></span>
<span data-ttu-id="55171-151">[**エクスポート**] を選択して、.Csv ファイルとしてすべての既存の Q&をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="55171-151">Select **Export** to download all the existing Q&As in a .csv file.</span></span>
1. <span data-ttu-id="55171-152">右側のウィンドウで、.csv ファイルを使用してインポートするオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="55171-152">In the right pane, select the option to import by using a .csv file.</span></span> <span data-ttu-id="55171-153">テンプレートファイルをダウンロードして、必要なフィールドと詳細のリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="55171-153">Download the template file to get a list of the required fields and details.</span></span>
1. <span data-ttu-id="55171-154">テンプレートファイルに Q&追加または編集して、コンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="55171-154">Add or edit Q&A details in the template file, and save it on your computer.</span></span>
1. <span data-ttu-id="55171-155">[ **Q&をインポート**する] ウィンドウで、[**参照**] を選択し、インポートする .csv ファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="55171-155">In the **Import Q&A** pane, select **Browse**, and then select the .csv file that you want to import.</span></span>
1. <span data-ttu-id="55171-156">**[インポート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="55171-156">Select **Import**.</span></span>

<span data-ttu-id="55171-157">重要なテンプレートファイルのヒント:</span><span class="sxs-lookup"><span data-stu-id="55171-157">Important template file tips:</span></span>

- <span data-ttu-id="55171-158">次のフィールドのデータは決して編集しないでください: **ID**、**最終更新日時**、**最終更新者**</span><span class="sxs-lookup"><span data-stu-id="55171-158">Never edit data in these fields: **Id**, **Last Modified**, and **Last Modified By**</span></span>
- <span data-ttu-id="55171-159">既存のブックマークの **ID** を含めると、インポート ファイルの情報に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="55171-159">If you include the **Id** of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="55171-160">同じタイトルまたは URL を持つ既存のブックマークがある場合、ブックマークはインポートファイルの情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="55171-160">If there's an existing bookmark that has the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="55171-161">テンプレートファイルのすべてのフィールドが必須であるわけではなく、ブックマークの状態によって必須のフィールドが異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="55171-161">Not all fields in the template file are required, and the required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="55171-162">[**状態**] フィールドに基づいて、ブックマークは*下書き*、*提案*済み、または*スケジュール*済みとして保存されるか、自動的に公開されます。</span><span class="sxs-lookup"><span data-stu-id="55171-162">Based on the **State** field, bookmarks are saved as *draft*, *suggested*, or *scheduled*, or they are published automatically.</span></span>
- <span data-ttu-id="55171-163">複数の組織を管理するパートナーの場合: ブックマークを1つの組織からエクスポートして、別の組織にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="55171-163">For partners who manage multiple organizations: You can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="55171-164">ただし、インポートする前に **ID** 列のデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55171-164">But you must remove the data in the **Id** column before you import.</span></span>

> [!NOTE]
> <span data-ttu-id="55171-165">テンプレートファイルにエラーがある場合は、Q&をインポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="55171-165">You can't import Q&As if there are any errors in the template file.</span></span> <span data-ttu-id="55171-166">エラーが発生しないようにするには、インポートファイルが適切に書式設定されていることを確認し、必要な情報をすべて含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="55171-166">To prevent errors, make sure your import file is properly formatted, and include all the required information.</span></span>

<span data-ttu-id="55171-167">エラーを回避する方法の詳細については、「[インポートエラーの防止](manage-bookmarks.md#prevent-import-errors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55171-167">For more information about avoiding errors, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>
