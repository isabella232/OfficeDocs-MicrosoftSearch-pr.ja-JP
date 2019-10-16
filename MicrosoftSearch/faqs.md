---
title: FAQ
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 10/19/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: エンタープライズ検索と Microsoft Search についてよく寄せられる質問に対する回答です
ms.openlocfilehash: d3cf7e4a6f252711f94e90a4e6561c8f25769c27
ms.sourcegitcommit: 5204b3c85e2fc190a8807d5268fb87145624a969
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/14/2019
ms.locfileid: "37502931"
---
# <a name="frequently-asked-questions"></a>よく寄せられる質問

以下は、よく寄せられる質問の一覧です。

> [!TIP]
> ここで質問に対する回答が得られなかった場合は、 この記事のフィードバックを使用してご質問ください。

## <a name="is-advanced-query-understanding-supported"></a>高度なクエリ理解はサポートされていますか?

はい。Microsoft Search は、長いフレーズからクエリの意図を解析します。この機能は、AI を使ってユーザーがよく使う検索の意図に影響しない余分なフレーズの一般的なものを学習します。たとえば、ユーザーが「パスワードの変更方法について詳しく教えてください」と検索した場合、クエリから重要度の低いワードを抽出し、「パスワード変更」などの関連のあるワードに基づいてトリガーします。
  
この機能により、管理センターで設定されたキーワードが無効になることはありません。
  
## <a name="can-you-search-for-files-on-premises"></a>オンプレミスのファイルを検索できますか?

はい。 SharePoint のハイブリッド展開を使用している場合は、SharePoint のオンプレミスのファイルを検索することができます。
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>自分の組織のユーザーに対して Bing を既定の検索エンジンとして設定する方法を教えてください。

既定の検索エンジン、既定のホームページ、既定のブラウザーを設定する手順は以下でご覧いただけます。Microsoft Search in Bing では最適な操作性がユーザーに提供されています。

- [Microsoft Edge を既定のブラウザーとして設定する](set-default-browser.md)
- [Bing を既定の検索エンジンとして設定する](set-default-search-engine.md)
- [Bing.com をエンタープライズ ホームページとして設定する](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a>検索結果に対する保護について教えてください。

信頼できるクラウドから結果にアクセスするには、Azure Active Directory (AAD) 認証が必要です。 認証されたユーザーには、そのユーザーがアクセス権を持つコンテンツのみが表示されます。 検索クエリは匿名化され、ログは公開された Bing 検索トラフィックから分離されます。 このレベルの保護が提供されているのは、業界内でも Microsoft Search だけです。

## <a name="can-i-search-across-federated-organizations"></a>フェデレーション組織間を検索できますか?

いいえ。

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a>Office 365 および Microsoft 365 のコンプライアンス階層とカテゴリに関する情報はどこで入手できますか?

「[業界標準と規制に関するコンプライアンス フレームワーク](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf)」(PDF ダウンロード) で詳細を入手できます。

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>ユーザーは職場または学校のアカウントで Microsoft リワード ポイントを獲得できますか?

Microsoft Search では、エンタープライズ ユーザーが職場または学校のアカウントでサインインする必要があります。 ただし、ユーザーはこれらのアカウントで Microsoft リワード プログラムに参加またはサインインすることはできません。 しかし、エンタープライズ ユーザーにリワード ポイントが発生する場合があります。 これは、Microsoft Search ユーザーが <a href="https://www.microsoft.com/en-us/welcome?rtc=1">Microsoft アカウント</a>で作成されたリワード アカウントを持っている場合に発生する可能性があります。 (Microsoft アカウントに関連付けられている電子メール アドレスに、Outlook.com、Hotmail.com、Gmail、Yahoo、またはその他のプロバイダーからのものが使用できます。) ユーザーが同じブラウザー セッションで仕事用アカウントと Microsoft アカウントの両方で交互にサインインする場合、リワード アカウントにポイントが加算される場合があります。 ユーザーは、Cookie をクリアすることにより、Microsoft Search での検索中にポイントの発生を停止できます。 

