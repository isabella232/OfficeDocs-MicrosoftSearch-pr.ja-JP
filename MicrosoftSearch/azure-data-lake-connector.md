---
title: Microsoft Search 用 Azure Data Lake connector
ms.author: v-pamcn
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
ms.openlocfilehash: bedd7307ca2add52408bb9a5e3b3b21fd75df258
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949900"
---
# <a name="azure-data-lake-storage-gen2-connector"></a><span data-ttu-id="bcc30-103">Azure Data Lake Storage Gen2 connector</span><span class="sxs-lookup"><span data-stu-id="bcc30-103">Azure Data Lake Storage Gen2 connector</span></span>

<span data-ttu-id="bcc30-104">[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)コネクタを使用すると、組織内のユーザーはファイルとそのコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="bcc30-104">With the [Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) connector, users in your organization can search for files and their content.</span></span> <span data-ttu-id="bcc30-105">このコネクタは、azure Data Lake Storage Gen 2 アカウント内の Azure Blob コンテナーおよび階層対応フォルダーに格納されているデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="bcc30-105">This connector accesses data stored in Azure Blob containers and hierarchy-enabled folders within an Azure Data Lake Storage Gen 2 account.</span></span>

<span data-ttu-id="bcc30-106">この記事は、Microsoft 365 管理者または Azure Data Lake Storage Gen2 connector を構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="bcc30-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="bcc30-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bcc30-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="bcc30-108">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="bcc30-108">Connect to a data source</span></span>

### <a name="primary-storage-connection-string"></a><span data-ttu-id="bcc30-109">プライマリストレージ接続文字列</span><span class="sxs-lookup"><span data-stu-id="bcc30-109">Primary storage connection string</span></span> 
<span data-ttu-id="bcc30-110">[**認証と構成**] 画面で、プライマリストレージ接続文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="bcc30-110">On the **Authentication and config** screen, provide the Primary Storage Connection String.</span></span> <span data-ttu-id="bcc30-111">この文字列は、ストレージアカウントへのアクセスを許可するために必要です。</span><span class="sxs-lookup"><span data-stu-id="bcc30-111">That string is required to allow access to your storage account.</span></span> <span data-ttu-id="bcc30-112">接続文字列を検索するには、 [azure portal](https://ms.portal.azure.com/#home)に移動して、Azure Data Lake Storage Gen2 アカウントの [**キー** ] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="bcc30-112">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of the Azure Data Lake Storage Gen2 account.</span></span> <span data-ttu-id="bcc30-113">接続文字列をコピーして画面の適切なフィールドに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bcc30-113">Copy and paste the connection string in the appropriate field on the screen.</span></span>

<span data-ttu-id="bcc30-114">**AccountKey** (プライマリストレージ接続文字列のパラメーター) を指定しない場合は、Graph connector Service への読み取りアクセス権を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc30-114">If you do not want to provide the **AccountKey** (a parameter in the primary storage connection string), you have to grant read access to our Graph Connectors Service.</span></span> <span data-ttu-id="bcc30-115">Azure Data Lake Storage Gen2 アカウントの [**アクセス制御**] タブで、そのページの指示に従って、次のアプリへのアクセス権を付与します。</span><span class="sxs-lookup"><span data-stu-id="bcc30-115">In the **Access Control** tab of your Azure Data Lake Storage Gen2 account, follow the instructions on that page to grant access to the following app:</span></span>
* <span data-ttu-id="bcc30-116">**最初のパーティのアプリ ID:** 56c1da01-2127648f7-9355-af6d59d2766</span><span class="sxs-lookup"><span data-stu-id="bcc30-116">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="bcc30-117">**ファーストパーティのアプリ名:** Graph Connector サービス</span><span class="sxs-lookup"><span data-stu-id="bcc30-117">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="bcc30-118">ストレージアカウントとキューの通知 (オプション)</span><span class="sxs-lookup"><span data-stu-id="bcc30-118">Storage account and queue notifications (Optional)</span></span>
<span data-ttu-id="bcc30-119">グラフコネクタサービスでリアルタイムでの変更の処理のサポートが今後追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bcc30-119">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="bcc30-120">その場合は、Azure Data Lake Storage Gen2 の変更通知をキューに格納します。</span><span class="sxs-lookup"><span data-stu-id="bcc30-120">In that case, we'll monitor Azure Data Lake Storage Gen2 change notifications stored in a queue.</span></span> <span data-ttu-id="bcc30-121">Azure Data Lake Storage Gen2 と同じアカウント、または別のストレージアカウントにキューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bcc30-121">You'll need to create a queue in the same account as your Azure Data Lake Storage Gen2 or in another storage account.</span></span>

<span data-ttu-id="bcc30-122">キューを作成した後、[キュー] ページの [**イベント**] タブに移動して、イベントサブスクリプションを構成します。</span><span class="sxs-lookup"><span data-stu-id="bcc30-122">After you create a queue, go to the **Events** tab in the queue page to configure Event Subscription.</span></span> <span data-ttu-id="bcc30-123">キューが受信するすべての Blob イベントを選択し、そのキューを Azure Data Lake Storage Gen2 アカウントに接続します。</span><span class="sxs-lookup"><span data-stu-id="bcc30-123">Choose all the Blob events that the queue will receive and connect the queue to the Azure Data Lake Storage Gen2 account.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="bcc30-124">検索スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="bcc30-124">Manage the search schema</span></span>
<span data-ttu-id="bcc30-125">[**スキーマの管理**] 画面には、管理プロパティに関連付けられているスキーマ属性 (**クエリ**可能、**検索**可能、および取得**可能) を**変更するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="bcc30-125">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, and **retrievable**) associated with the managed properties.</span></span> <span data-ttu-id="bcc30-126">これらの管理プロパティの属性は、Azure Data Lake Storage Gen2 アカウントからインデックスが作成されたデータです。</span><span class="sxs-lookup"><span data-stu-id="bcc30-126">These managed property attributes are data indexed from your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="bcc30-127">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="bcc30-127">Manage search permissions</span></span>
<span data-ttu-id="bcc30-128">[**検索権限の管理**] 画面では、ストレージアカウントからアクセス制御リスト (acl) を取り込みます。</span><span class="sxs-lookup"><span data-stu-id="bcc30-128">On the **Manage search permissions** screen, you can choose to ingest the Access Control Lists (ACLs) from your storage account.</span></span> <span data-ttu-id="bcc30-129">これらの検索アクセス許可が設定されている場合、検索コンテンツは、コンテンツを検索している、サインインしている Azure AD ユーザーに割り当てられているアクセス許可に基づいてトリミングされます。</span><span class="sxs-lookup"><span data-stu-id="bcc30-129">When these search permissions are set, search content is trimmed based on the permissions assigned to the signed-in Azure AD user searching the content.</span></span> <span data-ttu-id="bcc30-130">または、組織内のすべてのユーザーに対して、ストレージアカウントからインデックスが作成されたすべてのコンテンツを表示するように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="bcc30-130">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="bcc30-131">この場合、組織内のすべてのユーザーがストレージアカウントのすべてのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="bcc30-131">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>
 
## <a name="set-the-refresh-schedule"></a><span data-ttu-id="bcc30-132">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="bcc30-132">Set the refresh schedule</span></span>
<span data-ttu-id="bcc30-133">[**更新の設定**] 画面で、増分クロールの間隔とフルクロールの間隔を設定できます。</span><span class="sxs-lookup"><span data-stu-id="bcc30-133">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="bcc30-134">Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールの場合は15分、フルクロールの場合は1週間です。</span><span class="sxs-lookup"><span data-stu-id="bcc30-134">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>
 
## <a name="limitations"></a><span data-ttu-id="bcc30-135">制限事項</span><span class="sxs-lookup"><span data-stu-id="bcc30-135">Limitations</span></span>
<span data-ttu-id="bcc30-136">現時点では、Azure Data Lake Storage Gen2 マルチプロトコルアクセスを使用できるのは、中部標準時、西中央アメリカ、カナダ中部、東部アメリカ、東アジア、北ヨーロッパ、東 US2、南アジア、西ヨーロッパ、西ヨーロッパ、西 US2、およびブラジルのみです。中南米.</span><span class="sxs-lookup"><span data-stu-id="bcc30-136">Currently, Azure Data Lake Storage Gen2 Multi-Protocol Access is available only in the Central US, West Central US, Canada Central, East US, East Asia, North Europe, East US2, South East Asia, West Europe, West US, Australia East, Japan East, West US2, and Brazil South.</span></span>

<span data-ttu-id="bcc30-137">更新プログラムと詳細については、「 [Azure Data Lake Storage でのマルチプロトコルアクセス (プレビュー)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcc30-137">For updates and more information, see  [Multi-protocol access on Azure Data Lake Storage (preview)](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-multi-protocol-access).</span></span>


