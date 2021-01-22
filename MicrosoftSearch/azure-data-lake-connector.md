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
# <a name="azure-data-lake-storage-gen2-connector"></a><span data-ttu-id="9d31c-103">Azure Data Lake Storage Gen2 コネクタ</span><span class="sxs-lookup"><span data-stu-id="9d31c-103">Azure Data Lake Storage Gen2 connector</span></span>

<span data-ttu-id="9d31c-104">Azure Data Lake Storage Gen2 コネクタを使用すると、組織内のユーザーは [、Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) および [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントに格納されているファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-104">With the Azure Data Lake Storage Gen2 connector, users in your organization can search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

<span data-ttu-id="9d31c-105">この記事は [、Microsoft 365](https://www.microsoft.com/microsoft-365) 管理者または Azure Data Lake Storage Gen2 コネクタを構成、実行、および監視するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="9d31c-105">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="9d31c-106">コネクタの構成、機能、制限事項、およびトラブルシューティングの手法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="9d31c-106">It gives an overview of the connector configuration, capabilities, limitations, and troubleshooting techniques.</span></span> <span data-ttu-id="9d31c-107">この記事では *、Azure Blob Storage* と [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) Data Lake Gen 2 Storage の一般的な用語として Azure [Storage を使用します](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)。</span><span class="sxs-lookup"><span data-stu-id="9d31c-107">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="9d31c-108">データ ソースに接続する</span><span class="sxs-lookup"><span data-stu-id="9d31c-108">Connect to a data source</span></span>

### <a name="primary-storage-connection-string"></a><span data-ttu-id="9d31c-109">プライマリ ストレージ接続文字列</span><span class="sxs-lookup"><span data-stu-id="9d31c-109">Primary storage connection string</span></span>

<span data-ttu-id="9d31c-110">[認証 **と構成] 画面で** 、プライマリ ストレージ接続文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="9d31c-110">On the **Authentication and config** screen, provide the Primary Storage Connection String.</span></span> <span data-ttu-id="9d31c-111">ストレージ アカウントへのアクセスを許可するには、この文字列が必要です。</span><span class="sxs-lookup"><span data-stu-id="9d31c-111">That string is required to allow access to your storage account.</span></span> <span data-ttu-id="9d31c-112">接続文字列を見つけるには [、Azure ポータル](https://ms.portal.azure.com/#home) に移動し、関連する Azure Storage アカウントの **[キー** ] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d31c-112">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span> <span data-ttu-id="9d31c-113">画面の適切なフィールドに接続文字列をコピーして貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-113">Copy and paste the connection string in the appropriate field on the screen.</span></span>

<span data-ttu-id="9d31c-114">**AccountKey** (プライマリ ストレージ接続文字列のパラメーター) を指定しない場合は、次の役割について Graph Connectors Service へのアクセスを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d31c-114">If you do not prefer to provide the **AccountKey** (a parameter in the primary storage connection string), you will need to grant access to our Graph Connectors Service for the following roles.</span></span> <span data-ttu-id="9d31c-115">(この機能は、階層ストレージでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-115">(This feature is only supported for hierarchical storage.</span></span> <span data-ttu-id="9d31c-116">従来の Blob ストレージでは、AccountKey を提供する必要があります)。</span><span class="sxs-lookup"><span data-stu-id="9d31c-116">Traditional Blob storage will have to provide AccountKey.)</span></span>
* <span data-ttu-id="9d31c-117">ストレージ BLOB データ リーダー</span><span class="sxs-lookup"><span data-stu-id="9d31c-117">Storage Blob Data Reader</span></span>
* <span data-ttu-id="9d31c-118">記憶域キュー データ共同作成者</span><span class="sxs-lookup"><span data-stu-id="9d31c-118">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="9d31c-119">ストレージ BLOB Delegator</span><span class="sxs-lookup"><span data-stu-id="9d31c-119">Storage Blob Delegator</span></span>

<span data-ttu-id="9d31c-120">Azure Storage アカウント **の [アクセス** 制御] タブに移動し、次の手順に従って、次のアプリへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="9d31c-120">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="9d31c-121">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="9d31c-121">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="9d31c-122">**ファースト パーティのアプリ名:** Graph Connector サービス</span><span class="sxs-lookup"><span data-stu-id="9d31c-122">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="9d31c-123">ストレージ アカウントとキューの通知 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="9d31c-123">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="9d31c-124">Graph Connectors Service でのリアルタイムでの変更処理のサポートは、今後追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d31c-124">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="9d31c-125">その場合は、キューに格納されている Azure Storage の変更通知を監視します。</span><span class="sxs-lookup"><span data-stu-id="9d31c-125">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="9d31c-126">Azure Storage アカウントと同じアカウントにキューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d31c-126">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="9d31c-127">キューを作成した後、キュー ページの [ **イベント** ] タブに移動して、イベント サブスクリプション **を構成します**。</span><span class="sxs-lookup"><span data-stu-id="9d31c-127">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="9d31c-128">キューが受信する BLOB イベントを選択し、キューを Azure Storage アカウントに接続します。</span><span class="sxs-lookup"><span data-stu-id="9d31c-128">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="9d31c-129">検索のアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="9d31c-129">Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="9d31c-130">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="9d31c-130">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="9d31c-131">[検索アクセス **許可** の管理] 画面で [、Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントからアクセス制御リスト (ACL) を取り込む方法を選択できます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-131">On the **Manage search permissions** screen, you can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="9d31c-132">これらの検索アクセス許可が設定されている場合、コンテンツを検索するサインイン済み [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) ユーザーに割り当てられているアクセス許可に基づいて、検索コンテンツがトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-132">When these search permissions are set, search content is trimmed based on the permissions assigned to the signed-in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) user searching the content.</span></span> <span data-ttu-id="9d31c-133">または、ストレージ アカウントからインデックスが作成されたコンテンツを組織内のすべてのユーザーに表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-133">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="9d31c-134">この場合、組織内のすべてのユーザーがストレージ アカウント内のすべてのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-134">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="9d31c-135">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="9d31c-135">Azure Blob Storage</span></span>

<span data-ttu-id="9d31c-136">Azure Blob [Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)への接続の場合、構成済みのソースからインデックスが作成されたコンテンツはすべて、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-136">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="9d31c-137">アクセス制御リストは、Azure Blob Storage の Blob レベルではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9d31c-137">Access control lists are not supported at Blob level in Azure Blob Storage.</span></span>

## <a name="search-permissions"></a><span data-ttu-id="9d31c-138">検索アクセス許可</span><span class="sxs-lookup"><span data-stu-id="9d31c-138">Search permissions</span></span>

<span data-ttu-id="9d31c-139">Azure Data Lake Storage Gen2 コネクタは、[すべてのユーザー] または [このデータ ソースにアクセスできるユーザーのみ] に表示される検索 **アクセス許可をサポートします**。</span><span class="sxs-lookup"><span data-stu-id="9d31c-139">The Azure Data Lake Storage Gen2 connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="9d31c-140">検索結果に表示されるインデックス付きデータは、組織内のすべてのユーザーに表示される場合と、各アイテムにアクセスできるユーザーにのみ表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d31c-140">Indexed data that appears in the search results could be visible to all users in the organization or only to users who have access to each item.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="9d31c-141">プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="9d31c-141">Assign property labels</span></span>

<span data-ttu-id="9d31c-142">オプションのメニューから選択すると、ソース プロパティを各ラベルに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-142">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="9d31c-143">この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="9d31c-143">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="9d31c-144">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="9d31c-144">Manage schema</span></span>

<span data-ttu-id="9d31c-145">[スキーマの管理] 画面で、プロパティに関連付けられたスキーマ属性 **(クエリ** 可能、検索可能、取得可能、絞り込み **可能)** を変更し、オプションのエイリアスを追加して **、Content** プロパティを選択できます。 </span><span class="sxs-lookup"><span data-stu-id="9d31c-145">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="9d31c-146">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="9d31c-146">Set the refresh schedule</span></span>

<span data-ttu-id="9d31c-147">[設定 **の更新] 画面** では、増分クロールの間隔とフル クロールの間隔を設定できます。</span><span class="sxs-lookup"><span data-stu-id="9d31c-147">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="9d31c-148">Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールの場合は 15 分、フル クロールの場合は 1 週間です。</span><span class="sxs-lookup"><span data-stu-id="9d31c-148">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="9d31c-149">制限事項</span><span class="sxs-lookup"><span data-stu-id="9d31c-149">Limitations</span></span>

<span data-ttu-id="9d31c-150">Azure Blob Storage の公開された接続は、Azure Data Lake Storage Gen2 ソースに対して再構成することはできません。その逆もできません。</span><span class="sxs-lookup"><span data-stu-id="9d31c-150">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and vice-versa.</span></span> <span data-ttu-id="9d31c-151">このようなシナリオでは、新しい接続を構成する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9d31c-151">In such scenarios, it is recommended to configure a new connection.</span></span>
