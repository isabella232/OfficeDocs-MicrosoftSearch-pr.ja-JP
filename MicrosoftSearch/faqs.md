---
title: FAQ
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: エンタープライズ検索と Microsoft Search についてよく寄せられる質問に対する回答です
ms.openlocfilehash: edfb8346263d60184d8655afa24118ed4b3e3bca
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699795"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="b3b64-103">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="b3b64-103">Frequently asked questions</span></span>

<span data-ttu-id="b3b64-104">以下は、よく寄せられる質問の一覧です。</span><span class="sxs-lookup"><span data-stu-id="b3b64-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="b3b64-105">ここで質問に対する回答が得られなかった場合は、</span><span class="sxs-lookup"><span data-stu-id="b3b64-105">Don't see your question answered here?</span></span> <span data-ttu-id="b3b64-106">この記事のフィードバックを使用してご質問ください。</span><span class="sxs-lookup"><span data-stu-id="b3b64-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="b3b64-107">高度なクエリ理解はサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="b3b64-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="b3b64-p102">はい、大規模な語句からクエリの目的を解析します。この機能は、AI を使用して、検索の目的に影響を与えないクエリにユーザーが追加する一般的な不必要な語句を調べます。たとえば、ユーザーが自分のパスワードを*変更する方法について詳しく説明して*いる場合は、「 *change password*」のような関連する用語に基づいて、クエリとトリガーから重要度の低い単語を抽出します。</span><span class="sxs-lookup"><span data-stu-id="b3b64-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password please*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="b3b64-111">この機能は、Microsoft 365[管理センター](https://admin.microsoft.com)で設定されたキーワードより優先されません。</span><span class="sxs-lookup"><span data-stu-id="b3b64-111">This feature won't override keywords set in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="b3b64-112">オンプレミスのファイルを検索できますか?</span><span class="sxs-lookup"><span data-stu-id="b3b64-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="b3b64-113">はい。</span><span class="sxs-lookup"><span data-stu-id="b3b64-113">Yes.</span></span> <span data-ttu-id="b3b64-114">SharePoint のハイブリッド展開がある場合は、オンプレミスの[sharepoint](http://sharepoint.com/)ファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b3b64-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="b3b64-115">自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="b3b64-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="b3b64-116">次の手順では、既定の検索エンジン、既定のホームページ、および既定のブラウザーを設定して、 [Bing](https://Bing.com)で Microsoft search の最適な環境をユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="b3b64-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="b3b64-117">Microsoft Edge を既定のブラウザーとして設定する</span><span class="sxs-lookup"><span data-stu-id="b3b64-117">Set Microsoft Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="b3b64-118">Bing を既定の検索エンジンとして設定する</span><span class="sxs-lookup"><span data-stu-id="b3b64-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="b3b64-119">Bing.com をエンタープライズ ホームページとして設定する</span><span class="sxs-lookup"><span data-stu-id="b3b64-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="b3b64-120">検索結果に対する保護について教えてください。</span><span class="sxs-lookup"><span data-stu-id="b3b64-120">How are my search results protected?</span></span>

<span data-ttu-id="b3b64-121">信頼されたクラウドからの結果にアクセスするには、 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="b3b64-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="b3b64-122">認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b3b64-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="b3b64-123">検索クエリは識別されないため、ログはパブリック[Bing](https://Bing.com)検索トラフィックから分離されます。</span><span class="sxs-lookup"><span data-stu-id="b3b64-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic.</span></span> <span data-ttu-id="b3b64-124">このレベルの保護が提供されているのは、業界内でも Microsoft Search だけです。</span><span class="sxs-lookup"><span data-stu-id="b3b64-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="b3b64-125">フェデレーション組織間を検索できますか?</span><span class="sxs-lookup"><span data-stu-id="b3b64-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="b3b64-126">いいえ。</span><span class="sxs-lookup"><span data-stu-id="b3b64-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="b3b64-127">Office 365 および Microsoft 365 のコンプライアンス階層とカテゴリに関する情報はどこで入手できますか?</span><span class="sxs-lookup"><span data-stu-id="b3b64-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="b3b64-128">「[業界標準と規制に関するコンプライアンス フレームワーク](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)」(PDF ダウンロード) で詳細を入手できます。</span><span class="sxs-lookup"><span data-stu-id="b3b64-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="b3b64-129">ユーザーは職場または学校のアカウントで Microsoft リワード ポイントを獲得できますか?</span><span class="sxs-lookup"><span data-stu-id="b3b64-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="b3b64-130">Microsoft Search では、エンタープライズ ユーザーが職場または学校のアカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b3b64-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="b3b64-131">ただし、ユーザーはこれらのアカウントで Microsoft リワード プログラムに参加またはサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b3b64-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="b3b64-132">しかし、エンタープライズ ユーザーにリワード ポイントが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3b64-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="b3b64-133">これは、Microsoft Search ユーザーが <a href="https://www.microsoft.com/welcome?rtc=1">Microsoft アカウント</a>で作成されたリワード アカウントを持っている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b3b64-133">This can happen when a Microsoft Search user has a Rewards account that was created with a <a href="https://www.microsoft.com/welcome?rtc=1">Microsoft account</a>.</span></span> <span data-ttu-id="b3b64-134">(Microsoft アカウントに関連付けられている電子メール アドレスに、Outlook.com、Hotmail.com、Gmail、Yahoo、またはその他のプロバイダーからのものが使用できます。) ユーザーが同じブラウザー セッションで仕事用アカウントと Microsoft アカウントの両方で交互にサインインする場合、リワード アカウントにポイントが加算される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b3b64-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="b3b64-135">ユーザーは、Cookie をクリアすることにより、Microsoft Search での検索中にポイントの発生を停止できます。</span><span class="sxs-lookup"><span data-stu-id="b3b64-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span> 

