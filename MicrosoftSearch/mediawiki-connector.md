---
title: MediaWiki GraphコネクタMicrosoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: ユーザーの MediaWiki GraphコネクタをMicrosoft Search
ms.openlocfilehash: 7e1c308eb1785dd7fec23fac7e9002957a0d50ca
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59376320"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>MediaWiki Graph コネクタ

MediaWiki Graphコネクタを使用すると、組織は MediaWiki ソフトウェアを使用して作成された Wiki からデータを検出してインデックスを作成できます。 このコネクタは、指定されたコンテンツMicrosoft Searchインデックスを作成し、インデックスを最新の状態に保つために定期的なクロールをサポートします。

> [!NOTE]
> 一般的な [**コネクタのセットアップGraph**](configure-connector.md) Graphについては、「Graphコネクタのセットアップ」をご覧ください。

この記事は、MediaWiki コネクタを構成、実行、および監視するGraphです。 一般的なセットアップ プロセスを補足し、MediaWiki コネクタにのみ適用される手順をGraphします。 この記事には、制限に関する [情報も含まれています](#limitations)。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Graphコネクタを追加Microsoft 365 管理センター

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

Wiki **URL を入力し** 、 **オプションのドロップダウン** メニューから [認証の種類] を選択します。 オプションは **None、Basic、OAuth** **2.0 AAD です**。

認証の種類として **[基本** ] を選択した場合は、Wiki の **ユーザー** 名と **パスワードを指定する** 必要があります。

認証の種類 **として [OAuth 2.0 AAD]** を選択した場合は、Wiki インストールの **リソース ID** を指定する必要があります。 また、[AAD アプリケーションの登録] ページで **生成されたクライアント** **ID** とクライアント シークレットを指定する必要があります。

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する

MediaWiki コネクタは、すべてのユーザーに表示される検索アクセス許可のみを **サポートします**。 インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>制限事項

MediaWiki コネクタには、プレビュー リリースで次の制限があります。

* クラウドベースの Wiki のみをサポートします。
* 基本認証または OAuth 2.0 のみをサポートし、Azure Active Directoryまたは Azure 認証をサポートします。
* インデックス作成の名前空間の選択はサポートされていません。 Main、Category、および File 名前空間のみをインデックス化します。
* アクセス制御リスト (ACL) はサポートされていません。 したがって、インデックス付きページは組織内のすべてのユーザーに表示されます。