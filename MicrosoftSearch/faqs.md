---
title: FAQ
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: エンタープライズ検索と Microsoft Search についてよく寄せられる質問に対する回答です
ms.openlocfilehash: 8b4de717ab63af8842dc86135748e551ff386a2a
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59376188"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>よく寄せられる質問

以下は、よく寄せられる質問の一覧です。

> [!TIP]
> ここで質問に対する回答が得られなかった場合は、 この記事のフィードバックを使用してご質問ください。

## <a name="is-advanced-query-understanding-supported"></a>高度なクエリ理解はサポートされていますか?

はい、Microsoft Searchより大きな語句からクエリの意図を解析します。 この機能では、AI を使用して、ユーザーが検索意図に影響しないクエリに追加する一般的な余分な語句を学習します。 たとえば、ユーザーが自分のパスワードを変更する方法について詳しい情報を検索すると、クエリからあまり重要な単語を抽出し、パスワードの変更など、関連する単語に基づいてトリガー *します。*
  
この機能は、 で設定されたキーワードを上書[きMicrosoft 365 管理センター。](https://admin.microsoft.com)
  
## <a name="can-you-search-for-files-on-premises"></a>オンプレミスのファイルを検索できますか?

はい。 ハイブリッド展開を使用している場合[SharePoint](http://sharepoint.com/)オンプレミスのファイルを検索SharePoint。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。

既定の検索エンジン、既定のホーム ページ、および既定のブラウザーを設定して、ユーザーが既定の検索エンジンで最高のエクスペリエンスを提供Microsoft Search手順[Bing。](https://Bing.com)

- [既定Microsoft Edgeブラウザーとして設定する](/deployedge/edge-default-browser)
- [Bing を既定の検索エンジンとして設定する](set-default-search-engine.md)
- [Bing.com をエンタープライズ ホームページとして設定する](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>検索結果に対する保護について教えてください。

信頼済み[クラウドAzure Active Directory](/azure/active-directory/)結果にアクセスするには、認証が必要です。 認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。 クエリでMicrosoft SearchをBing場合、検索クエリは識別され、ログはパブリック クエリと検索トラフィック[Bing](https://Bing.com)されます。

## <a name="can-i-search-across-federated-organizations"></a>フェデレーション組織間を検索できますか?

いいえ。

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>セキュリティ、コンプライアンス、およびOffice 365に関する情報はどこで取得できますか?

詳細については、「信頼センター」のページ[を参照Office 365。](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)

## <a name="can-guest-users-access-microsoft-search-in-my-organization"></a>ゲスト ユーザーは自分のMicrosoft Searchにアクセスできますか?

Microsoft 365アクセスを通じて、組織外のユーザーとの豊富なコラボレーション[を可能にします。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) これらのユーザーは、ドキュメント、サイト、グループ、リスト、およびライブラリを検索できます。 ただし、ゲスト ユーザーは完全でカスタマイズされた Microsoft Search エクスペリエンスを取得し、ヘッダーの統合 Microsoft Search ボックスではなく、ページ上の検索ボックスを使用する必要がある場合があります。

## <a name="how-do-i-turn-microsoft-search-in-bing-on-or-off"></a>オンまたはオフのMicrosoft SearchをBingする方法

エンタープライズおよび教育を含むほとんどの組織では、Microsoft SearchのBingがオンになっています。 このページでMicrosoft SearchをBing、サーバーの [構成] ページ[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/configurations)に移動Microsoft 365 管理センター。 [Microsoft Search設定Bing] で、[設定の変更]を選択し、[組織がユーザー設定を使用Microsoft Search **を** Bing。 この変更を有効にするのに最大 24 時間かかります。

この設定がオフの場合、ユーザーは、検索、検索、または検索で検索するときに内部Bing結果Windows取得Microsoft Edge。 検索インデックスMicrosoft Search Bingをオフにしても、内部コンテンツが検索インデックスに追加されるのを止めるか、または防ぐ必要があります。 エントリ ポイントがBingを無効Microsoft Search。 回答と内部結果を見つけるには、ユーザーは他のエントリ ポイント (たとえば、オンラインまたはアプリSharePoint使用するOffice 365があります。
