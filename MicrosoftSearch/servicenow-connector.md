---
title: Microsoft Search の ServiceNow Graph コネクタ
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
description: Microsoft Search の ServiceNow Graph コネクタをセットアップする
ms.openlocfilehash: d1fdfb5f1aec5091fd526152de2bdc86932cfdb9
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084895"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a><span data-ttu-id="e5f68-103">ServiceNow Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="e5f68-103">ServiceNow Graph Connector</span></span>

<span data-ttu-id="e5f68-104">ServiceNow Graph コネクタを使用すると、組織内のユーザー条件のアクセス許可に従って、ユーザーに表示されるナレッジ ベースの記事のインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-104">The ServiceNow Graph connector allows your organization to index knowledge-based articles visible to users according to the user criteria permissions within your organization.</span></span> <span data-ttu-id="e5f68-105">ServiceNow からコネクタとインデックス コンテンツを構成すると、ユーザーは任意の Microsoft Search クライアントから記事を検索できます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-105">After you configure the connector and index content from ServiceNow, users can search for the articles from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="e5f68-106">Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、Graph コネクタの一般的なセットアップ プロセスを理解してください。</span><span class="sxs-lookup"><span data-stu-id="e5f68-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="e5f68-107">この記事は、ServiceNow Graph コネクタを構成、実行、および監視するユーザーを対象にしています。</span><span class="sxs-lookup"><span data-stu-id="e5f68-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="e5f68-108">一般的なセットアップ プロセスを補完し、ServiceNow Graph コネクタにのみ適用される手順を示します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-108">It supplements the general setup process, and shows instructions that apply to only for the ServiceNow Graph connector.</span></span> <span data-ttu-id="e5f68-109">この記事には、トラブルシューティングと [制限事項に関する](#troubleshooting) 情報も [含まれています](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-109">This article also includes information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e5f68-110">手順 1: Microsoft 365 管理センターで Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="e5f68-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="e5f68-111">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="e5f68-112">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="e5f68-112">Step 2: Name the connection</span></span>

<span data-ttu-id="e5f68-113">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a><span data-ttu-id="e5f68-114">手順 3: 接続設定</span><span class="sxs-lookup"><span data-stu-id="e5f68-114">Step 3: Connection Settings</span></span>

<span data-ttu-id="e5f68-115">ServiceNow データに接続するには、このアカウントの組織の **ServiceNow** インスタンス URL 資格情報、クライアント ID、および OAuth 認証用のクライアント シークレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-115">To connect to your ServiceNow data, use your organization's **ServiceNow instance URL** credentials for this account, the Client ID, and Client Secret for OAuth authentication.</span></span>  

<span data-ttu-id="e5f68-116">組織の **ServiceNow** インスタンスの URL は、通常、組織https://ドメイン **&lt;>.service-now.com。**</span><span class="sxs-lookup"><span data-stu-id="e5f68-116">Your organization’s **ServiceNow instance URL** typically looks like **https://&lt;your-organization-domain>.service-now.com**.</span></span> <span data-ttu-id="e5f68-117">この URL と共に、ServiceNow への接続を設定し、Microsoft Search が更新スケジュールに基づいて ServiceNow から記事を更新できるように、アカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-117">Along with this URL, you need an account for setting up the connection to ServiceNow and for allowing Microsoft Search to update the articles from ServiceNow based on the refresh schedule.</span></span> <span data-ttu-id="e5f68-118">アカウントには、少なくともナレッジ ロールが <em>必要</em> です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-118">The account should at least have <em>knowledge</em> role.</span></span> <span data-ttu-id="e5f68-119">[ServiceNow アカウントにロールを割り当てる方法について学習します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-119">[Learn how to assign role for ServiceNow accounts](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span>

>[!NOTE]
><span data-ttu-id="e5f68-120">Microsoft Search の結果でナレッジ記事のアクセス許可を受け入れ、ユーザーおよびグループ ID をクロールする場合、アカウントは ServiceNow の次の表のレコードを読み取るアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f68-120">If you want to crawl user and group identities to honor access permissions of knowledge articles in Microsoft Search results, the account should have access to read the following table records in ServiceNow:</span></span>
>* <span data-ttu-id="e5f68-121">kb_uc_can_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="e5f68-121">kb_uc_can_contribute_mtom</span></span>
>* <span data-ttu-id="e5f68-122">kb_uc_can_read_mtom</span><span class="sxs-lookup"><span data-stu-id="e5f68-122">kb_uc_can_read_mtom</span></span>
>* <span data-ttu-id="e5f68-123">kb_uc_cannot_read_mtom</span><span class="sxs-lookup"><span data-stu-id="e5f68-123">kb_uc_cannot_read_mtom</span></span>
>* <span data-ttu-id="e5f68-124">kb_uc_cannot_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="e5f68-124">kb_uc_cannot_contribute_mtom</span></span>
>* <span data-ttu-id="e5f68-125">sys_user</span><span class="sxs-lookup"><span data-stu-id="e5f68-125">sys_user</span></span>
>* <span data-ttu-id="e5f68-126">sys_user_has_role</span><span class="sxs-lookup"><span data-stu-id="e5f68-126">sys_user_has_role</span></span>
>* <span data-ttu-id="e5f68-127">sys_user_grmember</span><span class="sxs-lookup"><span data-stu-id="e5f68-127">sys_user_grmember</span></span>
>* <span data-ttu-id="e5f68-128">user_criteria</span><span class="sxs-lookup"><span data-stu-id="e5f68-128">user_criteria</span></span>
>* <span data-ttu-id="e5f68-129">kb_knowledge_base</span><span class="sxs-lookup"><span data-stu-id="e5f68-129">kb_knowledge_base</span></span>  
> <span data-ttu-id="e5f68-130">Microsoft Search への接続に使用するアカウントの役割を作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-130">You can create and assign a role for the account you use to connect with Microsoft Search.</span></span> <span data-ttu-id="e5f68-131">テーブルへの読み取りアクセス権は、そのロールに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-131">Read access to the tables can be assigned on that role.</span></span> <span data-ttu-id="e5f68-132">テーブル レコードへの読み取りアクセスを設定する方法については、「テーブル レコードの [セキュリティ保護」を参照してください](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-132">To learn about setting read access to table records, see [Securing Table Records](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).</span></span>

<span data-ttu-id="e5f68-133">ServiceNow からコンテンツを認証して同期するには、次の 3 つのサポート **される** 方法のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-133">To authenticate and sync content from ServiceNow, choose **one of three** supported methods:</span></span>

1. <span data-ttu-id="e5f68-134">基本認証</span><span class="sxs-lookup"><span data-stu-id="e5f68-134">Basic authentication</span></span>
1. <span data-ttu-id="e5f68-135">ServiceNow OAuth (推奨)</span><span class="sxs-lookup"><span data-stu-id="e5f68-135">ServiceNow OAuth (recommended)</span></span>
1. <span data-ttu-id="e5f68-136">Azure AD OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="e5f68-136">Azure AD OpenID Connect</span></span>

### <a name="basic-authentication"></a><span data-ttu-id="e5f68-137">基本認証</span><span class="sxs-lookup"><span data-stu-id="e5f68-137">Basic authentication</span></span>

<span data-ttu-id="e5f68-138">インスタンスに対する認証を行うナレッジロールを持つ ServiceNow アカウントのユーザー名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-138">Enter the username and password of ServiceNow account with **knowledge** role to authenticate to your instance.</span></span>

### <a name="servicenow-oauth"></a><span data-ttu-id="e5f68-139">ServiceNow OAuth</span><span class="sxs-lookup"><span data-stu-id="e5f68-139">ServiceNow OAuth</span></span>

<span data-ttu-id="e5f68-140">認証に ServiceNow OAuth を使用するには、ServiceNow インスタンスにエンドポイントを準備します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-140">To use ServiceNow OAuth for authentication, provision an endpoint in your ServiceNow instance.</span></span> <span data-ttu-id="e5f68-141">Microsoft Search アプリは、このアプリを使用してインスタンスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="e5f68-141">The Microsoft Search app will use it to access the instance.</span></span> <span data-ttu-id="e5f68-142">詳細については、ServiceNow ドキュメント [の「クライアントがインスタンスにアクセス](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) するエンドポイントを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f68-142">To learn more, see [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in the ServiceNow documentation.</span></span>

<span data-ttu-id="e5f68-143">次の表に、エンドポイント作成フォームに入力する方法のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-143">The following table provides guidance on how to fill out the endpoint creation form:</span></span>

<span data-ttu-id="e5f68-144">Field</span><span class="sxs-lookup"><span data-stu-id="e5f68-144">Field</span></span> | <span data-ttu-id="e5f68-145">説明</span><span class="sxs-lookup"><span data-stu-id="e5f68-145">Description</span></span> | <span data-ttu-id="e5f68-146">推奨値</span><span class="sxs-lookup"><span data-stu-id="e5f68-146">Recommended Value</span></span> 
--- | --- | ---
<span data-ttu-id="e5f68-147">名前</span><span class="sxs-lookup"><span data-stu-id="e5f68-147">Name</span></span> | <span data-ttu-id="e5f68-148">OAuth アクセスが必要なアプリケーションを識別する一意の値。</span><span class="sxs-lookup"><span data-stu-id="e5f68-148">Unique value that identifies the application that you require OAuth access for.</span></span> | <span data-ttu-id="e5f68-149">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="e5f68-149">Microsoft Search</span></span>
<span data-ttu-id="e5f68-150">クライアント ID</span><span class="sxs-lookup"><span data-stu-id="e5f68-150">Client ID</span></span> | <span data-ttu-id="e5f68-151">アプリケーションの読み取り専用で自動生成された一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e5f68-151">A read-only, auto generated unique ID for the application.</span></span> <span data-ttu-id="e5f68-152">インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-152">The instance uses the client ID when it requests an access token.</span></span> | <span data-ttu-id="e5f68-153">該当なし</span><span class="sxs-lookup"><span data-stu-id="e5f68-153">NA</span></span>
<span data-ttu-id="e5f68-154">クライアント シークレット</span><span class="sxs-lookup"><span data-stu-id="e5f68-154">Client secret</span></span> | <span data-ttu-id="e5f68-155">この共有シークレット文字列を使用すると、ServiceNow インスタンスと Microsoft Search は互いに通信を承認します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-155">With this shared secret string, the ServiceNow instance and Microsoft Search authorize communications with each other.</span></span> | <span data-ttu-id="e5f68-156">シークレットをパスワードとして扱って、セキュリティのベスト プラクティスに従います。</span><span class="sxs-lookup"><span data-stu-id="e5f68-156">Follow security best-practices by treating the secret as a password.</span></span>
<span data-ttu-id="e5f68-157">リダイレクト URL</span><span class="sxs-lookup"><span data-stu-id="e5f68-157">Redirect URL</span></span> | <span data-ttu-id="e5f68-158">認証サーバーがリダイレクトする必須のコールバック URL。</span><span class="sxs-lookup"><span data-stu-id="e5f68-158">A required callback URL that the authorization server redirects to.</span></span> | https://gcs.office.com/v1.0/admin/oauth/callback
<span data-ttu-id="e5f68-159">ロゴ URL</span><span class="sxs-lookup"><span data-stu-id="e5f68-159">Logo URL</span></span> | <span data-ttu-id="e5f68-160">アプリケーション ロゴのイメージを含む URL。</span><span class="sxs-lookup"><span data-stu-id="e5f68-160">A URL that contains the image for the application logo.</span></span> | <span data-ttu-id="e5f68-161">該当なし</span><span class="sxs-lookup"><span data-stu-id="e5f68-161">NA</span></span>
<span data-ttu-id="e5f68-162">Active</span><span class="sxs-lookup"><span data-stu-id="e5f68-162">Active</span></span> | <span data-ttu-id="e5f68-163">チェック ボックスをオンにして、アプリケーション レジストリをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="e5f68-163">Select the check box to make the application registry active.</span></span> | <span data-ttu-id="e5f68-164">アクティブに設定</span><span class="sxs-lookup"><span data-stu-id="e5f68-164">Set to active</span></span>
<span data-ttu-id="e5f68-165">更新トークンの有効期限</span><span class="sxs-lookup"><span data-stu-id="e5f68-165">Refresh token lifespan</span></span> | <span data-ttu-id="e5f68-166">更新トークンが有効な時間 (秒)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-166">The number of seconds that a refresh token is valid.</span></span> <span data-ttu-id="e5f68-167">既定では、更新トークンの有効期限は 100 日 (8,640,000 秒) です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-167">By default, refresh tokens expire in 100 days (8,640,000 seconds).</span></span> | <span data-ttu-id="e5f68-168">31,536,000 (1 年間)</span><span class="sxs-lookup"><span data-stu-id="e5f68-168">31,536,000 (1 year)</span></span>
<span data-ttu-id="e5f68-169">アクセス トークンの有効期限</span><span class="sxs-lookup"><span data-stu-id="e5f68-169">Access token lifespan</span></span> | <span data-ttu-id="e5f68-170">アクセス トークンが有効な時間 (秒)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-170">The number of seconds that an access token is valid.</span></span> | <span data-ttu-id="e5f68-171">43,200 (12 時間)</span><span class="sxs-lookup"><span data-stu-id="e5f68-171">43,200 (12 hours)</span></span>

<span data-ttu-id="e5f68-172">インスタンスに接続するクライアント ID とクライアント シークレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-172">Enter the client ID and client secret to connect to your instance.</span></span> <span data-ttu-id="e5f68-173">接続後、ServiceNow アカウント資格情報を使用してクロールのアクセス許可を認証します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-173">After connecting, use a ServiceNow account credential to authenticate permission to crawl.</span></span> <span data-ttu-id="e5f68-174">アカウントには、少なくともナレッジ ロールが **必要** です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-174">The account should at least have **knowledge** role.</span></span>

### <a name="azure-ad-openid-connect"></a><span data-ttu-id="e5f68-175">Azure AD OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="e5f68-175">Azure AD OpenID Connect</span></span>

<span data-ttu-id="e5f68-176">認証に Azure AD OpenID Connect を使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-176">To use Azure AD OpenID Connect for authentication, follow the steps below.</span></span>

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a><span data-ttu-id="e5f68-177">手順 3.a: Azure Active Directory に新しいアプリケーションを登録する</span><span class="sxs-lookup"><span data-stu-id="e5f68-177">Step 3.a: Register a new application in Azure Active Directory</span></span>

<span data-ttu-id="e5f68-178">Azure Active Directory に新しいアプリケーションを登録する方法については、「アプリケーションの登録 [」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-178">To learn about registering a new application in Azure Active Directory, see [Register an application](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application).</span></span> <span data-ttu-id="e5f68-179">単一テナントの組織ディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-179">Select single tenant organizational directory.</span></span> <span data-ttu-id="e5f68-180">リダイレクト URI は必要ない。</span><span class="sxs-lookup"><span data-stu-id="e5f68-180">Redirect URI isn't needed.</span></span> <span data-ttu-id="e5f68-181">登録後、アプリケーション (クライアント) ID とディレクトリ (テナント) ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="e5f68-181">After registration, note down the Application (client) ID and Directory (tenant) ID.</span></span>

## <a name="step-3b-create-a-client-secret"></a><span data-ttu-id="e5f68-182">手順 3.b: クライアント シークレットを作成する</span><span class="sxs-lookup"><span data-stu-id="e5f68-182">Step 3.b: Create a client secret</span></span>

<span data-ttu-id="e5f68-183">クライアント シークレットの作成については、「クライアント シークレットの作成 [」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-183">To learn about creating a client secret, see [Creating a client secret](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).</span></span> <span data-ttu-id="e5f68-184">クライアント シークレットをメモします。</span><span class="sxs-lookup"><span data-stu-id="e5f68-184">Take a note of client secret.</span></span>

## <a name="step-3c-retrieve-service-principal-object-identifier"></a><span data-ttu-id="e5f68-185">手順 3.c: サービス プリンシパル オブジェクト識別子を取得する</span><span class="sxs-lookup"><span data-stu-id="e5f68-185">Step 3.c: Retrieve Service Principal Object Identifier</span></span>

<span data-ttu-id="e5f68-186">手順に従ってサービス プリンシパル オブジェクト識別子を取得する</span><span class="sxs-lookup"><span data-stu-id="e5f68-186">Follow the steps to retrieve Service Principal Object Identifier</span></span>

1. <span data-ttu-id="e5f68-187">PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-187">Run PowerShell.</span></span>

2. <span data-ttu-id="e5f68-188">次のコマンドを使用して Azure PowerShell をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e5f68-188">Install Azure PowerShell using the following command.</span></span>

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. <span data-ttu-id="e5f68-189">Azure に接続します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-189">Connect to Azure.</span></span>

   ```powershell
   Connect-AzAccount
   ```

4. <span data-ttu-id="e5f68-190">サービス プリンシパル オブジェクト識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-190">Get Service Principal Object Identifier.</span></span>

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   <span data-ttu-id="e5f68-191">"Application-ID" を手順 3.a. で登録したアプリケーションのアプリケーション (クライアント) ID (引用符なし) に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="e5f68-191">Replace "Application-ID" with Application (client) ID (without quotes) of the application you registered in step 3.a.</span></span> <span data-ttu-id="e5f68-192">PowerShell 出力からの ID オブジェクトの値をメモします。</span><span class="sxs-lookup"><span data-stu-id="e5f68-192">Note the value of ID object from PowerShell output.</span></span> <span data-ttu-id="e5f68-193">サービス プリンシパル ID です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-193">It's the Service Principal ID.</span></span>

<span data-ttu-id="e5f68-194">これで、Azure portal から必要なすべての情報が取得しました。</span><span class="sxs-lookup"><span data-stu-id="e5f68-194">Now you have all the information required from Azure portal.</span></span> <span data-ttu-id="e5f68-195">情報の簡単な概要を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-195">A quick summary of the information is given in the table below.</span></span>

<span data-ttu-id="e5f68-196">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e5f68-196">Property</span></span> | <span data-ttu-id="e5f68-197">説明</span><span class="sxs-lookup"><span data-stu-id="e5f68-197">Description</span></span> 
--- | ---
<span data-ttu-id="e5f68-198">ディレクトリ ID (テナント ID)</span><span class="sxs-lookup"><span data-stu-id="e5f68-198">Directory ID (Tenant ID)</span></span> | <span data-ttu-id="e5f68-199">手順 3.a. からの Azure Active Directory テナントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e5f68-199">Unique ID of the Azure Active Directory tenant, from step 3.a.</span></span>
<span data-ttu-id="e5f68-200">アプリケーション ID (クライアント ID)</span><span class="sxs-lookup"><span data-stu-id="e5f68-200">Application ID (Client ID)</span></span> | <span data-ttu-id="e5f68-201">手順 3.a. で登録したアプリケーションの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="e5f68-201">Unique ID of the application registered in step 3.a.</span></span>
<span data-ttu-id="e5f68-202">クライアントの秘密情報</span><span class="sxs-lookup"><span data-stu-id="e5f68-202">Client Secret</span></span> | <span data-ttu-id="e5f68-203">アプリケーションの秘密キー (手順 3.b)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-203">The secret key of the application (from step 3.b).</span></span> <span data-ttu-id="e5f68-204">パスワードのように扱います。</span><span class="sxs-lookup"><span data-stu-id="e5f68-204">Treat it like a password.</span></span>
<span data-ttu-id="e5f68-205">サービス プリンシパル ID</span><span class="sxs-lookup"><span data-stu-id="e5f68-205">Service Principal ID</span></span> | <span data-ttu-id="e5f68-206">サービスとして実行されているアプリケーションの ID。</span><span class="sxs-lookup"><span data-stu-id="e5f68-206">An identity for the application running as a service.</span></span> <span data-ttu-id="e5f68-207">(手順 3.c から)</span><span class="sxs-lookup"><span data-stu-id="e5f68-207">(from step 3.c)</span></span>

## <a name="step-3d-register-servicenow-application"></a><span data-ttu-id="e5f68-208">手順 3.d: ServiceNow アプリケーションを登録する</span><span class="sxs-lookup"><span data-stu-id="e5f68-208">Step 3.d: Register ServiceNow Application</span></span>

<span data-ttu-id="e5f68-209">ServiceNow インスタンスには、次の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-209">The ServiceNow instance needs the following configuration:</span></span>

1. <span data-ttu-id="e5f68-210">新しい OAuth OIDC エンティティを登録します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-210">Register a new OAuth OIDC entity.</span></span> <span data-ttu-id="e5f68-211">詳細については [、「OAuth OIDC プロバイダーの作成」を参照してください](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-211">To learn, see [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).</span></span>

2. <span data-ttu-id="e5f68-212">次の表に、OIDC プロバイダー登録フォームに入力する方法のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-212">The following table provides guidance on how to fill out OIDC provider registration form</span></span>

   <span data-ttu-id="e5f68-213">Field</span><span class="sxs-lookup"><span data-stu-id="e5f68-213">Field</span></span> | <span data-ttu-id="e5f68-214">説明</span><span class="sxs-lookup"><span data-stu-id="e5f68-214">Description</span></span> | <span data-ttu-id="e5f68-215">推奨値</span><span class="sxs-lookup"><span data-stu-id="e5f68-215">Recommended Value</span></span>
   --- | --- | ---
   <span data-ttu-id="e5f68-216">名前</span><span class="sxs-lookup"><span data-stu-id="e5f68-216">Name</span></span> | <span data-ttu-id="e5f68-217">OAuth OIDC エンティティを識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="e5f68-217">A unique name that identifies the OAuth OIDC entity.</span></span> | <span data-ttu-id="e5f68-218">Azure AD</span><span class="sxs-lookup"><span data-stu-id="e5f68-218">Azure AD</span></span>
   <span data-ttu-id="e5f68-219">クライアント ID</span><span class="sxs-lookup"><span data-stu-id="e5f68-219">Client ID</span></span> | <span data-ttu-id="e5f68-220">サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント ID。</span><span class="sxs-lookup"><span data-stu-id="e5f68-220">The client ID of the application registered in the third-party OAuth OIDC server.</span></span> <span data-ttu-id="e5f68-221">インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-221">The instance uses the client ID when requesting an access token.</span></span> | <span data-ttu-id="e5f68-222">手順 3.a のアプリケーション (クライアント) ID</span><span class="sxs-lookup"><span data-stu-id="e5f68-222">Application (Client) ID from step 3.a</span></span>
   <span data-ttu-id="e5f68-223">クライアントの秘密情報</span><span class="sxs-lookup"><span data-stu-id="e5f68-223">Client Secret</span></span> | <span data-ttu-id="e5f68-224">サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント シークレット。</span><span class="sxs-lookup"><span data-stu-id="e5f68-224">The client secret of the application registered in the third-party OAuth OIDC server.</span></span> | <span data-ttu-id="e5f68-225">手順 3.b のクライアント シークレット</span><span class="sxs-lookup"><span data-stu-id="e5f68-225">Client Secret from step 3.b</span></span>

   <span data-ttu-id="e5f68-226">その他の値はすべて既定に設定できます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-226">All other values can be default.</span></span>

3. <span data-ttu-id="e5f68-227">OIDC プロバイダー登録フォームで、新しい OIDC プロバイダー構成を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f68-227">In the OIDC provider registration form, you need to add a new OIDC provider configuration.</span></span> <span data-ttu-id="e5f68-228">*OAuth OIDC* プロバイダー構成フィールドに対する検索アイコンを選択して、OIDC 構成のレコードを開きます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-228">Select the search icon against *OAuth OIDC Provider Configuration* field to open the records of OIDC configurations.</span></span> <span data-ttu-id="e5f68-229">[新規]を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-229">Select New.</span></span>

4. <span data-ttu-id="e5f68-230">次の表に、OIDC プロバイダー構成フォームに入力する方法のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-230">The following table provides guidance on how to fill out OIDC provider configuration form</span></span>

   <span data-ttu-id="e5f68-231">Field</span><span class="sxs-lookup"><span data-stu-id="e5f68-231">Field</span></span> | <span data-ttu-id="e5f68-232">推奨値</span><span class="sxs-lookup"><span data-stu-id="e5f68-232">Recommended Value</span></span>
   --- | ---
   <span data-ttu-id="e5f68-233">OIDC プロバイダー</span><span class="sxs-lookup"><span data-stu-id="e5f68-233">OIDC Provider</span></span> |  <span data-ttu-id="e5f68-234">Azure AD</span><span class="sxs-lookup"><span data-stu-id="e5f68-234">Azure AD</span></span>
   <span data-ttu-id="e5f68-235">OIDC メタデータ URL</span><span class="sxs-lookup"><span data-stu-id="e5f68-235">OIDC Metadata URL</span></span> | <span data-ttu-id="e5f68-236">URL は https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration の形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f68-236">The URL must be in the form https\://login.microsoftonline.com/<tenandId">/.well-known/openid-configuration</span></span> <br/><span data-ttu-id="e5f68-237">手順 3.a の "tenantID" をディレクトリ (テナント) ID に置き換える。</span><span class="sxs-lookup"><span data-stu-id="e5f68-237">Replace "tenantID" with Directory (tenant) ID from step 3.a.</span></span>
   <span data-ttu-id="e5f68-238">OIDC 構成キャッシュの寿命</span><span class="sxs-lookup"><span data-stu-id="e5f68-238">OIDC Configuration Cache Life Span</span></span> |  <span data-ttu-id="e5f68-239">120</span><span class="sxs-lookup"><span data-stu-id="e5f68-239">120</span></span>
   <span data-ttu-id="e5f68-240">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="e5f68-240">Application</span></span> | <span data-ttu-id="e5f68-241">グローバル</span><span class="sxs-lookup"><span data-stu-id="e5f68-241">Global</span></span>
   <span data-ttu-id="e5f68-242">ユーザークレーム</span><span class="sxs-lookup"><span data-stu-id="e5f68-242">User Claim</span></span> | <span data-ttu-id="e5f68-243">sub</span><span class="sxs-lookup"><span data-stu-id="e5f68-243">sub</span></span>
   <span data-ttu-id="e5f68-244">ユーザー フィールド</span><span class="sxs-lookup"><span data-stu-id="e5f68-244">User Field</span></span> | <span data-ttu-id="e5f68-245">ユーザー ID</span><span class="sxs-lookup"><span data-stu-id="e5f68-245">User ID</span></span>
   <span data-ttu-id="e5f68-246">JTI 要求の検証を有効にする</span><span class="sxs-lookup"><span data-stu-id="e5f68-246">Enable JTI claim verification</span></span> | <span data-ttu-id="e5f68-247">無効</span><span class="sxs-lookup"><span data-stu-id="e5f68-247">Disabled</span></span>

5. <span data-ttu-id="e5f68-248">[OAuth OIDC エンティティ の送信と更新] フォームを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-248">Select Submit and Update the OAuth OIDC Entity form.</span></span>

## <a name="step-3e-create-a-servicenow-account"></a><span data-ttu-id="e5f68-249">手順 3.e: ServiceNow アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="e5f68-249">Step 3.e: Create a ServiceNow account</span></span>

<span data-ttu-id="e5f68-250">手順を参照して ServiceNow アカウントを作成し、ServiceNow [でユーザーを作成します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-250">Refer the instructions to create a ServiceNow account, [create a user in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).</span></span>

<span data-ttu-id="e5f68-251">次の表に、ServiceNow ユーザー アカウントの登録に入力する方法のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-251">The following table provides guidance on how to fill out the ServiceNow user account registration</span></span>

<span data-ttu-id="e5f68-252">Field</span><span class="sxs-lookup"><span data-stu-id="e5f68-252">Field</span></span> | <span data-ttu-id="e5f68-253">推奨値</span><span class="sxs-lookup"><span data-stu-id="e5f68-253">Recommended Value</span></span>
--- | ---
<span data-ttu-id="e5f68-254">ユーザー ID</span><span class="sxs-lookup"><span data-stu-id="e5f68-254">User ID</span></span> | <span data-ttu-id="e5f68-255">手順 3.c のサービス プリンシパル ID</span><span class="sxs-lookup"><span data-stu-id="e5f68-255">Service Principal ID from step 3.c</span></span>
<span data-ttu-id="e5f68-256">Web サービス アクセスのみ</span><span class="sxs-lookup"><span data-stu-id="e5f68-256">Web service access only</span></span> | <span data-ttu-id="e5f68-257">Checked</span><span class="sxs-lookup"><span data-stu-id="e5f68-257">Checked</span></span>

<span data-ttu-id="e5f68-258">その他の値はすべて既定のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-258">All other values can be left to default.</span></span>

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a><span data-ttu-id="e5f68-259">手順 3.f: ServiceNow アカウントのナレッジ ロールを有効にする</span><span class="sxs-lookup"><span data-stu-id="e5f68-259">Step 3.f: Enable Knowledge role for the ServiceNow account</span></span>

<span data-ttu-id="e5f68-260">ServiceNow プリンシパル ID をユーザー ID として作成した ServiceNow アカウントにアクセスし、ナレッジ ロールを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="e5f68-260">Access the ServiceNow account you created with ServiceNow Principal ID as User ID, and assign the knowledge role.</span></span> <span data-ttu-id="e5f68-261">ServiceNow アカウントにロールを割り当てる手順については、ユーザーにロールを割り当てる [方法をご覧ください](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-261">Instructions to assigning a role to a ServiceNow account can be found here: [assign a role to a user](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span>

<span data-ttu-id="e5f68-262">手順 3.a のクライアント ID としてアプリケーション ID を使用し、手順 3.b のクライアント シークレットを使用して、Azure AD OpenID Connect を使用して ServiceNow インスタンスに認証します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-262">Use Application ID as Client ID from step 3.a, and Client secret from step 3.b, to authenticate to your ServiceNow instance using Azure AD OpenID Connect.</span></span>

## <a name="step-4-select-properties-and-filter-data"></a><span data-ttu-id="e5f68-263">手順 4: プロパティを選択し、データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="e5f68-263">Step 4: Select properties and filter data</span></span>

<span data-ttu-id="e5f68-264">この手順では、ServiceNow データ ソースに対して使用可能なプロパティを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-264">In this step, you can add or remove available properties from your ServiceNow data source.</span></span> <span data-ttu-id="e5f68-265">Microsoft 365 では、既定でいくつかのプロパティが既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="e5f68-265">Microsoft 365 has already selected few properties by default.</span></span>

<span data-ttu-id="e5f68-266">ServiceNow クエリ文字列を使用すると、記事を同期する条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-266">With a ServiceNow query string, you can specify conditions for syncing articles.</span></span> <span data-ttu-id="e5f68-267">これは、Select ステートメントの **Where** **句SQL似たもの** です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-267">It's like a **Where** clause in a **SQL Select** statement.</span></span> <span data-ttu-id="e5f68-268">たとえば、発行済みでアクティブな記事のインデックスのみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-268">For example, you can choose to index only articles that are published and active.</span></span> <span data-ttu-id="e5f68-269">独自のクエリ文字列の作成については、「フィルターを使用してエンコードされたクエリ文字列を生成する [」を参照してください](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-269">To learn about creating your own query string, see [Generate an encoded query string using a filter](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).</span></span>

<span data-ttu-id="e5f68-270">[結果のプレビュー] ボタンを使用して、選択したプロパティとクエリ フィルターのサンプル値を確認します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-270">Use the preview results button to verify the sample values of the selected properties and query filter.</span></span>

## <a name="step-5-manage-search-permissions"></a><span data-ttu-id="e5f68-271">手順 5: 検索権限を管理する</span><span class="sxs-lookup"><span data-stu-id="e5f68-271">Step 5: Manage search permissions</span></span>

<span data-ttu-id="e5f68-272">ServiceNow コネクタは、[すべてのユーザー]または [このデータ ソースにアクセスできるユーザーのみ] に表示される検索 **アクセス許可をサポートします**。</span><span class="sxs-lookup"><span data-stu-id="e5f68-272">The ServiceNow connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="e5f68-273">インデックス付きデータは検索結果に表示され、それぞれアクセス権を持つ組織内のユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-273">Indexed data appears in the search results and is visible to users in the organization who have access to them respectively.</span></span> <span data-ttu-id="e5f68-274">ServiceNow Connector は、高度なスクリプトのない既定のユーザー条件のアクセス許可をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="e5f68-274">ServiceNow Connector supports default user criteria permissions without advanced scripts.</span></span> <span data-ttu-id="e5f68-275">コネクタが高度なスクリプトを使用してユーザー条件を見つけると、そのユーザー条件を使用しているすべてのデータが検索結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="e5f68-275">When the connector finds a user criteria with advanced script, all data using that user criteria won't be shown in search results.</span></span>

<span data-ttu-id="e5f68-276">[このデータソースにアクセスできるユーザーのみ] を選択した場合は、ServiceNow インスタンスに Azure Active Directory (AAD) がプロビジョニングされたユーザーと AAD 以外のユーザーの 2 人を含むかどうかをさらに選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5f68-276">If you select **Only people with access to this data source**, you need to further choose whether your ServiceNow instance has Azure Active Directory (AAD) provisioned users or Non-AAD users.</span></span>

>[!NOTE]
><span data-ttu-id="e5f68-277">The ServiceNow connector is in **preview** if you choose **Only people with access to this data source**.</span><span class="sxs-lookup"><span data-stu-id="e5f68-277">The ServiceNow connector is in **preview** if you choose **Only people with access to this data source**.</span></span>

>[!NOTE]
><span data-ttu-id="e5f68-278">ID ソースの種類として AAD を選択する場合は、ServiceNow の電子メールターゲット プロパティに UPN ソース プロパティを割り当て中です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-278">If you choose AAD as the type of identity source, make sure you are assigning UPN source property to email targeted property in ServiceNow.</span></span> <span data-ttu-id="e5f68-279">マッピングを確認または変更するには、「Azure Active Directory での SaaS アプリケーションのユーザー プロビジョニング属性マッピング [のカスタマイズ」を参照してください](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-279">To verify or change your mappings, see [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes).</span></span>

<span data-ttu-id="e5f68-280">ServiceNow インスタンスから ACL を取り込み、ID の種類として [非 AAD] を選択した場合は、「ID のマッピング方法については [、Azure 以外の AD](map-non-aad.md) ID をマップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e5f68-280">If you chose to ingest an ACL from your ServiceNow instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

## <a name="step-6-assign-property-labels"></a><span data-ttu-id="e5f68-281">手順 6: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e5f68-281">Step 6: Assign property labels</span></span>

<span data-ttu-id="e5f68-282">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-282">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a><span data-ttu-id="e5f68-283">手順 7: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="e5f68-283">Step 7: Manage schema</span></span>

<span data-ttu-id="e5f68-284">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-284">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a><span data-ttu-id="e5f68-285">手順 8: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="e5f68-285">Step 8: Choose refresh settings</span></span>

<span data-ttu-id="e5f68-286">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-286">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
><span data-ttu-id="e5f68-287">ID の場合は、スケジュールされたフル クロールだけが適用されます。</span><span class="sxs-lookup"><span data-stu-id="e5f68-287">For identities, only full crawl scheduled will be applied.</span></span>

## <a name="step-9-review-connection"></a><span data-ttu-id="e5f68-288">手順 9: 接続を確認する</span><span class="sxs-lookup"><span data-stu-id="e5f68-288">Step 9: Review Connection</span></span>

<span data-ttu-id="e5f68-289">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-289">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="e5f68-290">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e5f68-290">Troubleshooting</span></span>

<span data-ttu-id="e5f68-291">接続を発行し、結果ページをカスタマイズした後、管理センターの [コネクタ]タブで状態を[確認できます](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-291">After publishing your connection, customizing the results page, you can review the status under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="e5f68-292">更新と削除を行う方法については、「コネクタの管理」 [を参照してください](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="e5f68-292">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="e5f68-293">制限事項</span><span class="sxs-lookup"><span data-stu-id="e5f68-293">Limitations</span></span>

<span data-ttu-id="e5f68-294">ServiceNow Graph コネクタの最新リリースには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="e5f68-294">ServiceNow Graph connector has the following limitations in its latest release:</span></span>

- <span data-ttu-id="e5f68-295">組織内のすべてのユーザーが使用できるナレッジ項目のインデックス作成は、一般に利用可能な機能です。</span><span class="sxs-lookup"><span data-stu-id="e5f68-295">Indexing knowledge articles available to everyone in an organization is a generally available feature.</span></span>
- <span data-ttu-id="e5f68-296">*[検索のアクセス許可の* 管理] ステップでこのデータ ソース機能にアクセスできるユーザーだけがプレビュー段階であり、ユーザー条件のアクセス許可 [のみを](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 処理します。</span><span class="sxs-lookup"><span data-stu-id="e5f68-296">*Only people with access to this data source* feature under Manage Search permissions step is in preview and processes only [user criteria](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) permissions.</span></span> <span data-ttu-id="e5f68-297">その他の種類のアクセス許可は、検索結果には適用されません。</span><span class="sxs-lookup"><span data-stu-id="e5f68-297">Any other type of access permissions won't be applied in the search results.</span></span>
- <span data-ttu-id="e5f68-298">高度なスクリプトを使用したユーザーの条件は、現在のプレビュー バージョンではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e5f68-298">User criteria with advanced scripts aren't supported in the current preview version.</span></span> <span data-ttu-id="e5f68-299">アクセス制限を持つナレッジ項目には、すべてのユーザーのアクセスを拒否するインデックスが付けされ、サポートされるまでは検索結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="e5f68-299">Knowledge articles with an access restriction will be indexed with deny everyone access, and won't appear in search results to any user until we support them.</span></span>
