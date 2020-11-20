---
title: Microsoft Search 用 Azure Data Lake connector
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
description: Microsoft Search 用の Azure Data Lake Storage Gen2 connector をセットアップする
ms.openlocfilehash: 860c923c62495c7df20152fb530797e390949305
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367588"
---
# <a name="azure-data-lake-storage-gen2-connector"></a><span data-ttu-id="66a3c-103">Azure Data Lake Storage Gen2 connector</span><span class="sxs-lookup"><span data-stu-id="66a3c-103">Azure Data Lake Storage Gen2 connector</span></span>

<span data-ttu-id="66a3c-104">Azure Data Lake Storage Gen2 コネクタを使用すると、組織内のユーザーは、 [Azure Blob ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) と [Azure Data lake Gen 2 のストレージ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントに格納されているファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-104">With the Azure Data Lake Storage Gen2 connector, users in your organization can search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

<span data-ttu-id="66a3c-105">この記事は、 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理者または Azure Data Lake Storage Gen2 connector を構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="66a3c-105">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="66a3c-106">コネクタの構成、機能、制限事項、およびトラブルシューティングの手法の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="66a3c-106">It gives an overview of the connector configuration, capabilities, limitations, and troubleshooting techniques.</span></span> <span data-ttu-id="66a3c-107">この記事では、azure *ストレージ* を [azure Blob ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) と [Azure Data Lake Gen 2 ストレージ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)の一般的な用語として使用します。</span><span class="sxs-lookup"><span data-stu-id="66a3c-107">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="66a3c-108">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="66a3c-108">Connect to a data source</span></span>

### <a name="primary-storage-connection-string"></a><span data-ttu-id="66a3c-109">プライマリストレージ接続文字列</span><span class="sxs-lookup"><span data-stu-id="66a3c-109">Primary storage connection string</span></span>

<span data-ttu-id="66a3c-110">[ **認証と構成** ] 画面で、プライマリストレージ接続文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="66a3c-110">On the **Authentication and config** screen, provide the Primary Storage Connection String.</span></span> <span data-ttu-id="66a3c-111">この文字列は、ストレージアカウントへのアクセスを許可するために必要です。</span><span class="sxs-lookup"><span data-stu-id="66a3c-111">That string is required to allow access to your storage account.</span></span> <span data-ttu-id="66a3c-112">接続文字列を検索するには、 [azure ポータル](https://ms.portal.azure.com/#home) に移動して、関連する azure Storage アカウントの [ **キー** ] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="66a3c-112">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span> <span data-ttu-id="66a3c-113">接続文字列をコピーして画面の適切なフィールドに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-113">Copy and paste the connection string in the appropriate field on the screen.</span></span>

<span data-ttu-id="66a3c-114">**AccountKey** (プライマリストレージ接続文字列のパラメーター) を指定しない場合は、次の役割の Graph connector Service へのアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66a3c-114">If you do not prefer to provide the **AccountKey** (a parameter in the primary storage connection string), you will need to grant access to our Graph Connectors Service for the following roles.</span></span>

* <span data-ttu-id="66a3c-115">記憶域 Blob データリーダー</span><span class="sxs-lookup"><span data-stu-id="66a3c-115">Storage Blob Data Reader</span></span>
* <span data-ttu-id="66a3c-116">ストレージキューデータ寄稿者</span><span class="sxs-lookup"><span data-stu-id="66a3c-116">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="66a3c-117">Storage Blob 委任者 (階層型ストレージの場合のみ)</span><span class="sxs-lookup"><span data-stu-id="66a3c-117">Storage Blob Delegator (only for hierarchical storage)</span></span>

<span data-ttu-id="66a3c-118">Azure ストレージアカウントの [ **アクセス制御** ] タブに移動し、次のアプリへのアクセス権を付与するための手順に従います。</span><span class="sxs-lookup"><span data-stu-id="66a3c-118">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="66a3c-119">**最初のパーティのアプリ ID:** 56c1da01-2127648f7-9355-af6d59d2766</span><span class="sxs-lookup"><span data-stu-id="66a3c-119">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="66a3c-120">**ファーストパーティのアプリ名:** Graph Connector サービス</span><span class="sxs-lookup"><span data-stu-id="66a3c-120">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="66a3c-121">ストレージアカウントとキューの通知 (オプション)</span><span class="sxs-lookup"><span data-stu-id="66a3c-121">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="66a3c-122">グラフコネクタサービスでリアルタイムでの変更の処理のサポートが今後追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66a3c-122">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="66a3c-123">その場合は、キューに格納されている Azure ストレージの変更通知を監視します。</span><span class="sxs-lookup"><span data-stu-id="66a3c-123">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="66a3c-124">Azure ストレージアカウントと同じアカウントでキューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66a3c-124">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="66a3c-125">キューを作成した後、[キュー] ページの [ **イベント** ] タブに移動して、 **イベントサブスクリプション** を構成します。</span><span class="sxs-lookup"><span data-stu-id="66a3c-125">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="66a3c-126">キューが受信するすべての Blob イベントを選択し、キューを Azure ストレージアカウントに接続します。</span><span class="sxs-lookup"><span data-stu-id="66a3c-126">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="66a3c-127">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="66a3c-127">Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="66a3c-128">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="66a3c-128">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="66a3c-129">[ **検索権限の管理** ] 画面では、 [Azure Data Lake Gen 2 ストレージ](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントからアクセス制御リスト (acl) を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-129">On the **Manage search permissions** screen, you can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="66a3c-130">これらの検索権限が設定されている場合、コンテンツを検索するサインインしている [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) ユーザーに割り当てられているアクセス許可に基づいて、検索コンテンツがトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-130">When these search permissions are set, search content is trimmed based on the permissions assigned to the signed-in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) user searching the content.</span></span> <span data-ttu-id="66a3c-131">または、組織内のすべてのユーザーに対して、ストレージアカウントからインデックスが作成されたすべてのコンテンツを表示するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-131">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="66a3c-132">この場合、組織内のすべてのユーザーがストレージアカウントのすべてのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-132">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="66a3c-133">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="66a3c-133">Azure Blob Storage</span></span>

<span data-ttu-id="66a3c-134">[Azure Blob ストレージ](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)への接続の場合、構成されたソースからインデックスが作成されたすべてのコンテンツが組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-134">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="66a3c-135">アクセス制御リストは、Azure Blob ストレージの Blob レベルではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="66a3c-135">Access control lists are not supported at Blob level in Azure Blob Storage.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="66a3c-136">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="66a3c-136">Manage search permissions</span></span>

<span data-ttu-id="66a3c-137">Azure Data Lake Storage Gen2 コネクタは、 **すべてのユーザー** に表示される検索アクセス許可、または **このデータソースへのアクセス権を持つユーザーのみ** をサポートします。</span><span class="sxs-lookup"><span data-stu-id="66a3c-137">The Azure Data Lake Storage Gen2 connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="66a3c-138">検索結果に表示されるインデックス付きデータは、組織内のすべてのユーザーに表示される場合もあれば、各アイテムにアクセスできるユーザーに対して表示される場合もあります。</span><span class="sxs-lookup"><span data-stu-id="66a3c-138">Indexed data that appears in the search results could be visible to all users in the organization or only to users who have access to each item.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="66a3c-139">プロパティのラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="66a3c-139">Assign property labels</span></span>

<span data-ttu-id="66a3c-140">各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="66a3c-140">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="66a3c-141">この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="66a3c-141">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="66a3c-142">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="66a3c-142">Manage schema</span></span>

<span data-ttu-id="66a3c-143">[**スキーマの管理**] 画面で、プロパティに関連付けられているスキーマの属性 (**クエリ** 可能、**検索\*\*\*\*可能、取得可能、および\*\*\*\*絞り込み可能な**) を変更し、オプションのエイリアスを追加して、 **Content** プロパティを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-143">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="66a3c-144">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="66a3c-144">Set the refresh schedule</span></span>

<span data-ttu-id="66a3c-145">[ **更新の設定** ] 画面で、増分クロールの間隔とフルクロールの間隔を設定できます。</span><span class="sxs-lookup"><span data-stu-id="66a3c-145">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="66a3c-146">Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールの場合は15分、フルクロールの場合は1週間です。</span><span class="sxs-lookup"><span data-stu-id="66a3c-146">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="66a3c-147">制限事項</span><span class="sxs-lookup"><span data-stu-id="66a3c-147">Limitations</span></span>

<span data-ttu-id="66a3c-148">Azure Data Lake Storage Gen2 source に対して、公開されている接続を再構成することはできません。また、その逆も同様です。</span><span class="sxs-lookup"><span data-stu-id="66a3c-148">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and vice-versa.</span></span> <span data-ttu-id="66a3c-149">このようなシナリオでは、新しい接続を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66a3c-149">In such scenarios, it is recommended to configure a new connection.</span></span>
