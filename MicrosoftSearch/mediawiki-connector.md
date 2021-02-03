---
title: Microsoft Search 用 MediaWiki Graph コネクタ
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用に MediaWiki Graph コネクタをセットアップする
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084985"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a>MediaWiki Graph コネクタ

MediaWiki Graph コネクタを使用すると、組織は MediaWiki ソフトウェアを使用して作成された Wiki からデータを検出し、インデックスを作成できます。 このコネクタは、指定されたコンテンツのインデックスを Microsoft Search に作成し、インデックスを最新の状態に保つ定期的なクロールをサポートします。

> [!NOTE]
> Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、Graph コネクタの一般的なセットアップ プロセスを理解してください。

この記事は、ServiceNow Graph コネクタを構成、実行、および監視するユーザーを対象にしています。 一般的なセットアップ プロセスを補完し、MediaWiki Graph コネクタにのみ適用される手順を示します。 この記事には、制限事項に関する [情報も含まれています](#limitations)。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

Wiki **URL を入力し** 、 **オプションのドロップダウン** メニューから [認証の種類] を選択します。 オプションは **None、Basic、OAuth** **2.0 AAD です**。

認証の種類として **[基本** ] を選択した場合は、Wiki の **ユーザー** 名と **パスワードを入力** する必要があります。

認証の種類として **OAuth 2.0 AAD** を選択する場合は、Wiki インストールの **リソース ID** を指定する必要があります。 また、[AAD アプリケーションの登録]**ページで** 生成されたクライアント **ID** とクライアント シークレットも指定する必要があります。

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索権限を管理する

MediaWiki コネクタは、すべてのユーザーに表示される検索アクセス許可のみをサポート **します**。 インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>手順 8: 接続を確認する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a>制限事項

MediaWiki コネクタには、プレビュー リリースで次の制限があります。

* クラウドベースの Wiki のみをサポートします。
* Azure Active Directory または Azure 認証を使用する基本認証または OAuth 2.0 のみをサポートします。
* インデックス作成用の名前空間の選択はサポートされていません。 Main 名前空間、Category 名前空間、および File 名前空間のみをインデックス化します。
* アクセス制御リスト (ACL) をサポートしない。 したがって、インデックス付きページは組織内のすべてのユーザーに表示されます。
