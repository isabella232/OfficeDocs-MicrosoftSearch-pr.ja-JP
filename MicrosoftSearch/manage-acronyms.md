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
ms.openlocfilehash: 5677ff6915c9e43e2559964c40086cb360a05db7
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031370"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="cd378-103">Microsoft Search で頭字語の回答を管理する</span><span class="sxs-lookup"><span data-stu-id="cd378-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="cd378-104">ユーザーは、組織やチームで使用されている頭字語や略語に慣れていないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="cd378-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="cd378-105">組織またはチームに固有の用語は、チーム間を移動したり、社内パートナーと共同で作業する人、または組織の新人には新しい場合があります。  </span><span class="sxs-lookup"><span data-stu-id="cd378-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="cd378-106">組織の標準的な用語には、常に単一の参照があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="cd378-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="cd378-107">単一の参照がないと、これらの頭字語の定義や展開が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="cd378-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="cd378-108">Microsoft Search は、頭字語の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="cd378-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="cd378-109">ユーザーのエクスぺリエンス</span><span class="sxs-lookup"><span data-stu-id="cd378-109">What users experience</span></span>

<span data-ttu-id="cd378-110">Microsoft Search のユーザーは [Bing](https://Bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)および[Office 365](https://Office.com)の頭字語を使用して、定義を入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd378-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="cd378-111">**[検索]** ボックスで、次の例のようにクエリを入力します:</span><span class="sxs-lookup"><span data-stu-id="cd378-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="cd378-112">*What is* DNN</span><span class="sxs-lookup"><span data-stu-id="cd378-112">*What is* DNN</span></span>
- <span data-ttu-id="cd378-113">*Define* DNN</span><span class="sxs-lookup"><span data-stu-id="cd378-113">*Define* DNN</span></span>
- <span data-ttu-id="cd378-114">DNN *definition*</span><span class="sxs-lookup"><span data-stu-id="cd378-114">DNN *definition*</span></span>
- <span data-ttu-id="cd378-115">*Expand* DNN</span><span class="sxs-lookup"><span data-stu-id="cd378-115">*Expand* DNN</span></span>
- <span data-ttu-id="cd378-116">DNN *expansion*</span><span class="sxs-lookup"><span data-stu-id="cd378-116">DNN *expansion*</span></span>
- <span data-ttu-id="cd378-117">*Meaning of* DNN</span><span class="sxs-lookup"><span data-stu-id="cd378-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="cd378-118">DNN *means*</span><span class="sxs-lookup"><span data-stu-id="cd378-118">DNN *means*</span></span>

<span data-ttu-id="cd378-119">結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd378-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="cd378-120">ユーザーは、対応する回答をトリガーするために、頭字語で指定された *キーワード* を含むクエリを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd378-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="cd378-121">頭字語のクエリでは、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="cd378-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="cd378-122">頭字語の回答を設定する</span><span class="sxs-lookup"><span data-stu-id="cd378-122">Set up acronyms answers</span></span>

<span data-ttu-id="cd378-123">[Microsoft 365 管理センター](https://admin.microsoft.com)で、[**[頭字語]**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)に移動し、**[頭字語の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd378-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="cd378-124">Microsoft Search は、2 つのデータ ソースをクエリして、頭字語の回答をユーザーの検索に提供します:</span><span class="sxs-lookup"><span data-stu-id="cd378-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="cd378-125">**管理者が管理します**。</span><span class="sxs-lookup"><span data-stu-id="cd378-125">**Admin-curated**.</span></span> <span data-ttu-id="cd378-126">[管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の IT 管理者によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="cd378-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="cd378-127">**System-curated**.</span><span class="sxs-lookup"><span data-stu-id="cd378-127">**System-curated**.</span></span> <span data-ttu-id="cd378-128">ユーザーの電子メールとドキュメント、組織内で一般に利用可能なデータから Microsoft Search によって検出されました。</span><span class="sxs-lookup"><span data-stu-id="cd378-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="cd378-129">管理者が指定した頭字語を設定する</span><span class="sxs-lookup"><span data-stu-id="cd378-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="cd378-130">検索管理者は、Microsoft Search 管理センターの [[頭](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) 字語] タブに頭字語  [を追加できます](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。</span><span class="sxs-lookup"><span data-stu-id="cd378-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="cd378-131">すべての内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="cd378-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="cd378-132">これらの頭字語は、発行済みまたは下書 **き状態に\*\*\*\*追加** できます。</span><span class="sxs-lookup"><span data-stu-id="cd378-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="cd378-133">**公開状態**。</span><span class="sxs-lookup"><span data-stu-id="cd378-133">**Published state**.</span></span> <span data-ttu-id="cd378-134">頭字語は、Microsoft Search を通じて組織のユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="cd378-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="cd378-135">公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd378-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="cd378-136">**下書き状態**。</span><span class="sxs-lookup"><span data-stu-id="cd378-136">**Draft state**.</span></span> <span data-ttu-id="cd378-137">Microsoft Search で使用できる前に頭字語を確認する場合は、下書き状態で頭字語を追加できます。</span><span class="sxs-lookup"><span data-stu-id="cd378-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="cd378-138">下書き状態の頭字語は検索結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="cd378-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="cd378-139">検索結果に表示するには、頭字語を発行済み状態に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd378-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="cd378-140">頭字語を個別に追加するか、CSV ファイルに一括インポートできます。</span><span class="sxs-lookup"><span data-stu-id="cd378-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="cd378-141">次の表に示すフィールドを使用して CSV ファイルをアップロードします:</span><span class="sxs-lookup"><span data-stu-id="cd378-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="cd378-142">頭字語 (必須)</span><span class="sxs-lookup"><span data-stu-id="cd378-142">Acronym (Mandatory)</span></span> | <span data-ttu-id="cd378-143">拡張 (必須)</span><span class="sxs-lookup"><span data-stu-id="cd378-143">Expansion (Mandatory)</span></span> | <span data-ttu-id="cd378-144">Url</span><span class="sxs-lookup"><span data-stu-id="cd378-144">Url</span></span> | <span data-ttu-id="cd378-145">説明</span><span class="sxs-lookup"><span data-stu-id="cd378-145">Description</span></span>  | <span data-ttu-id="cd378-146">状態 (必須)</span><span class="sxs-lookup"><span data-stu-id="cd378-146">State (Mandatory)</span></span> | <span data-ttu-id="cd378-147">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="cd378-147">Last Modified</span></span> | <span data-ttu-id="cd378-148">最終変更者</span><span class="sxs-lookup"><span data-stu-id="cd378-148">Last Modified By</span></span> | <span data-ttu-id="cd378-149">ID</span><span class="sxs-lookup"><span data-stu-id="cd378-149">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="cd378-150">*XXX*</span><span class="sxs-lookup"><span data-stu-id="cd378-150">*XXX*</span></span> | <span data-ttu-id="cd378-151">*略語のスペル*</span><span class="sxs-lookup"><span data-stu-id="cd378-151">*Spelled out abbreviation*</span></span> | <span data-ttu-id="cd378-152">*Source*</span><span class="sxs-lookup"><span data-stu-id="cd378-152">*Source*</span></span> |  | <span data-ttu-id="cd378-153">*公開または下書き*</span><span class="sxs-lookup"><span data-stu-id="cd378-153">*Published or Draft*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="cd378-154">CSV フィールド</span><span class="sxs-lookup"><span data-stu-id="cd378-154">CSV fields</span></span>

<span data-ttu-id="cd378-155">**頭字語**。</span><span class="sxs-lookup"><span data-stu-id="cd378-155">**Acronym**.</span></span> <span data-ttu-id="cd378-156">実際の短い形式または頭字語を含みます。</span><span class="sxs-lookup"><span data-stu-id="cd378-156">Contains the actual short form or acronym.</span></span> <span data-ttu-id="cd378-157">たとえば、*DNN* などです。</span><span class="sxs-lookup"><span data-stu-id="cd378-157">An example is *DNN*.</span></span>

<span data-ttu-id="cd378-158">**展開**。</span><span class="sxs-lookup"><span data-stu-id="cd378-158">**Expansion**.</span></span> <span data-ttu-id="cd378-159">頭字語の展開を含みます。</span><span class="sxs-lookup"><span data-stu-id="cd378-159">Contains the expansion of the acronym.</span></span> <span data-ttu-id="cd378-160">たとえば、*Deep Neural Network* などです。</span><span class="sxs-lookup"><span data-stu-id="cd378-160">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="cd378-161">**説明**。</span><span class="sxs-lookup"><span data-stu-id="cd378-161">**Description**.</span></span> <span data-ttu-id="cd378-162">頭字語とその展開についての詳細情報をユーザーに伝える頭字語の簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="cd378-162">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="cd378-163">たとえば、*deep neural network とは、特定の複雑さを持つニューラル ネットワーク、2 つ以上の層を持つニューラル ネットワークです*。</span><span class="sxs-lookup"><span data-stu-id="cd378-163">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="cd378-164">**ソース**。</span><span class="sxs-lookup"><span data-stu-id="cd378-164">**Source**.</span></span> <span data-ttu-id="cd378-165">頭字語についての詳細情報をユーザーに表示するページまたは Web サイトの URL。</span><span class="sxs-lookup"><span data-stu-id="cd378-165">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="cd378-166">**状態**。</span><span class="sxs-lookup"><span data-stu-id="cd378-166">**State**.</span></span> <span data-ttu-id="cd378-167">このフィールドには 2 つの値を指定できます:</span><span class="sxs-lookup"><span data-stu-id="cd378-167">This field can take two values:</span></span>

- <span data-ttu-id="cd378-168">**下書き**。</span><span class="sxs-lookup"><span data-stu-id="cd378-168">**Draft**.</span></span> <span data-ttu-id="cd378-169">頭字語を下書き状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="cd378-169">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="cd378-170">**公開**。</span><span class="sxs-lookup"><span data-stu-id="cd378-170">**Published**.</span></span> <span data-ttu-id="cd378-171">公開状態に頭字語を追加して、Microsoft Search で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cd378-171">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="cd378-172">System-curated 頭字語</span><span class="sxs-lookup"><span data-stu-id="cd378-172">System-curated acronyms</span></span>

<span data-ttu-id="cd378-173">管理者にとって、組織内で使用されているすべての頭字語を回答に追加するのは難しいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="cd378-173">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="cd378-174">この機能により、検索管理者が認識していない頭字語を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="cd378-174">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="cd378-175">この作業を行うには、Microsoft Search は次のソースから頭字語を検出してキュレートします。</span><span class="sxs-lookup"><span data-stu-id="cd378-175">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="cd378-176">ユーザーのメール</span><span class="sxs-lookup"><span data-stu-id="cd378-176">Users’ emails</span></span>
- <span data-ttu-id="cd378-177">[SharePoint 、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive、Microsoft]( https://onedrive.live.com/about/) [OneNote のドキュメント](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="cd378-177">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="cd378-178">SharePoint、OneDrive、または OneNote でユーザーがアクセスできる組織内のパブリック ドキュメント</span><span class="sxs-lookup"><span data-stu-id="cd378-178">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="cd378-179">Microsoft Search では、ドキュメントへのアクセス権とアクセス許可を持つユーザーだけが、ドキュメントから検出された頭字語を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cd378-179">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="cd378-180">ユーザーのメールボックスで頭字語が見つかった場合、その頭字語を表示できるのはそのユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="cd378-180">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="cd378-181">管理者が指定した頭字語のセットアップは不要です。</span><span class="sxs-lookup"><span data-stu-id="cd378-181">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="cd378-182">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="cd378-182">Frequently asked questions</span></span>

<span data-ttu-id="cd378-183">**Q: 管理者が管理するデータとシステムで管理されたデータのランク付け方法**</span><span class="sxs-lookup"><span data-stu-id="cd378-183">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="cd378-184">**A:** 結果のランク付けは、結果が各ユーザーに合わせたものとして、個人ごとに異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd378-184">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="cd378-185">これらのどちらのカテゴリも、常に他のカテゴリよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cd378-185">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="cd378-186">**Q: 管理者が指定した頭字語が Microsoft Search で公開された後に表示されるのにどれくらいの時間が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="cd378-186">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="cd378-187">**A:** 公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかります。</span><span class="sxs-lookup"><span data-stu-id="cd378-187">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="cd378-188">**Q: ユーザーが頭字語の回答をトリガーする方法**</span><span class="sxs-lookup"><span data-stu-id="cd378-188">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="cd378-189">**A**: 頭字語の回答を取得するには [、Bing、SharePoint、](https://bing.com)または [](https://products.office.com/sharepoint/collaboration)[[365](https://Office.com) Search] ボックスに特定のクエリ Office **入力する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="cd378-189">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="cd378-190">**Q: 新しい電子メールまたはドキュメントを受信または送信した後に、システムで指定された頭字語が表示されるのにどのくらいの時間が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="cd378-190">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="cd378-191">**A:** 新しい電子メールまたはドキュメントで見つかった頭字語は、Microsoft 検索結果に表示されるまで最大 7 日かかっています。</span><span class="sxs-lookup"><span data-stu-id="cd378-191">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="cd378-192">**Q: 文書から採掘するには、文書が特定の形式である必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="cd378-192">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="cd378-193">**A:** いいえ。</span><span class="sxs-lookup"><span data-stu-id="cd378-193">**A:** No.</span></span> <span data-ttu-id="cd378-194">画像、フォルダー、および zip ファイル以外のすべての種類のファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cd378-194">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="cd378-195">**Q: Microsoft は、すべての言語のドキュメントから頭字語を検出しますか?**</span><span class="sxs-lookup"><span data-stu-id="cd378-195">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="cd378-196">**A**: Microsoft は、英語の文書からの採掘のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cd378-196">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="cd378-197">その他の言語のサポートは段階的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="cd378-197">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="cd378-198">**Q: 組織がシステムで指定された頭字語を表示しない場合は、どうしますか。検索結果にこの種類の頭字語が表示されるのを停止できますか?**</span><span class="sxs-lookup"><span data-stu-id="cd378-198">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="cd378-199">**A**: 検索結果にシステムで指定された頭字語を表示するをオフにする場合は、「ビジネス製品のサポートに問い合わせ」の指示に従って、カスタマー サポート [チケットを作成します](/microsoft-365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="cd378-199">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="cd378-200">サポート チケットを作成した後、システムでキュアされた頭字語が検索結果に表示されるのを停止するには、最大 48 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="cd378-200">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>