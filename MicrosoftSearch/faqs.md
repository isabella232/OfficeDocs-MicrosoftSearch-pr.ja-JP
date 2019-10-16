---
title: FAQ
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 10/19/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: エンタープライズ検索と Microsoft Search についてよく寄せられる質問に対する回答です
ms.openlocfilehash: d3cf7e4a6f252711f94e90a4e6561c8f25769c27
ms.sourcegitcommit: 5204b3c85e2fc190a8807d5268fb87145624a969
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2019
ms.locfileid: "37502931"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="e1900-103">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e1900-103">Frequently asked questions</span></span>

<span data-ttu-id="e1900-104">以下は、よく寄せられる質問の一覧です。</span><span class="sxs-lookup"><span data-stu-id="e1900-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="e1900-105">ここで質問に対する回答が得られなかった場合は、</span><span class="sxs-lookup"><span data-stu-id="e1900-105">Don't see your question answered here?</span></span> <span data-ttu-id="e1900-106">この記事のフィードバックを使用してご質問ください。</span><span class="sxs-lookup"><span data-stu-id="e1900-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="e1900-107">高度なクエリ理解はサポートされていますか?</span><span class="sxs-lookup"><span data-stu-id="e1900-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="e1900-p102">はい。Microsoft Search は、長いフレーズからクエリの意図を解析します。この機能は、AI を使ってユーザーがよく使う検索の意図に影響しない余分なフレーズの一般的なものを学習します。たとえば、ユーザーが「パスワードの変更方法について詳しく教えてください」と検索した場合、クエリから重要度の低いワードを抽出し、「パスワード変更」などの関連のあるワードに基づいてトリガーします。</span><span class="sxs-lookup"><span data-stu-id="e1900-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for 'tell me more about how to change my password please' we extract the less important words from the query and trigger based on the relevant ones like 'change password.'</span></span>
  
<span data-ttu-id="e1900-111">この機能により、管理センターで設定されたキーワードが無効になることはありません。</span><span class="sxs-lookup"><span data-stu-id="e1900-111">This feature will not override keywords set in the Admin portal.</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="e1900-112">オンプレミスのファイルを検索できますか?</span><span class="sxs-lookup"><span data-stu-id="e1900-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="e1900-113">はい。</span><span class="sxs-lookup"><span data-stu-id="e1900-113">Yes.</span></span> <span data-ttu-id="e1900-114">SharePoint のハイブリッド展開を使用している場合は、SharePoint のオンプレミスのファイルを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="e1900-114">You can search on-premises SharePoint files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="e1900-115">自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="e1900-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="e1900-116">既定の検索エンジン、既定のホームページ、既定のブラウザーを設定する手順は以下でご覧いただけます。Microsoft Search in Bing では最適な操作性がユーザーに提供されています。</span><span class="sxs-lookup"><span data-stu-id="e1900-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in Bing:</span></span>

- [<span data-ttu-id="e1900-117">Microsoft Edge を既定のブラウザーとして設定する</span><span class="sxs-lookup"><span data-stu-id="e1900-117">Set Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="e1900-118">Bing を既定の検索エンジンとして設定する</span><span class="sxs-lookup"><span data-stu-id="e1900-118">Make Bing the default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="e1900-119">Bing.com をエンタープライズ ホームページとして設定する</span><span class="sxs-lookup"><span data-stu-id="e1900-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="e1900-120">検索結果に対する保護について教えてください。</span><span class="sxs-lookup"><span data-stu-id="e1900-120">How are my search results protected?</span></span>

<span data-ttu-id="e1900-121">信頼できるクラウドから結果にアクセスするには、Azure Active Directory (AAD) 認証が必要です。</span><span class="sxs-lookup"><span data-stu-id="e1900-121">We require Azure Active Directory (AAD) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="e1900-122">認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e1900-122">Users will only see content which they have access to.</span></span> <span data-ttu-id="e1900-123">検索クエリは匿名化され、ログは公開された Bing 検索トラフィックから分離されます。</span><span class="sxs-lookup"><span data-stu-id="e1900-123">Search queries are de-identified and logs are separated from public Bing search traffic.</span></span> <span data-ttu-id="e1900-124">このレベルの保護が提供されているのは、業界内でも Microsoft Search だけです。</span><span class="sxs-lookup"><span data-stu-id="e1900-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="e1900-125">フェデレーション組織間を検索できますか?</span><span class="sxs-lookup"><span data-stu-id="e1900-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="e1900-126">いいえ。</span><span class="sxs-lookup"><span data-stu-id="e1900-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="e1900-127">Office 365 および Microsoft 365 のコンプライアンス階層とカテゴリに関する情報はどこで入手できますか?</span><span class="sxs-lookup"><span data-stu-id="e1900-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="e1900-128">「[業界標準と規制に関するコンプライアンス フレームワーク](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)」(PDF ダウンロード) で詳細を入手できます。</span><span class="sxs-lookup"><span data-stu-id="e1900-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="e1900-129">ユーザーは職場または学校のアカウントで Microsoft リワード ポイントを獲得できますか?</span><span class="sxs-lookup"><span data-stu-id="e1900-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="e1900-130">Microsoft Search では、エンタープライズ ユーザーが職場または学校のアカウントでサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1900-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="e1900-131">ただし、ユーザーはこれらのアカウントで Microsoft リワード プログラムに参加またはサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e1900-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="e1900-132">しかし、エンタープライズ ユーザーにリワード ポイントが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1900-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="e1900-133">これは、Microsoft Search ユーザーが <a href="https://www.microsoft.com/en-us/welcome?rtc=1">Microsoft アカウント</a>で作成されたリワード アカウントを持っている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e1900-133">This can happen when a Microsoft Search user has a Rewards account that was created with a <a href="https://www.microsoft.com/en-us/welcome?rtc=1">Microsoft account</a>.</span></span> <span data-ttu-id="e1900-134">(Microsoft アカウントに関連付けられている電子メール アドレスに、Outlook.com、Hotmail.com、Gmail、Yahoo、またはその他のプロバイダーからのものが使用できます。) ユーザーが同じブラウザー セッションで仕事用アカウントと Microsoft アカウントの両方で交互にサインインする場合、リワード アカウントにポイントが加算される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e1900-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="e1900-135">ユーザーは、Cookie をクリアすることにより、Microsoft Search での検索中にポイントの発生を停止できます。</span><span class="sxs-lookup"><span data-stu-id="e1900-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span> 

