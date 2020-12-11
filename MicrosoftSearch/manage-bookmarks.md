---
title: ブックマークの管理
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
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: ブックマークを作成および更新し、Microsoft Search のブックマークの結果を一括編集する方法
ms.openlocfilehash: 6a678464ec23c2d4c90190b6a02c0a73839b50ee
ms.sourcegitcommit: 41d28060238091455c7b8b011c67ae60c8a41f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619578"
---
# <a name="manage-bookmarks"></a><span data-ttu-id="8a14f-103">ブックマークの管理</span><span class="sxs-lookup"><span data-stu-id="8a14f-103">Manage bookmarks</span></span>

<span data-ttu-id="8a14f-104">ブックマークは、検索だけで重要なサイトやツールをすばやく見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-104">Bookmarks help people quickly find important sites and tools with just a search.</span></span> <span data-ttu-id="8a14f-105">各ブックマークには、タイトル、URL、ブックマークをトリガーするユーザーに優しいキーワードのセット、およびカテゴリが含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-105">Each bookmark includes a title, URL, a set of user-friendly keywords to trigger the bookmark, and a category.</span></span>

## <a name="what-makes-a-great-bookmark"></a><span data-ttu-id="8a14f-106">ブックマークを作成する機能</span><span class="sxs-lookup"><span data-stu-id="8a14f-106">What makes a great bookmark</span></span>

<span data-ttu-id="8a14f-107">ブックマークには、次の 4 つの主要な要素があります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-107">A great bookmark has four key elements:</span></span>

1. <span data-ttu-id="8a14f-108">強力で情報に基づいた **タイトル**。</span><span class="sxs-lookup"><span data-stu-id="8a14f-108">A strong, informative **title**.</span></span> <span data-ttu-id="8a14f-109">最大 8 単語または最大約 60 文字を指定してください。</span><span class="sxs-lookup"><span data-stu-id="8a14f-109">Aim for no more than 8 words or about 60 characters maximum.</span></span> <span data-ttu-id="8a14f-110">ユーザーがタイトルをクリックしてコンテンツを表示する必要がありますが、明らかなクリックバイトは避けるようにします。</span><span class="sxs-lookup"><span data-stu-id="8a14f-110">You want your users to click on the title and view the content, but avoid obvious clickbait:</span></span>
    - <span data-ttu-id="8a14f-111">良い: この週のお気に入りは、レストランのメニューで試してみてください。</span><span class="sxs-lookup"><span data-stu-id="8a14f-111">Good: Try this week’s tasty favorites from the cafeteria menu.</span></span> <span data-ttu-id="8a14f-112">タイトルは明確で簡潔で興味深いものの、過剰な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-112">Title is clear, concise, and interesting, but could be overpromising.</span></span>
    - <span data-ttu-id="8a14f-113">良い: 今週のセベリア メニュー。</span><span class="sxs-lookup"><span data-stu-id="8a14f-113">Better: This week’s cafeteria menu.</span></span> <span data-ttu-id="8a14f-114">広告のように過剰に使い過ぎたり、聞こえ過ぎない。</span><span class="sxs-lookup"><span data-stu-id="8a14f-114">Doesn't overpromise or sound like an ad.</span></span>
    - <span data-ttu-id="8a14f-115">避ける: 今週、何が起こってるのか分からない。</span><span class="sxs-lookup"><span data-stu-id="8a14f-115">Avoid: You won’t believe what’s coming to the cafeteria menu this week.</span></span> <span data-ttu-id="8a14f-116">広告のように聞こえるクリックバイト クリップを使います。</span><span class="sxs-lookup"><span data-stu-id="8a14f-116">Uses clickbait clichés that sound like an ad.</span></span>
2. <span data-ttu-id="8a14f-117">リンクされた **リソースの目的** または機能を要約した、約 300 文字の簡潔な説明。</span><span class="sxs-lookup"><span data-stu-id="8a14f-117">A succinct **description**, about 300 characters, that summarizes the purpose or functionality of the linked resource.</span></span>
3. <span data-ttu-id="8a14f-118">ユーザーが検索 **するときに** ブックマークを見つけるのに役立つキーワードのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="8a14f-118">A collection of **keywords** that will help people find the bookmark when they search.</span></span> <span data-ttu-id="8a14f-119">少なくとも 5 つのキーワードをお勧めしています。</span><span class="sxs-lookup"><span data-stu-id="8a14f-119">We suggest a minimum of at least five keywords.</span></span> <span data-ttu-id="8a14f-120">また、組織内のユーザーが使用する可能性のあるバリエーション (たとえば、レストランメニュー、ランチ メニュー、喫茶メニューなど) はすべて、レストランメニューのバリエーションとすることができます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-120">Also, include variations that people in your organization might use, for example, dining menu, lunch menus, and café menu could all be variations for cafeteria menu.</span></span>
4. <span data-ttu-id="8a14f-121">管理センター **でブックマークの** 並べ替えとフィルター処理を容易にする一連の便利なカテゴリ。</span><span class="sxs-lookup"><span data-stu-id="8a14f-121">A helpful set of **categories** that make it easier to sort and filter bookmarks in the admin center.</span></span> <span data-ttu-id="8a14f-122">割り当てられたカテゴリはユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-122">Your users never see the assigned categories.</span></span>

## <a name="create-bookmark-answers"></a><span data-ttu-id="8a14f-123">ブックマークの回答を作成する</span><span class="sxs-lookup"><span data-stu-id="8a14f-123">Create bookmark answers</span></span>

<span data-ttu-id="8a14f-124">Microsoft [365](https://admin.microsoft.com/)管理センターで、[ブックマーク[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks)] に移動し、新しいブックマークの作成方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-124">In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to [Bookmarks](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) and choose how you want to create new bookmarks:</span></span>

- <span data-ttu-id="8a14f-125">ブックマークを追加する</span><span class="sxs-lookup"><span data-stu-id="8a14f-125">Add bookmarks</span></span>
- <span data-ttu-id="8a14f-126">SharePoint の結果をインポートする</span><span class="sxs-lookup"><span data-stu-id="8a14f-126">Import SharePoint results</span></span>
- <span data-ttu-id="8a14f-127">既定のブックマークと推奨ブックマークを追加する</span><span class="sxs-lookup"><span data-stu-id="8a14f-127">Add default bookmarks and suggested bookmarks</span></span>
- <span data-ttu-id="8a14f-128">ブックマークをインポートする</span><span class="sxs-lookup"><span data-stu-id="8a14f-128">Import bookmarks</span></span>
- <span data-ttu-id="8a14f-129">推奨ブックマークを発行または確認する</span><span class="sxs-lookup"><span data-stu-id="8a14f-129">Publish or review recommended bookmarks</span></span>

### <a name="add-bookmarks"></a><span data-ttu-id="8a14f-130">ブックマークを追加する</span><span class="sxs-lookup"><span data-stu-id="8a14f-130">Add bookmarks</span></span>

<span data-ttu-id="8a14f-131">検索管理者と編集者は、Microsoft 365 管理センターでブックマークを追加できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-131">Search admins and editors can add bookmarks in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8a14f-132">ブックマークは、発行または下書きに保存できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-132">Bookmarks can be published or saved to draft.</span></span> <span data-ttu-id="8a14f-133">ブックマークを発行すると、検索インデックスがすぐに更新され、ユーザーはすぐに検索と使用を開始できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-133">Publishing a bookmark immediately refreshes the search index so users can begin discovering and using it right away.</span></span> <span data-ttu-id="8a14f-134">また、公開する日時を指定してブックマークをスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-134">You can also schedule a bookmark by specifying the date and time it will be published.</span></span>

- <span data-ttu-id="8a14f-135">**発行** 済み : Microsoft Search を使用して組織のユーザーがブックマークを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-135">**Published**: Bookmarks are available to the organization’s users through Microsoft Search.</span></span>
- <span data-ttu-id="8a14f-136">**下** 書き : 下書きとして保存されたブックマークは、ユーザーが使用できません。</span><span class="sxs-lookup"><span data-stu-id="8a14f-136">**Draft**: Bookmarks saved as drafts are not available to your users.</span></span> <span data-ttu-id="8a14f-137">自分または他の関係者がブックマークを公開する前に確認または更新する場合は、この状態を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-137">Use this status if you or other stakeholders want to review or update bookmarks before publishing them.</span></span>
- <span data-ttu-id="8a14f-138">**Scheduled**: 指定した日時に公開されるブックマーク。</span><span class="sxs-lookup"><span data-stu-id="8a14f-138">**Scheduled**: Bookmarks that will be published on the specified date and time.</span></span>

<span data-ttu-id="8a14f-139">Microsoft Search コンテンツ作成者のブラウザー拡張機能を使用すると、ブックマークを簡単に追加できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-139">You can use the Microsoft Search content creator browser extension to easily add bookmarks.</span></span> <span data-ttu-id="8a14f-140">ブラウザー拡張機能をインストールするには、ブックマークとして追加するサイトに移動し、拡張機能の [追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8a14f-140">To install the browser extension, go to the site you want to add as a bookmark, and click Add in the extension.</span></span>
<span data-ttu-id="8a14f-141">Edge と Chrome の拡張機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a14f-141">Install the extension for Edge and Chrome:</span></span>

- <span data-ttu-id="8a14f-142">Chromium Edge または Chrome の場合: Chrome Web ストア [に移動し](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) 、拡張機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-142">For Chromium Edge or Chrome: go to the [Chrome web store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) and add the extension.</span></span>
- <span data-ttu-id="8a14f-143">従来の Edge の場合: Microsoft Store に [移動し](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) 、拡張機能を追加します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-143">For legacy Edge: go to the [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) and add the extension.</span></span>

### <a name="import-sharepoint-results"></a><span data-ttu-id="8a14f-144">SharePoint の結果をインポートする</span><span class="sxs-lookup"><span data-stu-id="8a14f-144">Import SharePoint results</span></span>

<span data-ttu-id="8a14f-145">組織で SharePoint で昇格した結果を設定している場合は、タイトル、URL、および説明をテナントの昇格した結果から Microsoft Search にインポートし、インポートしたコンテンツをユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-145">If your organization set up Promoted Results in SharePoint, you can import the titles, URLs, and descriptions from the Promoted Results for your tenant into Microsoft Search and make the imported content available to your users.</span></span> <span data-ttu-id="8a14f-146">ほとんどの場合、SharePoint の結果のインポートには数分かかります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-146">In most cases, importing SharePoint results takes just a few minutes.</span></span> <span data-ttu-id="8a14f-147">大量の結果をインポートする場合、最大 48 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-147">If you're importing a large number of results, it may take up to 48 hours.</span></span> <span data-ttu-id="8a14f-148">これは、検索結果をすばやく設定し、ユーザーに対してより効果的な方法です。</span><span class="sxs-lookup"><span data-stu-id="8a14f-148">This is an easy way to quickly populate search results and make it more effective for your users.</span></span> <span data-ttu-id="8a14f-149">SharePoint から昇格した結果を参照として使用して、関連する検索結果に名前を付け、作成する方法を理解することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8a14f-149">We recommend using promoted results from SharePoint as a reference to understand how to name and create relevant search results.</span></span>

### <a name="add-default-and-suggested-bookmarks"></a><span data-ttu-id="8a14f-150">既定のブックマークと推奨ブックマークを追加する</span><span class="sxs-lookup"><span data-stu-id="8a14f-150">Add default and suggested bookmarks</span></span>

<span data-ttu-id="8a14f-151">人事、特典、IT サポート、パスワード管理などのブックマークなど、ユーザーが役立つ可能性がある既定の推奨ブックマークがいくつか含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a14f-151">We've included some default suggested bookmarks that your users may find helpful, including bookmarks for HR, benefits, IT support, password management and more.</span></span> <span data-ttu-id="8a14f-152">これらの推奨ブックマークを確認、更新、および公開して、ユーザーに高品質の結果を提供します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-152">Review, update, and publish these suggested bookmarks to provide high-quality results to your users right away.</span></span>

<span data-ttu-id="8a14f-153">ユーザーは、Microsoft Search のフィードバック リンクを使用して追加されたブックマークを提案できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-153">Your users can also suggest bookmarks that would like to see added using feedback links in Microsoft Search.</span></span> <span data-ttu-id="8a14f-154">推奨されるブックマークが候補として表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-154">Their recommendations will appear as suggested bookmarks.</span></span>

### <a name="import-bookmarks"></a><span data-ttu-id="8a14f-155">ブックマークをインポートする</span><span class="sxs-lookup"><span data-stu-id="8a14f-155">Import bookmarks</span></span>

<span data-ttu-id="8a14f-156">インポート機能を使用すると、多数のブックマークの追加や編集をより迅速かつ簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-156">Use the Import feature to make adding or editing a large number of bookmarks faster and easier.</span></span> <span data-ttu-id="8a14f-157">次の場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-157">Use it to:</span></span>

- <span data-ttu-id="8a14f-158">ブックマークの一括追加: ブックマーク テンプレート ファイルに詳細を追加し、インポートします。</span><span class="sxs-lookup"><span data-stu-id="8a14f-158">Bulk add bookmarks: Add details in the bookmark template file, and then import it.</span></span>
- <span data-ttu-id="8a14f-159">ブックマークの一括編集: ブックマークを .csv ファイルにエクスポートし、エクスポートしたファイルのブックマークの詳細を編集して、編集したファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="8a14f-159">Bulk edit bookmarks: Export bookmarks to a .csv file, edit the bookmark details in the exported file, and then import the edited file.</span></span>

<span data-ttu-id="8a14f-160">テンプレート ファイルに関する重要な点を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-160">A few important points about the template file:</span></span>

- <span data-ttu-id="8a14f-161">[ID]、[最終更新日時]、および [最終変更者]*フィールドのデータ\*\*を編集しない*</span><span class="sxs-lookup"><span data-stu-id="8a14f-161">Never edit data in these fields: *ID*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="8a14f-162">既存のブックマーク *の ID* を含める場合は、インポート ファイルの情報に置き換まれます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-162">If you include the *ID* of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="8a14f-163">同じタイトルまたは URL を持つ既存のブックマークの場合、ブックマークはインポート ファイル内の情報で更新されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-163">For existing bookmarks with the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="8a14f-164">テンプレート ファイルのすべてのフィールドが必要なわけではなく、ブックマークの状態によって必要なフィールドは変わります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-164">Not all fields in the template file are required and required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="8a14f-165">[状態] *フィールドに* 基づいて、ブックマークが下書き、推奨、スケジュール、除外として保存されます。または、ブックマークが自動的に公開されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-165">Based on the *State* field, bookmarks will be saved as draft, suggested, scheduled, excluded, or they'll be published automatically.</span></span>
- <span data-ttu-id="8a14f-166">複数の組織を管理するパートナーの場合は、組織間でブックマークをエクスポートし、別の組織にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-166">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="8a14f-167">ただし、インポートする前に *ID* 列のデータを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-167">But you must remove the data in the *ID* column before you import.</span></span>

### <a name="prevent-import-errors"></a><span data-ttu-id="8a14f-168">インポート エラーを回避する</span><span class="sxs-lookup"><span data-stu-id="8a14f-168">Prevent import errors</span></span>

<span data-ttu-id="8a14f-169">必要なデータが不足しているか無効な場合はエラーになり、修正する行と列に関する詳細情報を含むログ ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-169">You'll get an error if any required data is missing or invalid, and a log file is generated with more information about the rows and columns to be corrected.</span></span> <span data-ttu-id="8a14f-170">必要な編集を行い、ファイルのインポートを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="8a14f-170">Make necessary edits and try importing the file again.</span></span> <span data-ttu-id="8a14f-171">すべてのエラーが解決されるまで、ブックマークをインポートまたは保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a14f-171">You cannot import or save any bookmarks until all errors are resolved.</span></span>

<span data-ttu-id="8a14f-172">エラーを回避するには、インポート ファイルが正しく書式設定されていることに加えて、次の事項を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8a14f-172">To prevent errors, make sure your import file is properly formatted and:</span></span>

- <span data-ttu-id="8a14f-173">インポート テンプレートに存在していたヘッダー行とすべての列が含まれていること。</span><span class="sxs-lookup"><span data-stu-id="8a14f-173">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="8a14f-174">列の順序がインポート テンプレートと同じであること。</span><span class="sxs-lookup"><span data-stu-id="8a14f-174">The column order is the same as the import template</span></span>
- <span data-ttu-id="8a14f-175">すべての列に値があります。ただし、空にできる 3 つ *(ID、\*\*最終* 変更者、最終変更者 *) を除く*</span><span class="sxs-lookup"><span data-stu-id="8a14f-175">All columns have values, except the three that can be empty: *ID*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="8a14f-176">State *列* が空ではなく、必須の情報です。</span><span class="sxs-lookup"><span data-stu-id="8a14f-176">The *State* column is not empty, it's required information</span></span>
- <span data-ttu-id="8a14f-177">発行済み、推奨、スケジュール済み、下書きのブックマークをインポートする場合、*タイトル**、URL、**およびキーワードの列が* 必要です。</span><span class="sxs-lookup"><span data-stu-id="8a14f-177">When importing Published, Suggested, Scheduled, or Draft bookmarks, the *Title*, *URL*, and *Keywords* columns are required</span></span>
- <span data-ttu-id="8a14f-178">除外ブックマークをインポートする場合 *、URL* 列が必要です。</span><span class="sxs-lookup"><span data-stu-id="8a14f-178">When importing Excluded bookmarks, the *URL* column is required</span></span>

<span data-ttu-id="8a14f-179">ブックマーク間の重複エラーを回避するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-179">To prevent bookmark-to-bookmark duplication errors:</span></span>

- <span data-ttu-id="8a14f-180">異なるブックマークに重複する URL を使用しない。</span><span class="sxs-lookup"><span data-stu-id="8a14f-180">Don't use duplicate URLS for different bookmarks.</span></span> <span data-ttu-id="8a14f-181">URL が別のブックマークに割り当てられている場合に、インポート ファイルから URL を再度追加すると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-181">If a URL is assigned to another bookmark and you try to add it again from an import file, you'll get an error.</span></span> <span data-ttu-id="8a14f-182">これは、他の種類の回答の重複する URL にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-182">This also applies to duplicate URLs for other types of answers.</span></span>
- <span data-ttu-id="8a14f-183">既存のブックマークを更新する場合は、ブックマーク *ID 列を使用* します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-183">When updating existing bookmarks, use the *bookmark ID* column.</span></span> <span data-ttu-id="8a14f-184">既存のブックマークのその他のプロパティ (キーワードや説明など) を更新できますが、ブックマーク *ID* がインポート ファイルの適切な列に含けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-184">You can update any other property of an existing bookmark, such as keyword or description, but you should make sure the *bookmark ID* is in the appropriate column of the import file.</span></span> <span data-ttu-id="8a14f-185">ブックマーク *ID が* 存在する場合は、新しい追加として扱われるので、エラーとして処理されません。</span><span class="sxs-lookup"><span data-stu-id="8a14f-185">If the *bookmark ID* is present, it won't be treated as new addition and won't be processed as an error.</span></span>

### <a name="publish-or-review-recommended-bookmarks"></a><span data-ttu-id="8a14f-186">推奨ブックマークを発行または確認する</span><span class="sxs-lookup"><span data-stu-id="8a14f-186">Publish or review recommended bookmarks</span></span>

<span data-ttu-id="8a14f-187">ブックマークの追加に必要な手動の作業を減らすために、Microsoft Search は組織内の SharePoint リンクを評価し、ブックマークを推奨します。また、ブックマークを発行する前に確認したり、自動的に発行する設定を行います。</span><span class="sxs-lookup"><span data-stu-id="8a14f-187">To reduce the manual effort required to add bookmarks, Microsoft Search can evaluate SharePoint links in your organization and recommend bookmarks, and you can review them before publishing or set them to automatically publish.</span></span> <span data-ttu-id="8a14f-188">推奨ブックマークにはセットアップは必要ない。設定は有効で、既定では自動発行に設定されています。</span><span class="sxs-lookup"><span data-stu-id="8a14f-188">No setup is needed for recommended bookmarks, they're enabled and set to auto-publish by default.</span></span> <span data-ttu-id="8a14f-189">これらの設定をいつでも変更するには、[ブックマークの管理] **を選択して** [ブックマークの設定] パネルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-189">To change these settings at any time, select **Manage bookmarks** to open the Bookmark settings panel.</span></span>

![Microsoft 365 管理ポータルの推奨ブックマーク設定のスクリーンショット](media/bookmarks-recommendedsettings.png)

<span data-ttu-id="8a14f-191">推奨ブックマークが有効になっている場合、推奨事項エンジンは組織内の SharePoint サイトを評価してトラフィックの多いリンクを識別します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-191">If recommended bookmarks are enabled, the recommendation engine will evaluate SharePoint sites in your organization to identify high-traffic links.</span></span> <span data-ttu-id="8a14f-192">最初の評価期間が終了すると、推奨ブックマークが自動的に発行されるか、推奨ブックマークの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-192">After an initial evaluation period, the recommended bookmarks will either be auto-published or added to the list of suggested bookmarks.</span></span> <span data-ttu-id="8a14f-193">次のサイクル (30 日間の評価期間の後に自動発行または推奨ブックマークを追加) が開始されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-193">The next cycle—a 30-day evaluation period followed by auto-publishing or adding suggested bookmarks—will then begin.</span></span>

<span data-ttu-id="8a14f-194">検索管理者または編集者は、これらの自動公開ブックマークまたは推奨ブックマークを定期的に確認してください。</span><span class="sxs-lookup"><span data-stu-id="8a14f-194">We suggest Search admins or editors review these auto-published or suggested bookmarks on a regular basis.</span></span> <span data-ttu-id="8a14f-195">また、推奨ブックマークには、既存の発行済みブックマーク、おすすめブックマーク、スケジュール済みブックマーク、または除外ブックマークにある URL は含めつかりません。</span><span class="sxs-lookup"><span data-stu-id="8a14f-195">Also, recommended bookmarks will never include URLs found in existing Published, Suggested, Scheduled, or Excluded bookmarks.</span></span>

<span data-ttu-id="8a14f-196">アクセス権を持つユーザーにのみ、推奨ブックマークが作業結果に表示されるのを確認するために、すべての推奨ブックマークに対してアクセス チェック機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a14f-196">To ensure only users with access will see a recommended bookmark in their work results, an access check feature is included for all recommended bookmarks.</span></span> <span data-ttu-id="8a14f-197">SharePoint サイトにアクセスする権限を持たなかったユーザーには、そのサイトの推奨ブックマークが表示されません。</span><span class="sxs-lookup"><span data-stu-id="8a14f-197">Users that don't have permissions to access a SharePoint site will never see the recommended bookmark for that site.</span></span> <span data-ttu-id="8a14f-198">このアクセス チェックは、推奨ブックマークごとに[グループ] 設定の [このリンクにアクセスできるユーザーのみ] オプションによって制御されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-198">This access check is controlled by the option **Only people with access to this link** in the Groups setting for each recommended bookmark.</span></span>

<span data-ttu-id="8a14f-199">推奨ブックマークまたはグループ設定の URL が変更された場合、アクセス チェックは停止します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-199">The access check will stop if the URL in the recommended bookmark or the Groups setting is changed.</span></span>

<span data-ttu-id="8a14f-200">おすすめエンジンが特定のサイトにブックマークを発行または提案し込むのを防ぐには、除外するリストに URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-200">To prevent the recommendation engine from publishing or suggesting a bookmark to a particular site, you can add the URL to an excluded list.</span></span> <span data-ttu-id="8a14f-201">おすすめエンジンは、除外されたサイトまたは除外されたサイト内のページのブックマークを発行または提案しは行いません。</span><span class="sxs-lookup"><span data-stu-id="8a14f-201">The recommendation engine will never publish or suggest a bookmark for an excluded site or a page within an excluded site.</span></span>

## <a name="about-keywords-and-reserved-keywords"></a><span data-ttu-id="8a14f-202">キーワードと予約済みキーワードについて</span><span class="sxs-lookup"><span data-stu-id="8a14f-202">About keywords and reserved keywords</span></span>

<span data-ttu-id="8a14f-203">ブックマークには複数のキーワードを含め、ブックマークは同じキーワードを共有できますが、予約済みのキーワードは共有できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-203">A bookmark can have several keywords and bookmarks can share the same keyword, but reserved keyword can't be shared.</span></span> <span data-ttu-id="8a14f-204">予約済みキーワードは、1 つの特定のブックマークをトリガーする一意の用語または語句です。</span><span class="sxs-lookup"><span data-stu-id="8a14f-204">A reserved keyword is a unique term or phrase that triggers one specific bookmark.</span></span> <span data-ttu-id="8a14f-205">予約済みのキーワードは、1 つの回答にのみ関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-205">A reserved keyword can be associated with one answer only.</span></span> <span data-ttu-id="8a14f-206">予約済みのキーワードは、使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-206">Use reserved keywords sparingly.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8a14f-207">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="8a14f-207">Frequently asked questions</span></span>

<span data-ttu-id="8a14f-208">**Q: Microsoft Search の公開後にブックマークが表示されるのにどれくらいの時間がですか。**</span><span class="sxs-lookup"><span data-stu-id="8a14f-208">**Q: How long does it take for a bookmark to be visible in Microsoft Search after it's published?**</span></span>

<span data-ttu-id="8a14f-209">**A:**  Microsoft Search では、発行直後にブックマークを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-209">**A:**  A bookmark is available in Microsoft Search immediately after publishing.</span></span>

<span data-ttu-id="8a14f-210">**Q: 推奨ブックマークが表示されるのにどれくらいの時間が必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="8a14f-210">**Q: How long does it take for a recommended bookmark to appear?**</span></span>

<span data-ttu-id="8a14f-211">**A:**  推奨ブックマークは、推奨ブックマークと自動発行の両方が有効になっている場合にのみ、Microsoft Search に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-211">**A:**  Recommended bookmarks will only appear in Microsoft Search if both Recommended bookmarks and auto-publishing are enabled.</span></span> <span data-ttu-id="8a14f-212">最初の評価期間中に、推奨事項エンジンは SharePoint トラフィックを評価して適切なブックマークを識別し、自動発行します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-212">During the initial evaluation period, the recommendation engine will evaluate SharePoint traffic to identify suitable bookmarks and then auto-publish them.</span></span> <span data-ttu-id="8a14f-213">公開されたファイルは、Microsoft Search ですぐに利用できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-213">Once published they become available immediately in Microsoft Search.</span></span>

<span data-ttu-id="8a14f-214">**Q: Microsoft Search は、すべての言語のサイトからのブックマークを推奨しますか。**</span><span class="sxs-lookup"><span data-stu-id="8a14f-214">**Q: Will Microsoft Search recommend bookmarks from sites in all languages?**</span></span>

<span data-ttu-id="8a14f-215">**A**: はい、Microsoft Search は言語に関係なく、任意の内部 SharePoint サイトからのブックマークを推奨できます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-215">**A**: Yes, Microsoft Search can recommend bookmarks from any internal SharePoint site, regardless of the language.</span></span>

<span data-ttu-id="8a14f-216">**Q: 検索結果への推奨ブックマークの表示を停止できますか。**</span><span class="sxs-lookup"><span data-stu-id="8a14f-216">**Q: Can I stop showing recommended bookmarks in search results?**</span></span>

<span data-ttu-id="8a14f-217">**A:** 推奨ブックマークの表示を停止するには、管理センターで自動公開設定をオフにします。</span><span class="sxs-lookup"><span data-stu-id="8a14f-217">**A:** To stop showing recommended bookmarks, turn the auto-publish setting off in your admin center.</span></span> <span data-ttu-id="8a14f-218">推奨ブックマークは、推奨ブックマークの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-218">Recommended bookmarks will be added to the list of suggested bookmarks.</span></span>

<span data-ttu-id="8a14f-219">**Q: 検索結果または管理センターで推奨ブックマークを特定するにはどうすればよいですか。**</span><span class="sxs-lookup"><span data-stu-id="8a14f-219">**Q: How can I identify a recommended bookmark in search results or the admin center?**</span></span>

<span data-ttu-id="8a14f-220">**A:** 検索結果では、推奨ブックマークには URL の前に "Suggested for you" という語句が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-220">**A:** In search results, recommended bookmarks include the phrase "Suggested for you" before the URL.</span></span> <span data-ttu-id="8a14f-221">管理センターでは、マイニングされたブックマークの所有者の値は "SYSTEM" になります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-221">In the admin center, mined bookmarks will have an Owner value of "SYSTEM".</span></span>

<span data-ttu-id="8a14f-222">**Q: 推奨ブックマークへのアクセスは、どのように管理されますか。**</span><span class="sxs-lookup"><span data-stu-id="8a14f-222">**Q: How is access to a recommended bookmark managed?**</span></span>

<span data-ttu-id="8a14f-223">**A**: Microsoft によって設計されたアクセス エンジンは、ブックマーク URL が特定のユーザーがアクセス可能かどうかを判断し、適切な対象ユーザーにのみ推奨ブックマークを表示します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-223">**A**: A Microsoft-engineered access engine determines if the bookmark URL is accessible to a particular user and will only show the recommended bookmark to the correct audience.</span></span> <span data-ttu-id="8a14f-224">ただし、URL が編集された場合、またはグループの設定が変更された場合、設計されたアクセス エンジンは無効になります。</span><span class="sxs-lookup"><span data-stu-id="8a14f-224">However, if the URL is edited or the Groups setting is changed, the engineered access engine will be disabled.</span></span>

<span data-ttu-id="8a14f-225">**Q: 推奨リストに追加された推奨ブックマークに対して何もアクションが実行されないか。**</span><span class="sxs-lookup"><span data-stu-id="8a14f-225">**Q: What happens if no action is taken on recommended bookmarks added to the Suggested list?**</span></span>

<span data-ttu-id="8a14f-226">**A**: 推奨リスト内のブックマークの量が多くなことを避けるため、推奨ブックマーク (owner = SYSTEM) は 180 日後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="8a14f-226">**A**: To avoid a high volume of bookmarks in the suggested list, a recommended bookmark (owner = SYSTEM) will be purged after 180 days.</span></span>

<span data-ttu-id="8a14f-227">**Q: Power App のアプリ ID はどこで確認できますか。**</span><span class="sxs-lookup"><span data-stu-id="8a14f-227">**Q: Where do I find the App ID for a Power App?**</span></span>

<span data-ttu-id="8a14f-228">**A**: Power Apps サイトに移動し、アプリの [詳細] ウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="8a14f-228">**A**: Go to the Power Apps site and view the Details pane for the app.</span></span> <span data-ttu-id="8a14f-229">アプリ ID の [取得について詳しくは、次をご覧ください](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)。</span><span class="sxs-lookup"><span data-stu-id="8a14f-229">Learn more about [getting an app ID](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id).</span></span>
