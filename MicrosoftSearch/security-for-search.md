---
title: セキュリティとプライバシー Microsoft SearchのBing
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 承認されたユーザーに情報を提供しながら、会社のデータとエンド ユーザーを保護し、Microsoft SearchをBing
ms.openlocfilehash: 181a06ecb9c009d03c71e3e7f8ecfc7d675faa659967bc6a6c1560513a45a5ac
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532679"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>セキュリティとプライバシー Microsoft SearchのBing

プライバシーとセキュリティ対策の強化により、ユーザー Microsoft Search Bingを保護するのに役立ちます。

## <a name="secure-by-default"></a>既定のセキュリティ保護

Microsoft SearchのBing HTTPS 経由で行います。 セキュリティを強化するために、接続はエンドツーエンドで暗号化されます。
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Azure Active Directory による認証と承認

認証は、Microsoft SearchのBingに関連付Azure Active Directory。 ユーザー Microsoft Searchに移動すると、Bing Bing ヘッダーには、Microsoft アカウントのサインイン オプションと、仕事用または学校用のアカウントが表示されます。 ユーザー Bingが適格な参加者であるかどうかを判断できない場合、ユーザーは[[Microsoft Search](https://www.bing.com/business/explore)の探索] ページに移動して、組織のサインイン ページに自動的にリダイレクトされます。

ユーザーは職場または学校のアカウントを使用する場合にのみ Microsoft Search にアクセスできます。SharePoint or Outlook などの Office 365 サービスにアクセスするときに使用するのと同じ資格情報でサインインする必要があります。個人用の Microsoft アカウントを使用して Microsoft Search にサインインすることはできません。

## <a name="single-sign-on"></a>シングル サインオン

Outlook や SharePoint などの別のサービスでユーザーが既に仕事または学校のアカウントで認証されている場合、同じブラウザーで Bing に移動すると、そのユーザーは自動的に同じ仕事または学校のアカウントにサインインします。 また、ユーザーが自分の仕事または学校のアカウントからサインアウトすると、同じブラウザーの他の Microsoft Officeから自動的にサインアウトされます。
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>ブラウザーから Microsoft クラウドと通信する

ユーザーが自分の仕事または学校のアカウントでサインインすると、Bing Microsoft Search必要なクライアント ライブラリがブラウザーにダウンロードされます。 次に、検索時に、ブラウザー内のコードがクラウドOffice 365を呼び出して、作業結果を取得します。 これを行うには、Microsoft Search SSAE 18 SOC2 Type 1 の制御目的に従って運用される専用 API を使用します。 つまり、作業結果と作業データは、Office 365 Core Online Services で処理される場合よりも、データ処理制御の目的が厳しくなく、Bing システムを通過しません。
  
## <a name="permissions"></a>アクセス許可

SharePoint や OneDrive for Business などの Office 365 ワークロードから取得した作業結果は、ソースでセキュリティによるトリミングを受けます。ユーザーは、Office 365 で見たりアクセスしたりできない Word ドキュメントや PowerPoint プレゼンテーションなどのリソースを見ることはできません。ユーザーは、ユーザー自身のファイルまたはファイル作成者が SharePoint で明示的または (グループ メンバーシップなどを使用して) 暗黙的にユーザーと共有したファイルのみを見ることができます。

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Microsoft SearchのBingを保護する

ユーザーが検索クエリを入力すると、Microsoft SearchにBing 2 つの同時検索要求が発生します。

- 組織の内部リソースの検索。
- Bing.com から公開結果を個別に検索します。

ワークプレース検索は機密性が高い可能性があるため、Microsoft Search は、Bing.com から公開結果を個別に検索する方法を説明する一連の信頼対策を実装しています。

### <a name="logging"></a>ログ記録

- トラフィックBingのMicrosoft Searchに関連Bingすべての Bing.com 検索ログは、職場の ID から関連付け解除されます。
- クエリが特定の組織に固有ではないという自信を与える一連の制限または頻度のしきい値が満たされている場合、クエリはプライバシーに関する声明の「検索と人工知能」セクションで説明されているとおりに [処理](https://privacy.microsoft.com/privacystatement)されます。 たとえば、このようなクエリは、自動検索や関連する検索などのパブリック機能のモデル化とトレーニングに使用されます。
- 一連の制限または頻度のしきい値を満たしていないクエリは、Microsoft Search 以外のパブリック トラフィックとは別に保存されます。

### <a name="advertising"></a>広告

職場での検索に関連Bing.com に表示される広告は、検索クエリの内容にのみ関連しています。 広告は、職場 ID に基づいてユーザーをターゲットにすることはありません。

## <a name="gdpr"></a>GDPR

[2018](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)年 5 月 21 日の Microsoft のブログ投稿には、GDPR コンプライアンスへの取り組みと、企業や組織が独自の GDPR コンプライアンス義務を果たしている方法が反映されています。 詳細については、「Microsoft Trust [Center FAQ」を参照してください](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)。

Microsoft Searchの内部リソースに対して実行されたクエリと、返される結果は顧客データと見なされ、セキュリティ センターの[FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)に反映される第 28 条に記載されているプロセッサのコミットメントも満たします。 パブリック サーバーに送信されるMicrosoft Searchに関して、Microsoft はデータ 管理者Bing GDPR の義務を遵守します。
