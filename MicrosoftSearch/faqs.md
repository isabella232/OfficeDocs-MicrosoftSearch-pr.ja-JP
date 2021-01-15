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
ms.openlocfilehash: abaa1a232b08ba586dd6cd777f7e54c323159dee
ms.sourcegitcommit: aa7774d2bdff2bd9e1b7f51fcda90fa6b0c3a5ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49867380"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>よく寄せられる質問

以下は、よく寄せられる質問の一覧です。

> [!TIP]
> ここで質問に対する回答が得られなかった場合は、 この記事のフィードバックを使用してご質問ください。

## <a name="is-advanced-query-understanding-supported"></a>高度なクエリ理解はサポートされていますか?

はい、Microsoft Search は大きな語句からクエリの意図を解析します。この機能では、AI を使用して、検索の意図に影響を与えない、ユーザーがクエリに追加する一般的な余分な語句を学習します。たとえば、ユーザーが自分のパスワードを変更する方法について詳しい情報を検索すると、クエリからあまり重要な単語を抽出し、パスワードの変更など、関連する単語に基づいてトリガー *されます。*
  
この機能は、Microsoft 365 管理センターで設定された [キーワードを上書きする必要があります](https://admin.microsoft.com)。
  
## <a name="can-you-search-for-files-on-premises"></a>オンプレミスのファイルを検索できますか?

はい。 SharePoint のハイブリッド展開がある場合は、オンプレミスの [SharePoint](http://sharepoint.com/) ファイルを検索できます。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。

既定の検索エンジン、既定のホーム ページ、および既定のブラウザーを設定して、Bing の Microsoft Search でユーザーに最適なエクスペリエンスを提供する手順を次 [に示します](https://Bing.com)。

- [Microsoft Edge を既定のブラウザーとして設定する](/deployedge/edge-default-browser)
- [Bing を既定の検索エンジンとして設定する](set-default-search-engine.md)
- [Bing.com をエンタープライズ ホームページとして設定する](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>検索結果に対する保護について教えてください。

信頼済み [クラウドからの結果にアクセスするには、Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) 認証が必要です。 認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。 検索クエリは識別され、Bing で Microsoft Search を使用すると、ログはパブリック [Bing](https://Bing.com) 検索トラフィックから分離されます。

## <a name="can-i-search-across-federated-organizations"></a>フェデレーション組織間を検索できますか?

いいえ。

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Office 365 のセキュリティ、コンプライアンス、プライバシーに関する情報はどこで取得できますか?

詳細については、Office [365 の [信頼センター] ページを参照してください](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)。

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>ユーザーは職場または学校のアカウントで Microsoft リワード ポイントを獲得できますか?

Microsoft Search では、エンタープライズ ユーザーが職場または学校のアカウントでサインインする必要があります。 ただし、ユーザーはこれらのアカウントで Microsoft リワード プログラムに参加またはサインインすることはできません。 しかし、エンタープライズ ユーザーにリワード ポイントが発生する場合があります。 これは、Microsoft Search ユーザーが [Microsoft アカウント](https://www.microsoft.com/welcome?rtc=1)で作成されたリワード アカウントを持っている場合に発生する可能性があります。 (Microsoft アカウントに関連付けられている電子メール アドレスに、Outlook.com、Hotmail.com、Gmail、Yahoo、またはその他のプロバイダーからのものが使用できます。) ユーザーが同じブラウザー セッションで仕事用アカウントと Microsoft アカウントの両方で交互にサインインする場合、リワード アカウントにポイントが加算される場合があります。 ユーザーは、Cookie をクリアすることにより、Microsoft Search での検索中にポイントの発生を停止できます。

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>ゲスト ユーザーは自分の組織で Microsoft Search を利用できますか?

Microsoft 365 では、ゲスト アクセスを通じて、組織外のユーザーとの豊富な共同作業 [が可能になります。](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization) これらのユーザーは、ドキュメント、サイト、グループ、リスト、およびライブラリに対して検索操作を実行できます。 ただし、ゲスト ユーザーは、完全なカスタマイズされた Microsoft Search エクスペリエンスを利用できないので、ヘッダーの統合 Microsoft Search ボックスではなく、ページ上の検索ボックスを利用する必要がある場合があります。
