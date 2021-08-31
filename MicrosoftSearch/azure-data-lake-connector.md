---
title: Azure Data Lake GraphコネクタMicrosoft Search
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
description: Azure Data Lake Storage Gen2 GraphをセットアップMicrosoft Search
ms.openlocfilehash: f60de4252e514f84bc92daf4ea65c535cf40a13d
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701401"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Azure Data Lake Storage Gen2 Graph コネクタ

Azure Data Lake Storage Gen2 Graph コネクタを使用すると、組織内のユーザーは Azure [Blob Storage](/azure/storage/blobs/storage-blobs-introduction)および[Azure Data Lake Gen 2](/azure/storage/blobs/data-lake-storage-introduction) Storage アカウントに格納されているファイルを検索できます。

> [!NOTE]
> コネクタの [**セットアップに関する**](configure-connector.md)Graph一般的なコネクタのセットアップGraph説明します。

この記事は、Gen2 コネクタを使用して Azure Data Lake を構成、実行、監視するStorageです。 一般的なセットアップ プロセスを補足し、Azure Data Lake および Gen2 コネクタにのみ適用される手順Storage示します。 この記事には、制限に関する [情報も含まれています](#limitations)。

この記事では[、Azure](/azure/storage/blobs/storage-blobs-introduction)  Blob Azure Storage および Azure Data Lake [Gen 2](/azure/storage/blobs/data-lake-storage-introduction)のStorage用語として使用Storage。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Graphコネクタを追加Microsoft 365 管理センター

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

プライマリ ストレージ接続文字列を入力します。 この文字列は、ストレージ アカウントへのアクセスを許可するために必要です。 接続文字列を見つけるには [、Azure portal](https://ms.portal.azure.com/#home)に移動し、関連するアカウントの **[** キー] セクションAzure Storageします。

**AccountKey** (プライマリ ストレージ接続文字列のパラメーター) を指定しない場合は、次の役割に対して Graph Connectors Service へのアクセス権を付与します。

* StorageBLOB データ リーダー
* Storageキュー データの共同作成者
* StorageBlob Delegator

Azure Storage アカウントの [アクセス制御] タブに移動し、手順に従って次のアプリへのアクセスを許可します。

* **ファースト パーティ アプリ ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **ファースト パーティ アプリ名:** Graph コネクタ サービス

### <a name="storage-account-and-queue-notifications-optional"></a>Storageとキュー通知 (オプション)

将来、Connectors Service Graph変更をリアルタイムで処理するサポートが追加される可能性があります。 その場合は、キューに格納Azure Storage変更通知を監視します。 自分のアカウントと同じアカウントにキューを作成Azure Storageがあります。

キューを作成した後、キュー ページの [ **イベント** ] タブに移動して、イベント サブスクリプション **を構成します**。 キューが受信する BLOB イベントをすべて選択し、キューを別のアカウントAzure Storageします。

## <a name="step-4-assign-property-labels"></a>手順 4: プロパティ ラベルを割り当てる

各ラベルにソース プロパティを割り当てるには、オプションのメニューから選択します。 この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果が向上します。

## <a name="step-5-manage-schema"></a>手順 5: スキーマの管理

[スキーマ **の管理] 画面** で、プロパティに関連付けられているスキーマ属性を変更できます。オプションは **クエリ**、 **検索**、 **取得**、絞り込 **みです**。 オプションのエイリアスを追加し、[コンテンツ] プロパティを **選択** できます。

## <a name="step-6-manage-search-permissions"></a>手順 6: 検索アクセス許可を管理する

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Azure [Data Lake Gen 2](/azure/storage/blobs/data-lake-storage-introduction)アカウントからアクセス制御リスト (ACL) を取り込Storageできます。 これらの検索アクセス許可が設定されている場合、検索コンテンツは、サインインしているユーザーのアクセス許可に基[づいてトリミング](/azure/active-directory/)Azure Active Directory。 または、ストレージ アカウントからインデックスが作成されたコンテンツを組織内のすべてのユーザーに表示することもできます。 この場合、組織内のすべてのユーザーがストレージ アカウント内のすべてのデータにアクセスできます。

Azure Data Lake Storage Gen2 Graphコネクタは、[すべてのユーザー] または[このデータ ソースにアクセスできるユーザーのみ] に表示される検索アクセス許可 **をサポートします**。 検索結果に表示されるインデックス付きデータは、各アイテムにアクセスできる組織内のユーザーに表示される可能性があります。

### <a name="azure-blob-storage"></a>Azure Blob Storage

[Azure Blob](/azure/storage/blobs/storage-blobs-introduction)クライアントへの接続Storage構成されたソースからインデックスが作成されたコンテンツはすべて、組織内のすべてのユーザーに表示されます。 アクセス制御リストは、Azure Blob の Blob レベルではサポートStorage。

## <a name="step-7-set-the-refresh-schedule"></a>手順 7: 更新スケジュールを設定する

[更新 **] 設定、** 増分クロール間隔とフル クロール間隔を設定できます。 Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールで 15 分、フル クロールで 1 週間です。

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>制限事項

Azure Data Lake および Gen2 ソースStorage、その他の方法で Azure Data Lake に対して公開Storage接続を再構成することはできません。 このようなシナリオでは、新しい接続を構成する方法をお勧めします。

また、クロールするファイルのサイズは 4 MB 以下である必要があります。 現在サポートされているファイルの種類は次のとおりです。

* Word (docx、.docm、.dotx、.dotm)
* PowerPoint (.pptm、.pptx、.potm、.potx、.ppam、.ppsm、.ppsx)
* Excel (.xlsx.xlsm)
* 従来Office形式 (.doc、.dot など)
* テキスト (.txt)
* HTML
* PDF

画像などのバイナリ ファイル (.jpg、.bmpなど) はサポートされていません。 たとえば、ファイルにイメージ.docx含まれている場合、コンテンツが返さなかったためスキップされる可能性があります。