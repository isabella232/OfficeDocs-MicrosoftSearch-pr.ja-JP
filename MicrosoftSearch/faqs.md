---
title: FAQ
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: エンタープライズ検索と Microsoft Search についてよく寄せられる質問に対する回答です
ms.openlocfilehash: 98128297047d50e2d418a8ed062066ab9e86749e
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031622"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="51b42-103">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="51b42-103">Frequently asked questions</span></span>

<span data-ttu-id="51b42-104">以下は、よく寄せられる質問の一覧です。</span><span class="sxs-lookup"><span data-stu-id="51b42-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="51b42-105">ここで質問に対する回答が得られなかった場合は、</span><span class="sxs-lookup"><span data-stu-id="51b42-105">Don't see your question answered here?</span></span> <span data-ttu-id="51b42-106">この記事のフィードバックを使用してご質問ください。</span><span class="sxs-lookup"><span data-stu-id="51b42-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="51b42-107">高度なクエリ理解はサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="51b42-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="51b42-108">はい、Microsoft Search は大きな語句からクエリインテントを解析します。</span><span class="sxs-lookup"><span data-stu-id="51b42-108">Yes, Microsoft Search parses query intent from larger phrases.</span></span> <span data-ttu-id="51b42-109">この機能では、AI を使用して、ユーザーが検索意図に影響を与えないクエリに追加する一般的な余分な語句を学習します。</span><span class="sxs-lookup"><span data-stu-id="51b42-109">This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent.</span></span> <span data-ttu-id="51b42-110">たとえば、ユーザーが自分のパスワードを変更する方法について詳しい情報を検索すると、クエリからあまり重要な単語を抽出し、パスワードの変更など、関連する単語に基づいてトリガー *します。*</span><span class="sxs-lookup"><span data-stu-id="51b42-110">For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="51b42-111">この機能は [、Microsoft 365](https://admin.microsoft.com)管理センターで設定されたキーワードを上書きしない。</span><span class="sxs-lookup"><span data-stu-id="51b42-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="51b42-112">オンプレミスのファイルを検索できますか?</span><span class="sxs-lookup"><span data-stu-id="51b42-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="51b42-113">はい。</span><span class="sxs-lookup"><span data-stu-id="51b42-113">Yes.</span></span> <span data-ttu-id="51b42-114">SharePoint のハイブリッド展開がある場合は、オンプレミス [の SharePoint](http://sharepoint.com/) ファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="51b42-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="51b42-115">自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="51b42-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="51b42-116">既定の検索エンジン、既定のホームページ、および既定のブラウザーを設定して、Bing の Microsoft Search でユーザーに最高のエクスペリエンスを提供する手順を [次に示します](https://Bing.com)。</span><span class="sxs-lookup"><span data-stu-id="51b42-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="51b42-117">既定のブラウザーとして Microsoft Edge を設定する</span><span class="sxs-lookup"><span data-stu-id="51b42-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="51b42-118">Bing を既定の検索エンジンとして設定する</span><span class="sxs-lookup"><span data-stu-id="51b42-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="51b42-119">Bing.com をエンタープライズ ホームページとして設定する</span><span class="sxs-lookup"><span data-stu-id="51b42-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="51b42-120">検索結果に対する保護について教えてください。</span><span class="sxs-lookup"><span data-stu-id="51b42-120">How are my search results protected?</span></span>

<span data-ttu-id="51b42-121">信頼された [クラウドから結果にアクセスするには、Azure Active Directory](/azure/active-directory/) 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="51b42-121">We require [Azure Active Directory](/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="51b42-122">認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51b42-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="51b42-123">検索クエリは識別され、Bing で Microsoft Search を使用すると、ログはパブリック [Bing](https://Bing.com) 検索トラフィックから分離されます。</span><span class="sxs-lookup"><span data-stu-id="51b42-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="51b42-124">フェデレーション組織間を検索できますか?</span><span class="sxs-lookup"><span data-stu-id="51b42-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="51b42-125">いいえ。</span><span class="sxs-lookup"><span data-stu-id="51b42-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="51b42-126">365 セキュリティ、コンプライアンス、Officeに関する情報はどこで取得できますか?</span><span class="sxs-lookup"><span data-stu-id="51b42-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="51b42-127">詳細については、365 の [信頼センター [] ページOffice参照してください](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="51b42-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="51b42-128">ユーザーは職場または学校のアカウントで Microsoft リワード ポイントを獲得できますか?</span><span class="sxs-lookup"><span data-stu-id="51b42-128">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="51b42-129">Microsoft Search では、エンタープライズ ユーザーが職場または学校のアカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51b42-129">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="51b42-130">ただし、ユーザーはこれらのアカウントで Microsoft リワード プログラムに参加またはサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="51b42-130">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="51b42-131">しかし、エンタープライズ ユーザーにリワード ポイントが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="51b42-131">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="51b42-132">これは、Microsoft Search ユーザーが [Microsoft アカウント](https://www.microsoft.com/welcome?rtc=1)で作成されたリワード アカウントを持っている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="51b42-132">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="51b42-133">(Microsoft アカウントに関連付けられている電子メール アドレスに、Outlook.com、Hotmail.com、Gmail、Yahoo、またはその他のプロバイダーからのものが使用できます。) ユーザーが同じブラウザー セッションで仕事用アカウントと Microsoft アカウントの両方で交互にサインインする場合、リワード アカウントにポイントが加算される場合があります。</span><span class="sxs-lookup"><span data-stu-id="51b42-133">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="51b42-134">ユーザーは、Cookie をクリアすることにより、Microsoft Search での検索中にポイントの発生を停止できます。</span><span class="sxs-lookup"><span data-stu-id="51b42-134">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="51b42-135">ゲスト ユーザーは組織で Microsoft Search を活用できますか?</span><span class="sxs-lookup"><span data-stu-id="51b42-135">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="51b42-136">Microsoft 365 を使用すると、ゲスト アクセスを通じて組織外のユーザーとの豊富な [コラボレーションが可能になります。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="51b42-136">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="51b42-137">これらのユーザーは、ドキュメント、サイト、グループ、リスト、およびライブラリに対して検索操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="51b42-137">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="51b42-138">ただし、ゲスト ユーザーは完全な Microsoft Search エクスペリエンスを取得し、ヘッダーの統合された Microsoft Search ボックスではなく、ページ上の検索ボックスを活用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="51b42-138">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>