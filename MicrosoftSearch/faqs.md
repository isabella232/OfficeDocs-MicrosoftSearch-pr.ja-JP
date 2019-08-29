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
ms.assetid: cd3ee09d-58ab-4b8a-8822-fa11a1399672
ROBOTS: NoIndex
description: エンタープライズ検索と Microsoft Search についてよく寄せられる質問に対する回答です
ms.openlocfilehash: 3b30980c76915405767381fb3b6397468bdd1b68
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639505"
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