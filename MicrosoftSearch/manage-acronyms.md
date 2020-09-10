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
ms.openlocfilehash: e328ecb7604a144b51f3a1483eef1b1c3a7e0bcb
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422948"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="b3659-103">Microsoft Search で頭字語の回答を管理する</span><span class="sxs-lookup"><span data-stu-id="b3659-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="b3659-104">ユーザーは、組織やチームで使用されている頭字語や略語に慣れていないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="b3659-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="b3659-105">組織またはチームに固有の用語は、チーム間を移動したり、内部パートナーチームと連携したり、組織にとって新しくなったりするユーザーにとって新しいものになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3659-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="b3659-106">組織の標準的な用語には、常に単一の参照があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="b3659-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="b3659-107">単一の参照がないと、これらの頭字語の定義や展開が難しくなります。</span><span class="sxs-lookup"><span data-stu-id="b3659-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="b3659-108">Microsoft Search は、頭字語の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="b3659-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="b3659-109">ユーザーのエクスぺリエンス</span><span class="sxs-lookup"><span data-stu-id="b3659-109">What users experience</span></span>

<span data-ttu-id="b3659-110">Microsoft 検索ユーザーは、 [Bing](https://Bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)、および [Office 365](https://Office.com)の頭字語を使用して定義を取得できます。</span><span class="sxs-lookup"><span data-stu-id="b3659-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="b3659-111">**[検索]** ボックスで、次の例のようにクエリを入力します:</span><span class="sxs-lookup"><span data-stu-id="b3659-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="b3659-112">DNN *とは*</span><span class="sxs-lookup"><span data-stu-id="b3659-112">*What is* DNN</span></span>
- <span data-ttu-id="b3659-113">DNN *を定義する*</span><span class="sxs-lookup"><span data-stu-id="b3659-113">*Define* DNN</span></span>
- <span data-ttu-id="b3659-114">DNN *の定義*</span><span class="sxs-lookup"><span data-stu-id="b3659-114">DNN *definition*</span></span>
- <span data-ttu-id="b3659-115">DNN *を展開する*</span><span class="sxs-lookup"><span data-stu-id="b3659-115">*Expand* DNN</span></span>
- <span data-ttu-id="b3659-116">DNN *の展開*</span><span class="sxs-lookup"><span data-stu-id="b3659-116">DNN *expansion*</span></span>
- <span data-ttu-id="b3659-117">DNN *の意味*</span><span class="sxs-lookup"><span data-stu-id="b3659-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="b3659-118">DNN *は意味する*</span><span class="sxs-lookup"><span data-stu-id="b3659-118">DNN *means*</span></span>

<span data-ttu-id="b3659-119">結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b3659-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="b3659-120">ユーザーは、対応する回答をトリガーするために、頭字語で指定された *キーワード* を含むクエリを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3659-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="b3659-121">頭字語のクエリでは、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="b3659-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="b3659-122">頭字語の回答を設定する</span><span class="sxs-lookup"><span data-stu-id="b3659-122">Set up Acronyms answers</span></span>

<span data-ttu-id="b3659-123">[Microsoft 365 管理センター](https://admin.microsoft.com)で、[[**頭字**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)語] に移動し、[**頭字語の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b3659-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="b3659-124">Microsoft Search は、2 つのデータ ソースをクエリして、頭字語の回答をユーザーの検索に提供します:</span><span class="sxs-lookup"><span data-stu-id="b3659-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="b3659-125">**編集上の頭字語**。</span><span class="sxs-lookup"><span data-stu-id="b3659-125">**Editorial acronyms**.</span></span> <span data-ttu-id="b3659-126">[管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の IT 管理者によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="b3659-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="b3659-127">**採掘された頭字語**。</span><span class="sxs-lookup"><span data-stu-id="b3659-127">**Mined acronyms**.</span></span> <span data-ttu-id="b3659-128">ユーザーの個人的なメールと文書、および組織内で公開されているデータから Microsoft Search によって採掘されます。</span><span class="sxs-lookup"><span data-stu-id="b3659-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="b3659-129">編集上の頭字語を設定する</span><span class="sxs-lookup"><span data-stu-id="b3659-129">Set up editorial acronyms</span></span>

<span data-ttu-id="b3659-130">検索管理者は、[Microsoft Search 管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) の [[頭字語] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) で編集上の頭字語を設定できます。</span><span class="sxs-lookup"><span data-stu-id="b3659-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="b3659-131">すべての内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="b3659-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="b3659-132">編集上の頭字語は、**公開** または **下書き** の状態に追加されます:</span><span class="sxs-lookup"><span data-stu-id="b3659-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="b3659-133">**公開状態**。</span><span class="sxs-lookup"><span data-stu-id="b3659-133">**Published state**.</span></span> <span data-ttu-id="b3659-134">頭字語は、Microsoft Search を通じて組織の従業員が利用できます。</span><span class="sxs-lookup"><span data-stu-id="b3659-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="b3659-135">公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3659-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="b3659-136">**下書き状態**。</span><span class="sxs-lookup"><span data-stu-id="b3659-136">**Draft state**.</span></span> <span data-ttu-id="b3659-137">Microsoft Search で使用できるようにする前に、管理者が頭字語の回答を確認したい場合は、頭字語を下書き状態に追加できます。</span><span class="sxs-lookup"><span data-stu-id="b3659-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="b3659-138">下書き状態に追加された略語は、Microsoft Search では使用できません。</span><span class="sxs-lookup"><span data-stu-id="b3659-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="b3659-139">管理者は、使用できるようにするには、頭字語を公開状態に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3659-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="b3659-140">管理者は、頭字語を個別に追加するか、CSV ファイルに一括インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="b3659-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="b3659-141">次の表に示すフィールドを使用して CSV ファイルをアップロードします:</span><span class="sxs-lookup"><span data-stu-id="b3659-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="b3659-142">頭字語 (必須)</span><span class="sxs-lookup"><span data-stu-id="b3659-142">Acronym (mandatory)</span></span> | <span data-ttu-id="b3659-143">展開 (必須)</span><span class="sxs-lookup"><span data-stu-id="b3659-143">Expansion (mandatory)</span></span> | <span data-ttu-id="b3659-144">説明</span><span class="sxs-lookup"><span data-stu-id="b3659-144">Description</span></span>  | <span data-ttu-id="b3659-145">ソース</span><span class="sxs-lookup"><span data-stu-id="b3659-145">Source</span></span> | <span data-ttu-id="b3659-146">状態 (必須)</span><span class="sxs-lookup"><span data-stu-id="b3659-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="b3659-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="b3659-147">*XXX*</span></span> | <span data-ttu-id="b3659-148">*略語のスペル*</span><span class="sxs-lookup"><span data-stu-id="b3659-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="b3659-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="b3659-149">*URL*</span></span> | <span data-ttu-id="b3659-150">*公開または下書き*</span><span class="sxs-lookup"><span data-stu-id="b3659-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="b3659-151">CSV フィールド</span><span class="sxs-lookup"><span data-stu-id="b3659-151">CSV fields</span></span>

<span data-ttu-id="b3659-152">**頭字語**。</span><span class="sxs-lookup"><span data-stu-id="b3659-152">**Acronym**.</span></span> <span data-ttu-id="b3659-153">実際の短い形式または頭字語を含みます。</span><span class="sxs-lookup"><span data-stu-id="b3659-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="b3659-154">たとえば、*DNN* などです。</span><span class="sxs-lookup"><span data-stu-id="b3659-154">An example is *DNN*.</span></span>

<span data-ttu-id="b3659-155">**展開**。</span><span class="sxs-lookup"><span data-stu-id="b3659-155">**Expansion**.</span></span> <span data-ttu-id="b3659-156">頭字語の展開を含みます。</span><span class="sxs-lookup"><span data-stu-id="b3659-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="b3659-157">たとえば、*Deep Neural Network* などです。</span><span class="sxs-lookup"><span data-stu-id="b3659-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="b3659-158">**説明**。</span><span class="sxs-lookup"><span data-stu-id="b3659-158">**Description**.</span></span> <span data-ttu-id="b3659-159">頭字語とその拡張に関する情報をユーザーに提供する略語の簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="b3659-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="b3659-160">たとえば、*deep neural network とは、特定の複雑さを持つニューラル ネットワーク、2 つ以上の層を持つニューラル ネットワークです*。</span><span class="sxs-lookup"><span data-stu-id="b3659-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="b3659-161">**ソース**。</span><span class="sxs-lookup"><span data-stu-id="b3659-161">**Source**.</span></span> <span data-ttu-id="b3659-162">頭字語についての詳細情報をユーザーに表示するページまたは Web サイトの URL。</span><span class="sxs-lookup"><span data-stu-id="b3659-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="b3659-163">**状態**。</span><span class="sxs-lookup"><span data-stu-id="b3659-163">**State**.</span></span> <span data-ttu-id="b3659-164">このフィールドには 2 つの値を指定できます:</span><span class="sxs-lookup"><span data-stu-id="b3659-164">This field can take two values:</span></span>

- <span data-ttu-id="b3659-165">**下書き**。</span><span class="sxs-lookup"><span data-stu-id="b3659-165">**Draft**.</span></span> <span data-ttu-id="b3659-166">頭字語を下書き状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="b3659-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="b3659-167">**公開**。</span><span class="sxs-lookup"><span data-stu-id="b3659-167">**Published**.</span></span> <span data-ttu-id="b3659-168">公開状態に頭字語を追加して、Microsoft Search で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b3659-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="b3659-169">採掘された頭字語</span><span class="sxs-lookup"><span data-stu-id="b3659-169">Mined acronyms</span></span>

<span data-ttu-id="b3659-170">管理者にとって、組織内で使用されているすべての頭字語を回答に追加するのは難しいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="b3659-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="b3659-171">この機能により、検索管理者が認識していない頭字語を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b3659-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="b3659-172">そのために、Microsoft Search は次のソースから頭字語を採掘します:</span><span class="sxs-lookup"><span data-stu-id="b3659-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="b3659-173">ユーザーのメール。</span><span class="sxs-lookup"><span data-stu-id="b3659-173">Users’ emails.</span></span>
- <span data-ttu-id="b3659-174">[SharePoint](https://products.office.com/sharepoint/collaboration)、 [Microsoft OneDrive]( https://onedrive.live.com/about/)、 [microsoft OneNote](https://www.onenote.com/)のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="b3659-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="b3659-175">ユーザーが SharePoint、OneDrive、または OneNote でアクセスできる組織内の公開文書。</span><span class="sxs-lookup"><span data-stu-id="b3659-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="b3659-176">Microsoft Search は、文書に対してアクセス権を持つユーザーのみが、その文書から採掘された頭字語を見ることができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b3659-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="b3659-177">頭字語がユーザーのメールボックスから採掘されると、そのユーザーのみがその頭字語を見ることができます。</span><span class="sxs-lookup"><span data-stu-id="b3659-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="b3659-178">採掘された頭字語に設定は必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b3659-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="b3659-179">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="b3659-179">Frequently asked questions</span></span>

<span data-ttu-id="b3659-180">**Q: 編集上の採掘されたデータはどのようにランク付けされていますか?**</span><span class="sxs-lookup"><span data-stu-id="b3659-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="b3659-181">**A:** この機能は現在、編集上の頭字語を採掘された頭字語より上にランク付けしています。</span><span class="sxs-lookup"><span data-stu-id="b3659-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="b3659-182">**Q: 編集上の頭字語が公開されてから Microsoft Search に表示されるまで、どのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="b3659-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="b3659-183">**A:** 公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかります。</span><span class="sxs-lookup"><span data-stu-id="b3659-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="b3659-184">**Q: ユーザーが頭字語の回答をトリガーするにはどうすればよいですか?**</span><span class="sxs-lookup"><span data-stu-id="b3659-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="b3659-185">**A**: 頭字語の回答を取得するには、ユーザーは [Bing](https://bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)、または [Office 365](https://Office.com)の **検索** ボックスに特定のクエリパターンを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3659-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="b3659-186">**Q: 新しいメールや文書の送受信後に、採掘された頭字語が表示されるまで、どのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="b3659-186">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="b3659-187">**A:** 新しいメールまたは文書から採掘された頭字語がMicrosoft Search 結果に表示されるまでには、最大 7 日かかります。</span><span class="sxs-lookup"><span data-stu-id="b3659-187">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="b3659-188">**Q: 文書から採掘するには、文書が特定の形式である必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="b3659-188">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="b3659-189">**A:** いいえ。</span><span class="sxs-lookup"><span data-stu-id="b3659-189">**A:** No.</span></span> <span data-ttu-id="b3659-190">画像、フォルダー、および zip ファイル以外のすべての種類のファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b3659-190">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="b3659-191">**Q: Microsoft はすべての言語の文書から頭字語を採掘しますか?**</span><span class="sxs-lookup"><span data-stu-id="b3659-191">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="b3659-192">**A**: Microsoft は、英語の文書からの採掘のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b3659-192">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="b3659-193">その他の言語のサポートは段階的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b3659-193">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="b3659-194">**Q: 組織内の採掘された頭字語を表示する必要がない場合はどうすればよいですか? 採掘された頭字語を検索結果に表示しないようにすることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="b3659-194">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="b3659-195">**A**: 検索結果に採掘された頭字語が表示されないようにするには、[「ビジネス製品のサポートに問い合わせる」](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support) の説明に従って、カスタマー サポート チケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="b3659-195">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="b3659-196">サポート チケットを作成してから、採掘された頭字語が検索結果に表示されなくなるまでに最大 48 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="b3659-196">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>
