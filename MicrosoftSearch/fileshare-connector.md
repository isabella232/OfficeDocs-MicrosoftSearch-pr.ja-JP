---
title: Microsoft Search 用のファイル共有 Graph コネクタ
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
ROBOTS: NoIndex
description: Microsoft Search のファイル共有 Graph コネクタをセットアップする
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097423"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="1b4d8-103">ファイル共有 Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="1b4d8-103">File share Graph connector</span></span>

<span data-ttu-id="1b4d8-104">ファイル共有 Graph コネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有を検索できます。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="1b4d8-105">Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、Graph コネクタの一般的なセットアップ プロセスを理解してください。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="1b4d8-106">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="1b4d8-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="1b4d8-107">Graph コネクタ エージェントをインストールする</span><span class="sxs-lookup"><span data-stu-id="1b4d8-107">Install the Graph connector agent</span></span>

<span data-ttu-id="1b4d8-108">Windows ファイル共有のインデックスを作成するには、Graph コネクタ エージェントをインストールして登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="1b4d8-109">詳細 [については、「Graph コネクタ エージェントのインストール」](on-prem-agent.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="1b4d8-110">コンテンツの要件</span><span class="sxs-lookup"><span data-stu-id="1b4d8-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="1b4d8-111">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="1b4d8-111">File types</span></span>

<span data-ttu-id="1b4d8-112">インデックスを作成して検索できる形式は DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPTM、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLSX、XLT、XLXM、XML、XPS、ZIP。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="1b4d8-113">これらの形式のテキスト コンテンツだけがインデックス付けされます。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="1b4d8-114">すべてのマルチメディア コンテンツは無視されます。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-114">All multimedia content is ignored.</span></span> <span data-ttu-id="1b4d8-115">この形式に属さないファイルでは、メタデータだけではインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="1b4d8-116">ファイル サイズの制限を超えている</span><span class="sxs-lookup"><span data-stu-id="1b4d8-116">File size limits</span></span>

<span data-ttu-id="1b4d8-117">サポートされるファイル の最大サイズは 100 MB です。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="1b4d8-118">100 MB を超えるファイルにはインデックスが作成されません。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="1b4d8-119">処理後の最大サイズ制限は 4 MB です。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="1b4d8-120">ファイルのサイズが 4 MB に達すると処理が停止します。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="1b4d8-121">したがって、ファイル内に存在する一部の語句は検索に使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1b4d8-122">手順 1: Microsoft 365 管理センターで Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="1b4d8-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1b4d8-123">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="1b4d8-124">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="1b4d8-124">Step 2: Name the connection</span></span>

<span data-ttu-id="1b4d8-125">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="1b4d8-126">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="1b4d8-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="1b4d8-127">[データ ソース **への接続] ページ** で、[ **ファイル共有]** を選択し、名前、接続 ID、および説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="1b4d8-128">次のページで、ファイル共有へのパスを指定し、以前にインストールした Graph コネクタ エージェントを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="1b4d8-129">ファイル共有内のすべてのファイルへの読み取りアクセス権を持つ [Microsoft Windows](https://microsoft.com/windows) ユーザー アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="1b4d8-130">最終アクセス時刻を保持する</span><span class="sxs-lookup"><span data-stu-id="1b4d8-130">Preserve last access time</span></span>

<span data-ttu-id="1b4d8-131">コネクタがファイルをクロールしようとすると、そのメタデータの "最終アクセス時刻" フィールドが更新されます。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="1b4d8-132">アーカイブ ソリューションとバックアップ ソリューションのフィールドに依存し、コネクタがアクセスするときに更新しない場合は、[詳細設定] ページでこのオプション **を構成** できます。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="1b4d8-133">手順 4: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="1b4d8-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="1b4d8-134">共有アクセス制御リストまたは新しいテクノロジ ファイル システム (NTFS) アクセス制御リストに基づいて、任意のファイルを検索するアクセス許可を制限できます。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="1b4d8-135">アクセス制御リストの共有を使用する場合は、[詳細設定] ページで適切 **なオプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-135">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="1b4d8-136">NTFS アクセス制御リストを使用する場合は、[検索アクセス許可の管理] ページ **で適切なオプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-136">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="1b4d8-137">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1b4d8-137">Step 5: Assign property labels</span></span>

<span data-ttu-id="1b4d8-138">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-138">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="1b4d8-139">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="1b4d8-139">Step 6: Manage schema</span></span>

<span data-ttu-id="1b4d8-140">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-140">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="1b4d8-141">手順 7: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="1b4d8-141">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="1b4d8-142">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-142">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="1b4d8-143">手順 8: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="1b4d8-143">Step 8: Review connection</span></span>

<span data-ttu-id="1b4d8-144">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b4d8-144">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
