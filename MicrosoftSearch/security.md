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
description: 権限のあるユーザーに情報を提供する Microsoft の検索を使用しているときに、エンタープライズ ・ データとユーザーを保護します。
ms.openlocfilehash: 5f59e0e2969ef829d7c14b07ecb47d645cc63013
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612523"
---
# <a name="security-for-microsoft-search"></a><span data-ttu-id="0545c-103">Microsoft Search のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="0545c-103">Security for Microsoft Search</span></span>

<span data-ttu-id="0545c-104">エンタープライズ ・ クラスのセキュリティ、Microsoft Search は常に、ユーザーとデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="0545c-104">With enterprise-grade security, Microsoft Search always keeps your users and data protected.</span></span>
  
## <a name="secure-by-default"></a><span data-ttu-id="0545c-105">既定のセキュリティ設定します。</span><span class="sxs-lookup"><span data-stu-id="0545c-105">Secure by default</span></span>

<span data-ttu-id="0545c-p101">Microsoft Search では、HTTPS 経由で行われる要求を常に、です。この保護機能は暗号化されたエンド ・ ツー ・ エンド セキュリティ強化のため、接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="0545c-p101">Microsoft Search always ensures requests are made over HTTPS. This safeguard ensures the connection is encrypted end-to-end for enhanced security.</span></span>
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a><span data-ttu-id="0545c-108">認証と Azure Active Directory で承認</span><span class="sxs-lookup"><span data-stu-id="0545c-108">Authentication and authorization with Azure Active Directory</span></span>

<span data-ttu-id="0545c-p102">Microsoft Search の認証は、Azure Active Directory につながっています。Microsoft Search のユーザーは、Bing に移動して、ヘッダーとして Microsoft アカウントのサインインのオプションを表示、Bing は著作物としてもまたは、アカウントの学校します。Bing では、ユーザーが、対象となる参加者であるかどうかを判断できない、ユーザーことができます、それらが自動的にリダイレクトされます、組織のサインイン ページに[Microsoft Search の表示](https://www.bing.com/business/explore)のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0545c-p102">Authentication for Microsoft Search is tied to Azure Active Directory. When Microsoft Search users go to Bing, the Bing header will show sign-in options for a Microsoft account as well as a work or school account. If Bing can't determine whether a user is an eligible participant, users can go to the [Explore Microsoft Search](https://www.bing.com/business/explore) page, where they'll be automatically redirected to your organization's sign-in page.</span></span> 
  
<span data-ttu-id="0545c-p103">Microsoft Search は、職場または学校のアカウントからのみアクセスできます。SharePoint や Outlook などの Office 365 サービスにアクセスするために同じ資格情報を使用してサインインする必要があります。Microsoft Search へのサインインには、個人用の Microsoft アカウントを使用できません。</span><span class="sxs-lookup"><span data-stu-id="0545c-p103">Users can access Microsoft Search only through a work or school account. They need to sign in with the same credentials they use to access Office 365 services such as SharePoint or Outlook. A personal Microsoft account can't be used to sign in to Microsoft Search.</span></span>
  
<span data-ttu-id="0545c-115">ユーザー署名できません Bing に Microsoft アカウントと、職場、学校のアカウントの両方を同時にします。</span><span class="sxs-lookup"><span data-stu-id="0545c-115">Users can't be signed in to Bing with both a Microsoft account and a work or school account at the same time.</span></span>
  
## <a name="single-sign-on"></a><span data-ttu-id="0545c-116">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0545c-116">Single sign-on</span></span>

<span data-ttu-id="0545c-p104">Outlook や、SharePoint などの別のサービスに、職場、学校のアカウントを持つユーザーがまだ認証されている場合、自動的にサインインして Microsoft Search を同じブラウザーで Bing に移動するとします。ユーザーは、Microsoft Search から署名をすると、自動的にサインイン同じブラウザーの他のサービスから。</span><span class="sxs-lookup"><span data-stu-id="0545c-p104">If a user is already authenticated with their work or school account in another service, such as Outlook or SharePoint, they'll be automatically signed in to Microsoft Search when they go to Bing in the same browser. Also, when the user signs out of Microsoft Search, they'll be automatically signed out from other services in the same browser.</span></span>
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a><span data-ttu-id="0545c-119">ブラウザーから信頼されているクラウドとの通信します。</span><span class="sxs-lookup"><span data-stu-id="0545c-119">Communicates with the Trusted Cloud from the browser</span></span>

<span data-ttu-id="0545c-p105">ユーザーが自分の仕事にサインインまたは、学校のアカウント、Bing はマイクロソフトの検索結果を有効にするブラウザーに必要なクライアント ライブラリをダウンロードすると。それらを検索するときにブラウザーでコードは、作業の結果を取得するのには Office 365 のクラウドを呼び出します。これを行うには、Microsoft Search は、層の C (SOC2 Type 1) により、Office 365[の業界標準や規制のコンプライアンス ・ フレームワーク](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)(PDF ダウンロード) 準拠である専用の API を使用します。これは、作業の結果と作業データを Bing の非準拠のシステムでフローしないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="0545c-p105">When a user signs in with their work or school account, Bing will download the necessary client libraries to the browser to enable Microsoft Search results. Then, when they search, the in-browser code calls the Office 365 cloud to get work results. To do this, Microsoft Search uses a dedicated API that is Tier C (SOC2 Type 1) compliant pursuant to the Office 365 [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download). This means work results and work data never flow through non-compliant Bing systems.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="0545c-124">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="0545c-124">Permissions</span></span>

<span data-ttu-id="0545c-p106">SharePoint およびビジネスのための OneDrive は、セキュリティなど、Office 365 の作業負荷から取得した作業の結果は、ソースで切り取られます。ユーザーは、Word 文書や PowerPoint のプレゼンテーションを参照してくださいし、Office 365 を使用してアクセスすることはできませんなどのリソースを表示できません。独自のファイルと共有されているそれらの作成者によって明示的または暗黙的にファイルのみ参照できます (例では、グループ メンバーシップ) を SharePoint にします。</span><span class="sxs-lookup"><span data-stu-id="0545c-p106">Work results retrieved from Office 365 workloads such as SharePoint and OneDrive for Business are security trimmed at the source. Users can't see resources such as Word documents or PowerPoint presentations they can't see and access through Office 365. They can only see their own files and files that have been shared with them by the author explicitly or implicitly (through a group membership, for example) in SharePoint.</span></span>
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a><span data-ttu-id="0545c-128">Bing の公開部分からユーザーのクエリを保護します。</span><span class="sxs-lookup"><span data-stu-id="0545c-128">Protects user queries from the public portion of Bing</span></span>

<span data-ttu-id="0545c-129">作業に関連する検索は、機密性の高い可能性がある、ために、Microsoft Search は、Bing の公開 web の結果の一部でこれらの処理方法の信頼のメジャーのセットを実装しました。</span><span class="sxs-lookup"><span data-stu-id="0545c-129">Because work-related searches may be sensitive, Microsoft Search has implemented a set of trust measures for how these are handled by the public web results part of Bing.</span></span>
  
<span data-ttu-id="0545c-130">ユーザー クエリは、返された応答内の 1 つまたは複数の作業結果を含むかどうかに関係なく、次の対策を実行します。</span><span class="sxs-lookup"><span data-stu-id="0545c-130">Regardless of whether a user query contains one or more work results in the returned response, the following measures are taken:</span></span>
  
- <span data-ttu-id="0545c-131">Logging</span><span class="sxs-lookup"><span data-stu-id="0545c-131">Logging</span></span>
    
  - <span data-ttu-id="0545c-p107">Microsoft 検索トラフィックに関連するすべての検索ログは、識別され、公開、非 Microsoft 検索トラフィックから個別に格納します。18 か月間保持していることと、アクセスはデバッグのためだけに制限されます。</span><span class="sxs-lookup"><span data-stu-id="0545c-p107">All search logs pertaining to Microsoft Search traffic are de-identified and stored separately from public, non-Microsoft Search traffic. They're retained for 18 months, and access is restricted for debugging purposes only.</span></span>
    
  - <span data-ttu-id="0545c-134">モデルまたは列車 autosuggest や公開 web の検索の関連などの公開の機能には、これらのログ内のクエリは使用されません。</span><span class="sxs-lookup"><span data-stu-id="0545c-134">The queries in these logs are not used to model or train public features such as autosuggest or related searches for the public web.</span></span>
    
  - <span data-ttu-id="0545c-135">アクセス制限は、セキュリティ グループ、エンジニア リング ・ システム内で他のレイヤーなど、さまざまなセキュリティで保護されたメカニズムを使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="0545c-135">Restricted access is managed via various secure mechanisms, including security groups and other layers within the engineering system.</span></span>
    
- <span data-ttu-id="0545c-136">検索履歴</span><span class="sxs-lookup"><span data-stu-id="0545c-136">Search history</span></span>
    
  - <span data-ttu-id="0545c-137">職場または学校のアカウントを使用して署名されている場合、ユーザーの検索履歴は他のコンピューターまたはデバイスで使用可能なできません。</span><span class="sxs-lookup"><span data-stu-id="0545c-137">When signed in with a work or school account, a user's search history won't be available on other computers or devices.</span></span>
    
- <span data-ttu-id="0545c-138">広告</span><span class="sxs-lookup"><span data-stu-id="0545c-138">Advertising</span></span>
    
  - <span data-ttu-id="0545c-139">エンタープライズ検索のクエリは、共有または広告主に提案しないでください。</span><span class="sxs-lookup"><span data-stu-id="0545c-139">Enterprise search queries are never shared with or suggested to advertisers.</span></span>
    
  - <span data-ttu-id="0545c-140">マイクロソフトの検索に関連する検索広告のログは、パブリック トラフィックから個別に格納されます。</span><span class="sxs-lookup"><span data-stu-id="0545c-140">Search Ads logs pertaining to Microsoft Search are stored separately from public traffic.</span></span>
    
  - <span data-ttu-id="0545c-141">組織または作業時間の id に基づいてユーザーに広告しない対象になります。</span><span class="sxs-lookup"><span data-stu-id="0545c-141">Ads are never targeted to a user based on their work identity or organization.</span></span>
    
## <a name="gdpr"></a><span data-ttu-id="0545c-142">GDPR</span><span class="sxs-lookup"><span data-stu-id="0545c-142">GDPR</span></span>

<span data-ttu-id="0545c-p108">[2018、5 月 21日ブログの投稿](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)から Microsoft には、GDPR のコンプライアンスへの取り組みとマイクロソフトが企業や、独自の GDPR の遵守義務を持つ組織を支援する方法が反映されます。マイクロソフトの[信頼に関する FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)の追加の詳細が表示されます。オンライン サービス内での組織の顧客の顧客データを操作する Microsoft の検索クエリの[信頼に関する FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)に反映されるように、資料 28 に記載されているプロセッサのコミットメントを満たすも。パブリック Bing に移動するクエリから Microsoft 検索に関しては、マイクロソフトはデータ コント ローラーであり、除外 GDPR の下で説明したようにクエリを識別するための対策を実装しています。</span><span class="sxs-lookup"><span data-stu-id="0545c-p108">The [May 21, 2018, blog post](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/) from Microsoft reflects our commitment to GDPR compliance and how Microsoft helps businesses and organizations with their own GDPR compliance obligations. You can find additional detail in the Microsoft [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). Microsoft Search queries that operate against organizational customers' Customer Data within the Online Services will also meet the processor commitments outlined in Article 28 as reflected in the [Trust Center FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs). With respect to queries from Microsoft Search that go to public Bing, Microsoft is a data controller and has implemented measures to de-identify the queries as outlined under GDPR.</span></span>


