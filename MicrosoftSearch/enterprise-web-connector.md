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
ms.openlocfilehash: 443e903e0fa371d2a056fd4bf06310eb2627b11c
ms.sourcegitcommit: 031e7c595496d9faed9038725b04f3c8b5f9ccbd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604775"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a><span data-ttu-id="5dc47-103">エンタープライズ web サイトコネクタ</span><span class="sxs-lookup"><span data-stu-id="5dc47-103">Enterprise websites connector</span></span>

<span data-ttu-id="5dc47-104">エンタープライズ web サイトコネクタを使用すると、組織は **内部に接続している web サイトの** 記事とコンテンツにインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5dc47-104">With the Enterprise websites connector, your organization can index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="5dc47-105">コネクタを構成し、web サイトからコンテンツを同期すると、エンドユーザーは任意の Microsoft 検索クライアントからそのコンテンツを検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5dc47-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

<span data-ttu-id="5dc47-106">この記事は、 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理者またはエンタープライズ websites コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="5dc47-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="5dc47-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>  

## <a name="connection-settings"></a><span data-ttu-id="5dc47-108">接続設定</span><span class="sxs-lookup"><span data-stu-id="5dc47-108">Connection settings</span></span>

<span data-ttu-id="5dc47-109">データソースに接続するには、web サイトのルート URL を入力し、クロールソースを選択して、使用する認証の種類を選択する必要があります。これは、 [Azure Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/)を使用した場合は、[なし]、[基本認証]、または OAuth 2.0 です。</span><span class="sxs-lookup"><span data-stu-id="5dc47-109">To connect to your data source, you need to fill in the root URL of the website, select a crawl source, and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="5dc47-110">この情報を入力したら、[接続のテスト] をクリックして設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-110">After you complete this information, click Test Connection to verify your settings.</span></span>

### <a name="url"></a><span data-ttu-id="5dc47-111">URL</span><span class="sxs-lookup"><span data-stu-id="5dc47-111">URL</span></span>

<span data-ttu-id="5dc47-112">[URL] フィールドを使用して、クロールする web サイトのルートを指定します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-112">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="5dc47-113">エンタープライズ web サイトコネクタは、この URL を開始点として使用し、この URL からのすべてのリンクをクロール対象にします。</span><span class="sxs-lookup"><span data-stu-id="5dc47-113">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

### <a name="crawl-mode-cloud-or-on-premises-preview"></a><span data-ttu-id="5dc47-114">クロールモード: クラウドまたはオンプレミス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="5dc47-114">Crawl mode: Cloud or On-premises (Preview)</span></span>

<span data-ttu-id="5dc47-115">クロールモードは、インデックスを作成する web サイトの種類 (クラウドまたはオンプレミス) を決定します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-115">The crawl mode determines the type of websites you want to index, either cloud or on-premises.</span></span> <span data-ttu-id="5dc47-116">クラウドの web サイトでは、クロールモードとして [ **cloud** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-116">For your cloud websites, select **Cloud** as the crawl mode.</span></span>

<span data-ttu-id="5dc47-117">また、コネクタは、オンプレミスの web サイトのクロールをサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="5dc47-117">Also, the connector now supports crawling of on-premises websites.</span></span> <span data-ttu-id="5dc47-118">このモードはプレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="5dc47-118">This mode is in preview.</span></span> <span data-ttu-id="5dc47-119">オンプレミスのデータにアクセスするには、最初に Graph connector エージェントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dc47-119">To access your on-premises data, you must first install and configure the Graph connector agent.</span></span> <span data-ttu-id="5dc47-120">詳細については、「 [Graph connector agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-120">To learn more, see [Graph connector agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).</span></span>

<span data-ttu-id="5dc47-121">オンプレミスの web サイトでは、クロールモードとして [ **エージェント** ] を選択し、オン **プレミスエージェント** フィールドで、以前にインストールして構成した Graph コネクタエージェントを選択します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-121">For your on-premises websites, select **Agent** as the crawl mode and in the **On-Prem Agent** field, choose the Graph connector agent that you installed and configured earlier.</span></span>  

![エンタープライズ Web コネクタの接続設定ウィンドウのスクリーンショット](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a><span data-ttu-id="5dc47-123">認証</span><span class="sxs-lookup"><span data-stu-id="5dc47-123">Authentication</span></span>

<span data-ttu-id="5dc47-124">基本認証には、ユーザー名とパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="5dc47-124">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="5dc47-125">[Microsoft 365 管理センター](https://admin.microsoft.com)を使用して、この bot アカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-125">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="5dc47-126">[AZURE AD](https://docs.microsoft.com/azure/active-directory/)を使用する OAuth 2.0 には、リソース ID、クライアント ID、およびクライアントシークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="5dc47-126">OAuth 2.0 with [Azure AD](https://docs.microsoft.com/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span> <span data-ttu-id="5dc47-127">OAuth 2.0 は、クラウドモードでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-127">OAuth 2.0 only works with Cloud mode.</span></span>

<span data-ttu-id="5dc47-128">詳細については、「 [OAuth 2.0 コード付与フローを使用して Azure Active Directory web アプリケーションへのアクセスを承認する](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-128">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="5dc47-129">次の値を使用して登録します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-129">Register with the following values:</span></span>

<span data-ttu-id="5dc47-130">**Name:** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="5dc47-130">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="5dc47-131">**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="5dc47-131">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="5dc47-132">リソース、client_id、client_secret の値を取得するには、「承認コードを使用して、リダイレクト URL web ページで **アクセストークンを要求** する」に移動します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-132">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="5dc47-133">詳細については、「 [クイックスタート: アプリケーションを Microsoft identity platform に登録する](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-133">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="support-for-robotstxt"></a><span data-ttu-id="5dc47-134">robots.txt のサポート</span><span class="sxs-lookup"><span data-stu-id="5dc47-134">Support for robots.txt</span></span>

<span data-ttu-id="5dc47-135">コネクタは、ルートサイトに robots.txt ファイルがあるかどうかを確認し、存在する場合は、そのファイル内で見つかった指示に従います。</span><span class="sxs-lookup"><span data-stu-id="5dc47-135">The connector checks to see if there is a robots.txt file for your root site and, if one exists, it will follow and respect the directions found within that file.</span></span> <span data-ttu-id="5dc47-136">サイト上の特定のページまたはディレクトリをコネクタでクロールしないようにするには、robots.txt ファイルの "禁止" 宣言にあるページまたはディレクトリを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-136">If you do not want the connector to crawl certain pages or directories on your site, you can call out those pages or directories in the "Disallow" declarations in your robots.txt file.</span></span>

## <a name="add-urls-to-exclude"></a><span data-ttu-id="5dc47-137">除外する Url を追加する</span><span class="sxs-lookup"><span data-stu-id="5dc47-137">Add URLs to exclude</span></span>

<span data-ttu-id="5dc47-138">必要に応じて、コンテンツに機密がある場合やクロール価値がない場合は、一部の Url をクロール対象から除外するように除外 **リスト** を作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5dc47-138">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="5dc47-139">除外リストを作成するには、ルート URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-139">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="5dc47-140">構成プロセス中に、除外された Url をリストに追加するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5dc47-140">You have the option to add the excluded URLs to the list during the configuration process.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="5dc47-141">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="5dc47-141">Manage search permissions</span></span>

<span data-ttu-id="5dc47-142">エンタープライズ web サイトコネクタは、 **すべてのユーザー** に表示される検索アクセス許可のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5dc47-142">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="5dc47-143">インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dc47-143">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="5dc47-144">プロパティのラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5dc47-144">Assign property labels</span></span>

<span data-ttu-id="5dc47-145">各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-145">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="5dc47-146">この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="5dc47-146">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="5dc47-147">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="5dc47-147">Manage schema</span></span>

<span data-ttu-id="5dc47-148">[**スキーマの管理**] 画面で、プロパティに関連付けられているスキーマの属性 (**クエリ** 可能、**検索\*\*\*\*可能、取得可能、および\*\*\*\*絞り込み可能な**) を変更し、オプションのエイリアスを追加して、 **Content** プロパティを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5dc47-148">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="5dc47-149">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="5dc47-149">Set the refresh schedule</span></span>

<span data-ttu-id="5dc47-150">エンタープライズ web サイトコネクタは、完全な更新のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5dc47-150">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="5dc47-151">これは、すべての更新時にコネクタがすべての web サイトのコンテンツを再クロールすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-151">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="5dc47-152">コネクタがコンテンツをクロールするのに十分な時間を確保できるようにするには、更新のスケジュール間隔を大きく設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5dc47-152">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="5dc47-153">スケジュールされた更新は、1週間から2週間の間で行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5dc47-153">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5dc47-154">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5dc47-154">Troubleshooting</span></span>

<span data-ttu-id="5dc47-155">Web サイトのコンテンツを読み取る際に、クロールによってソースエラーが発生することがあります。これは、以下の詳細なエラーコードで表されます。</span><span class="sxs-lookup"><span data-stu-id="5dc47-155">When reading the website's content, the crawl may encounter some source errors, which are represented by the detailed error codes below.</span></span> <span data-ttu-id="5dc47-156">エラーの種類に関する詳細を確認するには、接続を選択した後、[ **エラーの詳細** ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-156">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="5dc47-157">**エラーコード** をクリックして、より詳細なエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-157">Click on the **error code** to see more detailed errors.</span></span> <span data-ttu-id="5dc47-158">詳細については [、「コネクタの管理](https://docs.microsoft.com/microsoftsearch/manage-connector) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-158">Also refer to [Manage your connector](https://docs.microsoft.com/microsoftsearch/manage-connector) to learn more.</span></span>

 <span data-ttu-id="5dc47-159">詳細なエラーコード</span><span class="sxs-lookup"><span data-stu-id="5dc47-159">Detailed Error code</span></span> | <span data-ttu-id="5dc47-160">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="5dc47-160">Error message</span></span>
 --- | ---
 <span data-ttu-id="5dc47-161">6001</span><span class="sxs-lookup"><span data-stu-id="5dc47-161">6001</span></span> | <span data-ttu-id="5dc47-162">インデックスを作成しようとしているサイトに到達できない</span><span class="sxs-lookup"><span data-stu-id="5dc47-162">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="5dc47-163">6005</span><span class="sxs-lookup"><span data-stu-id="5dc47-163">6005</span></span> | <span data-ttu-id="5dc47-164">インデックスを作成しようとしているソースページは robots.txt 構成ごとにブロックされています。</span><span class="sxs-lookup"><span data-stu-id="5dc47-164">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="5dc47-165">6008</span><span class="sxs-lookup"><span data-stu-id="5dc47-165">6008</span></span> | <span data-ttu-id="5dc47-166">DNS を解決できない</span><span class="sxs-lookup"><span data-stu-id="5dc47-166">Unable to resolve the DNS</span></span>
 <span data-ttu-id="5dc47-167">6009</span><span class="sxs-lookup"><span data-stu-id="5dc47-167">6009</span></span> | <span data-ttu-id="5dc47-168">すべてのクライアント側エラー (HTTP 404, 408 を除く) については、「HTTP 4xx エラーコード」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-168">For all client-side errors (Except HTTP 404, 408), refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="5dc47-169">6013</span><span class="sxs-lookup"><span data-stu-id="5dc47-169">6013</span></span> | <span data-ttu-id="5dc47-170">インデックスを作成しようとしているソースページが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="5dc47-170">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="5dc47-171">(HTTP 404 エラー)</span><span class="sxs-lookup"><span data-stu-id="5dc47-171">(HTTP 404 error)</span></span>
 <span data-ttu-id="5dc47-172">6018</span><span class="sxs-lookup"><span data-stu-id="5dc47-172">6018</span></span> | <span data-ttu-id="5dc47-173">ソースページが応答していないため、要求がタイムアウトしました。(HTTP 408 エラー)</span><span class="sxs-lookup"><span data-stu-id="5dc47-173">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="5dc47-174">6021</span><span class="sxs-lookup"><span data-stu-id="5dc47-174">6021</span></span> | <span data-ttu-id="5dc47-175">インデックスを作成しようとしているソースページには、ページ上にテキストコンテンツがありません。</span><span class="sxs-lookup"><span data-stu-id="5dc47-175">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="5dc47-176">6023</span><span class="sxs-lookup"><span data-stu-id="5dc47-176">6023</span></span> | <span data-ttu-id="5dc47-177">インデックスを作成しようとしているソースページはサポートされていません (HTML ページではありません)。</span><span class="sxs-lookup"><span data-stu-id="5dc47-177">The source page that is being tried to index is unsupported (not an HTML page)</span></span>
 <span data-ttu-id="5dc47-178">6024</span><span class="sxs-lookup"><span data-stu-id="5dc47-178">6024</span></span> | <span data-ttu-id="5dc47-179">インデックスを作成しようとしているソースページに、サポートされていないコンテンツがあります。</span><span class="sxs-lookup"><span data-stu-id="5dc47-179">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="5dc47-180">エラー6001-6013 は、ネットワークの問題が原因でデータソースに到達できない場合、またはデータソース自体が削除、移動、または名前変更された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-180">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="5dc47-181">指定したデータソースの詳細が有効であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-181">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="5dc47-182">エラー6021-6024 は、データソースにページ上にテキスト以外のコンテンツが含まれている場合、またはページが HTML ではない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-182">Errors 6021-6024 occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="5dc47-183">データソースを確認し、このページを除外リストに追加するか、エラーを無視します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-183">Check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="5dc47-184">制限事項</span><span class="sxs-lookup"><span data-stu-id="5dc47-184">Limitations</span></span>

<span data-ttu-id="5dc47-185">エンタープライズ web サイトコネクタは、 **動的 web ページ** 上のデータの検索をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5dc47-185">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="5dc47-186">これらの web ページの例は、コンテンツ管理システム ( [Confluence](https://www.atlassian.com/software/confluence) 、 [Unily](https://www.unily.com/) 、web サイトのコンテンツを格納するデータベースなど) に存在します。</span><span class="sxs-lookup"><span data-stu-id="5dc47-186">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5dc47-187">次の手順</span><span class="sxs-lookup"><span data-stu-id="5dc47-187">Next steps</span></span>

<span data-ttu-id="5dc47-188">接続を公開した後、[検索結果] ページをカスタマイズする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dc47-188">After publishing the connection, you need to customize the search results page.</span></span> <span data-ttu-id="5dc47-189">検索結果のカスタマイズについては、「 [検索結果ページをカスタマイズ](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dc47-189">To learn about customizing search results, see [Customize the search results page](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).</span></span>
