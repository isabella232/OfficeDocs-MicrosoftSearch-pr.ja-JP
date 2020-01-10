---
title: Bing での Microsoft Search のセキュリティとプライバシー
ms.author: jeffkizn
author: jeffkizn
manager: pmanek
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Bing で Microsoft Search を使用して、承認されたユーザーに情報を提供しながら、会社のデータとエンドユーザーを保護する
ms.openlocfilehash: 7f19327f3d62f68ed876875596610181b5f1bc0e
ms.sourcegitcommit: ac1209d11b8cc265d2224917fbe2a2bb0f65ef84
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2020
ms.locfileid: "41005623"
---
# <a name="security-and-privacy-for-microsoft-search-in-bing"></a>Bing での Microsoft Search のセキュリティとプライバシー

高度なプライバシーとセキュリティ対策により、Bing での Microsoft Search は、ユーザーおよび workplace データを保護します。

## <a name="secure-by-default"></a>既定のセキュリティ保護

Bing 要求での Microsoft Search は HTTPS を介して行われます。 接続は、セキュリティを強化するためにエンドツーエンドで暗号化されます。
  
## <a name="authentication-and-authorization-with-azure-active-directory"></a>Azure Active Directory による認証と承認

Bing での Microsoft Search の認証は、Azure Active Directory に関連付けられています。 Microsoft Search ユーザーが Bing にアクセスすると、Bing ヘッダーには Microsoft アカウントと職場または学校のアカウントのサインインオプションが表示されます。 ユーザーが対象の参加者であるかどうかを Bing が判断できない場合、ユーザーは [ [Microsoft Search の検索](https://www.bing.com/business/explore)] ページに移動し、自動的に組織のサインインページにリダイレクトされます。

ユーザーは職場または学校のアカウントを使用する場合にのみ Microsoft Search にアクセスできます。SharePoint or Outlook などの Office 365 サービスにアクセスするときに使用するのと同じ資格情報でサインインする必要があります。個人用の Microsoft アカウントを使用して Microsoft Search にサインインすることはできません。

## <a name="single-sign-on"></a>シングル サインオン

ユーザーが Outlook や SharePoint などの別のサービスで既に職場または学校のアカウントで認証されている場合は、同じブラウザーで Bing にアクセスすると、同じ職場または学校のアカウントに自動的にサインインします。 また、ユーザーが職場または学校のアカウントからサインアウトすると、そのユーザーは同じブラウザーの他の Microsoft Office サービスから自動的にサインアウトされます。
  
## <a name="communicates-with-the-microsoft-cloud-from-the-browser"></a>ブラウザーから Microsoft cloud と通信する

ユーザーが職場または学校のアカウントを使用してサインインすると、Bing では Microsoft Search 結果を表示できるようにブラウザーに必要なクライアント ライブラリをダウンロードします。その後に検索を行うと、ブラウザー内のコードによって Office 365 クラウドが呼び出され、結果を取得できるようになります。そのため、Microsoft Search は、Office 365 の[業界標準と規制に関するコンプライアンス フレームワーク ](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf) (PDF ダウンロード) に従い、Tier C (SOC2 Type 1) に準拠する専用 API が使用されます。つまり、作業結果と作業データが非準拠の Bing システムを通ることはありません。
  
## <a name="permissions"></a>アクセス許可

SharePoint や OneDrive for Business などの Office 365 ワークロードから取得した作業結果は、ソースでセキュリティによるトリミングを受けます。ユーザーは、Office 365 で見たりアクセスしたりできない Word ドキュメントや PowerPoint プレゼンテーションなどのリソースを見ることはできません。ユーザーは、ユーザー自身のファイルまたはファイル作成者が SharePoint で明示的または (グループ メンバーシップなどを使用して) 暗黙的にユーザーと共有したファイルのみを見ることができます。

## <a name="microsoft-search-in-bing-protects-workplace-searches"></a>Bing での Microsoft Search による workplace の検索の保護

ユーザーが Bing の Microsoft Search で検索クエリを入力すると、次の2つの同時検索要求が発生します。

- 組織の内部リソースの検索。
- Bing.com からの公開結果を個別に検索します。

Workplace の検索では機密になる場合があるため、Microsoft Search では、Bing.com からのパブリック結果の個別の検索をどのように処理するかを記述する一連の信頼手段が実装されています。

### <a name="logging"></a>ログ記録

- Bing トラフィックで Microsoft Search に関連するすべての Bing.com 検索ログは、workplace identity から切り離されます。
- クエリが特定の組織に固有ではないという確証を得るために、制限または頻度のしきい値が満たされている場合は、プライバシーに関する[声明](https://privacy.microsoft.com/privacystatement)の「検索と人工知能」セクションの説明に従ってクエリが処理されます。 たとえば、このようなクエリを使用して、autosuggest や関連する検索などのパブリック機能をモデル化し、トレーニングします。
- 一連の制限または頻度のしきい値を満たしていないクエリは、Microsoft Search 以外のパブリック トラフィックとは別に保存されます。

### <a name="advertising"></a>広告

Workplace search に関連する Bing.com に表示される広告は、検索クエリの内容にのみ関連しています。 広告は、職場 ID に基づいてユーザーをターゲットにすることはありません。

## <a name="gdpr"></a>GDPR

2018年5月21日、Microsoft からの[ブログ投稿](https://blogs.microsoft.com/on-the-issues/2018/05/21/microsofts-commitment-to-gdpr-privacy-and-putting-customers-in-control-of-their-own-data/)では、GDPR 準拠に対するコミットメントが反映されています。また、microsoft が自社の GDPR コンプライアンスの義務を持つビジネスおよび組織をサポートする方法を紹介しています。 詳細については、Microsoft[セキュリティセンターの FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)を参照してください。

お客様の内部リソースに対して実行された Microsoft 検索クエリと返される結果は顧客データとみなされるため、[セキュリティセンターの FAQ](https://www.microsoft.com/trustcenter/privacy/gdpr/gdpr-faqs)に示されているように、記事28で概説されているプロセッサのコミットメントにも対応しています。 Microsoft Search からパブリック Bing に移行するクエリに関しては、Microsoft はデータコントローラーとしての GDPR 義務に準拠しています。
