---
title: Microsoft Search のエンタープライズ Web サイト Graph コネクタ
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
description: Microsoft Search のエンタープライズ Web サイト Graph コネクタをセットアップする
ms.openlocfilehash: 4b8a14b216d7df68d0898bb72d926abe671047a4
ms.sourcegitcommit: 56b7b5aa55413141c805f766bdf7bc63d721ef53
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2021
ms.locfileid: "51951023"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a><span data-ttu-id="dffb8-103">エンタープライズ Web サイト Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="dffb8-103">Enterprise websites Graph connector</span></span>

<span data-ttu-id="dffb8-104">エンタープライズ Web サイトグラフ コネクタを使用すると、組織は内部向け Web サイトから記事やコンテンツ **をインデックス化できます**。</span><span class="sxs-lookup"><span data-stu-id="dffb8-104">The Enterprise websites Graph connector allows your organization to index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="dffb8-105">コネクタを構成し、Web サイトからコンテンツを同期すると、エンド ユーザーは任意の Microsoft Search クライアントからそのコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="dffb8-106">グラフ コネクタ [**のセットアップの一**](configure-connector.md) 般的な手順については、「グラフ コネクタのセットアップ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-106">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="dffb8-107">この記事は、エンタープライズ Web サイト コネクタを構成、実行、および監視するユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="dffb8-107">This article is for anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="dffb8-108">一般的なセットアップ プロセスを補足し、Enterprise Web サイト コネクタにのみ適用される手順を示します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-108">It supplements the general setup process, and shows instructions that apply only for the Enterprise websites connector.</span></span> <span data-ttu-id="dffb8-109">この記事には、トラブルシューティングと [制限事項に関](#troubleshooting) する情報 [も含まれています](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-109">This article also includes information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="dffb8-110">手順 1: Microsoft 365 管理センターに Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="dffb8-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="dffb8-111">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="dffb8-112">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="dffb8-112">Step 2: Name the connection</span></span>

<span data-ttu-id="dffb8-113">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="dffb8-114">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="dffb8-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="dffb8-115">データ ソースに接続するには、Web サイトのルート URL を入力し、クロール ソースを選択し、使用する認証の種類 [(None、Basic Authentication、または](/azure/active-directory/)OAuth 2.0 と Azure Active Directory (Azure AD) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-115">To connect to your data source, you need to fill in the root URL of the website, select a crawl source, and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](/azure/active-directory/).</span></span> <span data-ttu-id="dffb8-116">この情報を完了したら、[接続のテスト] を選択して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-116">After you complete this information, select Test Connection to verify your settings.</span></span>

### <a name="url"></a><span data-ttu-id="dffb8-117">URL</span><span class="sxs-lookup"><span data-stu-id="dffb8-117">URL</span></span>

<span data-ttu-id="dffb8-118">URL フィールドを使用して、クロールする Web サイトのルートを指定します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-118">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="dffb8-119">エンタープライズ Web サイト コネクタは、この URL を開始点として使用し、クロールのためにこの URL からのすべてのリンクに従います。</span><span class="sxs-lookup"><span data-stu-id="dffb8-119">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

> [!NOTE]
> <span data-ttu-id="dffb8-120">クロールするサイトにサイトマップが定義されている場合、コネクタはサイトマップにリストされている URL のみをクロールします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-120">If the site you want to crawl has a sitemap defined, the connector will only crawl the URLs listed in the sitemap.</span></span> <span data-ttu-id="dffb8-121">サイトマップが定義されていない場合、コネクタはサイトのルート URL で見つかったすべてのリンクを深くクロールします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-121">If no sitemap is defined, the connector will do a deep crawl of all the links found on the root URL of the site.</span></span>

### <a name="crawl-mode-cloud-or-on-premises"></a><span data-ttu-id="dffb8-122">クロール モード: クラウドまたはオンプレミス</span><span class="sxs-lookup"><span data-stu-id="dffb8-122">Crawl mode: Cloud or On-premises</span></span>

<span data-ttu-id="dffb8-123">クロール モードは、インデックスを作成する Web サイトの種類 (クラウドまたはオンプレミス) を決定します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-123">The crawl mode determines the type of websites you want to index, either cloud or on-premises.</span></span> <span data-ttu-id="dffb8-124">クラウド Web サイトの場合は、クロール **モードとして [クラウド** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-124">For your cloud websites, select **Cloud** as the crawl mode.</span></span>

<span data-ttu-id="dffb8-125">また、コネクタはオンプレミス Web サイトのクロールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="dffb8-125">Also, the connector now supports crawling of on-premises websites.</span></span> <span data-ttu-id="dffb8-126">オンプレミスのデータにアクセスするには、まず Graph コネクタ エージェントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-126">To access your on-premises data, you must first install and configure the Graph connector agent.</span></span> <span data-ttu-id="dffb8-127">詳細については [、「Graph コネクタ エージェント」を参照してください](./on-prem-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-127">To learn more, see [Graph connector agent](./on-prem-agent.md).</span></span>

<span data-ttu-id="dffb8-128">オンプレミス Web サイトの場合は、クロール モードとして [エージェント] を選択し **、[On-Prem Agent]** フィールドで、前にインストールして構成した Graph コネクタ エージェントを選択します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-128">For your on-premises websites, select **Agent** as the crawl mode and in the **On-Prem Agent** field, choose the Graph connector agent that you installed and configured earlier.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dffb8-129">![Enterprise Web コネクタの [接続設定] ウィンドウのスクリーンショット](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="dffb8-129">![Screenshot of Connection Settings pane for Enterprise Web connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)</span></span>

### <a name="authentication"></a><span data-ttu-id="dffb8-130">認証</span><span class="sxs-lookup"><span data-stu-id="dffb8-130">Authentication</span></span>

<span data-ttu-id="dffb8-131">基本認証には、ユーザー名とパスワードが必要です。</span><span class="sxs-lookup"><span data-stu-id="dffb8-131">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="dffb8-132">Microsoft 365 管理センターを使用して [、このボット アカウントを作成します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-132">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="dffb8-133">Azure サーバーを使用する [OAuth](/azure/active-directory/) 2.0 AD ID、クライアント ID、およびクライアント シークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="dffb8-133">OAuth 2.0 with [Azure AD](/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span> <span data-ttu-id="dffb8-134">OAuth 2.0 はクラウド モードでのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-134">OAuth 2.0 only works with Cloud mode.</span></span>

<span data-ttu-id="dffb8-135">詳細については [、「OAuth 2.0](/azure/active-directory/develop/v1-protocols-oauth-code)コード許可フローを使用して Azure Active Directory Web アプリケーションへのアクセスを承認する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-135">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="dffb8-136">次の値を使用して登録します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-136">Register with the following values:</span></span>

<span data-ttu-id="dffb8-137">**名前:** Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="dffb8-137">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="dffb8-138">**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="dffb8-138">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="dffb8-139">リソース、client_id、client_secretの値を取得するには、「承認コードを使用してリダイレクト URL  Web ページでアクセス トークンを要求する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-139">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="dffb8-140">詳細については、「クイック スタート [: アプリケーションを Microsoft ID プラットフォームに登録する」を参照してください](/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-140">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a><span data-ttu-id="dffb8-141">手順 3a: 除外する URL を追加する (オプションのクロール制限)</span><span class="sxs-lookup"><span data-stu-id="dffb8-141">Step 3a: Add URLs to exclude (Optional crawl restrictions)</span></span>

<span data-ttu-id="dffb8-142">ページがクロールされるのを防ぐ方法は、robots.txt ファイルで禁止するか、除外リストに追加する方法の 2 つがあります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-142">There are two ways to prevent pages from being crawled: disallow them in your robots.txt file or add them to the Exclusion list.</span></span>

### <a name="support-for-robotstxt"></a><span data-ttu-id="dffb8-143">サービスのrobots.txt</span><span class="sxs-lookup"><span data-stu-id="dffb8-143">Support for robots.txt</span></span>

<span data-ttu-id="dffb8-144">コネクタは、ルート サイトの robots.txt ファイルが存在するかどうかを確認し、存在する場合は、そのファイル内で見つかった方向に従って尊重します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-144">The connector checks to see if there is a robots.txt file for your root site and, if one exists, it will follow and respect the directions found within that file.</span></span> <span data-ttu-id="dffb8-145">コネクタでサイト上の特定のページまたはディレクトリをクロールしない場合は、robots.txt ファイルの "Disallow" 宣言でそれらのページまたはディレクトリを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-145">If you do not want the connector to crawl certain pages or directories on your site, you can call out those pages or directories in the "Disallow" declarations in your robots.txt file.</span></span>

### <a name="add-urls-to-exclude"></a><span data-ttu-id="dffb8-146">除外する URL を追加する</span><span class="sxs-lookup"><span data-stu-id="dffb8-146">Add URLs to exclude</span></span>

<span data-ttu-id="dffb8-147">必要に応じて除外リストを作成して、コンテンツが機密性の高い場合やクロールする価値がない場合に、一部の URL をクロールから除外できます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-147">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="dffb8-148">除外リストを作成するには、ルート URL を参照します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-148">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="dffb8-149">構成プロセス中に、除外された URL をリストに追加できます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-149">You can add the excluded URLs to the list during the configuration process.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="dffb8-150">手順 4: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dffb8-150">Step 4: Assign property labels</span></span>

<span data-ttu-id="dffb8-151">各ラベルにソース プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-151">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="dffb8-152">この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果の精度が向上します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-152">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="dffb8-153">手順 5: スキーマの管理</span><span class="sxs-lookup"><span data-stu-id="dffb8-153">Step 5: Manage schema</span></span>

<span data-ttu-id="dffb8-154">[スキーマの **管理**] 画面で、プロパティに関連付けられたスキーマ属性(オプションはクエリ、**検索**、取得、絞り込 **み)** を変更し、オプションのエイリアスを追加し **、Content** プロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-154">On the **Manage Schema** screen, you can change the schema attributes (the options are **Query**, **Search**, **Retrieve**, and **Refine**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="dffb8-155">手順 6: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="dffb8-155">Step 6: Manage search permissions</span></span>

<span data-ttu-id="dffb8-156">エンタープライズ Web サイト コネクタは、Everyone に表示される検索アクセス許可のみを **サポートします**。</span><span class="sxs-lookup"><span data-stu-id="dffb8-156">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="dffb8-157">インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-157">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="dffb8-158">手順 7: 更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="dffb8-158">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="dffb8-159">エンタープライズ Web サイト コネクタは、完全な更新のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-159">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="dffb8-160">つまり、更新の度にコネクタが Web サイトのすべてのコンテンツを再スキャンします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-160">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="dffb8-161">コネクタがコンテンツをクロールするのに十分な時間を取得するには、大規模な更新スケジュール間隔を設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-161">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="dffb8-162">1 ~ 2 週間の間にスケジュールされた更新をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dffb8-162">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="dffb8-163">手順 8: 接続の確認</span><span class="sxs-lookup"><span data-stu-id="dffb8-163">Step 8: Review connection</span></span>

<span data-ttu-id="dffb8-164">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="dffb8-164">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="dffb8-165">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="dffb8-165">Troubleshooting</span></span>

<span data-ttu-id="dffb8-166">Web サイトのコンテンツを読み取る場合、クロールでソース エラーが発生する可能性があります。これは、以下の詳細なエラー コードで表されます。</span><span class="sxs-lookup"><span data-stu-id="dffb8-166">When reading the website's content, the crawl may encounter some source errors, which are represented by the detailed error codes below.</span></span> <span data-ttu-id="dffb8-167">エラーの種類の詳細については、接続を選択した後でエラー **の詳細** ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-167">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="dffb8-168">エラー コード **を選択して** 、詳細なエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-168">Select the **error code** to see more detailed errors.</span></span> <span data-ttu-id="dffb8-169">詳細については、「 [コネクタの管理」](./manage-connector.md) も参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-169">Also refer to [Manage your connector](./manage-connector.md) to learn more.</span></span>

 <span data-ttu-id="dffb8-170">詳細なエラー コード</span><span class="sxs-lookup"><span data-stu-id="dffb8-170">Detailed Error code</span></span> | <span data-ttu-id="dffb8-171">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="dffb8-171">Error message</span></span>
 --- | ---
 <span data-ttu-id="dffb8-172">6001</span><span class="sxs-lookup"><span data-stu-id="dffb8-172">6001</span></span> | <span data-ttu-id="dffb8-173">インデックス作成を試みようとしているサイトに到達できない</span><span class="sxs-lookup"><span data-stu-id="dffb8-173">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="dffb8-174">6005</span><span class="sxs-lookup"><span data-stu-id="dffb8-174">6005</span></span> | <span data-ttu-id="dffb8-175">インデックス作成を試みようとしているソース ページは、構成に基robots.txtされています。</span><span class="sxs-lookup"><span data-stu-id="dffb8-175">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="dffb8-176">6008</span><span class="sxs-lookup"><span data-stu-id="dffb8-176">6008</span></span> | <span data-ttu-id="dffb8-177">DNS を解決できません</span><span class="sxs-lookup"><span data-stu-id="dffb8-177">Unable to resolve the DNS</span></span>
 <span data-ttu-id="dffb8-178">6009</span><span class="sxs-lookup"><span data-stu-id="dffb8-178">6009</span></span> | <span data-ttu-id="dffb8-179">クライアント側のすべてのエラー (HTTP 404、408 を除く) については、HTTP 4xx エラー コードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dffb8-179">For all client-side errors (Except HTTP 404, 408), refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="dffb8-180">6013</span><span class="sxs-lookup"><span data-stu-id="dffb8-180">6013</span></span> | <span data-ttu-id="dffb8-181">インデックス作成を試みようとしているソース ページが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="dffb8-181">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="dffb8-182">(HTTP 404 エラー)</span><span class="sxs-lookup"><span data-stu-id="dffb8-182">(HTTP 404 error)</span></span>
 <span data-ttu-id="dffb8-183">6018</span><span class="sxs-lookup"><span data-stu-id="dffb8-183">6018</span></span> | <span data-ttu-id="dffb8-184">ソース ページが応答していないと、要求がタイム アウトしました。(HTTP 408 エラー)</span><span class="sxs-lookup"><span data-stu-id="dffb8-184">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="dffb8-185">6021</span><span class="sxs-lookup"><span data-stu-id="dffb8-185">6021</span></span> | <span data-ttu-id="dffb8-186">インデックスを作成するソース ページには、ページにテキスト コンテンツはありません。</span><span class="sxs-lookup"><span data-stu-id="dffb8-186">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="dffb8-187">6023</span><span class="sxs-lookup"><span data-stu-id="dffb8-187">6023</span></span> | <span data-ttu-id="dffb8-188">インデックス作成を試みようとしているソース ページはサポートされていません (HTML ページではありません)</span><span class="sxs-lookup"><span data-stu-id="dffb8-188">The source page that is being tried to index is unsupported (not an HTML page)</span></span>
 <span data-ttu-id="dffb8-189">6024</span><span class="sxs-lookup"><span data-stu-id="dffb8-189">6024</span></span> | <span data-ttu-id="dffb8-190">インデックス作成を試みようとしているソース ページには、サポートされていないコンテンツがあります。</span><span class="sxs-lookup"><span data-stu-id="dffb8-190">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="dffb8-191">エラー 6001~6013 は、ネットワークの問題が原因でデータ ソースに到達できない場合、またはデータ ソース自体が削除、移動、または名前変更された場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-191">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="dffb8-192">提供されたデータ ソースの詳細がまだ有効か確認します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-192">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="dffb8-193">エラー 6021-6024 は、データ ソースにページにテキスト以外のコンテンツが含まれている場合、またはページが HTML でない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-193">Errors 6021-6024 occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="dffb8-194">データ ソースを確認し、除外リストにこのページを追加するか、エラーを無視します。</span><span class="sxs-lookup"><span data-stu-id="dffb8-194">Check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="dffb8-195">制限事項</span><span class="sxs-lookup"><span data-stu-id="dffb8-195">Limitations</span></span>

<span data-ttu-id="dffb8-196">エンタープライズ Web サイト コネクタは、動的 Web ページ上のデータの検索 **をサポートされていません**。</span><span class="sxs-lookup"><span data-stu-id="dffb8-196">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="dffb8-197">これらの Web ページの例は [、Confluence](https://www.atlassian.com/software/confluence) や [Unily](https://www.unily.com/) のようなコンテンツ管理システム、または Web サイトのコンテンツを格納するデータベースに含まれています。</span><span class="sxs-lookup"><span data-stu-id="dffb8-197">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>