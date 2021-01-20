---
title: Microsoft Search 用 MediaWiki コネクタ
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用に MediaWiki コネクタをセットアップする
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905956"
---
# <a name="mediawiki-connector"></a>MediaWiki コネクタ

MediaWiki コネクタを使用すると、組織は MediaWiki ソフトウェアを使用して作成された Wiki からデータを検出し、インデックスを作成できます。 このコネクタは、指定されたコンテンツのインデックスを Microsoft Search に作成し、インデックスを最新の状態に保つ定期的なクロールをサポートします。

この記事は、Microsoft 365 管理者または MediaWiki Graph コネクタを構成、実行、および監視するユーザーを対象にしています。 これは、Graph コネクタのセットアップに関する記事に記載されている一 [般的な手順を補完](configure-connector.md) します。 まだ設定していない場合は、「Graph コネクタのセットアップ」の記事全体を読んで、一般的なセットアップ プロセスについて理解してください。

以下に、セットアップ プロセスの各手順と共に、一般的なセットアップ手順に従う必要があるというメモ、または MediaWiki Graph コネクタにのみ適用されるその他の手順を示します。 この記事には、MediaWiki Graph コネクタの制限事項に関する情報も含まれています。 [](#limitations) 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加します。
一般的なセットアップ手順に従います。

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付けています。
一般的なセットアップ手順に従います。
 
## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成します。
Wiki **URL を入力し** 、 **オプションのドロップダウン** メニューから [認証の種類] を選択します。 オプションは **None、Basic、OAuth** **2.0 AAD です**。

認証の種類として **[基本** ] を選択した場合は、Wiki の **ユーザー** 名と **パスワードを入力** する必要があります。

認証の種類として **OAuth 2.0 AAD** を選択した場合は、Wiki インストールの **リソース ID** を指定する必要があります。 また、AAD アプリケーション登録 **ページで生成** されたクライアント **ID** とクライアント シークレットも指定する必要があります。 

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する
MediaWiki コネクタは、すべてのユーザーに表示される検索アクセス許可のみをサポート **します**。 インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる
一般的なセットアップ手順に従います。

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する
一般的なセットアップ手順に従います。

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する
一般的なセットアップ手順に従います。

## <a name="step-8-review-connection"></a>手順 8: 接続を確認する
一般的なセットアップ手順に従います。

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>制限事項
MediaWiki コネクタには、プレビュー リリースで次の制限があります。

* クラウドベースの Wiki のみをサポートします。
* Azure Active Directory または Azure 認証を使用する基本認証または OAuth 2.0 のみをサポートします。
* インデックス作成用の名前空間の選択はサポートされていません。 Main 名前空間、Category 名前空間、および File 名前空間のみをインデックス化します。
* アクセス制御リスト (ACL) はサポートされていません。 したがって、インデックス付きページは組織内のすべてのユーザーに表示されます。
