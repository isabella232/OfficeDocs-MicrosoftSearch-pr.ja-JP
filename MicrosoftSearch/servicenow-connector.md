---
title: Microsoft Search 用の ServiceNow コネクタ
ms.author: mnirkhe
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の ServiceNow コネクタをセットアップする
ms.openlocfilehash: 357722f83e7f276615d231c8d3e56016bc17ba6e
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206961"
---
# <a name="servicenow-connector"></a><span data-ttu-id="12fa0-103">ServiceNow コネクタ</span><span class="sxs-lookup"><span data-stu-id="12fa0-103">ServiceNow connector</span></span>

<span data-ttu-id="12fa0-104">ServiceNow コネクタを使用すると、組織内のすべてのユーザーに表示されるナレッジベースの記事にインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="12fa0-104">With the ServiceNow connector, your organization can index knowledge-base articles that are visible to all users within your organization.</span></span> <span data-ttu-id="12fa0-105">ServiceNow からコネクタとインデックスコンテンツを構成した後は、エンドユーザーは任意の Microsoft 検索クライアントからこれらの記事を検索できます。</span><span class="sxs-lookup"><span data-stu-id="12fa0-105">After you configure the connector and index content from ServiceNow, end users can search for those articles from any Microsoft Search client.</span></span>  

<span data-ttu-id="12fa0-106">この記事は、Microsoft 365 管理者、または ServiceNow コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="12fa0-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a ServiceNow connector.</span></span> <span data-ttu-id="12fa0-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12fa0-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="12fa0-108">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="12fa0-108">Connect to a data source</span></span>

<span data-ttu-id="12fa0-109">ServiceNow データに接続するには、組織の **servicenow インスタンスの URL**、このアカウントの資格情報、および OAuth 認証用のクライアント ID とクライアントシークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="12fa0-109">To connect to your ServiceNow data, you need your organization's **ServiceNow instance URL**, credentials for this account, and the Client ID and Client Secret for OAuth authentication.</span></span>  

<span data-ttu-id="12fa0-110">組織の **ServiceNow インスタンスの URL** は、通常 \*\* &lt; 、https://> service-now.com\*\*のようになります。</span><span class="sxs-lookup"><span data-stu-id="12fa0-110">Your organization’s **ServiceNow instance URL** typically looks like **https://&lt;your-organization-domain>.service-now.com**.</span></span> <span data-ttu-id="12fa0-111">この URL に加えて、ServiceNow への接続を設定するためのアカウントと、更新スケジュールに基づいて、Microsoft Search が ServiceNow から定期的に記事を更新できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12fa0-111">Along with this URL, you will need an account for setting up the connection to ServiceNow as well as for allowing Microsoft Search to periodically update the articles from ServiceNow based on the refresh schedule.</span></span>

<span data-ttu-id="12fa0-112">ServiceNow からコンテンツを認証および同期するには、次の2つのサポートされている方法のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="12fa0-112">To authenticate and sync content from ServiceNow, choose one of two supported methods:</span></span>

 - <span data-ttu-id="12fa0-113">基本認証</span><span class="sxs-lookup"><span data-stu-id="12fa0-113">Basic authentication</span></span>
 - <span data-ttu-id="12fa0-114">OAuth (推奨)</span><span class="sxs-lookup"><span data-stu-id="12fa0-114">OAuth (recommended)</span></span>

> [!Note]
> <span data-ttu-id="12fa0-115">認証に OAuth を使用するには、servicenow 管理者が ServiceNow インスタンスにエンドポイントをプロビジョニングする必要があります。これにより、Microsoft Search アプリがインスタンスにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="12fa0-115">To use OAuth for authentication, a ServiceNow admin needs to provision an endpoint in your ServiceNow instance, so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="12fa0-116">詳細については、「クライアントが ServiceNow ドキュメントの [インスタンスにアクセスするためのエンドポイントを作成する](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12fa0-116">To learn more, see [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in the ServiceNow documentation.</span></span>

<span data-ttu-id="12fa0-117">次の表に、エンドポイント作成フォームに記入する方法についてのガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="12fa0-117">The following table provides guidance on how to fill out the endpoint creation form:</span></span>

<span data-ttu-id="12fa0-118">Field</span><span class="sxs-lookup"><span data-stu-id="12fa0-118">Field</span></span> | <span data-ttu-id="12fa0-119">説明</span><span class="sxs-lookup"><span data-stu-id="12fa0-119">Description</span></span> | <span data-ttu-id="12fa0-120">推奨値</span><span class="sxs-lookup"><span data-stu-id="12fa0-120">Recommended Value</span></span>
--- | --- | ---
<span data-ttu-id="12fa0-121">名前</span><span class="sxs-lookup"><span data-stu-id="12fa0-121">Name</span></span> | <span data-ttu-id="12fa0-122">この一意の値は、OAuth アクセスを必要とするアプリケーションを識別します。</span><span class="sxs-lookup"><span data-stu-id="12fa0-122">This unique value identifies the application that you require OAuth access for.</span></span> | <span data-ttu-id="12fa0-123">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="12fa0-123">Microsoft Search</span></span>
<span data-ttu-id="12fa0-124">クライアント ID</span><span class="sxs-lookup"><span data-stu-id="12fa0-124">Client ID</span></span> | <span data-ttu-id="12fa0-125">読み取り専用で、自動生成されたアプリケーションの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="12fa0-125">A read-only, auto-generated unique ID for the application.</span></span> <span data-ttu-id="12fa0-126">このインスタンスは、アクセストークンを要求するときにクライアント ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="12fa0-126">The instance uses the client ID when it requests an access token.</span></span> | <span data-ttu-id="12fa0-127">該当なし</span><span class="sxs-lookup"><span data-stu-id="12fa0-127">NA</span></span>
<span data-ttu-id="12fa0-128">クライアントシークレット</span><span class="sxs-lookup"><span data-stu-id="12fa0-128">Client secret</span></span> | <span data-ttu-id="12fa0-129">この共有シークレット文字列を使用すると、ServiceNow インスタンスと Microsoft Search は相互に通信を承認します。</span><span class="sxs-lookup"><span data-stu-id="12fa0-129">With this shared secret string, the ServiceNow instance and Microsoft Search authorize communications with each other.</span></span> | <span data-ttu-id="12fa0-130">これをパスワードとして扱うことにより、セキュリティのベストプラクティスに従います。</span><span class="sxs-lookup"><span data-stu-id="12fa0-130">Follow security best-practices by treating this as a password.</span></span>
<span data-ttu-id="12fa0-131">リダイレクト URL</span><span class="sxs-lookup"><span data-stu-id="12fa0-131">Redirect URL</span></span> | <span data-ttu-id="12fa0-132">承認サーバーのリダイレクト先となる必要なコールバック URL。</span><span class="sxs-lookup"><span data-stu-id="12fa0-132">A required callback URL that the authorization server redirects to.</span></span> | https://gcs.office.com/v1.0/admin/oauth/callback
<span data-ttu-id="12fa0-133">ロゴの URL</span><span class="sxs-lookup"><span data-stu-id="12fa0-133">Logo URL</span></span> | <span data-ttu-id="12fa0-134">アプリケーションロゴのイメージを含む URL。</span><span class="sxs-lookup"><span data-stu-id="12fa0-134">A URL that contains the image for the application logo.</span></span> | <span data-ttu-id="12fa0-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="12fa0-135">NA</span></span>
<span data-ttu-id="12fa0-136">Active</span><span class="sxs-lookup"><span data-stu-id="12fa0-136">Active</span></span> | <span data-ttu-id="12fa0-137">アプリケーションレジストリをアクティブにするには、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="12fa0-137">Select the check box to make the application registry active.</span></span> | <span data-ttu-id="12fa0-138">Active に設定</span><span class="sxs-lookup"><span data-stu-id="12fa0-138">Set to active</span></span>
<span data-ttu-id="12fa0-139">トークンの寿命を更新する</span><span class="sxs-lookup"><span data-stu-id="12fa0-139">Refresh token lifespan</span></span> | <span data-ttu-id="12fa0-140">更新トークンが有効になる秒数。</span><span class="sxs-lookup"><span data-stu-id="12fa0-140">The number of seconds that a refresh token is valid.</span></span> <span data-ttu-id="12fa0-141">既定では、更新トークンの有効期限は100日 (864万秒) です。</span><span class="sxs-lookup"><span data-stu-id="12fa0-141">By default, refresh tokens expire in 100 days (8640000 seconds).</span></span> | <span data-ttu-id="12fa0-142">31536000 (1 年)</span><span class="sxs-lookup"><span data-stu-id="12fa0-142">31,536,000 (1 year)</span></span>
<span data-ttu-id="12fa0-143">アクセストークンの寿命</span><span class="sxs-lookup"><span data-stu-id="12fa0-143">Access token lifespan</span></span> | <span data-ttu-id="12fa0-144">アクセストークンの有効期間 (秒数)。</span><span class="sxs-lookup"><span data-stu-id="12fa0-144">The number of seconds that an access token is valid.</span></span> | <span data-ttu-id="12fa0-145">43200 (12 時間)</span><span class="sxs-lookup"><span data-stu-id="12fa0-145">43,200 (12 hours)</span></span>

## <a name="set-a-sync-filter"></a><span data-ttu-id="12fa0-146">同期フィルターを設定する</span><span class="sxs-lookup"><span data-stu-id="12fa0-146">Set a sync filter</span></span>

<span data-ttu-id="12fa0-147">同期フィルターを使用すると、記事を同期するための条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="12fa0-147">With a sync filter, you can specify conditions for syncing articles.</span></span> <span data-ttu-id="12fa0-148">**SQL Select**ステートメントの**where**句のようになります。</span><span class="sxs-lookup"><span data-stu-id="12fa0-148">It's like a **Where** clause in a **SQL Select** statement.</span></span> <span data-ttu-id="12fa0-149">たとえば、公開されていてアクティブな記事のみにインデックスを作成することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="12fa0-149">For example, you can choose to index only articles that are published and active.</span></span> <span data-ttu-id="12fa0-150">[SyncNow の構成] ページには、同期フィルターをキャプチャして設定する方法が記載されています。</span><span class="sxs-lookup"><span data-stu-id="12fa0-150">The SyncNow configuration page describes how to capture and set a sync filter.</span></span>

## <a name="manage-the-search-schema"></a><span data-ttu-id="12fa0-151">検索スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="12fa0-151">Manage the search schema</span></span>

<span data-ttu-id="12fa0-152">接続が成功した後、検索スキーママッピングを構成します。</span><span class="sxs-lookup"><span data-stu-id="12fa0-152">After successful connection, configure the search schema mapping.</span></span> <span data-ttu-id="12fa0-153">**クエリ**可能、**検索**可能、および取得可能なプロパティを選択でき**ます。**</span><span class="sxs-lookup"><span data-stu-id="12fa0-153">You can choose which properties to make **queryable**, **searchable**, and **retrievable**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="12fa0-154">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="12fa0-154">Manage search permissions</span></span>

<span data-ttu-id="12fa0-155">ServiceNow コネクタは、 **すべてのユーザー**に表示される検索アクセス許可のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="12fa0-155">The ServiceNow connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="12fa0-156">インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="12fa0-156">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="12fa0-157">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="12fa0-157">Set the refresh schedule</span></span>

<span data-ttu-id="12fa0-158">ServiceNow コネクタは、フルクロールと増分クロールの両方の更新スケジュールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="12fa0-158">The ServiceNow connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="12fa0-159">両方を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="12fa0-159">We recommend that you set both.</span></span>

<span data-ttu-id="12fa0-160">フルクロールスケジュールは、Microsoft 検索インデックスと同期フィルターから移動したすべての記事に対して以前に同期された削除済み記事を検索します。</span><span class="sxs-lookup"><span data-stu-id="12fa0-160">A full crawl schedule finds deleted articles that were previously synced to the Microsoft Search index and any articles that moved out of the sync filter.</span></span> <span data-ttu-id="12fa0-161">最初に ServiceNow に接続すると、フルクロールが実行され、すべてのナレッジベースの記事が同期されます。</span><span class="sxs-lookup"><span data-stu-id="12fa0-161">When you first connect to ServiceNow, a full crawl runs to sync all the knowledge-base articles.</span></span> <span data-ttu-id="12fa0-162">新しいアイテムを同期し、更新を行うには、増分クロールをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12fa0-162">To sync new items and make updates, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="12fa0-163">推奨される既定値は、フルクロールの場合は1日、増分クロールの場合は4時間です。</span><span class="sxs-lookup"><span data-stu-id="12fa0-163">The recommended default is one day for a full crawl and four hours for an incremental crawl.</span></span>
