---
title: Microsoft Search 用の MediaWiki コネクタ
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の MediaWiki コネクタをセットアップする
ms.openlocfilehash: 281d270a47051e20cb1cfd44540bd51371557c13
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949951"
---
# <a name="mediawiki-connector"></a>MediaWiki コネクタ

MediaWiki コネクタを使用すると、MediaWiki ソフトウェアを使用して作成された wiki から、組織がデータを検出してインデックスを作成できます。 このコネクタは、指定されたコンテンツを Microsoft Search にインデックス処理し、定期的なクロールをサポートしてインデックスを最新の状態に保ちます。

この記事は、Microsoft 365 管理者または、MediaWiki コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

## <a name="connect-to-a-data-source"></a>データソースへの接続
接続を認証するために、MediaWiki の URL と資格情報を入力します。 **テナント ID**、**リソース ID**、**クライアント ID**、**クライアントシークレット**の情報が必要です。

## <a name="manage-the-search-schema"></a>検索スキーマを管理する
接続が成功した後、検索スキーママッピングを構成します。 **クエリ**可能、**検索**可能、および取得可能なプロパティを選択でき**ます。**

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する
MediaWiki コネクタは、**すべてのユーザー**に表示される検索アクセス許可のみをサポートします。 インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する 
このスケジュールによってインデックスが作成されたデータが更新されるので、wiki への変更は Microsoft Search に反映されます。 新しいページ、削除されたページ、ページコンテンツ、またはメタデータの変更は、指定した更新間隔の後に検索結果に表示されます。 クロール時間は wiki のサイズによって異なります。 現在、コネクタは1分間に50ページ以内にクロールされます。

## <a name="limitations"></a>制限事項 
MediaWiki コネクタには、次のようなプレビューリリースの制限があります。
* クラウドベースの wiki のみをサポートします。
* Azure Active Directory または Azure 認証で基本または OAuth 2.0 のみをサポートします。
* インデックス作成のための名前空間の選択をサポートしていません。 インデックスは、**メイン**、**カテゴリ**、および**ファイル**の名前空間のみになります。
* は、アクセス制御リスト (Acl) をサポートしていません。 そのため、インデックスが作成されたページは、組織内のすべてのユーザーが参照できます。
