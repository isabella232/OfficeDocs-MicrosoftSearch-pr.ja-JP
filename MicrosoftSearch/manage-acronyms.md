---
title: Microsoft Search で頭字語の回答を管理する
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
description: Microsoft Search で頭字語の回答を作成および更新する
ms.openlocfilehash: 9d58306751f735cef77eba4404597c73c0528c11
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996078"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="69af8-103">Microsoft Search で頭字語の回答を管理する</span><span class="sxs-lookup"><span data-stu-id="69af8-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="69af8-104">ユーザーは、組織やチームで使用されている頭字語や略語に慣れていないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="69af8-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="69af8-105">組織またはチームに固有の用語は、チーム間を移動したり、社内パートナーと共同で作業する人、または組織の新人には新しい場合があります。</span><span class="sxs-lookup"><span data-stu-id="69af8-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, those who work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="69af8-106">組織の標準的な用語には、常に単一の参照があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="69af8-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="69af8-107">単一の参照がないと、これらの頭字語の定義や展開が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="69af8-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="69af8-108">Microsoft Search は、頭字語の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="69af8-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="69af8-109">ユーザーのエクスぺリエンス</span><span class="sxs-lookup"><span data-stu-id="69af8-109">What users experience</span></span>

<span data-ttu-id="69af8-110">Microsoft Search のユーザーは [Bing](https://bing.com) の頭字語を使用して、定義を入手できます。</span><span class="sxs-lookup"><span data-stu-id="69af8-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://bing.com).</span></span> <span data-ttu-id="69af8-111">**[検索]** ボックスで、次の例のようにクエリを入力します:</span><span class="sxs-lookup"><span data-stu-id="69af8-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="69af8-112">DNN *とは*</span><span class="sxs-lookup"><span data-stu-id="69af8-112">*What is* DNN</span></span>
- <span data-ttu-id="69af8-113">DNN *を定義する*</span><span class="sxs-lookup"><span data-stu-id="69af8-113">*Define* DNN</span></span>
- <span data-ttu-id="69af8-114">DNN *の定義*</span><span class="sxs-lookup"><span data-stu-id="69af8-114">DNN *definition*</span></span>
- <span data-ttu-id="69af8-115">DNN *を展開する*</span><span class="sxs-lookup"><span data-stu-id="69af8-115">*Expand* DNN</span></span>
- <span data-ttu-id="69af8-116">DNN *の展開*</span><span class="sxs-lookup"><span data-stu-id="69af8-116">DNN *expansion*</span></span>
- <span data-ttu-id="69af8-117">DNN *の意味*</span><span class="sxs-lookup"><span data-stu-id="69af8-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="69af8-118">DNN *は意味する*</span><span class="sxs-lookup"><span data-stu-id="69af8-118">DNN *means*</span></span>

<span data-ttu-id="69af8-119">結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。</span><span class="sxs-lookup"><span data-stu-id="69af8-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="69af8-120">ユーザーは、対応する回答をトリガーするために、頭字語で指定された *キーワード* を含むクエリを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69af8-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="69af8-121">頭字語のクエリでは、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="69af8-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="69af8-122">頭字語の回答を設定する</span><span class="sxs-lookup"><span data-stu-id="69af8-122">Set up Acronyms answers</span></span>

<span data-ttu-id="69af8-123">Microsoft 365 [管理センター](https://admin.microsoft.com) で、**[設定]** > **[Microsoft Search]** > \*\* [回答]\*\* > [**[頭字語]**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の順に移動し、**[頭字語の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="69af8-123">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Answers** > [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronyms**.</span></span>

<span data-ttu-id="69af8-124">Microsoft Search は、2 つのデータ ソースをクエリして、頭字語の回答をユーザーの検索に提供します:</span><span class="sxs-lookup"><span data-stu-id="69af8-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="69af8-125">**編集上の頭字語**。</span><span class="sxs-lookup"><span data-stu-id="69af8-125">**Editorial acronyms**.</span></span> <span data-ttu-id="69af8-126">[管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の IT 管理者によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="69af8-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="69af8-127">**採掘された頭字語**。</span><span class="sxs-lookup"><span data-stu-id="69af8-127">**Mined acronyms**.</span></span> <span data-ttu-id="69af8-128">ユーザーの個人的なメールと文書、および組織内で公開されているデータから Microsoft Search によって採掘されます。</span><span class="sxs-lookup"><span data-stu-id="69af8-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="69af8-129">編集上の頭字語を設定する</span><span class="sxs-lookup"><span data-stu-id="69af8-129">Set up editorial acronyms</span></span>

<span data-ttu-id="69af8-130">検索管理者は、[Microsoft Search 管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) の [[頭字語] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) で編集上の頭字語を設定できます。</span><span class="sxs-lookup"><span data-stu-id="69af8-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="69af8-131">すべての内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="69af8-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="69af8-132">編集上の頭字語は、**公開** または **下書き** の状態に追加されます:</span><span class="sxs-lookup"><span data-stu-id="69af8-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="69af8-133">**公開状態**。</span><span class="sxs-lookup"><span data-stu-id="69af8-133">**Published state**.</span></span> <span data-ttu-id="69af8-134">頭字語は、Microsoft Search を通じて組織の従業員が利用できます。</span><span class="sxs-lookup"><span data-stu-id="69af8-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="69af8-135">公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="69af8-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="69af8-136">**下書き状態**。</span><span class="sxs-lookup"><span data-stu-id="69af8-136">**Draft state**.</span></span> <span data-ttu-id="69af8-137">Microsoft Search で使用できるようにする前に、管理者が頭字語の回答を確認したい場合は、頭字語を下書き状態に追加できます。</span><span class="sxs-lookup"><span data-stu-id="69af8-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="69af8-138">下書き状態に追加された略語は、Microsoft Search では使用できません。</span><span class="sxs-lookup"><span data-stu-id="69af8-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="69af8-139">管理者は、使用できるようにするには、頭字語を公開状態に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69af8-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="69af8-140">管理者は、頭字語を個別に追加するか、CSV ファイルに一括インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="69af8-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="69af8-141">次の表に示すフィールドを使用して CSV ファイルをアップロードします:</span><span class="sxs-lookup"><span data-stu-id="69af8-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="69af8-142">頭字語 (必須)</span><span class="sxs-lookup"><span data-stu-id="69af8-142">Acronym (mandatory)</span></span> | <span data-ttu-id="69af8-143">展開 (必須)</span><span class="sxs-lookup"><span data-stu-id="69af8-143">Expansion (mandatory)</span></span> | <span data-ttu-id="69af8-144">説明</span><span class="sxs-lookup"><span data-stu-id="69af8-144">Description</span></span>  | <span data-ttu-id="69af8-145">ソース</span><span class="sxs-lookup"><span data-stu-id="69af8-145">Source</span></span> | <span data-ttu-id="69af8-146">状態 (必須)</span><span class="sxs-lookup"><span data-stu-id="69af8-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="69af8-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="69af8-147">*XXX*</span></span> | <span data-ttu-id="69af8-148">*略語のスペル*</span><span class="sxs-lookup"><span data-stu-id="69af8-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="69af8-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="69af8-149">*URL*</span></span> | <span data-ttu-id="69af8-150">*公開または下書き*</span><span class="sxs-lookup"><span data-stu-id="69af8-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="69af8-151">CSV フィールド</span><span class="sxs-lookup"><span data-stu-id="69af8-151">CSV fields</span></span>

<span data-ttu-id="69af8-152">**頭字語**。</span><span class="sxs-lookup"><span data-stu-id="69af8-152">**Acronym**.</span></span> <span data-ttu-id="69af8-153">実際の短い形式または頭字語を含みます。</span><span class="sxs-lookup"><span data-stu-id="69af8-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="69af8-154">たとえば、*DNN* などです。</span><span class="sxs-lookup"><span data-stu-id="69af8-154">An example is *DNN*.</span></span>

<span data-ttu-id="69af8-155">**展開**。</span><span class="sxs-lookup"><span data-stu-id="69af8-155">**Expansion**.</span></span> <span data-ttu-id="69af8-156">頭字語の展開を含みます。</span><span class="sxs-lookup"><span data-stu-id="69af8-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="69af8-157">たとえば、*Deep Neural Network* などです。</span><span class="sxs-lookup"><span data-stu-id="69af8-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="69af8-158">**説明**。</span><span class="sxs-lookup"><span data-stu-id="69af8-158">**Description**.</span></span> <span data-ttu-id="69af8-159">頭字語とその展開の意味をユーザーにすばやく伝える頭字語の簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="69af8-159">A brief description of the acronym that gives users quick insight into what the acronym and its expansion mean.</span></span> <span data-ttu-id="69af8-160">たとえば、*deep neural network とは、特定の複雑さを持つニューラル ネットワーク、2 つ以上の層を持つニューラル ネットワークです*。</span><span class="sxs-lookup"><span data-stu-id="69af8-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="69af8-161">**ソース**。</span><span class="sxs-lookup"><span data-stu-id="69af8-161">**Source**.</span></span> <span data-ttu-id="69af8-162">頭字語についての詳細情報をユーザーに表示するページまたは Web サイトの URL。</span><span class="sxs-lookup"><span data-stu-id="69af8-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="69af8-163">**状態**。</span><span class="sxs-lookup"><span data-stu-id="69af8-163">**State**.</span></span> <span data-ttu-id="69af8-164">このフィールドには 2 つの値を指定できます:</span><span class="sxs-lookup"><span data-stu-id="69af8-164">This field can take two values:</span></span>

- <span data-ttu-id="69af8-165">**下書き**。</span><span class="sxs-lookup"><span data-stu-id="69af8-165">**Draft**.</span></span> <span data-ttu-id="69af8-166">頭字語を下書き状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="69af8-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="69af8-167">**公開**。</span><span class="sxs-lookup"><span data-stu-id="69af8-167">**Published**.</span></span> <span data-ttu-id="69af8-168">公開状態に頭字語を追加して、Microsoft Search で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="69af8-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="69af8-169">採掘された頭字語</span><span class="sxs-lookup"><span data-stu-id="69af8-169">Mined acronyms</span></span>

<span data-ttu-id="69af8-170">管理者にとって、組織内で使用されているすべての頭字語を回答に追加するのは難しいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="69af8-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="69af8-171">この機能により、検索管理者が認識していない頭字語を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="69af8-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="69af8-172">そのために、Microsoft Search は次のソースから頭字語を採掘します:</span><span class="sxs-lookup"><span data-stu-id="69af8-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="69af8-173">ユーザーのメール。</span><span class="sxs-lookup"><span data-stu-id="69af8-173">Users’ emails.</span></span>
- <span data-ttu-id="69af8-174">[SharePoint](https://products.office.com/sharepoint/collaboration)、[Microsoft OneDrive]( https://onedrive.live.com/about/)、[Microsoft OneNote](http://www.onenote.com/) の文書。</span><span class="sxs-lookup"><span data-stu-id="69af8-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) and [Microsoft OneNote](http://www.onenote.com/).</span></span>
- <span data-ttu-id="69af8-175">ユーザーが SharePoint、OneDrive、または OneNote でアクセスできる組織内の公開文書。</span><span class="sxs-lookup"><span data-stu-id="69af8-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="69af8-176">Microsoft Search は、文書に対してアクセス権を持つユーザーのみが、その文書から採掘された頭字語を見ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="69af8-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="69af8-177">頭字語がユーザーのメールボックスから採掘されると、そのユーザーのみがその頭字語を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="69af8-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="69af8-178">採掘された頭字語に設定は必要はありません。</span><span class="sxs-lookup"><span data-stu-id="69af8-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="69af8-179">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="69af8-179">Frequently asked questions</span></span>

<span data-ttu-id="69af8-180">**Q: 編集上の採掘されたデータはどのようにランク付けされていますか?**</span><span class="sxs-lookup"><span data-stu-id="69af8-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="69af8-181">**A:** この機能は現在、編集上の頭字語を採掘された頭字語より上にランク付けしています。</span><span class="sxs-lookup"><span data-stu-id="69af8-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="69af8-182">**Q: 編集上の頭字語が公開されてから Microsoft Search に表示されるまで、どのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="69af8-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="69af8-183">**A:** 公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかります。</span><span class="sxs-lookup"><span data-stu-id="69af8-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="69af8-184">**Q: ユーザーが頭字語の回答をトリガーするにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="69af8-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="69af8-185">**A**: 頭字語の回答を取得するには、ユーザーは [Bing](https://bing.com) **検索** ボックスに特定のクエリ パターンを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69af8-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com) **Search** box.</span></span> <span data-ttu-id="69af8-186">現在、頭字語の回答は [Office 365](https://Office.com) または [SharePoint](https://products.office.com/sharepoint/collaboration) では利用できません。</span><span class="sxs-lookup"><span data-stu-id="69af8-186">Currently, Acronym answers aren't available in [Office 365](https://Office.com) or [SharePoint](https://products.office.com/sharepoint/collaboration).</span></span>

<span data-ttu-id="69af8-187">**Q: 新しいメールや文書の送受信後に、採掘された頭字語が表示されるまで、どのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="69af8-187">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="69af8-188">**A:** 新しいメールまたは文書から採掘された頭字語がMicrosoft Search 結果に表示されるまでには、最大 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="69af8-188">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="69af8-189">**Q: 文書から採掘するには、文書が特定の形式である必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="69af8-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="69af8-190">**A:** いいえ。</span><span class="sxs-lookup"><span data-stu-id="69af8-190">**A:** No.</span></span> <span data-ttu-id="69af8-191">画像、フォルダー、および zip ファイル以外のすべての種類のファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="69af8-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="69af8-192">**Q: Microsoft はすべての言語の文書から頭字語を採掘しますか?**</span><span class="sxs-lookup"><span data-stu-id="69af8-192">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="69af8-193">**A**: Microsoft は、英語の文書からの採掘のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="69af8-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="69af8-194">その他の言語のサポートは段階的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="69af8-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="69af8-195">**Q: 組織内の採掘された頭字語を表示する必要がない場合はどうすればよいですか? 採掘された頭字語を検索結果に表示しないようにすることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="69af8-195">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="69af8-196">**A**: 検索結果に採掘された頭字語が表示されないようにするには、[「ビジネス製品のサポートに問い合わせる」](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support) の説明に従って、カスタマー サポート チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="69af8-196">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="69af8-197">サポート チケットを作成してから、採掘された頭字語が検索結果に表示されなくなるまでに最大 48 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="69af8-197">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>

<span data-ttu-id="69af8-198">**Q: [Office 365](https://Office.com) と [SharePoint Online](https://products.office.com/sharepoint/collaboration) で頭字語の回答はいつ表示されますか?**</span><span class="sxs-lookup"><span data-stu-id="69af8-198">**Q: When will I see Acronyms answers in [Office 365](https://Office.com) and [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**</span></span>

<span data-ttu-id="69af8-199">**A**: Office 365 および SharePoint Online での頭字語の回答は、製品ロードマップに含まれていますが、現在のところ、日付や時間枠を提供することはできません。</span><span class="sxs-lookup"><span data-stu-id="69af8-199">**A**: Acronyms answers in Office 365 and SharePoint Online are part of our product roadmap, but we're currently unable to provide a date or timeframe.</span></span>
