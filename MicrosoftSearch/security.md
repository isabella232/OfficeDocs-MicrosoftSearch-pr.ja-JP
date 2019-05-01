---
title: Microsoft Search のセキュリティ
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/12/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 50461cb9-8707-46c1-935a-1b9608a98800
description: Microsoft Search において、承認されたユーザーに情報を提供するときにエンタープライズのデータとユーザーを保護します
ms.openlocfilehash: 5f59e0e2969ef829d7c14b07ecb47d645cc63013
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508713"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="17f70-103">Microsoft Search のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="17f70-103">Security for Microsoft Search</span></span>

<span data-ttu-id="17f70-104">Microsoft Search では、エンタープライズ レベルのセキュリティによって常時ユーザーとデータが保護されます。</span><span class="sxs-lookup"><span data-stu-id="17f70-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="17f70-105">既定のセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="17f70-105">Secure by default</span></span>

<span data-ttu-id="17f70-p101">Microsoft Search では、要求は必ず HTTPS 経由で行われます。この保護機能によって、接続はエンドツーエンドで暗号化され、高度なセキュリティが確保されます。</span><span class="sxs-lookup"><span data-stu-id="17f70-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="17f70-108">Azure Active Directory による認証と承認</span><span class="sxs-lookup"><span data-stu-id="17f70-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="17f70-p102">Microsoft Search の認証は Azure Active Directory に結び付けられています。Microsoft Search ユーザーが Bing にアクセスすると、Bing ヘッダーには Microsoft アカウント、および職場と学校のアカウントのサインイン オプションが表示されます。ユーザーが参加資格を有しているかどうかを Bing が判断できない場合、ユーザーは[Microsoft Search の探索](https://www.bing.com/business/explore)ページに移動できます。このページでは、組織のサインイン ページに自動的にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="17f70-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="17f70-p103">ユーザーは職場または学校のアカウントを使用する場合にのみ Microsoft Search にアクセスできます。SharePoint or Outlook などの Office 365 サービスにアクセスするときに使用するのと同じ資格情報でサインインする必要があります。個人用の Microsoft アカウントを使用して Microsoft Search にサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="17f70-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="17f70-115">Microsoft アカウントと職場または学校のアカウントを同時に使用して Bing にサインインすることはできません。</span><span class="sxs-lookup"><span data-stu-id="17f70-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="17f70-116">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="17f70-116">Single sign-on</span></span>

<span data-ttu-id="17f70-p104">ユーザーが Outlook または SharePoint などの別のサービスで職場または学校のアカウントを使用して既に認証されている場合には、同じブラウザーで Bing にアクセスすると自動的に Microsoft Search にサインインされます。また、Microsoft Search からサインアウトすると、同じブラウザーで使用している他のサービスからも自動的にサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="17f70-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="17f70-119">信頼されているクラウドとブラウザーから通信する</span><span class="sxs-lookup"><span data-stu-id="17f70-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="17f70-p105">ユーザーが職場または学校のアカウントを使用してサインインすると、Bing では Microsoft Search 結果を表示できるようにブラウザーに必要なクライアント ライブラリをダウンロードします。その後に検索を行うと、ブラウザー内のコードによって Office 365 クラウドが呼び出され、結果を取得できるようになります。そのため、Microsoft Search は、Office 365 の[業界標準と規制に関するコンプライアンス フレームワーク ](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF ダウンロード) に従い、Tier C (SOC2 Type 1) に準拠する専用 API が使用されます。つまり、作業結果と作業データが非準拠の Bing システムを通ることはありません。</span><span class="sxs-lookup"><span data-stu-id="17f70-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="17f70-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="17f70-124">Permissions</span></span>

<span data-ttu-id="17f70-p106">SharePoint や OneDrive for Business などの Office 365 ワークロードから取得した作業結果は、ソースでセキュリティによるトリミングを受けます。ユーザーは、Office 365 で見たりアクセスしたりできない Word ドキュメントや PowerPoint プレゼンテーションなどのリソースを見ることはできません。ユーザーは、ユーザー自身のファイルまたはファイル作成者が SharePoint で明示的または (グループ メンバーシップなどを使用して) 暗黙的にユーザーと共有したファイルのみを見ることができます。</span><span class="sxs-lookup"><span data-stu-id="17f70-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="17f70-128">Bing の一般部分からユーザーのクエリを保護する</span><span class="sxs-lookup"><span data-stu-id="17f70-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="17f70-129">職務に関連する検索は機密性が求められる場合があるため、Microsoft Search では、Bing の一般の Web の検索結果部分でのそうした検索の取り扱いに関する一連の信頼性対策が実装されています。</span><span class="sxs-lookup"><span data-stu-id="17f70-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="17f70-130">ユーザーのクエリに返された応答に作業結果が含まれるかどうかに関わらず、次の対策がとられます。</span><span class="sxs-lookup"><span data-stu-id="17f70-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="17f70-131">ログ記録</span><span class="sxs-lookup"><span data-stu-id="17f70-131">Logging</span></span>
    
  - <span data-ttu-id="17f70-p107">Microsoft Search トラフィックに関するすべての検索ログは匿名化され、Microsoft Search トラフィック以外の一般のトラフィックとは別に保管されます。検索ログは 18 か月間保持され、デバッグの目的以外にはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="17f70-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="17f70-134">これらのログのクエリは、一般の Web 検索のためのモデルや自動検索候補や関連検索などの一般検索用の機能の学習には使われません。</span><span class="sxs-lookup"><span data-stu-id="17f70-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="17f70-135">アクセス制限は、セキュリティ グループおよびエンジニアリング システム内の他のレイヤーなどのさまざまなセキュリティ メカニズムを通して管理されます。</span><span class="sxs-lookup"><span data-stu-id="17f70-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="17f70-136">検索履歴</span><span class="sxs-lookup"><span data-stu-id="17f70-136">Search history</span></span>
    
  - <span data-ttu-id="17f70-137">職場または学校のアカウントでサインインした場合、他のコンピューターまたはデバイスからユーザーの検索履歴へアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="17f70-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="17f70-138">広告</span><span class="sxs-lookup"><span data-stu-id="17f70-138">Advertising</span></span>
    
  - <span data-ttu-id="17f70-139">エンタープライズ検索クエリが広告業者と共有されたり、広告業者に通知されたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="17f70-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="17f70-140">Microsoft Search に関係する検索広告のログは、一般のトラフィックとは別に保管されます。</span><span class="sxs-lookup"><span data-stu-id="17f70-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="17f70-141">ユーザーの職場 ID または組織を基にユーザーが広告のターゲットになることはありません。</span><span class="sxs-lookup"><span data-stu-id="17f70-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="17f70-142">GDPR</span><span class="sxs-lookup"><span data-stu-id="17f70-142">GDPR</span></span>

<span data-ttu-id="17f70-p108">Microsoft の [2018 年 5 月 21 日のブログ投稿](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)は、Microsoft における GDPR 遵守への取り組みと、Microsoft によるそれぞれの企業や組織での GDPR 遵守義務への支援の仕方を書き表したものです。追加詳細については、Microsoft [セキュリティ センターの FAQ](https://www.microsoft.com/ja-JP/trustcenter/privacy/gdpr/gdpr-faqs) をご覧ください。Microsoft Search オンライン サービス内で組織の顧客の顧客データに対して処理が行われるクエリは、[セキュリティ センターの FAQ](https://www.microsoft.com/ja-JP/trustcenter/privacy/gdpr/gdpr-faqs) の説明にある通り、第 28 条で説明される処理者に関する取り組みへ準拠しています。Microsoft Search から一般の Bing に対してのクエリに関しては、Microsoft がデータ管理者となり、GDPR の説明に従いクエリを匿名化する対応を実施しています。</span><span class="sxs-lookup"><span data-stu-id="17f70-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/ja-JP/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/ja-JP/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


