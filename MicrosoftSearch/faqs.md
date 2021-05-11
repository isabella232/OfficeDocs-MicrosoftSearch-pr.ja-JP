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
ms.openlocfilehash: 614fa241f353533b1c1e181904eb961fd55d0dfa
ms.sourcegitcommit: ea784081bc9c3ae7981a87a493d3a74503859dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306072"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="7b338-103">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="7b338-103">Frequently asked questions</span></span>

<span data-ttu-id="7b338-104">以下は、よく寄せられる質問の一覧です。</span><span class="sxs-lookup"><span data-stu-id="7b338-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="7b338-105">ここで質問に対する回答が得られなかった場合は、</span><span class="sxs-lookup"><span data-stu-id="7b338-105">Don't see your question answered here?</span></span> <span data-ttu-id="7b338-106">この記事のフィードバックを使用してご質問ください。</span><span class="sxs-lookup"><span data-stu-id="7b338-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="7b338-107">高度なクエリ理解はサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="7b338-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="7b338-108">はい、Microsoft Search は大きな語句からクエリインテントを解析します。</span><span class="sxs-lookup"><span data-stu-id="7b338-108">Yes, Microsoft Search parses query intent from larger phrases.</span></span> <span data-ttu-id="7b338-109">この機能では、AI を使用して、ユーザーが検索意図に影響を与えないクエリに追加する一般的な余分な語句を学習します。</span><span class="sxs-lookup"><span data-stu-id="7b338-109">This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent.</span></span> <span data-ttu-id="7b338-110">たとえば、ユーザーが自分のパスワードを変更する方法について詳しい情報を検索すると、クエリからあまり重要な単語を抽出し、パスワードの変更など、関連する単語に基づいてトリガー *します。*</span><span class="sxs-lookup"><span data-stu-id="7b338-110">For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="7b338-111">この機能は、管理センターで設定された[キーワードを上書Microsoft 365使用します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="7b338-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="7b338-112">オンプレミスのファイルを検索できますか?</span><span class="sxs-lookup"><span data-stu-id="7b338-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="7b338-113">はい。</span><span class="sxs-lookup"><span data-stu-id="7b338-113">Yes.</span></span> <span data-ttu-id="7b338-114">ハイブリッド展開を使用している場合[SharePoint](http://sharepoint.com/)オンプレミスのファイルを検索SharePoint。</span><span class="sxs-lookup"><span data-stu-id="7b338-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="7b338-115">自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="7b338-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="7b338-116">既定の検索エンジン、既定のホーム ページ、および既定のブラウザーを設定して、ユーザーが Microsoft Search で最高のエクスペリエンスを提供[Bing。](https://Bing.com)</span><span class="sxs-lookup"><span data-stu-id="7b338-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="7b338-117">既定Microsoft Edgeブラウザーとして設定する</span><span class="sxs-lookup"><span data-stu-id="7b338-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="7b338-118">Bing を既定の検索エンジンとして設定する</span><span class="sxs-lookup"><span data-stu-id="7b338-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="7b338-119">Bing.com をエンタープライズ ホームページとして設定する</span><span class="sxs-lookup"><span data-stu-id="7b338-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="7b338-120">検索結果に対する保護について教えてください。</span><span class="sxs-lookup"><span data-stu-id="7b338-120">How are my search results protected?</span></span>

<span data-ttu-id="7b338-121">信頼済み[クラウドAzure Active Directory](/azure/active-directory/)結果にアクセスするには、認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="7b338-121">We require [Azure Active Directory](/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="7b338-122">認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7b338-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="7b338-123">検索クエリは識別され、Microsoft Search を使用する場合、[](https://Bing.com)ログはパブリック Bing検索トラフィックから分離Bing。</span><span class="sxs-lookup"><span data-stu-id="7b338-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="7b338-124">フェデレーション組織間を検索できますか?</span><span class="sxs-lookup"><span data-stu-id="7b338-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="7b338-125">いいえ。</span><span class="sxs-lookup"><span data-stu-id="7b338-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="7b338-126">セキュリティ、コンプライアンス、およびOffice 365に関する情報はどこで取得できますか?</span><span class="sxs-lookup"><span data-stu-id="7b338-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="7b338-127">詳細については、「信頼センター」のページ[を参照Office 365。](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="7b338-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="7b338-128">ゲスト ユーザーは組織で Microsoft Search を活用できますか?</span><span class="sxs-lookup"><span data-stu-id="7b338-128">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="7b338-129">Microsoft 365アクセスを通じて、組織外のユーザーとの豊富なコラボレーション[を可能にします。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="7b338-129">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="7b338-130">これらのユーザーは、ドキュメント、サイト、グループ、リスト、およびライブラリに対して検索操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="7b338-130">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="7b338-131">ただし、ゲスト ユーザーは完全な Microsoft Search エクスペリエンスを取得し、ヘッダーの統合された Microsoft Search ボックスではなく、ページ上の検索ボックスを活用する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7b338-131">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>