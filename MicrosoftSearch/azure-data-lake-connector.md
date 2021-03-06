---
title: Microsoft Search 用 Azure Data Lake Graph コネクタ
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の Azure Data Lake Storage Gen2 Graph コネクタをセットアップする
ms.openlocfilehash: 2bb9570bc3b0a5adef7ac72ea1620c4f22a8aefb
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508888"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a>Azure Data Lake Storage Gen2 Graph コネクタ

Azure Data Lake Storage Gen2 Graph コネクタを使用すると、組織内のユーザーは [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) および Azure Data Lake Gen [2 ストレージ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントに格納されているファイルを検索できます。

> [!NOTE]
> グラフ コネクタ [**のセットアップの一**](configure-connector.md) 般的な手順については、「グラフ コネクタのセットアップ」をご覧ください。

この記事は、Azure Data Lake Storage Gen2 コネクタを構成、実行、および監視するユーザーを対象にしています。 これは、一般的なセットアップ プロセスを補足し、Azure Data Lake Storage Gen2 コネクタにのみ適用される手順を示します。 この記事には、制限に関する [情報も含まれています](#limitations)。

この記事では *、Azure Blob Storage* および [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) Data Lake Gen 2 Storage の総称として Azure [Storage を使用します](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターに Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

プライマリ ストレージ接続文字列を入力します。 この文字列は、ストレージ アカウントへのアクセスを許可するために必要です。 接続文字列を見つけるには [、Azure portal](https://ms.portal.azure.com/#home) に移動し、関連する Azure Storage アカウントの **[キー** ] セクションに移動します。

**AccountKey** (プライマリ ストレージ接続文字列のパラメーター) を指定しない場合は、次の役割に対して Graph Connectors Service へのアクセス権を付与します。

* 記憶域 BLOB データ リーダー
* 記憶域キュー データの共同作成者
* 記憶域 BLOB の Delegator

Azure Storage アカウント **の [アクセス制御** ] タブに移動し、指示に従って次のアプリへのアクセスを許可します。

* **ファースト パーティ アプリ ID:** 56c1da01-2129-48f7-9355-af6d59d42766
* **ファースト パーティ アプリ名:** Graph Connector Service

### <a name="storage-account-and-queue-notifications-optional"></a>ストレージ アカウントとキュー通知 (オプション)

Graph Connectors Service で変更をリアルタイムで処理するサポートは、将来追加される可能性があります。 その場合は、キューに格納されている Azure Storage の変更通知を監視します。 Azure Storage アカウントと同じアカウントにキューを作成する必要があります。

キューを作成した後、キュー ページの [ **イベント** ] タブに移動して、イベント サブスクリプション **を構成します**。 キューが受信する BLOB イベントをすべて選択し、キューを Azure Storage アカウントに接続します。

## <a name="step-4-assign-property-labels"></a>手順 4: プロパティ ラベルを割り当てる

各ラベルにソース プロパティを割り当てるには、オプションのメニューから選択します。 この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果が向上します。

## <a name="step-5-manage-schema"></a>手順 5: スキーマの管理

[スキーマ **の管理] 画面** で、プロパティに関連付けられているスキーマ属性を変更できます。オプションは **クエリ**、 **検索**、 **取得**、絞り込 **みです**。 オプションのエイリアスを追加し、[コンテンツ] プロパティを **選択** できます。

## <a name="step-6-manage-search-permissions"></a>手順 6: 検索アクセス許可を管理する

### <a name="azure-data-lake-gen-2"></a>Azure Data Lake Gen 2

Azure Data Lake Gen 2 ストレージ アカウントからアクセス制御リスト (ACL) を取り [込む方法を選択](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) できます。 これらの検索アクセス許可を設定すると、Azure Active Directory にサインインしているユーザーのアクセス許可に基づいて検索コンテンツ [がトリミングされます](https://docs.microsoft.com/azure/active-directory/)。 または、ストレージ アカウントからインデックスが作成されたコンテンツを組織内のすべてのユーザーに表示することもできます。 この場合、組織内のすべてのユーザーがストレージ アカウント内のすべてのデータにアクセスできます。

Azure Data Lake Storage Gen2 Graph コネクタは、[すべてのユーザー] または [このデータ ソースにアクセスできるユーザーのみ] に表示される検索 **アクセス許可をサポートしています**。 検索結果に表示されるインデックス付きデータは、各アイテムにアクセスできる組織内のユーザーに表示される可能性があります。

### <a name="azure-blob-storage"></a>Azure Blob Storage

Azure Blob [Storage への接続では](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)、構成済みのソースからインデックスが作成されたコンテンツはすべて、組織内のすべてのユーザーに表示されます。 アクセス制御リストは、Azure Blob Storage の BLOB レベルではサポートされていません。

## <a name="step-7-set-the-refresh-schedule"></a>手順 7: 更新スケジュールを設定する

[設定 **の更新] 画面** で、増分クロール間隔とフル クロール間隔を設定できます。 Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールで 15 分、フル クロールで 1 週間です。

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>制限事項

Azure Data Lake Storage Gen2 ソースとそれ以外の方法では、Azure Blob Storage の発行済み接続を再構成できません。 このようなシナリオでは、新しい接続を構成する方法をお勧めします。

また、クロールするファイルのサイズは 4 MB 以下である必要があります。 現在サポートされているファイルの種類は次のとおりです。

* Word (docx、.docm、.dotx、.dotm)
* PowerPoint (.pptm、.pptx、.potm、.potx、.ppam、.ppsm、.ppsx)
* Excel (.xlsx, .xlsm)
* 従来Office形式 (.doc、.dot など)
* テキスト (.txt)
* HTML
* PDF

イメージ (.jpg、.bmp など) などのバイナリ ファイルはサポートされていません。 たとえば、.docx ファイルにイメージだけが含まれている場合、コンテンツが返さなかったため、スキップされる可能性があります。
