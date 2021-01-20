---
title: Microsoft Search 用 MediaWiki コネクタ
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用に MediaWiki コネクタをセットアップする
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905956"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="91ec3-103">MediaWiki コネクタ</span><span class="sxs-lookup"><span data-stu-id="91ec3-103">MediaWiki connector</span></span>

<span data-ttu-id="91ec3-104">MediaWiki コネクタを使用すると、組織は MediaWiki ソフトウェアを使用して作成された Wiki からデータを検出し、インデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="91ec3-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="91ec3-105">このコネクタは、指定されたコンテンツのインデックスを Microsoft Search に作成し、インデックスを最新の状態に保つ定期的なクロールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="91ec3-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="91ec3-106">この記事は、Microsoft 365 管理者または MediaWiki Graph コネクタを構成、実行、および監視するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="91ec3-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="91ec3-107">これは、Graph コネクタのセットアップに関する記事に記載されている一 [般的な手順を補完](configure-connector.md) します。</span><span class="sxs-lookup"><span data-stu-id="91ec3-107">It supplements the general instructions provided in the [Set up your Graph connector](configure-connector.md) article.</span></span> <span data-ttu-id="91ec3-108">まだ設定していない場合は、「Graph コネクタのセットアップ」の記事全体を読んで、一般的なセットアップ プロセスについて理解してください。</span><span class="sxs-lookup"><span data-stu-id="91ec3-108">If you have not already done so, read the entire Set up your Graph connector article to understand the general setup process.</span></span>

<span data-ttu-id="91ec3-109">以下に、セットアップ プロセスの各手順と共に、一般的なセットアップ手順に従う必要があるというメモ、または MediaWiki Graph コネクタにのみ適用されるその他の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="91ec3-109">Each step in the setup process is listed below along with either a note that indicates you should follow the general setup instructions OR other instructions that apply to only MediaWiki Graph connectors.</span></span> <span data-ttu-id="91ec3-110">この記事には、MediaWiki Graph コネクタの制限事項に関する情報も含まれています。 [](#limitations)</span><span class="sxs-lookup"><span data-stu-id="91ec3-110">This article also includes information about [Limitations](#limitations) for MediaWiki Graph connectors.</span></span> 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="91ec3-111">手順 1: Microsoft 365 管理センターで Graph コネクタを追加します。</span><span class="sxs-lookup"><span data-stu-id="91ec3-111">Step 1: Add a Graph connector in the Microsoft 365 admin center.</span></span>
<span data-ttu-id="91ec3-112">一般的なセットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="91ec3-112">Follow the general setup instructions.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="91ec3-113">手順 2: 接続に名前を付けています。</span><span class="sxs-lookup"><span data-stu-id="91ec3-113">Step 2: Name the connection.</span></span>
<span data-ttu-id="91ec3-114">一般的なセットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="91ec3-114">Follow the general setup instructions.</span></span>
 
## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="91ec3-115">手順 3: 接続設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="91ec3-115">Step 3: Configure the connection settings.</span></span>
<span data-ttu-id="91ec3-116">Wiki **URL を入力し** 、 **オプションのドロップダウン** メニューから [認証の種類] を選択します。</span><span class="sxs-lookup"><span data-stu-id="91ec3-116">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="91ec3-117">オプションは **None、Basic、OAuth** **2.0 AAD です**。</span><span class="sxs-lookup"><span data-stu-id="91ec3-117">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="91ec3-118">認証の種類として **[基本** ] を選択した場合は、Wiki の **ユーザー** 名と **パスワードを入力** する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91ec3-118">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="91ec3-119">認証の種類として **OAuth 2.0 AAD** を選択した場合は、Wiki インストールの **リソース ID** を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91ec3-119">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="91ec3-120">また、AAD アプリケーション登録 **ページで生成** されたクライアント **ID** とクライアント シークレットも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91ec3-120">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span> 

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="91ec3-121">手順 4: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="91ec3-121">Step 4: Manage search permissions</span></span>
<span data-ttu-id="91ec3-122">MediaWiki コネクタは、すべてのユーザーに表示される検索アクセス許可のみをサポート **します**。</span><span class="sxs-lookup"><span data-stu-id="91ec3-122">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="91ec3-123">インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="91ec3-123">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="91ec3-124">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="91ec3-124">Step 5: Assign property labels</span></span>
<span data-ttu-id="91ec3-125">一般的なセットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="91ec3-125">Follow the general setup instructions.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="91ec3-126">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="91ec3-126">Step 6: Manage schema</span></span>
<span data-ttu-id="91ec3-127">一般的なセットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="91ec3-127">Follow the general setup instructions.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="91ec3-128">手順 7: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="91ec3-128">Step 7: Choose refresh settings</span></span>
<span data-ttu-id="91ec3-129">一般的なセットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="91ec3-129">Follow the general setup instructions.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="91ec3-130">手順 8: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="91ec3-130">Step 8: Review connection</span></span>
<span data-ttu-id="91ec3-131">一般的なセットアップ手順に従います。</span><span class="sxs-lookup"><span data-stu-id="91ec3-131">Follow the general setup instructions.</span></span>

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="91ec3-132">制限事項</span><span class="sxs-lookup"><span data-stu-id="91ec3-132">Limitations</span></span>
<span data-ttu-id="91ec3-133">MediaWiki コネクタには、プレビュー リリースで次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="91ec3-133">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="91ec3-134">クラウドベースの Wiki のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="91ec3-134">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="91ec3-135">Azure Active Directory または Azure 認証を使用する基本認証または OAuth 2.0 のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="91ec3-135">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="91ec3-136">インデックス作成用の名前空間の選択はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="91ec3-136">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="91ec3-137">Main 名前空間、Category 名前空間、および File 名前空間のみをインデックス化します。</span><span class="sxs-lookup"><span data-stu-id="91ec3-137">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="91ec3-138">アクセス制御リスト (ACL) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="91ec3-138">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="91ec3-139">したがって、インデックス付きページは組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="91ec3-139">Thus, indexed pages are visible to all users in the organization.</span></span>
