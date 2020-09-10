---
title: Microsoft Search 用の MediaWiki コネクタ
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の MediaWiki コネクタをセットアップする
ms.openlocfilehash: b9c8d80ae5cb8e86b0f6341bfe9231b709569e7a
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47423020"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="12254-103">MediaWiki コネクタ</span><span class="sxs-lookup"><span data-stu-id="12254-103">MediaWiki connector</span></span>

<span data-ttu-id="12254-104">MediaWiki コネクタを使用すると、MediaWiki ソフトウェアを使用して作成された wiki から、組織がデータを検出してインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="12254-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="12254-105">このコネクタは、指定されたコンテンツを Microsoft Search にインデックス処理し、定期的なクロールをサポートしてインデックスを最新の状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="12254-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="12254-106">この記事は、Microsoft 365 管理者または、MediaWiki コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="12254-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="12254-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12254-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="12254-108">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="12254-108">Connect to a data source</span></span>

<span data-ttu-id="12254-109">接続を認証するために、MediaWiki の URL と資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="12254-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="12254-110">**テナント ID**、**リソース ID**、**クライアント ID**、**クライアントシークレット**の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="12254-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="12254-111">検索スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="12254-111">Manage the search schema</span></span>

<span data-ttu-id="12254-112">接続が成功した後、検索スキーママッピングを構成します。</span><span class="sxs-lookup"><span data-stu-id="12254-112">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="12254-113">**クエリ**可能、**検索**可能、および取得可能なプロパティを選択でき**ます。**</span><span class="sxs-lookup"><span data-stu-id="12254-113">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="12254-114">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="12254-114">Manage search permissions</span></span>

<span data-ttu-id="12254-115">MediaWiki コネクタは、 **すべてのユーザー**に表示される検索アクセス許可のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="12254-115">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="12254-116">インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="12254-116">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="12254-117">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="12254-117">Set the refresh schedule</span></span>

<span data-ttu-id="12254-118">このスケジュールによってインデックスが作成されたデータが更新されるので、wiki への変更は Microsoft Search に反映されます。</span><span class="sxs-lookup"><span data-stu-id="12254-118">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="12254-119">新しいページ、削除されたページ、ページコンテンツ、またはメタデータの変更は、指定した更新間隔の後に検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="12254-119">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="12254-120">クロール時間は wiki のサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="12254-120">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="12254-121">現在、コネクタは1分間に50ページ以内にクロールされます。</span><span class="sxs-lookup"><span data-stu-id="12254-121">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="12254-122">制限事項</span><span class="sxs-lookup"><span data-stu-id="12254-122">Limitations</span></span>

<span data-ttu-id="12254-123">MediaWiki コネクタには、次のようなプレビューリリースの制限があります。</span><span class="sxs-lookup"><span data-stu-id="12254-123">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="12254-124">クラウドベースの wiki のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="12254-124">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="12254-125">Azure Active Directory または Azure 認証で基本または OAuth 2.0 のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="12254-125">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="12254-126">インデックス作成のための名前空間の選択をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="12254-126">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="12254-127">インデックスは、 **メイン**、 **カテゴリ**、および **ファイル** の名前空間のみになります。</span><span class="sxs-lookup"><span data-stu-id="12254-127">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="12254-128">は、アクセス制御リスト (Acl) をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="12254-128">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="12254-129">そのため、インデックスが作成されたページは、組織内のすべてのユーザーが参照できます。</span><span class="sxs-lookup"><span data-stu-id="12254-129">Thus, indexed pages are visible to all users in the organization.</span></span>
