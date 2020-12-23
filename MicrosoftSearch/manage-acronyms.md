---
title: Microsoft Search で頭字語の回答を管理する
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search で頭字語の回答を作成および更新する
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728008"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="8691d-103">Microsoft Search で頭字語の回答を管理する</span><span class="sxs-lookup"><span data-stu-id="8691d-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="8691d-104">ユーザーは、組織やチームで使用されている頭字語や略語に慣れていないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="8691d-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="8691d-105">組織またはチームに固有の用語は、チーム間を移動したり、社内パートナーと共同で作業する人、または組織の新人には新しい場合があります。  </span><span class="sxs-lookup"><span data-stu-id="8691d-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="8691d-106">組織の標準的な用語には、常に単一の参照があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="8691d-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="8691d-107">単一の参照がないと、これらの頭字語の定義や展開が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="8691d-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="8691d-108">Microsoft Search は、頭字語の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="8691d-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="8691d-109">ユーザーのエクスぺリエンス</span><span class="sxs-lookup"><span data-stu-id="8691d-109">What users experience</span></span>

<span data-ttu-id="8691d-110">Microsoft Search のユーザーは [Bing](https://Bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)および[Office 365](https://Office.com)の頭字語を使用して、定義を入手できます。</span><span class="sxs-lookup"><span data-stu-id="8691d-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="8691d-111">**[検索]** ボックスで、次の例のようにクエリを入力します:</span><span class="sxs-lookup"><span data-stu-id="8691d-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="8691d-112">*What is* DNN</span><span class="sxs-lookup"><span data-stu-id="8691d-112">*What is* DNN</span></span>
- <span data-ttu-id="8691d-113">*Define* DNN</span><span class="sxs-lookup"><span data-stu-id="8691d-113">*Define* DNN</span></span>
- <span data-ttu-id="8691d-114">DNN *definition*</span><span class="sxs-lookup"><span data-stu-id="8691d-114">DNN *definition*</span></span>
- <span data-ttu-id="8691d-115">*Expand* DNN</span><span class="sxs-lookup"><span data-stu-id="8691d-115">*Expand* DNN</span></span>
- <span data-ttu-id="8691d-116">DNN *expansion*</span><span class="sxs-lookup"><span data-stu-id="8691d-116">DNN *expansion*</span></span>
- <span data-ttu-id="8691d-117">*Meaning of* DNN</span><span class="sxs-lookup"><span data-stu-id="8691d-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="8691d-118">DNN *means*</span><span class="sxs-lookup"><span data-stu-id="8691d-118">DNN *means*</span></span>

<span data-ttu-id="8691d-119">結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8691d-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="8691d-120">ユーザーは、対応する回答をトリガーするために、頭字語で指定された *キーワード* を含むクエリを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8691d-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="8691d-121">頭字語のクエリでは、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="8691d-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="8691d-122">頭字語の回答を設定する</span><span class="sxs-lookup"><span data-stu-id="8691d-122">Set up acronyms answers</span></span>

<span data-ttu-id="8691d-123">[Microsoft 365 管理センター](https://admin.microsoft.com)で、[**[頭字語]**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)に移動し、**[頭字語の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8691d-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="8691d-124">Microsoft Search は、2 つのデータ ソースをクエリして、頭字語の回答をユーザーの検索に提供します:</span><span class="sxs-lookup"><span data-stu-id="8691d-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="8691d-125">**管理者が選択しました**。</span><span class="sxs-lookup"><span data-stu-id="8691d-125">**Admin-curated**.</span></span> <span data-ttu-id="8691d-126">[管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の IT 管理者によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="8691d-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="8691d-127">**システムによって選択されます**。</span><span class="sxs-lookup"><span data-stu-id="8691d-127">**System-curated**.</span></span> <span data-ttu-id="8691d-128">ユーザーの電子メールとドキュメント、および組織内で一般に利用可能なデータから Microsoft Search によって検出されます。</span><span class="sxs-lookup"><span data-stu-id="8691d-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="8691d-129">管理者が選択した頭字語を設定する</span><span class="sxs-lookup"><span data-stu-id="8691d-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="8691d-130">検索管理者は、Microsoft Search 管理センターの[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)頭字語タブに頭字語[を追加できます](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。</span><span class="sxs-lookup"><span data-stu-id="8691d-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="8691d-131">すべての内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8691d-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="8691d-132">これらの頭字語は、発行済みまたは下書き **状態** に **追加** できます。</span><span class="sxs-lookup"><span data-stu-id="8691d-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="8691d-133">**公開状態**。</span><span class="sxs-lookup"><span data-stu-id="8691d-133">**Published state**.</span></span> <span data-ttu-id="8691d-134">頭字語は、Microsoft Search を通じて組織のユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="8691d-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="8691d-135">公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8691d-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="8691d-136">**下書き状態**。</span><span class="sxs-lookup"><span data-stu-id="8691d-136">**Draft state**.</span></span> <span data-ttu-id="8691d-137">Microsoft Search で使用する前に頭字語を確認する場合は、下書き状態で頭字語を追加できます。</span><span class="sxs-lookup"><span data-stu-id="8691d-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="8691d-138">下書き状態の頭字語は検索結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="8691d-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="8691d-139">検索結果に表示するには、頭字語を発行済み状態に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8691d-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="8691d-140">頭字語を個別に追加したり、CSV ファイルに一括インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="8691d-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="8691d-141">次の表に示すフィールドを使用して CSV ファイルをアップロードします:</span><span class="sxs-lookup"><span data-stu-id="8691d-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="8691d-142">頭字語 (必須)</span><span class="sxs-lookup"><span data-stu-id="8691d-142">Acronym (mandatory)</span></span> | <span data-ttu-id="8691d-143">展開 (必須)</span><span class="sxs-lookup"><span data-stu-id="8691d-143">Expansion (mandatory)</span></span> | <span data-ttu-id="8691d-144">説明</span><span class="sxs-lookup"><span data-stu-id="8691d-144">Description</span></span>  | <span data-ttu-id="8691d-145">ソース</span><span class="sxs-lookup"><span data-stu-id="8691d-145">Source</span></span> | <span data-ttu-id="8691d-146">状態 (必須)</span><span class="sxs-lookup"><span data-stu-id="8691d-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="8691d-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="8691d-147">*XXX*</span></span> | <span data-ttu-id="8691d-148">*略語のスペル*</span><span class="sxs-lookup"><span data-stu-id="8691d-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="8691d-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="8691d-149">*URL*</span></span> | <span data-ttu-id="8691d-150">*公開または下書き*</span><span class="sxs-lookup"><span data-stu-id="8691d-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="8691d-151">CSV フィールド</span><span class="sxs-lookup"><span data-stu-id="8691d-151">CSV fields</span></span>

<span data-ttu-id="8691d-152">**頭字語**。</span><span class="sxs-lookup"><span data-stu-id="8691d-152">**Acronym**.</span></span> <span data-ttu-id="8691d-153">実際の短い形式または頭字語を含みます。</span><span class="sxs-lookup"><span data-stu-id="8691d-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="8691d-154">たとえば、*DNN* などです。</span><span class="sxs-lookup"><span data-stu-id="8691d-154">An example is *DNN*.</span></span>

<span data-ttu-id="8691d-155">**展開**。</span><span class="sxs-lookup"><span data-stu-id="8691d-155">**Expansion**.</span></span> <span data-ttu-id="8691d-156">頭字語の展開を含みます。</span><span class="sxs-lookup"><span data-stu-id="8691d-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="8691d-157">たとえば、*Deep Neural Network* などです。</span><span class="sxs-lookup"><span data-stu-id="8691d-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="8691d-158">**説明**。</span><span class="sxs-lookup"><span data-stu-id="8691d-158">**Description**.</span></span> <span data-ttu-id="8691d-159">頭字語とその展開についての詳細情報をユーザーに伝える頭字語の簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="8691d-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="8691d-160">たとえば、*deep neural network とは、特定の複雑さを持つニューラル ネットワーク、2 つ以上の層を持つニューラル ネットワークです*。</span><span class="sxs-lookup"><span data-stu-id="8691d-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="8691d-161">**ソース**。</span><span class="sxs-lookup"><span data-stu-id="8691d-161">**Source**.</span></span> <span data-ttu-id="8691d-162">頭字語についての詳細情報をユーザーに表示するページまたは Web サイトの URL。</span><span class="sxs-lookup"><span data-stu-id="8691d-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="8691d-163">**状態**。</span><span class="sxs-lookup"><span data-stu-id="8691d-163">**State**.</span></span> <span data-ttu-id="8691d-164">このフィールドには 2 つの値を指定できます:</span><span class="sxs-lookup"><span data-stu-id="8691d-164">This field can take two values:</span></span>

- <span data-ttu-id="8691d-165">**下書き**。</span><span class="sxs-lookup"><span data-stu-id="8691d-165">**Draft**.</span></span> <span data-ttu-id="8691d-166">頭字語を下書き状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="8691d-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="8691d-167">**公開**。</span><span class="sxs-lookup"><span data-stu-id="8691d-167">**Published**.</span></span> <span data-ttu-id="8691d-168">公開状態に頭字語を追加して、Microsoft Search で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8691d-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="8691d-169">システムで選択された頭字語</span><span class="sxs-lookup"><span data-stu-id="8691d-169">System-curated acronyms</span></span>

<span data-ttu-id="8691d-170">管理者にとって、組織内で使用されているすべての頭字語を回答に追加するのは難しいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="8691d-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="8691d-171">この機能により、検索管理者が認識していない頭字語を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="8691d-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="8691d-172">これを行うには、Microsoft Search は次のソースから頭字語を検出して作成します。</span><span class="sxs-lookup"><span data-stu-id="8691d-172">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="8691d-173">ユーザーのメール</span><span class="sxs-lookup"><span data-stu-id="8691d-173">Users’ emails</span></span>
- <span data-ttu-id="8691d-174">[SharePoint、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive、Microsoft OneNote]( https://onedrive.live.com/about/)[のドキュメント](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="8691d-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="8691d-175">SharePoint、OneDrive、または OneNote でユーザーがアクセスできる組織内のパブリック ドキュメント</span><span class="sxs-lookup"><span data-stu-id="8691d-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="8691d-176">Microsoft Search では、ドキュメントに対するアクセス権とアクセス許可を持つユーザーだけが、ドキュメントから検出された頭字語を確認できます。</span><span class="sxs-lookup"><span data-stu-id="8691d-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="8691d-177">ユーザーのメールボックスで頭字語が見つかると、そのユーザーだけがその頭字語を見る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8691d-177">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="8691d-178">管理者が選択した頭字語にはセットアップは必要ない。</span><span class="sxs-lookup"><span data-stu-id="8691d-178">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8691d-179">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="8691d-179">Frequently asked questions</span></span>

<span data-ttu-id="8691d-180">**Q: 管理者が選択したデータとシステムで管理されたデータは、どのようにランク付けされますか。**</span><span class="sxs-lookup"><span data-stu-id="8691d-180">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="8691d-181">**A:** 結果のランク付けは、結果がユーザーごとにカスタマイズされるので、人によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8691d-181">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="8691d-182">これらのカテゴリはどちらも常に他のカテゴリよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="8691d-182">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="8691d-183">**Q: 管理者が選択した頭字語が Microsoft Search に公開された後に表示されるのに、どれくらいの時間が必要ですか。**</span><span class="sxs-lookup"><span data-stu-id="8691d-183">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="8691d-184">**A:** 公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかります。</span><span class="sxs-lookup"><span data-stu-id="8691d-184">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="8691d-185">**Q: ユーザーが頭字語の回答をトリガーする方法**</span><span class="sxs-lookup"><span data-stu-id="8691d-185">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="8691d-186">**A**: 頭字語の回答を取得するには [、Bing、SharePoint、](https://bing.com)または Office [](https://products.office.com/sharepoint/collaboration) [365](https://Office.com)検索ボックスに特定のクエリ パターンを入力する **必要** があります。</span><span class="sxs-lookup"><span data-stu-id="8691d-186">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="8691d-187">**Q: 新しいメールやドキュメントを受信または送信した後、システムで指定された頭字語が表示されるのに、どれくらいの時間がですか。**</span><span class="sxs-lookup"><span data-stu-id="8691d-187">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="8691d-188">**A:** 新しいメールまたはドキュメントで見つかった頭字語は、Microsoft Search の結果に表示されるのに最大 7 日間かかる。</span><span class="sxs-lookup"><span data-stu-id="8691d-188">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="8691d-189">**Q: 文書から採掘するには、文書が特定の形式である必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="8691d-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="8691d-190">**A:** いいえ。</span><span class="sxs-lookup"><span data-stu-id="8691d-190">**A:** No.</span></span> <span data-ttu-id="8691d-191">画像、フォルダー、および zip ファイル以外のすべての種類のファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8691d-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="8691d-192">**Q: Microsoft は、すべての言語のドキュメントから頭字語を見つけるのか。**</span><span class="sxs-lookup"><span data-stu-id="8691d-192">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="8691d-193">**A**: Microsoft は、英語の文書からの採掘のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8691d-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="8691d-194">その他の言語のサポートは段階的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="8691d-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="8691d-195">**Q: 組織でシステムで作成された頭字語を表示しない場合は、どうでしょうか。この種の頭字語が検索結果に表示されるのを停止できますか。**</span><span class="sxs-lookup"><span data-stu-id="8691d-195">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="8691d-196">**A**: 検索結果にシステム指定の頭字語が表示されるのをオフにする場合は、ビジネス製品のサポートに問い合わせの指示に従ってカスタマー サポート チケット [を作成します](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)。</span><span class="sxs-lookup"><span data-stu-id="8691d-196">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="8691d-197">サポート チケットを作成した後、システムが選択した頭字語が検索結果に表示されな最大 48 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="8691d-197">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
