---
title: Microsoft Search 用 Azure Data Lake コネクタ
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用に Azure Data Lake Storage Gen2 コネクタをセットアップする
ms.openlocfilehash: 8891c9a1fdf5397c397a941b5131f014db9e7a54
ms.sourcegitcommit: 597c338bf9c1c425747ac74a9a1ae57c5e8957ce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "49920724"
---
# <a name="azure-data-lake-storage-gen2-connector"></a>Azure Data Lake Storage Gen2 コネクタ

Azure Data Lake Storage Gen2 コネクタを使用すると、組織内のユーザーは [、Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) および [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントに格納されているファイルを検索できます。

この記事は [、Microsoft 365](https://www.microsoft.com/microsoft-365) 管理者または Azure Data Lake Storage Gen2 コネクタを構成、実行、および監視するユーザーを対象にしています。 コネクタの構成、機能、制限事項、およびトラブルシューティングの手法の概要を示します。 この記事では *、Azure Blob Storage* と [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) Data Lake Gen 2 Storage の一般的な用語として Azure [Storage を使用します](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)。

## <a name="connect-to-a-data-source"></a>データ ソースに接続する

### <a name="primary-storage-connection-string"></a>プライマリ ストレージ接続文字列

[認証 **と構成] 画面で** 、プライマリ ストレージ接続文字列を指定します。 ストレージ アカウントへのアクセスを許可するには、この文字列が必要です。 接続文字列を見つけるには [、Azure ポータル](https://ms.portal.azure.com/#home) に移動し、関連する Azure Storage アカウントの **[キー** ] セクションに移動します。 画面の適切なフィールドに接続文字列をコピーして貼り付けます。

**AccountKey** (プライマリ ストレージ接続文字列のパラメーター) を指定しない場合は、次の役割について Graph Connectors Service へのアクセスを許可する必要があります。 (この機能は、階層ストレージでのみサポートされます。 従来の Blob ストレージでは、AccountKey を提供する必要があります)。
* ストレージ BLOB データ リーダー
* 記憶域キュー データ共同作成者
* ストレージ BLOB Delegator

Azure Storage アカウント **の [アクセス** 制御] タブに移動し、次の手順に従って、次のアプリへのアクセスを許可します。

* **First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **ファースト パーティのアプリ名:** Graph Connector サービス

### <a name="storage-account-and-queue-notifications-optional"></a>ストレージ アカウントとキューの通知 (省略可能)

Graph Connectors Service でのリアルタイムでの変更処理のサポートは、今後追加される可能性があります。 その場合は、キューに格納されている Azure Storage の変更通知を監視します。 Azure Storage アカウントと同じアカウントにキューを作成する必要があります。

キューを作成した後、キュー ページの [ **イベント** ] タブに移動して、イベント サブスクリプション **を構成します**。 キューが受信する BLOB イベントを選択し、キューを Azure Storage アカウントに接続します。

## <a name="manage-search-permissions"></a>検索のアクセス許可を管理する

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

[検索アクセス **許可** の管理] 画面で [、Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントからアクセス制御リスト (ACL) を取り込む方法を選択できます。 これらの検索アクセス許可が設定されている場合、コンテンツを検索するサインイン済み [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) ユーザーに割り当てられているアクセス許可に基づいて、検索コンテンツがトリミングされます。 または、ストレージ アカウントからインデックスが作成されたコンテンツを組織内のすべてのユーザーに表示することもできます。 この場合、組織内のすべてのユーザーがストレージ アカウント内のすべてのデータにアクセスできます。

### <a name="azure-blob-storage"></a>Azure Blob Storage

Azure Blob [Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)への接続の場合、構成済みのソースからインデックスが作成されたコンテンツはすべて、組織内のすべてのユーザーに表示されます。 アクセス制御リストは、Azure Blob Storage の Blob レベルではサポートされていません。

## <a name="search-permissions"></a>検索アクセス許可

Azure Data Lake Storage Gen2 コネクタは、[すべてのユーザー] または [このデータ ソースにアクセスできるユーザーのみ] に表示される検索 **アクセス許可をサポートします**。 検索結果に表示されるインデックス付きデータは、組織内のすべてのユーザーに表示される場合と、各アイテムにアクセスできるユーザーにのみ表示される場合があります。

## <a name="assign-property-labels"></a>プロパティ ラベルを割り当てる

オプションのメニューから選択すると、ソース プロパティを各ラベルに割り当てできます。 この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果の精度が向上します。

## <a name="manage-schema"></a>スキーマを管理する

[スキーマの管理] 画面で、プロパティに関連付けられたスキーマ属性 **(クエリ** 可能、検索可能、取得可能、絞り込み **可能)** を変更し、オプションのエイリアスを追加して **、Content** プロパティを選択できます。 

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する

[設定 **の更新] 画面** では、増分クロールの間隔とフル クロールの間隔を設定できます。 Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールの場合は 15 分、フル クロールの場合は 1 週間です。

## <a name="limitations"></a>制限事項

Azure Blob Storage の公開された接続は、Azure Data Lake Storage Gen2 ソースに対して再構成することはできません。その逆もできません。 このようなシナリオでは、新しい接続を構成する方法をお勧めします。
