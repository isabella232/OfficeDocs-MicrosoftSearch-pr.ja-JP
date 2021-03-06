---
title: Microsoft Search のファイル共有グラフ コネクタ
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
ROBOTS: NoIndex
description: Microsoft Search のファイル共有グラフ コネクタをセットアップする
ms.openlocfilehash: cd3f28356e41d24182e2da712d476ce2223b39b2
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508789"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="1b3de-103">ファイル共有グラフ コネクタ</span><span class="sxs-lookup"><span data-stu-id="1b3de-103">File share Graph connector</span></span>

<span data-ttu-id="1b3de-104">ファイル共有グラフ コネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有を検索できます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="1b3de-105">グラフ コネクタ [**の一般的なセットアップ**](configure-connector.md) プロセスについて詳しくは、Graph コネクタのセットアップに関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1b3de-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="1b3de-106">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="1b3de-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="1b3de-107">Graph コネクタ エージェントのインストール</span><span class="sxs-lookup"><span data-stu-id="1b3de-107">Install the Graph connector agent</span></span>

<span data-ttu-id="1b3de-108">Windows ファイル共有のインデックスを作成するには、Graph コネクタ エージェントをインストールして登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b3de-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="1b3de-109">詳細については [、「Graph コネクタ エージェントのインストール](on-prem-agent.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b3de-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="1b3de-110">コンテンツ要件</span><span class="sxs-lookup"><span data-stu-id="1b3de-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="1b3de-111">ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="1b3de-111">File types</span></span>

<span data-ttu-id="1b3de-112">次の形式のコンテンツは、インデックスを作成して検索できます。DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPTM、PPTX、PPTX、TXT、XLB、XLC、XLSB、XLSX、XLT、XML、XML、XPS、および ZIP。</span><span class="sxs-lookup"><span data-stu-id="1b3de-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="1b3de-113">これらの形式のテキスト コンテンツだけがインデックス付けされます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="1b3de-114">すべてのマルチメディア コンテンツは無視されます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-114">All multimedia content is ignored.</span></span> <span data-ttu-id="1b3de-115">この形式に属していないファイルの場合は、メタデータだけでインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="1b3de-116">ファイル サイズの制限を超えている</span><span class="sxs-lookup"><span data-stu-id="1b3de-116">File size limits</span></span>

<span data-ttu-id="1b3de-117">サポートされるファイルの最大サイズは 100 MB です。</span><span class="sxs-lookup"><span data-stu-id="1b3de-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="1b3de-118">100 MB を超えるファイルはインデックス付けされません。</span><span class="sxs-lookup"><span data-stu-id="1b3de-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="1b3de-119">処理後の最大サイズ制限は 4 MB です。</span><span class="sxs-lookup"><span data-stu-id="1b3de-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="1b3de-120">ファイルのサイズが 4 MB に達すると、処理が停止します。</span><span class="sxs-lookup"><span data-stu-id="1b3de-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="1b3de-121">したがって、ファイルに存在する一部の語句が検索に使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="1b3de-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1b3de-122">手順 1: Microsoft 365 管理センターに Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="1b3de-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1b3de-123">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b3de-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="1b3de-124">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="1b3de-124">Step 2: Name the connection</span></span>

<span data-ttu-id="1b3de-125">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b3de-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="1b3de-126">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="1b3de-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="1b3de-127">[データ **ソースへの接続] ページで、[** ファイル共有] **を** 選択し、名前、接続 ID、および説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="1b3de-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="1b3de-128">次のページで、ファイル共有へのパスを指定し、以前にインストールした Graph コネクタ エージェントを選択します。</span><span class="sxs-lookup"><span data-stu-id="1b3de-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="1b3de-129">ファイル共有内のすべてのファイルへの読み取りアクセス権を持つ [Microsoft Windows](https://microsoft.com/windows) ユーザー アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="1b3de-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="1b3de-130">最後のアクセス時間を保持する</span><span class="sxs-lookup"><span data-stu-id="1b3de-130">Preserve last access time</span></span>

<span data-ttu-id="1b3de-131">コネクタがファイルをクロールしようとすると、そのメタデータ内の "最終アクセス時刻" フィールドが更新されます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="1b3de-132">アーカイブソリューションとバックアップ ソリューションのフィールドに依存し、コネクタがアクセスするときに更新しない場合は、[詳細設定] ページでこのオプション **を構成** できます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="1b3de-133">手順 4: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="1b3de-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="1b3de-134">[検索アクセス許可の管理] ページで目的のオプションを選択することにより、Share Access Control Lists または New Technology File System (NTFS) Access Control Lists に基づいて任意のファイルを検索するアクセス許可を制限できます。 </span><span class="sxs-lookup"><span data-stu-id="1b3de-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists, by selecting the desired option in **Manage search permissions** page.</span></span> <span data-ttu-id="1b3de-135">これらのアクセス制御リストで提供されるユーザー アカウントとグループは、Active Directory (AD) によって管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b3de-135">The user accounts and groups provided in these Access Control Lists must be managed by Active Directory (AD).</span></span> <span data-ttu-id="1b3de-136">ユーザー アカウント管理に他のシステムを使用している場合は、[すべてのユーザー] オプションを選択して、ユーザーがアクセス制限なしですべてのファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-136">If you are using any other system for user accounts management, you can select 'everyone' option, which lets users search for all the files without any access restrictions.</span></span> <span data-ttu-id="1b3de-137">ただし、ユーザーがファイルを開く場合は、ソースで設定されたアクセス制御が適用されます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-137">However, when users try to open the file, access controls set at the source apply.</span></span>

<span data-ttu-id="1b3de-138">既定では、フォルダーがネットワーク上で共有されている場合、Windows は Share ACL の 'Everyone' に対する 「読み取り」 アクセス許可を提供します。</span><span class="sxs-lookup"><span data-stu-id="1b3de-138">Note that windows by default provides 'Read' permission to 'Everyone' in Share ACLs when a folder is shared on network.</span></span> <span data-ttu-id="1b3de-139">[検索アクセス許可の管理] で [ACLの共有] を選択している場合、ユーザーはすべてのファイルを検索できます。</span><span class="sxs-lookup"><span data-stu-id="1b3de-139">By extension, if you are choosing Share ACLs in **Manage search permissions**, users will be able to search for all the files.</span></span> <span data-ttu-id="1b3de-140">アクセスを制限する場合は、ファイル共有の 'Everyone' の 'Read' アクセスを削除し、目的のユーザーとグループにのみアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="1b3de-140">If you want to restrict access, remove 'Read' access for 'Everyone' in file shares and provide access only to the desired users and groups.</span></span> <span data-ttu-id="1b3de-141">コネクタは次に、これらのアクセス制限を読み取り、それらを検索に適用します。</span><span class="sxs-lookup"><span data-stu-id="1b3de-141">The connector then reads these access restrictions and applies them to search.</span></span>

<span data-ttu-id="1b3de-142">[ACL の共有] を選択できるのは、指定した共有パスが UNC パス形式に従う場合のみです。</span><span class="sxs-lookup"><span data-stu-id="1b3de-142">You can choose Share ACLs only if the share path you provided follows UNC path format.</span></span> <span data-ttu-id="1b3de-143">UNC 形式のパスを作成するには、[共有] オプションの [高度な共有] に進む必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b3de-143">You can create a path in UNC format by going to 'Advanced Sharing' under 'Sharing' option.</span></span>

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="1b3de-145">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1b3de-145">Step 5: Assign property labels</span></span>

<span data-ttu-id="1b3de-146">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b3de-146">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="1b3de-147">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="1b3de-147">Step 6: Manage schema</span></span>

<span data-ttu-id="1b3de-148">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b3de-148">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="1b3de-149">手順 7: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="1b3de-149">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="1b3de-150">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b3de-150">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="1b3de-151">手順 8: 接続の確認</span><span class="sxs-lookup"><span data-stu-id="1b3de-151">Step 8: Review connection</span></span>

<span data-ttu-id="1b3de-152">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="1b3de-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
