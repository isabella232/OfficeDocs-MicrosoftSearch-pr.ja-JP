---
title: Microsoft Search 用 MediaWiki Graph コネクタ
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
description: Microsoft Search 用に MediaWiki Graph コネクタをセットアップする
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084985"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="bb1a9-103">MediaWiki Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="bb1a9-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="bb1a9-104">MediaWiki Graph コネクタを使用すると、組織は MediaWiki ソフトウェアを使用して作成された Wiki からデータを検出し、インデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="bb1a9-105">このコネクタは、指定されたコンテンツのインデックスを Microsoft Search に作成し、インデックスを最新の状態に保つ定期的なクロールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="bb1a9-106">Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、Graph コネクタの一般的なセットアップ プロセスを理解してください。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="bb1a9-107">この記事は、ServiceNow Graph コネクタを構成、実行、および監視するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="bb1a9-108">一般的なセットアップ プロセスを補完し、MediaWiki Graph コネクタにのみ適用される手順を示します。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="bb1a9-109">この記事には、制限事項に関する [情報も含まれています](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="bb1a9-110">手順 1: Microsoft 365 管理センターで Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="bb1a9-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="bb1a9-111">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="bb1a9-112">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="bb1a9-112">Step 2: Name the connection</span></span>

<span data-ttu-id="bb1a9-113">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="bb1a9-114">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="bb1a9-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="bb1a9-115">Wiki **URL を入力し** 、 **オプションのドロップダウン** メニューから [認証の種類] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="bb1a9-116">オプションは **None、Basic、OAuth** **2.0 AAD です**。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="bb1a9-117">認証の種類として **[基本** ] を選択した場合は、Wiki の **ユーザー** 名と **パスワードを入力** する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="bb1a9-118">認証の種類として **OAuth 2.0 AAD** を選択する場合は、Wiki インストールの **リソース ID** を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="bb1a9-119">また、[AAD アプリケーションの登録]**ページで** 生成されたクライアント **ID** とクライアント シークレットも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="bb1a9-120">手順 4: 検索権限を管理する</span><span class="sxs-lookup"><span data-stu-id="bb1a9-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="bb1a9-121">MediaWiki コネクタは、すべてのユーザーに表示される検索アクセス許可のみをサポート **します**。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="bb1a9-122">インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="bb1a9-123">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bb1a9-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="bb1a9-124">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-124">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="bb1a9-125">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="bb1a9-125">Step 6: Manage schema</span></span>

<span data-ttu-id="bb1a9-126">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-126">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="bb1a9-127">手順 7: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="bb1a9-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="bb1a9-128">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-128">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="bb1a9-129">手順 8: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="bb1a9-129">Step 8: Review connection</span></span>

<span data-ttu-id="bb1a9-130">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-130">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="bb1a9-131">制限事項</span><span class="sxs-lookup"><span data-stu-id="bb1a9-131">Limitations</span></span>

<span data-ttu-id="bb1a9-132">MediaWiki コネクタには、プレビュー リリースで次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="bb1a9-133">クラウドベースの Wiki のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="bb1a9-134">Azure Active Directory または Azure 認証を使用する基本認証または OAuth 2.0 のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="bb1a9-135">インデックス作成用の名前空間の選択はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="bb1a9-136">Main 名前空間、Category 名前空間、および File 名前空間のみをインデックス化します。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="bb1a9-137">アクセス制御リスト (ACL) をサポートしない。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="bb1a9-138">したがって、インデックス付きページは組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb1a9-138">Thus, indexed pages are visible to all users in the organization.</span></span>
