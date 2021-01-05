---
title: ファイル共有コネクタ
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Microsoft Search のファイル共有コネクタをセットアップする
ms.openlocfilehash: bf9fb730abd4ca6e42b681893525bbe3dd8a1419
ms.sourcegitcommit: 249f41723dd6fda1e93ee1a8f3f7571ef066454b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750899"
---
# <a name="file-share-connector"></a><span data-ttu-id="4789b-103">ファイル共有コネクタ</span><span class="sxs-lookup"><span data-stu-id="4789b-103">File share connector</span></span>

<span data-ttu-id="4789b-104">ファイル共有 Graph コネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有を検索できます。</span><span class="sxs-lookup"><span data-stu-id="4789b-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="4789b-105">この記事は、Microsoft 365 管理者またはファイル共有コネクタを構成、実行、および監視するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="4789b-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="4789b-106">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4789b-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="4789b-107">Graph コネクタ エージェントをインストールする</span><span class="sxs-lookup"><span data-stu-id="4789b-107">Install Graph connector agent</span></span>

<span data-ttu-id="4789b-108">Windows ファイル共有のインデックスを作成するには、Graph コネクタ エージェント ソフトウェアをインストール [して登録する必要](on-prem-agent.md) があります。</span><span class="sxs-lookup"><span data-stu-id="4789b-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="4789b-109">コンテンツの要件</span><span class="sxs-lookup"><span data-stu-id="4789b-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="4789b-110">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="4789b-110">File types</span></span>

<span data-ttu-id="4789b-111">インデックスを作成して検索できる形式は DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPTM、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLSX、XLT、XLXM、XML、XPS、ZIP。</span><span class="sxs-lookup"><span data-stu-id="4789b-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="4789b-112">これらの形式のテキスト コンテンツだけがインデックス付けされます。</span><span class="sxs-lookup"><span data-stu-id="4789b-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="4789b-113">すべてのマルチメディア コンテンツは無視されます。</span><span class="sxs-lookup"><span data-stu-id="4789b-113">All multimedia content is ignored.</span></span> <span data-ttu-id="4789b-114">この形式に属さないファイルでは、メタデータだけではインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4789b-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="4789b-115">ファイル サイズの制限を超えている</span><span class="sxs-lookup"><span data-stu-id="4789b-115">File size limits</span></span>

<span data-ttu-id="4789b-116">サポートされるファイル の最大サイズは 100 MB です。</span><span class="sxs-lookup"><span data-stu-id="4789b-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="4789b-117">100 MB を超えるファイルにはインデックスが作成されません。</span><span class="sxs-lookup"><span data-stu-id="4789b-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="4789b-118">処理後の最大サイズ制限は 4 MB です。</span><span class="sxs-lookup"><span data-stu-id="4789b-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="4789b-119">ファイルのサイズが 4 MB に達すると処理が停止します。</span><span class="sxs-lookup"><span data-stu-id="4789b-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="4789b-120">したがって、ファイル内に存在する一部の語句は検索に使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="4789b-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="4789b-121">データ ソースに接続する</span><span class="sxs-lookup"><span data-stu-id="4789b-121">Connect to a data source</span></span>

<span data-ttu-id="4789b-122">[データ ソース **への接続] ページ** で、[ **ファイル共有]** を選択し、名前、接続 ID、および説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="4789b-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="4789b-123">次のページで、ファイル共有へのパスを指定し、以前にインストールした Graph コネクタ エージェントを選択します。</span><span class="sxs-lookup"><span data-stu-id="4789b-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="4789b-124">ファイル共有内のすべてのファイルへの読み取りアクセス権を持つ [Microsoft Windows](https://microsoft.com/windows) ユーザー アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="4789b-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="4789b-125">最終アクセス時刻を保持する</span><span class="sxs-lookup"><span data-stu-id="4789b-125">Preserve last access time</span></span>

<span data-ttu-id="4789b-126">コネクタがファイルをクロールしようとすると、そのメタデータの "最終アクセス時刻" フィールドが更新されます。</span><span class="sxs-lookup"><span data-stu-id="4789b-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="4789b-127">アーカイブ ソリューションとバックアップ ソリューションのフィールドに依存し、コネクタがアクセスするときに更新しない場合は、[詳細設定] ページでこのオプション **を構成** できます。</span><span class="sxs-lookup"><span data-stu-id="4789b-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="4789b-128">検索のアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="4789b-128">Manage search permissions</span></span>

<span data-ttu-id="4789b-129">共有アクセス制御リストまたは新しいテクノロジ ファイル システム (NTFS) アクセス制御リストに基づいて、任意のファイルを検索するアクセス許可を制限できます。</span><span class="sxs-lookup"><span data-stu-id="4789b-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="4789b-130">アクセス制御リストの共有を使用する場合は、[詳細設定] ページで適切 **なオプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="4789b-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="4789b-131">NTFS アクセス制御リストを使用する場合は、[検索アクセス許可の管理] ページ **で適切なオプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="4789b-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="4789b-132">プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4789b-132">Assign property labels</span></span>

<span data-ttu-id="4789b-133">オプションのメニューから選択すると、各ラベルにソース プロパティを割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="4789b-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="4789b-134">この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="4789b-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="4789b-135">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="4789b-135">Manage schema</span></span>

<span data-ttu-id="4789b-136">[スキーマの管理] 画面で、プロパティに関連付けられているスキーマ属性 **(クエリ** 可能、**検索** 可能、取得可能、絞り込み **可能)** を変更し、オプションのエイリアスを追加して **、Content** プロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4789b-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="4789b-137">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="4789b-137">Set the refresh schedule</span></span>

<span data-ttu-id="4789b-138">推奨される既定の更新スケジュール間隔は 15 分ですが、設定に基づいて変更できます。</span><span class="sxs-lookup"><span data-stu-id="4789b-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>

## <a name="result-layout"></a><span data-ttu-id="4789b-139">結果レイアウト</span><span class="sxs-lookup"><span data-stu-id="4789b-139">Result layout</span></span>

<span data-ttu-id="4789b-140">ファイル 共有コネクタには、ファイル パスへの移動に役立つ適切なアイコンとコントロールが含まれていますので、既定の結果レイアウトを使用してファイル共有コネクタの結果を表示することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4789b-140">We recommend that you use the default result layout to display your Fileshare connector results because it has appropriate icons and controls that help you navigate to the file path.</span></span> <span data-ttu-id="4789b-141">新しい結果レイアウトを作成すると、既定のレイアウトが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4789b-141">If you create a new result layout, it will override the default.</span></span>
