---
title: Microsoft Search のエンタープライズ Web サイト Graph コネクタ
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
description: Microsoft Search の Enterprise Web サイト Graph コネクタをセットアップする
ms.openlocfilehash: bf706399ec55fafbe96ce53622ce8502c81c2190
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084886"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a><span data-ttu-id="0ed10-103">エンタープライズ Web サイト Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="0ed10-103">Enterprise websites Graph connector</span></span>

<span data-ttu-id="0ed10-104">Enterprise Websites Graph コネクタを使用すると、組織は内部向け Web サイトの記事やコンテンツに **インデックスを作成できます**。</span><span class="sxs-lookup"><span data-stu-id="0ed10-104">The Enterprise websites Graph connector allows your organization to index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="0ed10-105">コネクタを構成し、Web サイトからコンテンツを同期すると、エンド ユーザーは任意の Microsoft Search クライアントからそのコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="0ed10-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="0ed10-106">Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、一般的な Graph コネクタのセットアップ プロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-106">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="0ed10-107">この記事は、ServiceNow Graph コネクタを構成、実行、および監視するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="0ed10-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="0ed10-108">一般的なセットアップ プロセスを補完し、ServiceNow Graph コネクタにのみ適用する手順を示します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-108">It supplements the general setup process, and shows instructions that apply only for the ServiceNow Graph connector.</span></span> <span data-ttu-id="0ed10-109">この記事には、トラブルシューティングと [制限事項に関する](#troubleshooting) 情報も [含まれています](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="0ed10-109">This article also includes information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0ed10-110">手順 1: Microsoft 365 管理センターで Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="0ed10-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0ed10-111">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0ed10-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="0ed10-112">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="0ed10-112">Step 2: Name the connection</span></span>

<span data-ttu-id="0ed10-113">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0ed10-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="0ed10-114">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="0ed10-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="0ed10-115">データ ソースに接続するには、Web サイトのルート URL を入力し、クロール ソースを選択し、使用する認証の種類 (なし、基本認証、 [または Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/)を使用した OAuth 2.0) を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ed10-115">To connect to your data source, you need to fill in the root URL of the website, select a crawl source, and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/).</span></span> <span data-ttu-id="0ed10-116">この情報を入力したら、[テスト接続] を選択して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-116">After you complete this information, select Test Connection to verify your settings.</span></span>

### <a name="url"></a><span data-ttu-id="0ed10-117">URL</span><span class="sxs-lookup"><span data-stu-id="0ed10-117">URL</span></span>

<span data-ttu-id="0ed10-118">URL フィールドを使用して、クロールする Web サイトのルートを指定します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-118">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="0ed10-119">エンタープライズ Web サイト コネクタは、この URL を開始点として使用し、この URL からのすべてのリンクをクロールに従います。</span><span class="sxs-lookup"><span data-stu-id="0ed10-119">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

### <a name="crawl-mode-cloud-or-on-premises-preview"></a><span data-ttu-id="0ed10-120">クロール モード: クラウドまたはオンプレミス (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0ed10-120">Crawl mode: Cloud or On-premises (Preview)</span></span>

<span data-ttu-id="0ed10-121">クロール モードでは、クラウドまたはオンプレミスのどちらかで、インデックスを作成する Web サイトの種類を決定します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-121">The crawl mode determines the type of websites you want to index, either cloud or on-premises.</span></span> <span data-ttu-id="0ed10-122">クラウド Web サイトの場合は、クロール **モードとして [クラウド** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-122">For your cloud websites, select **Cloud** as the crawl mode.</span></span>

<span data-ttu-id="0ed10-123">また、このコネクタは、オンプレミスの Web サイトのクロールもサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0ed10-123">Also, the connector now supports crawling of on-premises websites.</span></span> <span data-ttu-id="0ed10-124">このモードはプレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="0ed10-124">This mode is in preview.</span></span> <span data-ttu-id="0ed10-125">オンプレミスのデータにアクセスするには、最初に Graph コネクタ エージェントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ed10-125">To access your on-premises data, you must first install and configure the Graph connector agent.</span></span> <span data-ttu-id="0ed10-126">詳細については [、「Graph コネクタ エージェント」を参照してください](https://docs.microsoft.com/microsoftsearch/on-prem-agent)。</span><span class="sxs-lookup"><span data-stu-id="0ed10-126">To learn more, see [Graph connector agent](https://docs.microsoft.com/microsoftsearch/on-prem-agent).</span></span>

<span data-ttu-id="0ed10-127">オンプレミス Web サイトの場合は、クロール モードとして [エージェント]を選択し、[オンプレミス エージェント] フィールドで、前にインストールして構成した Graph コネクタ エージェントを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-127">For your on-premises websites, select **Agent** as the crawl mode and in the **On-Prem Agent** field, choose the Graph connector agent that you installed and configured earlier.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0ed10-128">![エンタープライズ Web コネクタの [接続設定] ウィンドウのスクリーンショット](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="0ed10-128">![Screenshot of Connection Settings pane for Enterprise Web connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)</span></span>

### <a name="authentication"></a><span data-ttu-id="0ed10-129">認証</span><span class="sxs-lookup"><span data-stu-id="0ed10-129">Authentication</span></span>

<span data-ttu-id="0ed10-130">基本認証には、ユーザー名とパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ed10-130">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="0ed10-131">Microsoft 365 管理センターを使用して [、このボット アカウントを作成します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="0ed10-131">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="0ed10-132">Azure ADを使用した OAuth 2.0 には、 [リソース](https://docs.microsoft.com/azure/active-directory/) ID、クライアント ID、およびクライアント シークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ed10-132">OAuth 2.0 with [Azure AD](https://docs.microsoft.com/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span> <span data-ttu-id="0ed10-133">OAuth 2.0 はクラウド モードでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-133">OAuth 2.0 only works with Cloud mode.</span></span>

<span data-ttu-id="0ed10-134">詳細については [、「OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)コード付与フローを使用して Azure Active Directory Web アプリケーションへのアクセスを承認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ed10-134">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="0ed10-135">次の値を使用して登録します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-135">Register with the following values:</span></span>

<span data-ttu-id="0ed10-136">**名前:** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="0ed10-136">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="0ed10-137">**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="0ed10-137">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="0ed10-138">リソース、client_id、および client_secret の値を取得するには、「認証コードを使用して、リダイレクト URL の Web ページでアクセス トークンを要求する」に移動します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-138">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="0ed10-139">詳細については、「クイック スタート: Microsoft ID プラットフォームにアプリケーションを [登録する」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="0ed10-139">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a><span data-ttu-id="0ed10-140">手順 3a: 除外する URL を追加する (オプションのクロール制限)</span><span class="sxs-lookup"><span data-stu-id="0ed10-140">Step 3a: Add URLs to exclude (Optional crawl restrictions)</span></span>

<span data-ttu-id="0ed10-141">ページがクロールされるのを防ぐには、robots.txt ファイルで禁止する方法と除外一覧に追加する方法の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="0ed10-141">There are two ways to prevent pages from being crawled: disallow them in your robots.txt file or add them to the Exclusion list.</span></span>

### <a name="support-for-robotstxt"></a><span data-ttu-id="0ed10-142">サービスのrobots.txt</span><span class="sxs-lookup"><span data-stu-id="0ed10-142">Support for robots.txt</span></span>

<span data-ttu-id="0ed10-143">コネクタは、ルート サイト用の robots.txt ファイルが存在するかどうかを確認し、存在する場合は、そのファイル内で見つかったルート案内に従って従います。</span><span class="sxs-lookup"><span data-stu-id="0ed10-143">The connector checks to see if there is a robots.txt file for your root site and, if one exists, it will follow and respect the directions found within that file.</span></span> <span data-ttu-id="0ed10-144">コネクタでサイト上の特定のページまたはディレクトリをクロールしない場合は、robots.txt ファイルの "Disallow" 宣言でこれらのページまたはディレクトリを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-144">If you do not want the connector to crawl certain pages or directories on your site, you can call out those pages or directories in the "Disallow" declarations in your robots.txt file.</span></span>

### <a name="add-urls-to-exclude"></a><span data-ttu-id="0ed10-145">除外する URL を追加する</span><span class="sxs-lookup"><span data-stu-id="0ed10-145">Add URLs to exclude</span></span>

<span data-ttu-id="0ed10-146">必要に応じて、除外一覧を作成して、そのコンテンツが機密性の高い場合やクロールする価値がない場合に、一部の URL をクロール対象から除外できます。</span><span class="sxs-lookup"><span data-stu-id="0ed10-146">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="0ed10-147">除外一覧を作成するには、ルート URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-147">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="0ed10-148">構成プロセス中に、除外された URL をリストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="0ed10-148">You can add the excluded URLs to the list during the configuration process.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="0ed10-149">手順 4: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="0ed10-149">Step 4: Assign property labels</span></span>

<span data-ttu-id="0ed10-150">オプションのメニューから選択すると、ソース プロパティを各ラベルに割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="0ed10-150">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="0ed10-151">この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-151">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="0ed10-152">手順 5: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="0ed10-152">Step 5: Manage schema</span></span>

<span data-ttu-id="0ed10-153">[スキーマ **の管理**] 画面では、プロパティに関連付けられているスキーマ属性(クエリ、**検索**、**取得**、絞り込み **オプション)** を変更し、オプションのエイリアスを追加して **、Content** プロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ed10-153">On the **Manage Schema** screen, you can change the schema attributes (the options are **Query**, **Search**, **Retrieve**, and **Refine**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="0ed10-154">手順 6: 検索権限を管理する</span><span class="sxs-lookup"><span data-stu-id="0ed10-154">Step 6: Manage search permissions</span></span>

<span data-ttu-id="0ed10-155">エンタープライズ Web サイト コネクタは、すべてのユーザーに表示される検索アクセス許可のみをサポート **します**。</span><span class="sxs-lookup"><span data-stu-id="0ed10-155">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="0ed10-156">インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ed10-156">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="0ed10-157">手順 7: 更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="0ed10-157">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="0ed10-158">エンタープライズ Web サイト コネクタは、完全な更新のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0ed10-158">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="0ed10-159">つまり、コネクタは更新の間に Web サイトのすべてのコンテンツを再スキャンします。</span><span class="sxs-lookup"><span data-stu-id="0ed10-159">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="0ed10-160">コネクタがコンテンツをクロールするのに十分な時間を取得するには、大規模な更新スケジュール間隔を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ed10-160">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="0ed10-161">1 週間から 2 週間の間にスケジュールされた更新をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ed10-161">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="0ed10-162">手順 8: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="0ed10-162">Step 8: Review connection</span></span>

<span data-ttu-id="0ed10-163">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="0ed10-163">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="0ed10-164">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0ed10-164">Troubleshooting</span></span>

<span data-ttu-id="0ed10-165">Web サイトのコンテンツを読み取る際に、クロールでソース エラーが発生する場合があります。これは、以下の詳細なエラー コードで表されます。</span><span class="sxs-lookup"><span data-stu-id="0ed10-165">When reading the website's content, the crawl may encounter some source errors, which are represented by the detailed error codes below.</span></span> <span data-ttu-id="0ed10-166">エラーの種類に関する詳細を取得するには、接続を **選択した後** 、エラーの詳細ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-166">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="0ed10-167">エラー コード **を選択すると** 、より詳細なエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ed10-167">Select the **error code** to see more detailed errors.</span></span> <span data-ttu-id="0ed10-168">詳細については、「 [コネクタの管理」](https://docs.microsoft.com/microsoftsearch/manage-connector) も参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ed10-168">Also refer to [Manage your connector](https://docs.microsoft.com/microsoftsearch/manage-connector) to learn more.</span></span>

 <span data-ttu-id="0ed10-169">詳細なエラー コード</span><span class="sxs-lookup"><span data-stu-id="0ed10-169">Detailed Error code</span></span> | <span data-ttu-id="0ed10-170">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="0ed10-170">Error message</span></span>
 --- | ---
 <span data-ttu-id="0ed10-171">6001</span><span class="sxs-lookup"><span data-stu-id="0ed10-171">6001</span></span> | <span data-ttu-id="0ed10-172">インデックス作成を試みたサイトに到達できません</span><span class="sxs-lookup"><span data-stu-id="0ed10-172">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="0ed10-173">6005</span><span class="sxs-lookup"><span data-stu-id="0ed10-173">6005</span></span> | <span data-ttu-id="0ed10-174">インデックス作成を試みようとしているソース ページは、構成に基robots.txtされています。</span><span class="sxs-lookup"><span data-stu-id="0ed10-174">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="0ed10-175">6008</span><span class="sxs-lookup"><span data-stu-id="0ed10-175">6008</span></span> | <span data-ttu-id="0ed10-176">DNS を解決できません</span><span class="sxs-lookup"><span data-stu-id="0ed10-176">Unable to resolve the DNS</span></span>
 <span data-ttu-id="0ed10-177">6009</span><span class="sxs-lookup"><span data-stu-id="0ed10-177">6009</span></span> | <span data-ttu-id="0ed10-178">クライアント側のすべてのエラー (HTTP 404、408 を除く) の詳細については、HTTP 4xx エラー コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ed10-178">For all client-side errors (Except HTTP 404, 408), refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="0ed10-179">6013</span><span class="sxs-lookup"><span data-stu-id="0ed10-179">6013</span></span> | <span data-ttu-id="0ed10-180">インデックスを作成しようとしたソース ページが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="0ed10-180">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="0ed10-181">(HTTP 404 エラー)</span><span class="sxs-lookup"><span data-stu-id="0ed10-181">(HTTP 404 error)</span></span>
 <span data-ttu-id="0ed10-182">6018</span><span class="sxs-lookup"><span data-stu-id="0ed10-182">6018</span></span> | <span data-ttu-id="0ed10-183">ソース ページが応答していないので、要求がタイム アウトしました。(HTTP 408 エラー)</span><span class="sxs-lookup"><span data-stu-id="0ed10-183">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="0ed10-184">6021</span><span class="sxs-lookup"><span data-stu-id="0ed10-184">6021</span></span> | <span data-ttu-id="0ed10-185">インデックスを作成しようとしたソース ページには、ページ上にテキスト コンテンツはありません。</span><span class="sxs-lookup"><span data-stu-id="0ed10-185">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="0ed10-186">6023</span><span class="sxs-lookup"><span data-stu-id="0ed10-186">6023</span></span> | <span data-ttu-id="0ed10-187">インデックスを作成しようとしたソース ページがサポートされていません (HTML ページではありません)</span><span class="sxs-lookup"><span data-stu-id="0ed10-187">The source page that is being tried to index is unsupported (not an HTML page)</span></span>
 <span data-ttu-id="0ed10-188">6024</span><span class="sxs-lookup"><span data-stu-id="0ed10-188">6024</span></span> | <span data-ttu-id="0ed10-189">インデックス作成を試みようとしているソース ページに、サポートされていないコンテンツがあります。</span><span class="sxs-lookup"><span data-stu-id="0ed10-189">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="0ed10-190">ネットワークの問題が原因でデータ ソースに到達できない場合、またはデータ ソース自体が削除、移動、または名前変更された場合に、エラー 6001 から 6013 が発生します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-190">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="0ed10-191">指定されたデータ ソースの詳細がまだ有効な場合に確認します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-191">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="0ed10-192">エラー 6021 から 6024 は、データ ソースにページにテキスト以外のコンテンツが含まれている場合、またはページが HTML ではない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-192">Errors 6021-6024 occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="0ed10-193">データ ソースを確認し、除外一覧にこのページを追加するか、エラーを無視します。</span><span class="sxs-lookup"><span data-stu-id="0ed10-193">Check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="0ed10-194">制限事項</span><span class="sxs-lookup"><span data-stu-id="0ed10-194">Limitations</span></span>

<span data-ttu-id="0ed10-195">エンタープライズ Web サイト コネクタは、動的 Web ページ上のデータの検索 **をサポートしています**。</span><span class="sxs-lookup"><span data-stu-id="0ed10-195">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="0ed10-196">これらの Web ページの例は [、Confluence](https://www.atlassian.com/software/confluence) や [Unily](https://www.unily.com/) のようなコンテンツ管理システム、または Web サイトコンテンツを格納するデータベースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ed10-196">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>