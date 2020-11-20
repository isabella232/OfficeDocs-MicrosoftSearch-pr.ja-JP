---
title: Microsoft Search 用の MediaWiki コネクタ
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
description: Microsoft Search 用の MediaWiki コネクタをセットアップする
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367642"
---
# <a name="mediawiki-connector"></a>MediaWiki コネクタ

MediaWiki コネクタを使用すると、MediaWiki ソフトウェアを使用して作成された wiki から、組織がデータを検出してインデックスを作成できます。 このコネクタは、指定されたコンテンツを Microsoft Search にインデックス処理し、定期的なクロールをサポートしてインデックスを最新の状態に保ちます。

この記事は、Microsoft 365 管理者または、MediaWiki コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

## <a name="connect-to-a-data-source"></a>データソースへの接続

接続を認証するために、MediaWiki の URL と資格情報を入力します。 **テナント ID**、**リソース ID**、**クライアント ID**、**クライアントシークレット** の情報が必要です。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する

MediaWiki コネクタは、 **すべてのユーザー** に表示される検索アクセス許可のみをサポートします。 インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="assign-property-labels"></a>プロパティのラベルを割り当てる

各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。 この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。

## <a name="manage-schema"></a>スキーマを管理する

[**スキーマの管理**] 画面で、プロパティに関連付けられているスキーマの属性 (**クエリ** 可能、**検索****可能、取得可能、および****絞り込み可能な**) を変更し、オプションのエイリアスを追加して、 **Content** プロパティを選択することができます。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する

このスケジュールによってインデックスが作成されたデータが更新されるので、wiki への変更は Microsoft Search に反映されます。 新しいページ、削除されたページ、ページコンテンツ、またはメタデータの変更は、指定した更新間隔の後に検索結果に表示されます。 クロール時間は wiki のサイズによって異なります。 現在、コネクタは1分間に50ページ以内にクロールされます。

## <a name="limitations"></a>制限事項

MediaWiki コネクタには、次のようなプレビューリリースの制限があります。

* クラウドベースの wiki のみをサポートします。
* Azure Active Directory または Azure 認証で基本または OAuth 2.0 のみをサポートします。
* インデックス作成のための名前空間の選択をサポートしていません。 インデックスは、 **メイン**、 **カテゴリ**、および **ファイル** の名前空間のみになります。
* は、アクセス制御リスト (Acl) をサポートしていません。 そのため、インデックスが作成されたページは、組織内のすべてのユーザーが参照できます。
