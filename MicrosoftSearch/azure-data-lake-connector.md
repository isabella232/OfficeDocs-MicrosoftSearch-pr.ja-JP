---
title: Microsoft Search 用 Azure Data Lake connector
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の Azure Data Lake Storage Gen2 connector をセットアップする
ms.openlocfilehash: d6adabc6ea40b4385059f80375f49fb73e63e65b
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996096"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Azure Data Lake Storage Gen2 connector

Azure Data Lake Storage Gen2 コネクタを使用すると、組織内のユーザーは、 [Azure Blob ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)と[Azure Data lake Gen 2 のストレージ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)アカウントに格納されているファイルを検索できます。

この記事は、 [Microsoft 365](https://www.microsoft.com/microsoft-365)管理者または Azure Data Lake Storage Gen2 connector を構成、実行、および監視するユーザーを対象としています。 コネクタの構成、機能、制限事項、およびトラブルシューティングの手法の概要を示します。 この記事では、azure*ストレージ*を[azure Blob ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)と[Azure Data Lake Gen 2 ストレージ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)の一般的な用語として使用します。

## <a name="connect-to-a-data-source"></a>データソースへの接続
### <a name="primary-storage-connection-string"></a>プライマリストレージ接続文字列 
[**認証と構成**] 画面で、プライマリストレージ接続文字列を指定します。 この文字列は、ストレージアカウントへのアクセスを許可するために必要です。 接続文字列を検索するには、 [azure ポータル](https://ms.portal.azure.com/#home)に移動して、関連する azure Storage アカウントの [**キー** ] セクションに移動します。 接続文字列をコピーして画面の適切なフィールドに貼り付けます。

**AccountKey** (プライマリストレージ接続文字列のパラメーター) を指定しない場合は、Graph connector Service への読み取りアクセス権を与える必要があります。 Azure ストレージアカウントの [**アクセス制御**] タブに移動し、次のアプリへのアクセス権を付与するための手順に従います。
* **最初のパーティのアプリ ID:** 56c1da01-2127648f7-9355-af6d59d2766
* **ファーストパーティのアプリ名:** Graph Connector サービス

### <a name="storage-account-and-queue-notifications-optional"></a>ストレージアカウントとキューの通知 (オプション)
グラフコネクタサービスでリアルタイムでの変更の処理のサポートが今後追加される可能性があります。 その場合は、キューに格納されている Azure ストレージの変更通知を監視します。 Azure ストレージアカウントと同じアカウントでキューを作成する必要があります。

キューを作成した後、[キュー] ページの [**イベント**] タブに移動して、**イベントサブスクリプション**を構成します。 キューが受信するすべての Blob イベントを選択し、キューを Azure ストレージアカウントに接続します。

## <a name="manage-the-search-schema"></a>検索スキーマを管理する
[**スキーマの管理**] 画面には、管理プロパティに関連付けられているスキーマ属性 (**クエリ**可能、**検索**可能、および取得**可能) を**変更するオプションがあります。 これらの管理プロパティの属性は、Azure データストレージアカウントからインデックスが作成されたデータです。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する
### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2
[**検索権限の管理**] 画面では、 [Azure Data Lake Gen 2 ストレージ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)アカウントからアクセス制御リスト (acl) を取り込みます。 これらの検索権限が設定されている場合、コンテンツを検索するサインインしている[Azure Active Directory](https://docs.microsoft.com/azure/active-directory/)ユーザーに割り当てられているアクセス許可に基づいて、検索コンテンツがトリミングされます。 または、組織内のすべてのユーザーに対して、ストレージアカウントからインデックスが作成されたすべてのコンテンツを表示するように選択することもできます。 この場合、組織内のすべてのユーザーがストレージアカウントのすべてのデータにアクセスできます。

### <a name="azure-blob-storage"></a>Azure Blob Storage
[Azure Blob ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)への接続の場合、構成されたソースからインデックスが作成されたすべてのコンテンツが組織内のすべてのユーザーに表示されます。 アクセス制御リストは、Azure Blob ストレージの Blob レベルではサポートされていません。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する
[**更新の設定**] 画面で、増分クロールの間隔とフルクロールの間隔を設定できます。 Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールの場合は15分、フルクロールの場合は1週間です。

## <a name="limitations"></a>制限事項
Azure Data Lake Storage Gen2 source に対して、公開されている接続を再構成することはできません。また、その逆も同様です。 このようなシナリオでは、新しい接続を構成することをお勧めします。