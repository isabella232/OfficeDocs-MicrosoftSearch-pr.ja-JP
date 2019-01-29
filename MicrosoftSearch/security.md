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
# <a name="security-for-microsoft-search"></a>Microsoft Search のセキュリティ

エンタープライズ ・ クラスのセキュリティ、Microsoft Search は常に、ユーザーとデータを保護します。
  
## <a name="secure-by-default"></a>既定のセキュリティ設定します。

Microsoft Search では、HTTPS 経由で行われる要求を常に、です。この保護機能は暗号化されたエンド ・ ツー ・ エンド セキュリティ強化のため、接続を確認します。
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>認証と Azure Active Directory で承認

Microsoft Search の認証は、Azure Active Directory につながっています。Microsoft Search のユーザーは、Bing に移動して、ヘッダーとして Microsoft アカウントのサインインのオプションを表示、Bing は著作物としてもまたは、アカウントの学校します。Bing では、ユーザーが、対象となる参加者であるかどうかを判断できない、ユーザーことができます、それらが自動的にリダイレクトされます、組織のサインイン ページに[Microsoft Search の表示](https://www.bing.com/business/explore)のページに移動します。 
  
Microsoft Search は、職場または学校のアカウントからのみアクセスできます。SharePoint や Outlook などの Office 365 サービスにアクセスするために同じ資格情報を使用してサインインする必要があります。Microsoft Search へのサインインには、個人用の Microsoft アカウントを使用できません。
  
ユーザー署名できません Bing に Microsoft アカウントと、職場、学校のアカウントの両方を同時にします。
  
## <a name="single-sign-on"></a>シングル サインオン

Outlook や、SharePoint などの別のサービスに、職場、学校のアカウントを持つユーザーがまだ認証されている場合、自動的にサインインして Microsoft Search を同じブラウザーで Bing に移動するとします。ユーザーは、Microsoft Search から署名をすると、自動的にサインイン同じブラウザーの他のサービスから。
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>ブラウザーから信頼されているクラウドとの通信します。

ユーザーが自分の仕事にサインインまたは、学校のアカウント、Bing はマイクロソフトの検索結果を有効にするブラウザーに必要なクライアント ライブラリをダウンロードすると。それらを検索するときにブラウザーでコードは、作業の結果を取得するのには Office 365 のクラウドを呼び出します。これを行うには、Microsoft Search は、層の C (SOC2 Type 1) により、Office 365[の業界標準や規制のコンプライアンス ・ フレームワーク](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)(PDF ダウンロード) 準拠である専用の API を使用します。これは、作業の結果と作業データを Bing の非準拠のシステムでフローしないことを意味します。 
  
## <a name="permissions"></a>アクセス許可

SharePoint およびビジネスのための OneDrive は、セキュリティなど、Office 365 の作業負荷から取得した作業の結果は、ソースで切り取られます。ユーザーは、Word 文書や PowerPoint のプレゼンテーションを参照してくださいし、Office 365 を使用してアクセスすることはできませんなどのリソースを表示できません。独自のファイルと共有されているそれらの作成者によって明示的または暗黙的にファイルのみ参照できます (例では、グループ メンバーシップ) を SharePoint にします。
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Bing の公開部分からユーザーのクエリを保護します。

作業に関連する検索は、機密性の高い可能性がある、ために、Microsoft Search は、Bing の公開 web の結果の一部でこれらの処理方法の信頼のメジャーのセットを実装しました。
  
ユーザー クエリは、返された応答内の 1 つまたは複数の作業結果を含むかどうかに関係なく、次の対策を実行します。
  
- Logging
    
  - Microsoft 検索トラフィックに関連するすべての検索ログは、識別され、公開、非 Microsoft 検索トラフィックから個別に格納します。18 か月間保持していることと、アクセスはデバッグのためだけに制限されます。
    
  - モデルまたは列車 autosuggest や公開 web の検索の関連などの公開の機能には、これらのログ内のクエリは使用されません。
    
  - アクセス制限は、セキュリティ グループ、エンジニア リング ・ システム内で他のレイヤーなど、さまざまなセキュリティで保護されたメカニズムを使用して管理されます。
    
- 検索履歴
    
  - 職場または学校のアカウントを使用して署名されている場合、ユーザーの検索履歴は他のコンピューターまたはデバイスで使用可能なできません。
    
- 広告
    
  - エンタープライズ検索のクエリは、共有または広告主に提案しないでください。
    
  - マイクロソフトの検索に関連する検索広告のログは、パブリック トラフィックから個別に格納されます。
    
  - 組織または作業時間の id に基づいてユーザーに広告しない対象になります。
    
## <a name="gdpr"></a>GDPR

[2018、5 月 21日ブログの投稿](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)から Microsoft には、GDPR のコンプライアンスへの取り組みとマイクロソフトが企業や、独自の GDPR の遵守義務を持つ組織を支援する方法が反映されます。マイクロソフトの[信頼に関する FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)の追加の詳細が表示されます。オンライン サービス内での組織の顧客の顧客データを操作する Microsoft の検索クエリの[信頼に関する FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs)に反映されるように、資料 28 に記載されているプロセッサのコミットメントを満たすも。パブリック Bing に移動するクエリから Microsoft 検索に関しては、マイクロソフトはデータ コント ローラーであり、除外 GDPR の下で説明したようにクエリを識別するための対策を実装しています。


