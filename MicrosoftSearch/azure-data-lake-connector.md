---
title: Microsoft Search 用 Azure Data Lake Graph コネクタ
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
description: Microsoft Search 用に Azure Data Lake Storage Gen2 Graph コネクタをセットアップする
ms.openlocfilehash: da508694929d3c83a456c664aa4613b09a1b14a3
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084859"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Azure Data Lake Storage Gen2 Graph コネクタ

Azure Data Lake Storage Gen2 Graph コネクタを使用すると、組織内のユーザーは [、Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) および [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントに格納されているファイルを検索できます。

> [!NOTE]
> Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、一般的な Graph コネクタのセットアップ プロセスについて理解してください。

この記事は、Azure Data Lake Storage Gen2 コネクタを構成、実行、および監視するユーザーを対象にしています。 一般的なセットアップ プロセスを補完し、Azure Data Lake Storage Gen2 コネクタにのみ適用される手順を示します。 この記事には、制限事項に関する [情報も含まれています](#limitations)。

この記事では *、Azure Blob Storage* と [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) Data Lake Gen 2 Storage の一般的な用語として Azure [Storage を使用します](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

プライマリ ストレージ接続文字列を入力します。 この文字列は、ストレージ アカウントへのアクセスを許可するために必要です。 接続文字列を見つけるには [、Azure ポータル](https://ms.portal.azure.com/#home) に移動し、関連する Azure Storage アカウントの **[キー** ] セクションに移動します。

**AccountKey** (プライマリ ストレージ接続文字列のパラメーター) を指定しない場合は、Graph Connectors Service へのアクセス権を次の役割に付与します。

* ストレージ BLOB データ リーダー
* 記憶域キュー データ共同作成者
* ストレージ BLOB Delegator

Azure Storage アカウント **の [アクセス** 制御] タブに移動し、次の手順に従って、次のアプリへのアクセスを許可します。

* **First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **ファースト パーティのアプリ名:** Graph Connector サービス

### <a name="storage-account-and-queue-notifications-optional"></a>ストレージ アカウントとキューの通知 (省略可能)

Graph Connectors Service でのリアルタイムでの変更処理のサポートは、今後追加される可能性があります。 その場合は、キューに格納されている Azure Storage の変更通知を監視します。 Azure Storage アカウントと同じアカウントにキューを作成する必要があります。

キューを作成した後、キュー ページの [ **イベント** ] タブに移動して、イベント サブスクリプション **を構成します**。 キューが受信する BLOB イベントを選択し、キューを Azure Storage アカウントに接続します。

## <a name="step-4-assign-property-labels"></a>手順 4: プロパティ ラベルを割り当てる

オプションのメニューから選択すると、ソース プロパティを各ラベルに割り当てできます。 この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果が向上します。

## <a name="step-5-manage-schema"></a>手順 5: スキーマを管理する

[スキーマ **の管理]** 画面では、プロパティに関連付けられているスキーマ属性を変更できます。オプションは **、クエリ**、 **検索**、 **取得**、および絞り込 **みです**。 オプションのエイリアスを追加し、Content プロパティを **選択** できます。

## <a name="step-6-manage-search-permissions"></a>手順 6: 検索権限を管理する

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Azure Data Lake Gen 2 Storage アカウントからアクセス制御リスト [(ACL) を取り込む方法を選択](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) できます。 これらの検索アクセス許可を設定すると、Azure Active Directory にサインインしているユーザーのアクセス許可に基づいて検索コンテンツ [がトリミングされます](https://docs.microsoft.com/azure/active-directory/)。 または、ストレージ アカウントからインデックスが作成されたコンテンツを組織内のすべてのユーザーに表示することもできます。 この場合、組織内のすべてのユーザーがストレージ アカウント内のすべてのデータにアクセスできます。

Azure Data Lake Storage Gen2 Graph コネクタは、[すべてのユーザー] または [このデータ ソースにアクセスできるユーザーのみ] に表示される検索アクセス **許可をサポートします**。 検索結果に表示されるインデックス付きデータは、各アイテムにアクセスできる組織内のユーザーに表示される可能性があります。

### <a name="azure-blob-storage"></a>Azure Blob Storage

Azure Blob [Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)への接続の場合、構成済みのソースからインデックスが作成されたコンテンツはすべて、組織内のすべてのユーザーに表示されます。 アクセス制御リストは、Azure Blob Storage の Blob レベルではサポートされていません。

## <a name="step-7-set-the-refresh-schedule"></a>手順 7: 更新スケジュールを設定する

[設定 **の更新] 画面** では、増分クロールの間隔とフル クロールの間隔を設定できます。 Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールの場合は 15 分、フル クロールの場合は 1 週間です。

## <a name="step-8-review-connection"></a>手順 8: 接続を確認する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>制限事項

Azure Blob Storage の公開接続は、Azure Data Lake Storage Gen2 ソースとそれ以外の方法では再構成できません。 このようなシナリオでは、新しい接続を構成する方法をお勧めします。

また、ファイルをクロールするには、ファイルのサイズを 4 MB 以下に設定する必要があります。 現在サポートされているファイルの種類は次のとおりです。

* Word (docx、.docm、.dotx、.dotm)
* PowerPoint (.pptm、.pptx、.potm、.potx、.ppam、.ppsm、.ppsx)
* Excel (.xlsx, .xlsm)
* 従来Office形式 (.doc、.dot など)
* テキスト (.txt)
* HTML
* PDF

画像 (.jpg、.bmp など) などのバイナリ ファイルはサポートされていません。 たとえば、.docx ファイルに画像だけが含まれている場合、コンテンツが返さなかったためスキップされる可能性があります。
