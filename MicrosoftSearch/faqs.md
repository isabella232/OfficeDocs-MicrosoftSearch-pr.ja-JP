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
ms.openlocfilehash: 94161d3ac53ca72a9f8298674a53fdaa0a80caaf5ca3802d47ea693043a30530
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533934"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>よく寄せられる質問

以下は、よく寄せられる質問の一覧です。

> [!TIP]
> ここで質問に対する回答が得られなかった場合は、 この記事のフィードバックを使用してご質問ください。

## <a name="is-advanced-query-understanding-supported"></a>高度なクエリ理解はサポートされていますか?

はい、Microsoft Searchより大きな語句からクエリの意図を解析します。 この機能では、AI を使用して、ユーザーが検索意図に影響を与えないクエリに追加する一般的な余分な語句を学習します。 たとえば、ユーザーが自分のパスワードを変更する方法について詳しい情報を検索すると、クエリからあまり重要な単語を抽出し、パスワードの変更など、関連する単語に基づいてトリガー *します。*
  
この機能は、 で設定されたキーワードを上書[きMicrosoft 365 管理センター。](https://admin.microsoft.com)
  
## <a name="can-you-search-for-files-on-premises"></a>オンプレミスのファイルを検索できますか?

はい。 ハイブリッド展開を使用している場合[SharePoint](http://sharepoint.com/)オンプレミスのファイルを検索SharePoint。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。

既定の検索エンジン、既定のホーム ページ、および既定のブラウザーを設定して、ユーザーが既定の検索エンジンで最高のエクスペリエンスを提供Microsoft Search手順[Bing。](https://Bing.com)

- [既定Microsoft Edgeブラウザーとして設定する](/deployedge/edge-default-browser)
- [Bing を既定の検索エンジンとして設定する](set-default-search-engine.md)
- [Bing.com をエンタープライズ ホームページとして設定する](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>検索結果に対する保護について教えてください。

信頼済み[クラウドAzure Active Directory](/azure/active-directory/)結果にアクセスするには、認証が必要です。 認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。 検索クエリは識別され、ログは、ユーザーが検索トラフィックを使用[](https://Bing.com)するときにBingトラフィックからMicrosoft Search分離Bing。

## <a name="can-i-search-across-federated-organizations"></a>フェデレーション組織間を検索できますか?

いいえ。

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>セキュリティ、コンプライアンス、およびOffice 365に関する情報はどこで取得できますか?

詳細については、「信頼センター」のページ[を参照Office 365。](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>ゲスト ユーザーは、組織のMicrosoft Searchを活用できますか?

Microsoft 365アクセスを通じて、組織外のユーザーとの豊富なコラボレーション[を可能にします。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) これらのユーザーは、ドキュメント、サイト、グループ、リスト、およびライブラリに対して検索操作を実行できます。 ただし、ゲスト ユーザーは完全でカスタマイズされた Microsoft Search エクスペリエンスを取得し、ヘッダーの統合された Microsoft Search ボックスではなく、ページ上の検索ボックスを活用する必要がある場合があります。