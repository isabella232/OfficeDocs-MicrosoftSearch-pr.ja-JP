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

# <a name="azure-data-lake-storage-gen2-graph-connector"></a><span data-ttu-id="a404e-103">Azure Data Lake Storage Gen2 Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="a404e-103">Azure Data Lake Storage Gen2 Graph connector</span></span>

<span data-ttu-id="a404e-104">Azure Data Lake Storage Gen2 Graph コネクタを使用すると、組織内のユーザーは [、Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) および [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) アカウントに格納されているファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="a404e-104">The Azure Data Lake Storage Gen2 Graph connector allows users in your organization to search for files stored in [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="a404e-105">Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、一般的な Graph コネクタのセットアップ プロセスについて理解してください。</span><span class="sxs-lookup"><span data-stu-id="a404e-105">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="a404e-106">この記事は、Azure Data Lake Storage Gen2 コネクタを構成、実行、および監視するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="a404e-106">This article is for anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="a404e-107">一般的なセットアップ プロセスを補完し、Azure Data Lake Storage Gen2 コネクタにのみ適用される手順を示します。</span><span class="sxs-lookup"><span data-stu-id="a404e-107">It supplements the general setup process, and shows instructions that apply only for the Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="a404e-108">この記事には、制限事項に関する [情報も含まれています](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="a404e-108">This article also includes information about [Limitations](#limitations).</span></span>

<span data-ttu-id="a404e-109">この記事では *、Azure Blob Storage* と [Azure](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) Data Lake Gen 2 Storage の一般的な用語として Azure [Storage を使用します](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)。</span><span class="sxs-lookup"><span data-stu-id="a404e-109">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="a404e-110">手順 1: Microsoft 365 管理センターで Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="a404e-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="a404e-111">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="a404e-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="a404e-112">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="a404e-112">Step 2: Name the connection</span></span>

<span data-ttu-id="a404e-113">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="a404e-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="a404e-114">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a404e-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="a404e-115">プライマリ ストレージ接続文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="a404e-115">Enter your Primary storage connection String.</span></span> <span data-ttu-id="a404e-116">この文字列は、ストレージ アカウントへのアクセスを許可するために必要です。</span><span class="sxs-lookup"><span data-stu-id="a404e-116">This string is required to allow access to your storage account.</span></span> <span data-ttu-id="a404e-117">接続文字列を見つけるには [、Azure ポータル](https://ms.portal.azure.com/#home) に移動し、関連する Azure Storage アカウントの **[キー** ] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="a404e-117">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span>

<span data-ttu-id="a404e-118">**AccountKey** (プライマリ ストレージ接続文字列のパラメーター) を指定しない場合は、Graph Connectors Service へのアクセス権を次の役割に付与します。</span><span class="sxs-lookup"><span data-stu-id="a404e-118">If you prefer not to provide the **AccountKey** (a parameter in the primary storage connection string), grant access to our Graph Connectors Service for the following roles:</span></span>

* <span data-ttu-id="a404e-119">ストレージ BLOB データ リーダー</span><span class="sxs-lookup"><span data-stu-id="a404e-119">Storage Blob Data Reader</span></span>
* <span data-ttu-id="a404e-120">記憶域キュー データ共同作成者</span><span class="sxs-lookup"><span data-stu-id="a404e-120">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="a404e-121">ストレージ BLOB Delegator</span><span class="sxs-lookup"><span data-stu-id="a404e-121">Storage Blob Delegator</span></span>

<span data-ttu-id="a404e-122">Azure Storage アカウント **の [アクセス** 制御] タブに移動し、次の手順に従って、次のアプリへのアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="a404e-122">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="a404e-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="a404e-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="a404e-124">**ファースト パーティのアプリ名:** Graph Connector サービス</span><span class="sxs-lookup"><span data-stu-id="a404e-124">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="a404e-125">ストレージ アカウントとキューの通知 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a404e-125">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="a404e-126">Graph Connectors Service でのリアルタイムでの変更処理のサポートは、今後追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a404e-126">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="a404e-127">その場合は、キューに格納されている Azure Storage の変更通知を監視します。</span><span class="sxs-lookup"><span data-stu-id="a404e-127">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="a404e-128">Azure Storage アカウントと同じアカウントにキューを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a404e-128">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="a404e-129">キューを作成した後、キュー ページの [ **イベント** ] タブに移動して、イベント サブスクリプション **を構成します**。</span><span class="sxs-lookup"><span data-stu-id="a404e-129">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="a404e-130">キューが受信する BLOB イベントを選択し、キューを Azure Storage アカウントに接続します。</span><span class="sxs-lookup"><span data-stu-id="a404e-130">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="a404e-131">手順 4: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="a404e-131">Step 4: Assign property labels</span></span>

<span data-ttu-id="a404e-132">オプションのメニューから選択すると、ソース プロパティを各ラベルに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="a404e-132">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="a404e-133">この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果が向上します。</span><span class="sxs-lookup"><span data-stu-id="a404e-133">While this step isn't mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="a404e-134">手順 5: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="a404e-134">Step 5: Manage schema</span></span>

<span data-ttu-id="a404e-135">[スキーマ **の管理]** 画面では、プロパティに関連付けられているスキーマ属性を変更できます。オプションは **、クエリ**、 **検索**、 **取得**、および絞り込 **みです**。</span><span class="sxs-lookup"><span data-stu-id="a404e-135">On the **Manage Schema** screen, you can change the schema attributes associated with the properties, the options are **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="a404e-136">オプションのエイリアスを追加し、Content プロパティを **選択** できます。</span><span class="sxs-lookup"><span data-stu-id="a404e-136">You also can add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="a404e-137">手順 6: 検索権限を管理する</span><span class="sxs-lookup"><span data-stu-id="a404e-137">Step 6: Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="a404e-138">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="a404e-138">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="a404e-139">Azure Data Lake Gen 2 Storage アカウントからアクセス制御リスト [(ACL) を取り込む方法を選択](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) できます。</span><span class="sxs-lookup"><span data-stu-id="a404e-139">You can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="a404e-140">これらの検索アクセス許可を設定すると、Azure Active Directory にサインインしているユーザーのアクセス許可に基づいて検索コンテンツ [がトリミングされます](https://docs.microsoft.com/azure/active-directory/)。</span><span class="sxs-lookup"><span data-stu-id="a404e-140">When these search permissions are set, search content is trimmed based on the permissions of the user signed in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="a404e-141">または、ストレージ アカウントからインデックスが作成されたコンテンツを組織内のすべてのユーザーに表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="a404e-141">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="a404e-142">この場合、組織内のすべてのユーザーがストレージ アカウント内のすべてのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a404e-142">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

<span data-ttu-id="a404e-143">Azure Data Lake Storage Gen2 Graph コネクタは、[すべてのユーザー] または [このデータ ソースにアクセスできるユーザーのみ] に表示される検索アクセス **許可をサポートします**。</span><span class="sxs-lookup"><span data-stu-id="a404e-143">The Azure Data Lake Storage Gen2 Graph connector supports search permissions visible to **Everyone**, or **Only people with access to this data source**.</span></span> <span data-ttu-id="a404e-144">検索結果に表示されるインデックス付きデータは、各アイテムにアクセスできる組織内のユーザーに表示される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a404e-144">Indexed data that appears in the search results could be visible to users in the organization who have access to each item.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="a404e-145">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="a404e-145">Azure Blob Storage</span></span>

<span data-ttu-id="a404e-146">Azure Blob [Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction)への接続の場合、構成済みのソースからインデックスが作成されたコンテンツはすべて、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a404e-146">For a connection to [Azure Blob Storage](https://docs.microsoft.com/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="a404e-147">アクセス制御リストは、Azure Blob Storage の Blob レベルではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a404e-147">Access control lists aren't supported at Blob level in Azure Blob Storage.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="a404e-148">手順 7: 更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="a404e-148">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="a404e-149">[設定 **の更新] 画面** では、増分クロールの間隔とフル クロールの間隔を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a404e-149">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="a404e-150">Azure Data Lake Storage Gen2 コネクタの既定の間隔は、増分クロールの場合は 15 分、フル クロールの場合は 1 週間です。</span><span class="sxs-lookup"><span data-stu-id="a404e-150">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="a404e-151">手順 8: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="a404e-151">Step 8: Review connection</span></span>

<span data-ttu-id="a404e-152">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="a404e-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="a404e-153">制限事項</span><span class="sxs-lookup"><span data-stu-id="a404e-153">Limitations</span></span>

<span data-ttu-id="a404e-154">Azure Blob Storage の公開接続は、Azure Data Lake Storage Gen2 ソースとそれ以外の方法では再構成できません。</span><span class="sxs-lookup"><span data-stu-id="a404e-154">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and the other way around.</span></span> <span data-ttu-id="a404e-155">このようなシナリオでは、新しい接続を構成する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a404e-155">In such scenarios, it's recommended to configure a new connection.</span></span>

<span data-ttu-id="a404e-156">また、ファイルをクロールするには、ファイルのサイズを 4 MB 以下に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a404e-156">Also, the size of the files needs to be 4 MB or less for it to be crawled.</span></span> <span data-ttu-id="a404e-157">現在サポートされているファイルの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a404e-157">File types currently supported are:</span></span>

* <span data-ttu-id="a404e-158">Word (docx、.docm、.dotx、.dotm)</span><span class="sxs-lookup"><span data-stu-id="a404e-158">Word (docx, .docm, .dotx, .dotm)</span></span>
* <span data-ttu-id="a404e-159">PowerPoint (.pptm、.pptx、.potm、.potx、.ppam、.ppsm、.ppsx)</span><span class="sxs-lookup"><span data-stu-id="a404e-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span></span>
* <span data-ttu-id="a404e-160">Excel (.xlsx, .xlsm)</span><span class="sxs-lookup"><span data-stu-id="a404e-160">Excel (.xlsx, .xlsm)</span></span>
* <span data-ttu-id="a404e-161">従来Office形式 (.doc、.dot など)</span><span class="sxs-lookup"><span data-stu-id="a404e-161">Legacy Office formats (.doc, .dot, etc.)</span></span>
* <span data-ttu-id="a404e-162">テキスト (.txt)</span><span class="sxs-lookup"><span data-stu-id="a404e-162">Text (.txt)</span></span>
* <span data-ttu-id="a404e-163">HTML</span><span class="sxs-lookup"><span data-stu-id="a404e-163">HTML</span></span>
* <span data-ttu-id="a404e-164">PDF</span><span class="sxs-lookup"><span data-stu-id="a404e-164">PDF</span></span>

<span data-ttu-id="a404e-165">画像 (.jpg、.bmp など) などのバイナリ ファイルはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a404e-165">Binary files like images (.jpg, .bmp, etc.) are not supported.</span></span> <span data-ttu-id="a404e-166">たとえば、.docx ファイルに画像だけが含まれている場合、コンテンツが返さなかったためスキップされる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a404e-166">For example, if a .docx file contains only images, it might be skipped because it didn't return any content.</span></span>
