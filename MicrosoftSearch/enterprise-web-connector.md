---
title: Microsoft Search のエンタープライズ Web サイトコネクタ
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
description: Microsoft Search のエンタープライズ web サイトコネクタを設定する
ms.openlocfilehash: 4b9d8a8472c81c2bc647b3cef3cdb437073d36cf
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367471"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a><span data-ttu-id="1aaf6-103">エンタープライズ web サイトコネクタ</span><span class="sxs-lookup"><span data-stu-id="1aaf6-103">Enterprise websites connector</span></span>

<span data-ttu-id="1aaf6-104">エンタープライズ web サイトコネクタを使用すると、組織は **内部に接続している web サイトの** 記事とコンテンツにインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-104">With the Enterprise websites connector, your organization can index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="1aaf6-105">コネクタを構成し、web サイトからコンテンツを同期すると、エンドユーザーは任意の Microsoft 検索クライアントからそのコンテンツを検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

<span data-ttu-id="1aaf6-106">この記事は、 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理者またはエンタープライズ websites コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="1aaf6-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="1aaf6-108">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="1aaf6-108">Connect to a data source</span></span>

<span data-ttu-id="1aaf6-109">データソースに接続するには、web サイトのルート URL と、使用する認証の種類を設定する必要があります。これには、 [Azure Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/)を使用した、[なし]、[基本認証]、または OAuth 2.0 があります。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-109">To connect to your data source, you need to fill in the root URL of the website and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).</span></span>

### <a name="url"></a><span data-ttu-id="1aaf6-110">URL</span><span class="sxs-lookup"><span data-stu-id="1aaf6-110">URL</span></span>

<span data-ttu-id="1aaf6-111">[URL] フィールドを使用して、クロールする web サイトのルートを指定します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-111">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="1aaf6-112">エンタープライズ web サイトコネクタは、この URL を開始点として使用し、この URL からのすべてのリンクをクロール対象にします。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-112">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

### <a name="authentication"></a><span data-ttu-id="1aaf6-113">認証</span><span class="sxs-lookup"><span data-stu-id="1aaf6-113">Authentication</span></span>

<span data-ttu-id="1aaf6-114">基本認証には、ユーザー名とパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-114">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="1aaf6-115">[Microsoft 365 管理センター](https://admin.microsoft.com)を使用して、この bot アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-115">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="1aaf6-116">[AZURE AD](https://docs.microsoft.com/azure/active-directory/)を使用する OAuth 2.0 には、リソース ID、クライアント ID、およびクライアントシークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-116">OAuth 2.0 with [Azure AD](https://docs.microsoft.com/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span>

<span data-ttu-id="1aaf6-117">詳細については、「 [OAuth 2.0 コード付与フローを使用して Azure Active Directory web アプリケーションへのアクセスを承認する](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-117">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="1aaf6-118">次の値を使用して登録します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-118">Register with the following values:</span></span>

<span data-ttu-id="1aaf6-119">**Name:** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="1aaf6-119">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="1aaf6-120">**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="1aaf6-120">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="1aaf6-121">リソース、client_id、client_secret の値を取得するには、「承認コードを使用して、リダイレクト URL web ページで **アクセストークンを要求** する」に移動します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-121">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="1aaf6-122">詳細については、「 [クイックスタート: アプリケーションを Microsoft identity platform に登録する](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-122">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="add-urls-to-exclude"></a><span data-ttu-id="1aaf6-123">除外する Url を追加する</span><span class="sxs-lookup"><span data-stu-id="1aaf6-123">Add URLs to exclude</span></span>

<span data-ttu-id="1aaf6-124">必要に応じて、コンテンツに機密がある場合やクロール価値がない場合は、一部の Url をクロール対象から除外するように除外 **リスト** を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-124">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="1aaf6-125">除外リストを作成するには、ルート URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-125">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="1aaf6-126">構成プロセス中に、除外された Url をリストに追加するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-126">You have the option to add the excluded URLs to the list during the configuration process.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="1aaf6-127">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="1aaf6-127">Manage search permissions</span></span>

<span data-ttu-id="1aaf6-128">エンタープライズ web サイトコネクタは、 **すべてのユーザー** に表示される検索アクセス許可のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-128">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="1aaf6-129">インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-129">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="1aaf6-130">プロパティのラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="1aaf6-130">Assign property labels</span></span>

<span data-ttu-id="1aaf6-131">各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-131">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="1aaf6-132">この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-132">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="1aaf6-133">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="1aaf6-133">Manage schema</span></span>

<span data-ttu-id="1aaf6-134">[**スキーマの管理**] 画面で、プロパティに関連付けられているスキーマの属性 (**クエリ** 可能、**検索\*\*\*\*可能、取得可能、および\*\*\*\*絞り込み可能な**) を変更し、オプションのエイリアスを追加して、 **Content** プロパティを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-134">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="1aaf6-135">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="1aaf6-135">Set the refresh schedule</span></span>

<span data-ttu-id="1aaf6-136">エンタープライズ web サイトコネクタは、完全な更新のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-136">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="1aaf6-137">これは、すべての更新時にコネクタがすべての web サイトのコンテンツを再クロールすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-137">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="1aaf6-138">コネクタがコンテンツをクロールするのに十分な時間を確保できるようにするには、更新のスケジュール間隔を大きく設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-138">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="1aaf6-139">スケジュールされた更新は、1週間から2週間の間で行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-139">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1aaf6-140">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="1aaf6-140">Troubleshooting</span></span>

<span data-ttu-id="1aaf6-141">Web サイトのコンテンツを読み取るときに、以下の詳細なエラーコードで示されているソースエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-141">When reading the website's content, the crawl may encounter some source errors which are represented by the detailed error codes below.</span></span> <span data-ttu-id="1aaf6-142">エラーの種類に関する詳細を確認するには、接続を選択した後、[ **エラーの詳細** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-142">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="1aaf6-143">**エラーコード** をクリックして、より詳細なエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-143">Click on the **error code** to see more detailed errors.</span></span> <span data-ttu-id="1aaf6-144">詳細については [、「コネクタの管理](https://docs.microsoft.com/microsoftsearch/manage-connector) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-144">Also refer to [Manage your connector](https://docs.microsoft.com/microsoftsearch/manage-connector) to learn more.</span></span>

 <span data-ttu-id="1aaf6-145">詳細なエラーコード</span><span class="sxs-lookup"><span data-stu-id="1aaf6-145">Detailed Error code</span></span> | <span data-ttu-id="1aaf6-146">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="1aaf6-146">Error message</span></span>
 --- | ---
 <span data-ttu-id="1aaf6-147">6001</span><span class="sxs-lookup"><span data-stu-id="1aaf6-147">6001</span></span> | <span data-ttu-id="1aaf6-148">インデックスを作成しようとしているサイトに到達できない</span><span class="sxs-lookup"><span data-stu-id="1aaf6-148">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="1aaf6-149">6005</span><span class="sxs-lookup"><span data-stu-id="1aaf6-149">6005</span></span> | <span data-ttu-id="1aaf6-150">インデックスを作成しようとしているソースページは robots.txt 構成ごとにブロックされています。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-150">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="1aaf6-151">6008</span><span class="sxs-lookup"><span data-stu-id="1aaf6-151">6008</span></span> | <span data-ttu-id="1aaf6-152">DNS を解決できない</span><span class="sxs-lookup"><span data-stu-id="1aaf6-152">Unable to resolve the DNS</span></span>
 <span data-ttu-id="1aaf6-153">6009</span><span class="sxs-lookup"><span data-stu-id="1aaf6-153">6009</span></span> | <span data-ttu-id="1aaf6-154">すべてのクライアント側エラー (HTTP 404、408を除く) については、「HTTP 4xx エラーコード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-154">For all client side errors (Except HTTP 404, 408), please refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="1aaf6-155">6013</span><span class="sxs-lookup"><span data-stu-id="1aaf6-155">6013</span></span> | <span data-ttu-id="1aaf6-156">インデックスを作成しようとしているソースページが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-156">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="1aaf6-157">(HTTP 404 エラー)</span><span class="sxs-lookup"><span data-stu-id="1aaf6-157">(HTTP 404 error)</span></span>
 <span data-ttu-id="1aaf6-158">6018</span><span class="sxs-lookup"><span data-stu-id="1aaf6-158">6018</span></span> | <span data-ttu-id="1aaf6-159">ソースページが応答していないため、要求がタイムアウトしました。(HTTP 408 エラー)</span><span class="sxs-lookup"><span data-stu-id="1aaf6-159">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="1aaf6-160">6021</span><span class="sxs-lookup"><span data-stu-id="1aaf6-160">6021</span></span> | <span data-ttu-id="1aaf6-161">インデックスを作成しようとしているソースページには、ページ上にテキストコンテンツがありません。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-161">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="1aaf6-162">6023</span><span class="sxs-lookup"><span data-stu-id="1aaf6-162">6023</span></span> | <span data-ttu-id="1aaf6-163">インデックスを作成しようとしているソースページはサポートされていません (HTML ページではありません)。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-163">The source page that is being tried to index is unsupported (not a HTML page)</span></span>
 <span data-ttu-id="1aaf6-164">6024</span><span class="sxs-lookup"><span data-stu-id="1aaf6-164">6024</span></span> | <span data-ttu-id="1aaf6-165">インデックスを作成しようとしているソースページに、サポートされていないコンテンツがあります。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-165">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="1aaf6-166">エラー6001-6013 は、ネットワークの問題が原因でデータソースに到達できない場合、またはデータソース自体が削除、移動、または名前変更された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-166">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="1aaf6-167">指定したデータソースの詳細が有効であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-167">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="1aaf6-168">エラー6021-6024 データソースにページ上にテキスト以外のコンテンツが含まれている場合、またはページが HTML ではない場合にエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-168">Errors 6021-6024 error occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="1aaf6-169">データソースを確認し、このページを除外リストに追加するか、エラーを無視してください。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-169">Please check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="1aaf6-170">制限事項</span><span class="sxs-lookup"><span data-stu-id="1aaf6-170">Limitations</span></span>

<span data-ttu-id="1aaf6-171">エンタープライズ web サイトコネクタは、 **動的 web ページ** 上のデータの検索をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-171">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="1aaf6-172">これらの web ページの例は、コンテンツ管理システム ( [Confluence](https://www.atlassian.com/software/confluence) 、 [Unily](https://www.unily.com/) 、web サイトのコンテンツを格納するデータベースなど) に存在します。</span><span class="sxs-lookup"><span data-stu-id="1aaf6-172">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>
