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
ms.openlocfilehash: 98128297047d50e2d418a8ed062066ab9e86749e
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031622"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>よく寄せられる質問

以下は、よく寄せられる質問の一覧です。

> [!TIP]
> ここで質問に対する回答が得られなかった場合は、 この記事のフィードバックを使用してご質問ください。

## <a name="is-advanced-query-understanding-supported"></a>高度なクエリ理解はサポートされていますか?

はい、Microsoft Search は大きな語句からクエリインテントを解析します。 この機能では、AI を使用して、ユーザーが検索意図に影響を与えないクエリに追加する一般的な余分な語句を学習します。 たとえば、ユーザーが自分のパスワードを変更する方法について詳しい情報を検索すると、クエリからあまり重要な単語を抽出し、パスワードの変更など、関連する単語に基づいてトリガー *します。*
  
この機能は [、Microsoft 365](https://admin.microsoft.com)管理センターで設定されたキーワードを上書きしない。
  
## <a name="can-you-search-for-files-on-premises"></a>オンプレミスのファイルを検索できますか?

はい。 SharePoint のハイブリッド展開がある場合は、オンプレミス [の SharePoint](http://sharepoint.com/) ファイルを検索できます。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。

既定の検索エンジン、既定のホームページ、および既定のブラウザーを設定して、Bing の Microsoft Search でユーザーに最高のエクスペリエンスを提供する手順を [次に示します](https://Bing.com)。

- [既定のブラウザーとして Microsoft Edge を設定する](/deployedge/edge-default-browser)
- [Bing を既定の検索エンジンとして設定する](set-default-search-engine.md)
- [Bing.com をエンタープライズ ホームページとして設定する](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>検索結果に対する保護について教えてください。

信頼された [クラウドから結果にアクセスするには、Azure Active Directory](/azure/active-directory/) 認証が必要です。 認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。 検索クエリは識別され、Bing で Microsoft Search を使用すると、ログはパブリック [Bing](https://Bing.com) 検索トラフィックから分離されます。

## <a name="can-i-search-across-federated-organizations"></a>フェデレーション組織間を検索できますか?

いいえ。

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>365 セキュリティ、コンプライアンス、Officeに関する情報はどこで取得できますか?

詳細については、365 の [信頼センター [] ページOffice参照してください](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx)。

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>ユーザーは職場または学校のアカウントで Microsoft リワード ポイントを獲得できますか?

Microsoft Search では、エンタープライズ ユーザーが職場または学校のアカウントでサインインする必要があります。 ただし、ユーザーはこれらのアカウントで Microsoft リワード プログラムに参加またはサインインすることはできません。 しかし、エンタープライズ ユーザーにリワード ポイントが発生する場合があります。 これは、Microsoft Search ユーザーが [Microsoft アカウント](https://www.microsoft.com/welcome?rtc=1)で作成されたリワード アカウントを持っている場合に発生する可能性があります。 (Microsoft アカウントに関連付けられている電子メール アドレスに、Outlook.com、Hotmail.com、Gmail、Yahoo、またはその他のプロバイダーからのものが使用できます。) ユーザーが同じブラウザー セッションで仕事用アカウントと Microsoft アカウントの両方で交互にサインインする場合、リワード アカウントにポイントが加算される場合があります。 ユーザーは、Cookie をクリアすることにより、Microsoft Search での検索中にポイントの発生を停止できます。

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>ゲスト ユーザーは組織で Microsoft Search を活用できますか?

Microsoft 365 を使用すると、ゲスト アクセスを通じて組織外のユーザーとの豊富な [コラボレーションが可能になります。](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) これらのユーザーは、ドキュメント、サイト、グループ、リスト、およびライブラリに対して検索操作を実行できます。 ただし、ゲスト ユーザーは完全な Microsoft Search エクスペリエンスを取得し、ヘッダーの統合された Microsoft Search ボックスではなく、ページ上の検索ボックスを活用する必要がある場合があります。