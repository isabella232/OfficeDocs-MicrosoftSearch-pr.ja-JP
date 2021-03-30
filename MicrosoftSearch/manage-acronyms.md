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
ms.openlocfilehash: 013510da28599f41c9dc4bf74da99efa2f6c3e97
ms.sourcegitcommit: 62cb7b8c6a311760cc728f2c70a9a22ca76e977e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408716"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="d5570-103">Microsoft Search で頭字語の回答を管理する</span><span class="sxs-lookup"><span data-stu-id="d5570-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="d5570-104">ユーザーは、組織やチームで使用されている頭字語や略語に慣れていないことがよくあります。</span><span class="sxs-lookup"><span data-stu-id="d5570-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="d5570-105">組織またはチームに固有の用語は、チーム間を移動したり、社内パートナーと共同で作業する人、または組織の新人には新しい場合があります。  </span><span class="sxs-lookup"><span data-stu-id="d5570-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="d5570-106">組織の標準的な用語には、常に単一の参照があるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="d5570-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="d5570-107">1 つの参照がない場合、これらの頭字語の定義を見つけるのは難しです。</span><span class="sxs-lookup"><span data-stu-id="d5570-107">Lack of a single reference makes it hard to find definitions for these acronyms.</span></span> <span data-ttu-id="d5570-108">Microsoft Search は、頭字語の問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="d5570-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="d5570-109">ユーザーのエクスぺリエンス</span><span class="sxs-lookup"><span data-stu-id="d5570-109">What users experience</span></span>

<span data-ttu-id="d5570-110">Microsoft Search のユーザーは [Bing](https://Bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)および[Office 365](https://Office.com)の頭字語を使用して、定義を入手できます。</span><span class="sxs-lookup"><span data-stu-id="d5570-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="d5570-111">**[検索]** ボックスで、次の例のようにクエリを入力します:</span><span class="sxs-lookup"><span data-stu-id="d5570-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="d5570-112">*What is* DNN</span><span class="sxs-lookup"><span data-stu-id="d5570-112">*What is* DNN</span></span>
- <span data-ttu-id="d5570-113">*Define* DNN</span><span class="sxs-lookup"><span data-stu-id="d5570-113">*Define* DNN</span></span>
- <span data-ttu-id="d5570-114">DNN *definition*</span><span class="sxs-lookup"><span data-stu-id="d5570-114">DNN *definition*</span></span>
- <span data-ttu-id="d5570-115">*Expand* DNN</span><span class="sxs-lookup"><span data-stu-id="d5570-115">*Expand* DNN</span></span>
- <span data-ttu-id="d5570-116">DNN *expansion*</span><span class="sxs-lookup"><span data-stu-id="d5570-116">DNN *expansion*</span></span>
- <span data-ttu-id="d5570-117">*Meaning of* DNN</span><span class="sxs-lookup"><span data-stu-id="d5570-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="d5570-118">DNN *means*</span><span class="sxs-lookup"><span data-stu-id="d5570-118">DNN *means*</span></span>
- <span data-ttu-id="d5570-119">DNN *の略*</span><span class="sxs-lookup"><span data-stu-id="d5570-119">DNN *stands for*</span></span>

<span data-ttu-id="d5570-120">結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d5570-120">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="d5570-121">ユーザーは、対応する回答をトリガーするために、頭字語で指定された *キーワード* を含むクエリを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5570-121">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="d5570-122">頭字語のクエリでは、大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="d5570-122">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="d5570-123">頭字語の回答を設定する</span><span class="sxs-lookup"><span data-stu-id="d5570-123">Set up acronyms answers</span></span>

<span data-ttu-id="d5570-124">[Microsoft 365 管理センター](https://admin.microsoft.com)で、[**[頭字語]**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)に移動し、**[頭字語の追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5570-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="d5570-125">Microsoft Search は、2 つのデータ ソースをクエリして、頭字語の回答をユーザーの検索に提供します:</span><span class="sxs-lookup"><span data-stu-id="d5570-125">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="d5570-126">**管理者が管理します**。</span><span class="sxs-lookup"><span data-stu-id="d5570-126">**Admin-curated**.</span></span> <span data-ttu-id="d5570-127">[管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の IT 管理者によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="d5570-127">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="d5570-128">**System-curated**.</span><span class="sxs-lookup"><span data-stu-id="d5570-128">**System-curated**.</span></span> <span data-ttu-id="d5570-129">ユーザーの電子メールとドキュメント、および組織内で一般に利用可能なデータから Microsoft Search によって検出されます。</span><span class="sxs-lookup"><span data-stu-id="d5570-129">Discovered by Microsoft Search from users' email and documents, as well as publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="d5570-130">管理者が指定した頭字語を設定する</span><span class="sxs-lookup"><span data-stu-id="d5570-130">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="d5570-131">検索管理者は、Microsoft Search 管理センターの [[頭](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) 字語] タブに頭字語  [を追加できます](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。</span><span class="sxs-lookup"><span data-stu-id="d5570-131">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="d5570-132">すべての内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d5570-132">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="d5570-133">これらの頭字語は、発行済みまたは下書 **き状態に\*\*\*\*追加** できます。</span><span class="sxs-lookup"><span data-stu-id="d5570-133">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="d5570-134">**公開状態**。</span><span class="sxs-lookup"><span data-stu-id="d5570-134">**Published state**.</span></span> <span data-ttu-id="d5570-135">頭字語は、Microsoft Search を通じて組織のユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="d5570-135">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="d5570-136">公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5570-136">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="d5570-137">**下書き状態**。</span><span class="sxs-lookup"><span data-stu-id="d5570-137">**Draft state**.</span></span> <span data-ttu-id="d5570-138">Microsoft Search で使用できる前に頭字語を確認する場合は、下書き状態で頭字語を追加できます。</span><span class="sxs-lookup"><span data-stu-id="d5570-138">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="d5570-139">下書き状態の頭字語は検索結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d5570-139">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="d5570-140">検索結果に表示するには、頭字語を発行済み状態に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5570-140">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="d5570-141">**除外された状態**。</span><span class="sxs-lookup"><span data-stu-id="d5570-141">**Excluded state**.</span></span> <span data-ttu-id="d5570-142">Microsoft Search に頭字語が表示されるのを防ぐ場合は、[頭字語を除外する] を使用して追加します。</span><span class="sxs-lookup"><span data-stu-id="d5570-142">If you want to prevent an acronym from appearing in Microsoft Search, use **Exclude an acronym** to add it.</span></span> <span data-ttu-id="d5570-143">頭字語が除外されるのを止めるには、除外された頭字語を削除して追加するか、発行済みリストに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5570-143">To stop an acronym from being excluded, you'll need to delete the excluded acronym and add it or verify it's in your published list.</span></span>

<span data-ttu-id="d5570-144">頭字語を個別に追加するか、CSV ファイルに一括インポートできます。</span><span class="sxs-lookup"><span data-stu-id="d5570-144">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="d5570-145">次の表に示すフィールドを使用して CSV ファイルをアップロードします:</span><span class="sxs-lookup"><span data-stu-id="d5570-145">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="d5570-146">頭字語 (必須)</span><span class="sxs-lookup"><span data-stu-id="d5570-146">Acronym (Mandatory)</span></span> | <span data-ttu-id="d5570-147">略 (必須)</span><span class="sxs-lookup"><span data-stu-id="d5570-147">Stands for (Mandatory)</span></span> | <span data-ttu-id="d5570-148">Url</span><span class="sxs-lookup"><span data-stu-id="d5570-148">Url</span></span> | <span data-ttu-id="d5570-149">説明</span><span class="sxs-lookup"><span data-stu-id="d5570-149">Description</span></span>  | <span data-ttu-id="d5570-150">状態 (必須)</span><span class="sxs-lookup"><span data-stu-id="d5570-150">State (Mandatory)</span></span> | <span data-ttu-id="d5570-151">最終更新日時</span><span class="sxs-lookup"><span data-stu-id="d5570-151">Last Modified</span></span> | <span data-ttu-id="d5570-152">最終変更者</span><span class="sxs-lookup"><span data-stu-id="d5570-152">Last Modified By</span></span> | <span data-ttu-id="d5570-153">Id</span><span class="sxs-lookup"><span data-stu-id="d5570-153">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="d5570-154">*XXX*</span><span class="sxs-lookup"><span data-stu-id="d5570-154">*XXX*</span></span> | <span data-ttu-id="d5570-155">*略語のスペル*</span><span class="sxs-lookup"><span data-stu-id="d5570-155">*Spelled out abbreviation*</span></span> | <span data-ttu-id="d5570-156">*Source*</span><span class="sxs-lookup"><span data-stu-id="d5570-156">*Source*</span></span> |  | <span data-ttu-id="d5570-157">*公開、下書き、または除外*</span><span class="sxs-lookup"><span data-stu-id="d5570-157">*Published, Draft, or Excluded*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="d5570-158">CSV フィールド</span><span class="sxs-lookup"><span data-stu-id="d5570-158">CSV fields</span></span>

<span data-ttu-id="d5570-159">**頭字語**。</span><span class="sxs-lookup"><span data-stu-id="d5570-159">**Acronym**.</span></span> <span data-ttu-id="d5570-160">実際の短い形式または頭字語を含みます。</span><span class="sxs-lookup"><span data-stu-id="d5570-160">Contains the actual short form or acronym.</span></span> <span data-ttu-id="d5570-161">たとえば、*DNN* などです。</span><span class="sxs-lookup"><span data-stu-id="d5570-161">An example is *DNN*.</span></span>

<span data-ttu-id="d5570-162">**を表します**。</span><span class="sxs-lookup"><span data-stu-id="d5570-162">**Stands for**.</span></span> <span data-ttu-id="d5570-163">頭字語の定義が含まれる。</span><span class="sxs-lookup"><span data-stu-id="d5570-163">Contains the definition of the acronym.</span></span> <span data-ttu-id="d5570-164">たとえば、*Deep Neural Network* などです。</span><span class="sxs-lookup"><span data-stu-id="d5570-164">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="d5570-165">**説明**。</span><span class="sxs-lookup"><span data-stu-id="d5570-165">**Description**.</span></span> <span data-ttu-id="d5570-166">頭字語とその定義に関する詳細情報をユーザーに提供する頭字語の簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="d5570-166">A brief description of the acronym that gives users more info about the acronym and its definition.</span></span> <span data-ttu-id="d5570-167">たとえば、*deep neural network とは、特定の複雑さを持つニューラル ネットワーク、2 つ以上の層を持つニューラル ネットワークです*。</span><span class="sxs-lookup"><span data-stu-id="d5570-167">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="d5570-168">**ソース**。</span><span class="sxs-lookup"><span data-stu-id="d5570-168">**Source**.</span></span> <span data-ttu-id="d5570-169">頭字語についての詳細情報をユーザーに表示するページまたは Web サイトの URL。</span><span class="sxs-lookup"><span data-stu-id="d5570-169">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="d5570-170">**状態**。</span><span class="sxs-lookup"><span data-stu-id="d5570-170">**State**.</span></span> <span data-ttu-id="d5570-171">このフィールドには 2 つの値を指定できます:</span><span class="sxs-lookup"><span data-stu-id="d5570-171">This field can take two values:</span></span>

- <span data-ttu-id="d5570-172">**下書き**。</span><span class="sxs-lookup"><span data-stu-id="d5570-172">**Draft**.</span></span> <span data-ttu-id="d5570-173">下書き状態に頭字語を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5570-173">Adds the acronym to the Draft state.</span></span>
- <span data-ttu-id="d5570-174">**公開**。</span><span class="sxs-lookup"><span data-stu-id="d5570-174">**Published**.</span></span> <span data-ttu-id="d5570-175">公開状態に頭字語を追加して、Microsoft Search で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="d5570-175">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>
- <span data-ttu-id="d5570-176">**除外します**。</span><span class="sxs-lookup"><span data-stu-id="d5570-176">**Excluded**.</span></span> <span data-ttu-id="d5570-177">頭字語を除外状態に追加し、Microsoft Search に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d5570-177">Adds the acronym to the Excluded state and prevents it from appearing in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="d5570-178">System-curated 頭字語</span><span class="sxs-lookup"><span data-stu-id="d5570-178">System-curated acronyms</span></span>

<span data-ttu-id="d5570-179">管理者にとって、組織内で使用されているすべての頭字語を回答に追加するのは難しいかもしれません。</span><span class="sxs-lookup"><span data-stu-id="d5570-179">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="d5570-180">この機能により、検索管理者が認識していない頭字語を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d5570-180">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="d5570-181">この作業を行うには、Microsoft Search は次のソースから頭字語を検出してキュレートします。</span><span class="sxs-lookup"><span data-stu-id="d5570-181">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="d5570-182">ユーザーのメール</span><span class="sxs-lookup"><span data-stu-id="d5570-182">Users’ emails</span></span>
- <span data-ttu-id="d5570-183">[SharePoint 、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive、Microsoft]( https://onedrive.live.com/about/) [OneNote のドキュメント](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="d5570-183">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="d5570-184">SharePoint、OneDrive、または OneNote でユーザーがアクセスできる組織内のパブリック ドキュメント</span><span class="sxs-lookup"><span data-stu-id="d5570-184">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="d5570-185">Microsoft Search では、ドキュメントへのアクセス権とアクセス許可を持つユーザーだけが、ドキュメントから検出された頭字語を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d5570-185">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="d5570-186">ユーザーのメールボックスで頭字語が見つかった場合、その頭字語を表示できるのはそのユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="d5570-186">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="d5570-187">システムが指定した頭字語のセットアップは不要です。</span><span class="sxs-lookup"><span data-stu-id="d5570-187">No setup is needed for system-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="d5570-188">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="d5570-188">Frequently asked questions</span></span>

<span data-ttu-id="d5570-189">**Q: 管理者が管理するデータとシステムで管理されたデータのランク付け方法**</span><span class="sxs-lookup"><span data-stu-id="d5570-189">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="d5570-190">**A:** 結果のランク付けは、結果が各ユーザーに合わせたものとして、個人ごとに異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d5570-190">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="d5570-191">これらのどちらのカテゴリも、常に他のカテゴリよりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="d5570-191">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="d5570-192">**Q: 管理者が指定した頭字語が Microsoft Search で公開された後に表示されるのにどれくらいの時間が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="d5570-192">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="d5570-193">**A:**  発行済み状態に追加された頭字語が Microsoft Search で使用可能になるには、最大 1 日かかる。</span><span class="sxs-lookup"><span data-stu-id="d5570-193">**A:**  It takes up to a day for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="d5570-194">**Q: ユーザーが頭字語の回答をトリガーする方法**</span><span class="sxs-lookup"><span data-stu-id="d5570-194">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="d5570-195">**A**: 頭字語の回答を取得するには [、Bing、SharePoint、](https://bing.com)または [](https://products.office.com/sharepoint/collaboration)[[365](https://Office.com) Search] ボックスに特定のクエリ Office **入力する必要** があります。</span><span class="sxs-lookup"><span data-stu-id="d5570-195">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="d5570-196">**Q: 新しい電子メールまたはドキュメントを受信または送信した後に、システムで指定された頭字語が表示されるのにどのくらいの時間が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="d5570-196">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="d5570-197">**A:** 新しい電子メールまたはドキュメントで見つかった頭字語は、Microsoft 検索結果に表示されるまで最大 7 日かかっています。</span><span class="sxs-lookup"><span data-stu-id="d5570-197">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="d5570-198">**Q: 頭字語が除外され、公開されている場合は、何が起こりますか?**</span><span class="sxs-lookup"><span data-stu-id="d5570-198">**Q: What happens when an acronym is both excluded and published?**</span></span>

<span data-ttu-id="d5570-199">**A:** 除外された頭字語が優先され、発行された頭字語が検索結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="d5570-199">**A:** The excluded acronym is given priority and prevents the published acronym from appearing in search results.</span></span> <span data-ttu-id="d5570-200">公開された頭字語は削除も削除もされません。</span><span class="sxs-lookup"><span data-stu-id="d5570-200">It doesn't delete or remove the published acronym.</span></span>

<span data-ttu-id="d5570-201">**Q: 頭字語が Microsoft 検索結果から除外されるのにどのくらいの時間が必要ですか?**</span><span class="sxs-lookup"><span data-stu-id="d5570-201">**Q: How long does it take for an acronym to be excluded from Microsoft Search results?**</span></span>

<span data-ttu-id="d5570-202">**A**: 除外された頭字語が検索結果に表示されるのを停止するには、最大で 1 日かかる。</span><span class="sxs-lookup"><span data-stu-id="d5570-202">**A**: It takes up to a day for an excluded acronym to stop appearing in search results.</span></span>

<span data-ttu-id="d5570-203">**Q: システムで指定された頭字語の場合、ドキュメントは特定の形式である必要がありますか?**</span><span class="sxs-lookup"><span data-stu-id="d5570-203">**Q: For system-curated acronyms, do documents need to be in a specific format?**</span></span>

<span data-ttu-id="d5570-204">**A:** いいえ。</span><span class="sxs-lookup"><span data-stu-id="d5570-204">**A:** No.</span></span> <span data-ttu-id="d5570-205">画像、フォルダー、zip ファイルを除くすべての種類のファイルをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d5570-205">We support all file types except image, folder, and zip files.</span></span>

<span data-ttu-id="d5570-206">**Q: Microsoft は、すべての言語のドキュメントから頭字語を検出しますか?**</span><span class="sxs-lookup"><span data-stu-id="d5570-206">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="d5570-207">**A**: Microsoft では、英語、スペイン語、フランス語、イタリア語、ドイツ語、ポルトガル語のドキュメントからのシステムキュアの頭字語のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="d5570-207">**A**: Microsoft only supports system-curated acronyms from documents in English, Spanish, French, Italian, German, and Portuguese.</span></span> <span data-ttu-id="d5570-208">その他の言語のサポートは段階的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="d5570-208">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="d5570-209">**Q: 組織がシステムで指定された頭字語を表示しない場合は、どうしますか。検索結果にこの種類の頭字語が表示されるのを停止できますか?**</span><span class="sxs-lookup"><span data-stu-id="d5570-209">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="d5570-210">**A**: 検索結果にシステムで指定された頭字語を表示するをオフにする場合は、「ビジネス製品のサポートに問い合わせ」の指示に従って、カスタマー サポート [チケットを作成します](/microsoft-365/admin/contact-support-for-business-products)。</span><span class="sxs-lookup"><span data-stu-id="d5570-210">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="d5570-211">サポート チケットを作成した後、システムでキュアされた頭字語が検索結果に表示されるのを停止するには、最大 48 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="d5570-211">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
