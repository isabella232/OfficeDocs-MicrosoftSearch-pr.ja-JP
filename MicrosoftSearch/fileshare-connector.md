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
description: Microsoft Search 用のファイル共有コネクタをセットアップする
ms.openlocfilehash: a95cfe90ca35a385bb9ce3a4c565c18c5a42ec80
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408935"
---
# <a name="file-share-connector"></a><span data-ttu-id="ec8ce-103">ファイル共有コネクタ</span><span class="sxs-lookup"><span data-stu-id="ec8ce-103">File share connector</span></span>

<span data-ttu-id="ec8ce-104">ファイル共有グラフコネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有を検索できます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="ec8ce-105">この記事は、Microsoft 365 管理者またはファイル共有コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="ec8ce-106">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="ec8ce-107">Graph connector エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="ec8ce-107">Install Graph connector agent</span></span>

<span data-ttu-id="ec8ce-108">Windows ファイル共有にインデックスを作成するために、 [Graph connector エージェント](on-prem-agent.md) ソフトウェアをインストールして登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="ec8ce-109">コンテンツの要件</span><span class="sxs-lookup"><span data-stu-id="ec8ce-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="ec8ce-110">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="ec8ce-110">File types</span></span>

<span data-ttu-id="ec8ce-111">次の形式のコンテンツをインデックス処理して検索することができます。 DOC、.DOCM、.DOCX、ドット、.DOTX、EML、GIF、HTML、JPEG、.MHT、MHTML、MSG、NWS、OBD、OBD、ODP、XLB、PPT、PPTM、.PPTX、TXT、、XLC、.XLSB、XLS、.XLSX、、XLXM、XML、XPS、および ZIP。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="ec8ce-112">これらの書式のテキストの内容のみがインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="ec8ce-113">すべてのマルチメディアコンテンツは無視されます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-113">All multimedia content is ignored.</span></span> <span data-ttu-id="ec8ce-114">この形式に属さないファイルでは、メタデータのみがインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="ec8ce-115">ファイル サイズの制限を超えている</span><span class="sxs-lookup"><span data-stu-id="ec8ce-115">File size limits</span></span>

<span data-ttu-id="ec8ce-116">サポートされているファイルの最大サイズは 100 MB です。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="ec8ce-117">100 MB を超えるファイルはインデックス付けされません。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="ec8ce-118">処理後の最大サイズ制限は 4 MB です。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="ec8ce-119">ファイルのサイズが 4 MB に達すると、処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="ec8ce-120">そのため、ファイルに含まれる一部の語句は検索に使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="ec8ce-121">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="ec8ce-121">Connect to a data source</span></span>

<span data-ttu-id="ec8ce-122">[ **データソースへの接続** ] ページで、[ **ファイル共有** ] を選択し、名前、接続 ID、および説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="ec8ce-123">次のページで、ファイル共有へのパスを指定し、以前にインストールしたグラフコネクタエージェントを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="ec8ce-124">ファイル共有内のすべてのファイルに対する読み取りアクセス権を持つ [Microsoft Windows](https://microsoft.com/windows) ユーザーアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="ec8ce-125">最終アクセス時刻を保持する</span><span class="sxs-lookup"><span data-stu-id="ec8ce-125">Preserve last access time</span></span>

<span data-ttu-id="ec8ce-126">コネクタがファイルをクロールしようとすると、そのメタデータの "最終アクセス時刻" フィールドが更新されます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="ec8ce-127">そのフィールドに依存していて、コネクタがアクセスするときにそのフィールドを更新したくない場合は、 **[詳細設定** ] ページでこのオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="ec8ce-128">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="ec8ce-128">Manage search permissions</span></span>

<span data-ttu-id="ec8ce-129">共有アクセス制御リストまたは新しいテクノロジファイルシステム (NTFS) アクセス制御リストに基づいて、任意のファイルを検索するアクセス許可を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="ec8ce-130">[共有アクセス制御リスト] を使用する場合は、[ **詳細設定** ] ページで適切なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="ec8ce-131">NTFS アクセス制御リストを使用する場合は、[ **検索権限の管理** ] ページで適切なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="ec8ce-132">プロパティのラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ec8ce-132">Assign property labels</span></span>

<span data-ttu-id="ec8ce-133">各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="ec8ce-134">この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="ec8ce-135">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="ec8ce-135">Manage schema</span></span>

<span data-ttu-id="ec8ce-136">[**スキーマの管理**] 画面で、プロパティに関連付けられているスキーマの属性 (**クエリ** 可能、**検索\*\*\*\*可能、取得可能、および\*\*\*\*絞り込み可能な**) を変更し、オプションのエイリアスを追加して、 **Content** プロパティを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="ec8ce-137">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="ec8ce-137">Set the refresh schedule</span></span>

<span data-ttu-id="ec8ce-138">推奨される既定の更新スケジュール間隔は15分ですが、ユーザーの設定に基づいて変更することができます。</span><span class="sxs-lookup"><span data-stu-id="ec8ce-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>
