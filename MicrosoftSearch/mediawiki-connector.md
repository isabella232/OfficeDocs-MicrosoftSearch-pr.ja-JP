---
title: Microsoft Search 用の MediaWiki コネクタ
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
description: Microsoft Search 用の MediaWiki コネクタをセットアップする
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367642"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="02917-103">MediaWiki コネクタ</span><span class="sxs-lookup"><span data-stu-id="02917-103">MediaWiki connector</span></span>

<span data-ttu-id="02917-104">MediaWiki コネクタを使用すると、MediaWiki ソフトウェアを使用して作成された wiki から、組織がデータを検出してインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="02917-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="02917-105">このコネクタは、指定されたコンテンツを Microsoft Search にインデックス処理し、定期的なクロールをサポートしてインデックスを最新の状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="02917-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="02917-106">この記事は、Microsoft 365 管理者または、MediaWiki コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="02917-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="02917-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02917-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="02917-108">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="02917-108">Connect to a data source</span></span>

<span data-ttu-id="02917-109">接続を認証するために、MediaWiki の URL と資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="02917-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="02917-110">**テナント ID**、**リソース ID**、**クライアント ID**、**クライアントシークレット** の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="02917-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="02917-111">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="02917-111">Manage search permissions</span></span>

<span data-ttu-id="02917-112">MediaWiki コネクタは、 **すべてのユーザー** に表示される検索アクセス許可のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="02917-112">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="02917-113">インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="02917-113">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="02917-114">プロパティのラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="02917-114">Assign property labels</span></span>

<span data-ttu-id="02917-115">各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="02917-115">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="02917-116">この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="02917-116">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="02917-117">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="02917-117">Manage schema</span></span>

<span data-ttu-id="02917-118">[**スキーマの管理**] 画面で、プロパティに関連付けられているスキーマの属性 (**クエリ** 可能、**検索\*\*\*\*可能、取得可能、および\*\*\*\*絞り込み可能な**) を変更し、オプションのエイリアスを追加して、 **Content** プロパティを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="02917-118">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="02917-119">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="02917-119">Set the refresh schedule</span></span>

<span data-ttu-id="02917-120">このスケジュールによってインデックスが作成されたデータが更新されるので、wiki への変更は Microsoft Search に反映されます。</span><span class="sxs-lookup"><span data-stu-id="02917-120">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="02917-121">新しいページ、削除されたページ、ページコンテンツ、またはメタデータの変更は、指定した更新間隔の後に検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="02917-121">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="02917-122">クロール時間は wiki のサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="02917-122">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="02917-123">現在、コネクタは1分間に50ページ以内にクロールされます。</span><span class="sxs-lookup"><span data-stu-id="02917-123">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="02917-124">制限事項</span><span class="sxs-lookup"><span data-stu-id="02917-124">Limitations</span></span>

<span data-ttu-id="02917-125">MediaWiki コネクタには、次のようなプレビューリリースの制限があります。</span><span class="sxs-lookup"><span data-stu-id="02917-125">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="02917-126">クラウドベースの wiki のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="02917-126">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="02917-127">Azure Active Directory または Azure 認証で基本または OAuth 2.0 のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="02917-127">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="02917-128">インデックス作成のための名前空間の選択をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="02917-128">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="02917-129">インデックスは、 **メイン**、 **カテゴリ**、および **ファイル** の名前空間のみになります。</span><span class="sxs-lookup"><span data-stu-id="02917-129">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="02917-130">は、アクセス制御リスト (Acl) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="02917-130">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="02917-131">そのため、インデックスが作成されたページは、組織内のすべてのユーザーが参照できます。</span><span class="sxs-lookup"><span data-stu-id="02917-131">Thus, indexed pages are visible to all users in the organization.</span></span>
