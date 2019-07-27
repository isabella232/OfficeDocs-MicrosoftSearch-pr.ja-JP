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
ms.openlocfilehash: b7b62173dc61d271a4953adbf20a6cf48b122694
ms.sourcegitcommit: 4eeb78066fd13e906daed3add003398bd9d0f6ca
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2019
ms.locfileid: "35917571"
---
# <a name="security-for-microsoft-search"></a>Microsoft Search のセキュリティ

Microsoft Search では、エンタープライズ レベルのセキュリティによって常時ユーザーとデータが保護されます。


## <a name="secure-by-default"></a>既定のセキュリティ保護

Microsoft Search では、要求は必ず HTTPS 経由で行われます。この保護機能によって、接続はエンドツーエンドで暗号化され、高度なセキュリティが確保されます。
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Azure Active Directory による認証と承認

Microsoft Search の認証は Azure Active Directory に結び付けられています。Microsoft Search ユーザーが Bing にアクセスすると、Bing ヘッダーには Microsoft アカウント、および職場と学校のアカウントのサインイン オプションが表示されます。ユーザーが参加資格を有しているかどうかを Bing が判断できない場合、ユーザーは[Microsoft Search の探索](https://www.bing.com/business/explore)ページに移動できます。このページでは、組織のサインイン ページに自動的にリダイレクトされます。
  
ユーザーは職場または学校のアカウントを使用する場合にのみ Microsoft Search にアクセスできます。SharePoint or Outlook などの Office 365 サービスにアクセスするときに使用するのと同じ資格情報でサインインする必要があります。個人用の Microsoft アカウントを使用して Microsoft Search にサインインすることはできません。
  
Microsoft アカウントと職場または学校のアカウントを同時に使用して Bing にサインインすることはできません。
  
## <a name="single-sign-on"></a>シングル サインオン

ユーザーが Outlook または SharePoint などの別のサービスで職場または学校のアカウントを使用して既に認証されている場合には、同じブラウザーで Bing にアクセスすると自動的に Microsoft Search にサインインされます。また、Microsoft Search からサインアウトすると、同じブラウザーで使用している他のサービスからも自動的にサインアウトします。
  
## <a name="communicates-with-the-trusted-cloud-from-the-browser"></a>信頼されているクラウドとブラウザーから通信する

ユーザーが職場または学校のアカウントを使用してサインインすると、Bing では Microsoft Search 結果を表示できるようにブラウザーに必要なクライアント ライブラリをダウンロードします。その後に検索を行うと、ブラウザー内のコードによって Office 365 クラウドが呼び出され、結果を取得できるようになります。そのため、Microsoft Search は、Office 365 の[業界標準と規制に関するコンプライアンス フレームワーク ](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF ダウンロード) に従い、Tier C (SOC2 Type 1) に準拠する専用 API が使用されます。つまり、作業結果と作業データが非準拠の Bing システムを通ることはありません。 
  
## <a name="permissions"></a>アクセス許可

SharePoint や OneDrive for Business などの Office 365 ワークロードから取得した作業結果は、ソースでセキュリティによるトリミングを受けます。ユーザーは、Office 365 で見たりアクセスしたりできない Word ドキュメントや PowerPoint プレゼンテーションなどのリソースを見ることはできません。ユーザーは、ユーザー自身のファイルまたはファイル作成者が SharePoint で明示的または (グループ メンバーシップなどを使用して) 暗黙的にユーザーと共有したファイルのみを見ることができます。
  
## <a name="protects-user-queries-from-the-public-portion-of-bing"></a>Bing の一般部分からユーザーのクエリを保護する

職務に関連する検索は機密性が求められる場合があるため、Microsoft Search では、Bing の一般の Web の検索結果部分でのそうした検索の取り扱いに関する一連の信頼性対策が実装されています。
  
ユーザーのクエリに返された応答に作業結果が含まれるかどうかに関わらず、次の対策がとられます。
  
- Logging 
  - Microsoft Search トラフィックに関するすべての検索ログは匿名化され、匿名化された状態で 18 か月間保持されます。
  - これらのシステムログに保存されたクエリは、制限一式と頻度しきい値が満たされている場合、自動検索候補や関連検索などのパブリックな検索機能のモデルや検索機能の学習にのみ使用されます。そしてそれは、これらのクエリが一般に普及しているものであり、特定の組織に特化したものではないという信頼を与えます。 クエリは、Microsoft 以外のユーザーからの関連付けデータに膨大な回数出現する必要があります。そしてそれは、企業の検索結果のみをトリガーするものであってはなりません。 クエリがこれらの要件を満たさない場合は、一般の、Microsoft Search 以外のトラフィックとは別に保管されます。
  - アクセス制限は、セキュリティ グループおよびエンジニアリング システム内の他のレイヤーなどのさまざまなセキュリティ メカニズムを通して管理されます。
- 検索履歴    
  - 職場または学校のアカウントでサインインした場合、他のコンピューターまたはデバイスからユーザーの検索履歴へアクセスすることはできません。
 
- 広告   
  - エンタープライズ検索クエリが広告業者と共有されたり、広告業者に通知されたりすることはありません。
  - ユーザーの職場 ID または組織を基にユーザーが広告のターゲットになることはありません。
    
## <a name="gdpr"></a>GDPR

Microsoft の [2018 年 5 月 21 日のブログ投稿](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)は、Microsoft における GDPR 遵守への取り組みと、Microsoft によるそれぞれの企業や組織での GDPR 遵守義務への支援の仕方を書き表したものです。追加詳細については、Microsoft [セキュリティ センターの FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs) をご覧ください。Microsoft Search オンライン サービス内で組織の顧客の顧客データに対して処理が行われるクエリは、[セキュリティ センターの FAQ](https://www.microsoft.com/en-us/trustcenter/privacy/gdpr/gdpr-faqs) の説明にある通り、第 28 条で説明される処理者に関する取り組みへ準拠しています。Microsoft Search から一般の Bing に対してのクエリに関しては、Microsoft がデータ管理者となり、GDPR の説明に従いクエリを匿名化する対応を実施しています。