---
title: Microsoft Search で頭字語の回答を管理する
ms.author: v-pamcna
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search で頭字語の回答を作成および更新する
ms.openlocfilehash: aa857cefe9a2a40a8519a91829e327d01a3f2391
ms.sourcegitcommit: 25cdb5e6111ec6bc6c130a36aa5f13a6328e1092
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928231"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="6b511-103">Microsoft Search で頭字語の回答を管理する</span><span class="sxs-lookup"><span data-stu-id="6b511-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="6b511-104">従業員は多くの場合、組織やチームで使用されている見慣れない頭字語や略語になります。</span><span class="sxs-lookup"><span data-stu-id="6b511-104">Employees often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="6b511-105">組織またはチームに固有の用語は、チーム間での移行、社内パートナーチームと連携するユーザー、または新入社員にとっては新しいものである可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b511-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, those who work with internal partner teams, or new employees.</span></span>

<span data-ttu-id="6b511-106">組織では、標準的な用語を常に参照することはありません。</span><span class="sxs-lookup"><span data-stu-id="6b511-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="6b511-107">単一の参照がないと、これらの略語の定義や拡張を見つけるのが困難になります。</span><span class="sxs-lookup"><span data-stu-id="6b511-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="6b511-108">Microsoft Search は、頭字語に問題があることを解決します。</span><span class="sxs-lookup"><span data-stu-id="6b511-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="6b511-109">ユーザーの作業</span><span class="sxs-lookup"><span data-stu-id="6b511-109">What users experience</span></span>
<span data-ttu-id="6b511-110">Microsoft 検索ユーザーは、 [Bing](https://Bing.com)、 [microsoft Office 365](https://Office.com)、 [microsoft SharePoint Online](https://products.office.com/sharepoint/collaboration)の頭字語を使用して定義を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6b511-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [Microsoft Office 365](https://Office.com), and [Microsoft SharePoint Online](https://products.office.com/sharepoint/collaboration).</span></span> <span data-ttu-id="6b511-111">ヘッダーバーの**検索**ボックスには、次の例のようなクエリが入力されます。</span><span class="sxs-lookup"><span data-stu-id="6b511-111">In the **Search** boxes in the header bars, users enter queries like these examples:</span></span>

- <span data-ttu-id="6b511-112">*機能*DNN</span><span class="sxs-lookup"><span data-stu-id="6b511-112">*What is* DNN</span></span>
- <span data-ttu-id="6b511-113">を*定義*するDNN</span><span class="sxs-lookup"><span data-stu-id="6b511-113">*Define* DNN</span></span>
- <span data-ttu-id="6b511-114">DNN*定義*</span><span class="sxs-lookup"><span data-stu-id="6b511-114">DNN *definition*</span></span>
- <span data-ttu-id="6b511-115">*展開*DNN</span><span class="sxs-lookup"><span data-stu-id="6b511-115">*Expand* DNN</span></span>
- <span data-ttu-id="6b511-116">DNN*拡張*</span><span class="sxs-lookup"><span data-stu-id="6b511-116">DNN *expansion*</span></span>
- <span data-ttu-id="6b511-117">*の意味*DNN</span><span class="sxs-lookup"><span data-stu-id="6b511-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="6b511-118">DNN*は*</span><span class="sxs-lookup"><span data-stu-id="6b511-118">DNN *means*</span></span>

<span data-ttu-id="6b511-119">提案される結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b511-119">The suggested results include all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="6b511-120">ユーザーは、頭字語の指定された*キーワード*を含むクエリを入力して、対応する回答をトリガーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b511-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="6b511-121">頭字語のクエリでは大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="6b511-121">Acronym queries are not case sensitive.</span></span> 

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="6b511-122">頭字語の回答を設定する</span><span class="sxs-lookup"><span data-stu-id="6b511-122">Set up Acronyms answers</span></span>
<span data-ttu-id="6b511-123">Microsoft 365[管理センター](https://admin.microsoft.com)で、[**microsoft Search** >**の\*\*\*\*設定** > ] に移動し、[**頭字**語の追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b511-123">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** >**Acronyms**, and then select **Add acronyms**.</span></span> 

<span data-ttu-id="6b511-124">Microsoft Search では、ユーザーの検索に頭字語の回答を提供するために2つのデータソースをクエリします。</span><span class="sxs-lookup"><span data-stu-id="6b511-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1.  <span data-ttu-id="6b511-125">**編集の略語**</span><span class="sxs-lookup"><span data-stu-id="6b511-125">**Editorial acronyms**.</span></span> <span data-ttu-id="6b511-126">[管理センター](https://admin.microsoft.com)の IT 管理者によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="6b511-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com).</span></span>
2.  <span data-ttu-id="6b511-127">抽出した**略語**。</span><span class="sxs-lookup"><span data-stu-id="6b511-127">**Mined acronyms**.</span></span> <span data-ttu-id="6b511-128">ユーザーの個人電子メールやドキュメントから組織内の一般に利用可能なデータから、Microsoft Search によってマイニングされます。</span><span class="sxs-lookup"><span data-stu-id="6b511-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="6b511-129">編集の略語を設定する</span><span class="sxs-lookup"><span data-stu-id="6b511-129">Set up editorial acronyms</span></span>
<span data-ttu-id="6b511-130">IT 管理者は、 [Microsoft 365 管理センター]( https://admin.microsoft.com)の [[頭字] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)で編集の略語を設定できます。</span><span class="sxs-lookup"><span data-stu-id="6b511-130">IT admins can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) in the  [Microsoft 365 admin center]( https://admin.microsoft.com).</span></span> <span data-ttu-id="6b511-131">任意の内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6b511-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="6b511-132">編集の略語は、**発行済み**または**下書き**の状態に追加できます。</span><span class="sxs-lookup"><span data-stu-id="6b511-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="6b511-133">**公開**された状態。</span><span class="sxs-lookup"><span data-stu-id="6b511-133">**Published state**.</span></span> <span data-ttu-id="6b511-134">頭字語は、組織の従業員が Microsoft Search を通じて使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b511-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="6b511-135">発行済みの状態に追加された頭字語が Microsoft Search で利用できるようになるまで、最大で3日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b511-135">It might take up  to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="6b511-136">**下書きの状態**です。</span><span class="sxs-lookup"><span data-stu-id="6b511-136">**Draft state**.</span></span> <span data-ttu-id="6b511-137">Microsoft Search で使用できるようにする前に、管理者が頭字語の回答を確認する必要がある場合は、略語を下書き状態に追加できます。</span><span class="sxs-lookup"><span data-stu-id="6b511-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="6b511-138">下書き状態に追加された頭字語は、Microsoft Search では使用できません。</span><span class="sxs-lookup"><span data-stu-id="6b511-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="6b511-139">管理者は、略語を公開済み状態に追加して利用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b511-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="6b511-140">管理者は、頭文字を個別に追加するか、または CSV ファイルに一括インポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b511-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="6b511-141">次の表に示すフィールドを使用して CSV ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="6b511-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="6b511-142">頭字語 (必須)</span><span class="sxs-lookup"><span data-stu-id="6b511-142">Acronym (mandatory)</span></span> | <span data-ttu-id="6b511-143">拡張 (必須)</span><span class="sxs-lookup"><span data-stu-id="6b511-143">Expansion (mandatory)</span></span> | <span data-ttu-id="6b511-144">説明</span><span class="sxs-lookup"><span data-stu-id="6b511-144">Description</span></span>  | <span data-ttu-id="6b511-145">ソース</span><span class="sxs-lookup"><span data-stu-id="6b511-145">Source</span></span> | <span data-ttu-id="6b511-146">状態 (必須)</span><span class="sxs-lookup"><span data-stu-id="6b511-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="6b511-147">*xxx*</span><span class="sxs-lookup"><span data-stu-id="6b511-147">*XXX*</span></span> | <span data-ttu-id="6b511-148">*スペルミスの省略形*</span><span class="sxs-lookup"><span data-stu-id="6b511-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="6b511-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="6b511-149">*URL*</span></span> | <span data-ttu-id="6b511-150">*公開または下書き*</span><span class="sxs-lookup"><span data-stu-id="6b511-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="6b511-151">CSV フィールド</span><span class="sxs-lookup"><span data-stu-id="6b511-151">CSV fields</span></span>
<span data-ttu-id="6b511-152">**頭字語**</span><span class="sxs-lookup"><span data-stu-id="6b511-152">**Acronym**.</span></span> <span data-ttu-id="6b511-153">実際の短い形式または頭字語を含みます。</span><span class="sxs-lookup"><span data-stu-id="6b511-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="6b511-154">例として、 *Dnn*が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="6b511-154">An example is *DNN*.</span></span>

<span data-ttu-id="6b511-155">**拡張**。</span><span class="sxs-lookup"><span data-stu-id="6b511-155">**Expansion**.</span></span> <span data-ttu-id="6b511-156">頭字語の拡張が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b511-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="6b511-157">例としては、*ディープニューラルネットワーク*があります。</span><span class="sxs-lookup"><span data-stu-id="6b511-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="6b511-158">**説明**。</span><span class="sxs-lookup"><span data-stu-id="6b511-158">**Description**.</span></span> <span data-ttu-id="6b511-159">頭字語とその拡張の意味をユーザーにすばやく理解できるようにするための、略語の簡単な説明。</span><span class="sxs-lookup"><span data-stu-id="6b511-159">A brief description of the acronym that gives users quick insight into what the acronym and its expansion mean.</span></span> <span data-ttu-id="6b511-160">たとえば、*深いニューラルネットワークとは、一定レベルの複雑な、3つ以上のレイヤーを持つニューラルネットワークのニューラルネットワーク*のことです。</span><span class="sxs-lookup"><span data-stu-id="6b511-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="6b511-161">**ソース**。</span><span class="sxs-lookup"><span data-stu-id="6b511-161">**Source**.</span></span> <span data-ttu-id="6b511-162">頭字語の詳細については、ユーザーが移動するページまたは web サイトの URL。</span><span class="sxs-lookup"><span data-stu-id="6b511-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="6b511-163">**状態**。</span><span class="sxs-lookup"><span data-stu-id="6b511-163">**State**.</span></span> <span data-ttu-id="6b511-164">このフィールドには、次の2つの値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6b511-164">This field can take two values:</span></span>

- <span data-ttu-id="6b511-165">**下書き**。</span><span class="sxs-lookup"><span data-stu-id="6b511-165">**Draft**.</span></span> <span data-ttu-id="6b511-166">頭字語を下書き状態に追加します。</span><span class="sxs-lookup"><span data-stu-id="6b511-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="6b511-167">**発行済み**。</span><span class="sxs-lookup"><span data-stu-id="6b511-167">**Published**.</span></span> <span data-ttu-id="6b511-168">頭字語を公開された状態に追加し、Microsoft Search で使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6b511-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="6b511-169">マイニング頭字語</span><span class="sxs-lookup"><span data-stu-id="6b511-169">Mined acronyms</span></span>
<span data-ttu-id="6b511-170">管理者が組織内で使用されているすべての略語を回答に追加することが課題となる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b511-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="6b511-171">この機能は、検索管理者が認識していない略語を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="6b511-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="6b511-172">この作業を行うために、Microsoft Search では、これらのソースからの略語も地雷しています。</span><span class="sxs-lookup"><span data-stu-id="6b511-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="6b511-173">ユーザーの電子メール。</span><span class="sxs-lookup"><span data-stu-id="6b511-173">Users’ emails.</span></span>
- <span data-ttu-id="6b511-174">[SharePoint](https://products.office.com/sharepoint/collaboration)、 [Microsoft OneDrive]( https://onedrive.live.com/about/) 、 [microsoft OneNote](http://www.onenote.com/)のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="6b511-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) and [Microsoft OneNote](http://www.onenote.com/).</span></span>
- <span data-ttu-id="6b511-175">ユーザーが SharePoint、OneDrive、または OneNote でアクセスできる組織内のパブリックドキュメント。</span><span class="sxs-lookup"><span data-stu-id="6b511-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="6b511-176">Microsoft Search を使用すると、ドキュメントに対するアクセスとアクセス許可を持つユーザーのみが、その文書から抽出された頭字語を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="6b511-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="6b511-177">頭字語は、ユーザーの受信トレイからマイニングされ、ユーザーのシャードに格納されます。</span><span class="sxs-lookup"><span data-stu-id="6b511-177">The acronyms are mined from a user’s inbox and stored in the user shard.</span></span> <span data-ttu-id="6b511-178">ユーザーが自分の受信トレイから抽出した略語にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6b511-178">Only the user can access the acronyms mined from the user’s own inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="6b511-179">マイニングされた頭字語には、IT 管理者のセットアップは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6b511-179">No IT admin setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="6b511-180">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="6b511-180">Frequently asked questions</span></span>
<span data-ttu-id="6b511-181">**Q: どのように編集とマイニングされたデータがランク付けされるのですか?**</span><span class="sxs-lookup"><span data-stu-id="6b511-181">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="6b511-182">**A:** 現在、機能は、抽出された略語の上に編集上の略語をランク付けします。</span><span class="sxs-lookup"><span data-stu-id="6b511-182">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="6b511-183">**Q: 発行後に編集者の略語が Microsoft Search に表示されるまでにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="6b511-183">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="6b511-184">**A:** 発行済みの状態に追加された頭字語が Microsoft Search で利用できるようになるまでに最大3日間かかります。</span><span class="sxs-lookup"><span data-stu-id="6b511-184">**A:**  It takes up  to three days for acronyms added to Published state to become available in Microsoft Search.</span></span> 

<span data-ttu-id="6b511-185">**Q: ユーザーが頭字語の回答を開始する方法を教えてください。**</span><span class="sxs-lookup"><span data-stu-id="6b511-185">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="6b511-186">**A**: 頭字語の回答を取得するには、 [Bing](https://bing.com)、 [Office 365](https://Office.com)、または SharePoint の[SharePoint](https://products.office.com/sharepoint/collaboration) **検索**ボックスに特定のクエリパターンを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b511-186">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [Office 365](https://Office.com), or [SharePoint](https://products.office.com/sharepoint/collaboration) **Search** box.</span></span> <span data-ttu-id="6b511-187">「 *Dnn* 」という用語の解答を検索するクエリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6b511-187">Examples of queries that find answers for the term *DNN* are as follows:</span></span>

- <span data-ttu-id="6b511-188">*機能*DNN</span><span class="sxs-lookup"><span data-stu-id="6b511-188">*What is* DNN</span></span>
- <span data-ttu-id="6b511-189">を*定義*するDNN</span><span class="sxs-lookup"><span data-stu-id="6b511-189">*Define* DNN</span></span>
- <span data-ttu-id="6b511-190">DNN*定義*</span><span class="sxs-lookup"><span data-stu-id="6b511-190">DNN *definition*</span></span>
- <span data-ttu-id="6b511-191">*展開*DNN</span><span class="sxs-lookup"><span data-stu-id="6b511-191">*Expand* DNN</span></span>
- <span data-ttu-id="6b511-192">DNN*拡張*</span><span class="sxs-lookup"><span data-stu-id="6b511-192">DNN *expansion*</span></span>
- <span data-ttu-id="6b511-193">*の意味*DNN</span><span class="sxs-lookup"><span data-stu-id="6b511-193">*Meaning of* DNN</span></span>
- <span data-ttu-id="6b511-194">DNN*は*</span><span class="sxs-lookup"><span data-stu-id="6b511-194">DNN *means*</span></span>

<span data-ttu-id="6b511-195">**Q: 新しい電子メールやドキュメントを受信または送信した後に、マイニングされた頭字語が表示されるまでにどのくらいの時間がかかりますか?**</span><span class="sxs-lookup"><span data-stu-id="6b511-195">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="6b511-196">**A:** 新しい電子メールまたはドキュメントから抽出された略語は、Microsoft 検索結果に表示されるまでに最大7日間かかります。</span><span class="sxs-lookup"><span data-stu-id="6b511-196">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="6b511-197">**Q: ドキュメントを選択するために、ドキュメントをマイニングの特定の形式にする必要がありますか。**</span><span class="sxs-lookup"><span data-stu-id="6b511-197">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="6b511-198">**A:** 違います。</span><span class="sxs-lookup"><span data-stu-id="6b511-198">**A:** No.</span></span> <span data-ttu-id="6b511-199">画像、フォルダー、および zip ファイル以外のすべてのファイルの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6b511-199">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="6b511-200">**Q: Microsoft はすべての言語のドキュメントから頭字語を地雷していますか?**</span><span class="sxs-lookup"><span data-stu-id="6b511-200">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="6b511-201">**A**: Microsoft は、ドキュメントからのマイニングのみを英語でサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6b511-201">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="6b511-202">他の言語のサポートは、フェーズで追加されます。</span><span class="sxs-lookup"><span data-stu-id="6b511-202">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="6b511-203">**Q: 組織でマイニングされた頭字語を表示したくない場合はどうすればよいですか?抽出された略語が検索結果に表示されないようにすることはできますか?**</span><span class="sxs-lookup"><span data-stu-id="6b511-203">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="6b511-204">**A**: 検索結果での抽出された略語を表示しないようにするには、「[ビジネス製品についてのサポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)」の手順に従ってカスタマーサポートチケットを作成します。</span><span class="sxs-lookup"><span data-stu-id="6b511-204">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="6b511-205">サポートチケットを作成した後は、検索結果に表示されなくなるまでに最大48時間かかります。</span><span class="sxs-lookup"><span data-stu-id="6b511-205">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span> 

<span data-ttu-id="6b511-206">**Q: [Office 365](https://Office.com)と[SharePoint Online](https://products.office.com/sharepoint/collaboration)で頭字語の回答が表示されるのはいつですか。**</span><span class="sxs-lookup"><span data-stu-id="6b511-206">**Q: When will I see Acronyms answers in [Office 365](https://Office.com) and [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**</span></span>

<span data-ttu-id="6b511-207">**A**: 頭字語の回答は現在、 [Bing](https://bing.com)の Microsoft Search でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="6b511-207">**A**: Acronyms answers are currently only available in Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="6b511-208">これらは、Office 365 および2020の SharePoint Online にロールアウトされます。</span><span class="sxs-lookup"><span data-stu-id="6b511-208">They’ll be rolled out to Office 365 and SharePoint Online in 2020.</span></span>
