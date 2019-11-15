---
title: Microsoft Search のエンタープライズ Web サイトコネクタ
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search のエンタープライズ web サイトコネクタを設定する
ms.openlocfilehash: c2495487b24b11512a182434f72a90044a439d5d
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626275"
---
# <a name="enterprise-websites-connector"></a><span data-ttu-id="8a35d-103">エンタープライズ web サイトコネクタ</span><span class="sxs-lookup"><span data-stu-id="8a35d-103">Enterprise websites connector</span></span>

<span data-ttu-id="8a35d-104">エンタープライズ web サイトコネクタを使用すると、組織は**内部に接続している web サイトの**記事とコンテンツにインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8a35d-104">With the Enterprise websites connector, your organization can index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="8a35d-105">コネクタを構成し、web サイトからコンテンツを同期すると、エンドユーザーは任意の Microsoft 検索クライアントからそのコンテンツを検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8a35d-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

<span data-ttu-id="8a35d-106">この記事は、Microsoft 365 管理者またはエンタープライズ websites コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="8a35d-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="8a35d-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8a35d-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="8a35d-108">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="8a35d-108">Connect to a data source</span></span> 
<span data-ttu-id="8a35d-109">データソースに接続するには、ルート URL と認証の形式 (Azure AD を使用する基本認証または OAuth 2.0) が必要です。</span><span class="sxs-lookup"><span data-stu-id="8a35d-109">To connect to your data source, you need your root URL and a form of authentication (Basic Authentication or OAuth 2.0 with Azure AD).</span></span>

### <a name="root-url"></a><span data-ttu-id="8a35d-110">ルート URL</span><span class="sxs-lookup"><span data-stu-id="8a35d-110">Root URL</span></span>
<span data-ttu-id="8a35d-111">ルート URL は、クロールを開始するもので、認証に使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a35d-111">The root URL is what initiates the crawl and is used for authentication.</span></span> <span data-ttu-id="8a35d-112">クロールする web サイトのホームページから URL を取得できます。</span><span class="sxs-lookup"><span data-stu-id="8a35d-112">You can get the URL from the home page of the website you want to crawl.</span></span>

### <a name="authentication"></a><span data-ttu-id="8a35d-113">認証</span><span class="sxs-lookup"><span data-stu-id="8a35d-113">Authentication</span></span> 
<span data-ttu-id="8a35d-114">基本認証には、ユーザー名とパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a35d-114">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="8a35d-115">[Microsoft 365 管理センター](https://admin.microsoft.com)を使用して、この bot アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="8a35d-115">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="8a35d-116">Azure AD を使用する OAuth 2.0 には、テナント ID、リソース ID、クライアント ID、およびクライアントシークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="8a35d-116">OAuth 2.0 with Azure AD requires a tenant ID, resource ID, Client ID, and Client Secret.</span></span>
<span data-ttu-id="8a35d-117">詳細については、「 [OAuth 2.0 コード付与フローを使用して Azure Active Directory web アプリケーションへのアクセスを承認する](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a35d-117">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="8a35d-118">次の値を使用して登録します。</span><span class="sxs-lookup"><span data-stu-id="8a35d-118">Register with the following values:</span></span>
* <span data-ttu-id="8a35d-119">**Name:** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="8a35d-119">**Name:** Microsoft Search</span></span>
* <span data-ttu-id="8a35d-120">**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="8a35d-120">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="8a35d-121">名前付きテナント、リソース、client_id、client_secret の値を取得するには、「承認コードを使用して、リダイレクト URL web ページで**アクセストークンを要求**します。</span><span class="sxs-lookup"><span data-stu-id="8a35d-121">To get the values for named tenant, resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="8a35d-122">詳細については、「[クイックスタート: アプリケーションを Microsoft identity platform に登録する](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a35d-122">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

### <a name="reverse-proxy-url"></a><span data-ttu-id="8a35d-123">リバースプロキシの URL</span><span class="sxs-lookup"><span data-stu-id="8a35d-123">Reverse proxy URL</span></span> 
<span data-ttu-id="8a35d-124">エンタープライズ web サイトコネクタはクラウドベースであるため、オンプレミスのコンテンツにはアクセスしません。</span><span class="sxs-lookup"><span data-stu-id="8a35d-124">The Enterprise websites connector is cloud-based, so it doesn't access on-premises content.</span></span> <span data-ttu-id="8a35d-125">そのアクセスを提供するには、リバースプロキシをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8a35d-125">To provide that access, install a reverse proxy.</span></span> <span data-ttu-id="8a35d-126">リバースプロキシは、オンプレミスの web サイトへの安全で信頼できるアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a35d-126">A reverse proxy provides secure, reliable access to on-premises websites.</span></span> <span data-ttu-id="8a35d-127">Azure アプリケーションプロキシ (AAP) をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8a35d-127">We recommend Azure Application Proxy (AAP).</span></span>

<span data-ttu-id="8a35d-128">ルート URL と認証のリバースプロキシの要件は、クラウドベースのコンテンツの場合と同じですが、ルート URL と認証はリバースプロキシサーバーによって提供される点が異なります。</span><span class="sxs-lookup"><span data-stu-id="8a35d-128">The reverse proxy requirement for root URL and authentication is the same as for cloud-based content except that the root URL and authentication are provided by the reverse proxy server.</span></span>

<span data-ttu-id="8a35d-129">[AZURE AD アプリケーションプロキシを使用してリモートでアプリにアクセスする場合のセキュリティに関する考慮事項を](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security)参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a35d-129">See [Security considerations for accessing apps remotely with Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security).</span></span>

## <a name="select-the-source-properties"></a><span data-ttu-id="8a35d-130">ソースのプロパティを選択する</span><span class="sxs-lookup"><span data-stu-id="8a35d-130">Select the source properties</span></span> 
<span data-ttu-id="8a35d-131">ソースのプロパティは、エンタープライズ web サイトのデータ形式に基づいて定義されます。</span><span class="sxs-lookup"><span data-stu-id="8a35d-131">Source properties are defined based on the data format of the enterprise website.</span></span> <span data-ttu-id="8a35d-132">ただし、コンテンツが機密である場合やクロールに価値がない場合があるため、一部の Url をクロール対象から除外する除外**リスト**を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8a35d-132">However you can create an **Exclusion list** to exclude some URLs from getting crawled since that content might be sensitive or not worth crawling.</span></span> <span data-ttu-id="8a35d-133">除外リストを作成するには、ルート URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="8a35d-133">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="8a35d-134">構成プロセス中に、除外された Url をリストに追加するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="8a35d-134">You have the option to add the excluded URLs to the list during the configuration process.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="8a35d-135">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="8a35d-135">Manage search permissions</span></span> 
<span data-ttu-id="8a35d-136">アクセス制御リスト (Acl) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="8a35d-136">There is no support for Access Control Lists (ACLs).</span></span> <span data-ttu-id="8a35d-137">そのため、組織内のどのユーザーにも表示されている web サイトのみを接続することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8a35d-137">Thus, it is advised to connect only the websites that are visible to any user within your organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="8a35d-138">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="8a35d-138">Set the refresh schedule</span></span>
<span data-ttu-id="8a35d-139">エンタープライズ web サイトコネクタは、フルクロールのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8a35d-139">The Enterprise websites connector only supports a full crawl.</span></span> <span data-ttu-id="8a35d-140">これは、すべてのクロール中にコネクタがすべての web サイトのコンテンツを読み取ることを意味します。</span><span class="sxs-lookup"><span data-stu-id="8a35d-140">This means that the connector reads all the website's content during every crawl.</span></span> <span data-ttu-id="8a35d-141">コネクタがコンテンツを読み取るのに十分な時間がかかることを確認するには、更新スケジュールの間隔を長く設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8a35d-141">To make sure the connector gets enough time to read the content, it is recommended to set a large refresh schedule interval.</span></span> <span data-ttu-id="8a35d-142">更新スケジュールは3日から2週間にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8a35d-142">We recommend a scheduled refresh between three days and two weeks.</span></span>

## <a name="limitations"></a><span data-ttu-id="8a35d-143">制限事項</span><span class="sxs-lookup"><span data-stu-id="8a35d-143">Limitations</span></span> 
<span data-ttu-id="8a35d-144">エンタープライズ web サイトコネクタは、動的 web ページ上のデータの検索をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="8a35d-144">The Enterprise websites connector doesn't support searching data on dynamic webpages.</span></span> <span data-ttu-id="8a35d-145">これらの web ページの例は、コンテンツ管理システム (Confluence、Unily、web サイトのコンテンツを格納するデータベースなど) に存在します。</span><span class="sxs-lookup"><span data-stu-id="8a35d-145">Examples of those webpages live in content management systems like Confluence and Unily or databases that store website content.</span></span>