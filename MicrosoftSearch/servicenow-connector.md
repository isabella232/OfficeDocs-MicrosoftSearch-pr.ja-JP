---
title: Microsoft Search Graph ServiceNow Graphコネクタ
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
description: Microsoft Search の ServiceNow Graphコネクタをセットアップする
ms.openlocfilehash: 31b581af2c51a5c26b161e778b242e396afe91fd
ms.sourcegitcommit: 6cffa2d29448be9a22514e7b4c3009c522af0860
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52774082"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a><span data-ttu-id="ceed5-103">ServiceNow Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="ceed5-103">ServiceNow Graph Connector</span></span>

<span data-ttu-id="ceed5-104">ServiceNow Graph コネクタを使用すると、組織内のユーザー条件のアクセス許可に従って、ユーザーに表示されるナレッジ ベースの記事にインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-104">The ServiceNow Graph connector allows your organization to index knowledge-based articles visible to users according to the user criteria permissions within your organization.</span></span> <span data-ttu-id="ceed5-105">ServiceNow からコネクタとインデックス コンテンツを構成した後、ユーザーは任意の Microsoft Search クライアントから記事を検索できます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-105">After you configure the connector and index content from ServiceNow, users can search for the articles from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="ceed5-106">一般的な [**コネクタのセットアップGraph**](configure-connector.md) Graphについては、「Graphコネクタのセットアップ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="ceed5-107">この記事は、ServiceNow コネクタを構成、実行、および監視するGraphです。</span><span class="sxs-lookup"><span data-stu-id="ceed5-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="ceed5-108">これは、一般的なセットアップ プロセスを補足し、ServiceNow コネクタに対してのみ適用される手順Graphします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-108">It supplements the general setup process, and shows instructions that apply to only for the ServiceNow Graph connector.</span></span> <span data-ttu-id="ceed5-109">この記事には、トラブルシューティングと [制限事項に関](#troubleshooting) する情報 [も含まれています](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-109">This article also includes information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ceed5-110">手順 1: 管理センター GraphコネクタをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="ceed5-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ceed5-111">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="ceed5-112">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="ceed5-112">Step 2: Name the connection</span></span>

<span data-ttu-id="ceed5-113">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a><span data-ttu-id="ceed5-114">手順 3: 接続設定</span><span class="sxs-lookup"><span data-stu-id="ceed5-114">Step 3: Connection Settings</span></span>

<span data-ttu-id="ceed5-115">ServiceNow データに接続するには、このアカウントの組織の **ServiceNow** インスタンス URL 資格情報、クライアント ID、OAuth 認証用のクライアント シークレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-115">To connect to your ServiceNow data, use your organization's **ServiceNow instance URL** credentials for this account, the Client ID, and Client Secret for OAuth authentication.</span></span>  

<span data-ttu-id="ceed5-116">組織の **ServiceNow** インスタンス URL は、通常、組織 **https://>.service-now.com のように &lt; 表示されます**。</span><span class="sxs-lookup"><span data-stu-id="ceed5-116">Your organization's **ServiceNow instance URL** typically looks like **https://&lt;your-organization-domain>.service-now.com**.</span></span> <span data-ttu-id="ceed5-117">この URL と共に、ServiceNow への接続をセットアップし、更新スケジュールに基づいて Microsoft Search が ServiceNow から記事を更新できるようにアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ceed5-117">Along with this URL, you need an account for setting up the connection to ServiceNow and for allowing Microsoft Search to update the articles from ServiceNow based on the refresh schedule.</span></span> <span data-ttu-id="ceed5-118">アカウントには、少なくともナレッジ ロール <em>が必要</em> です。</span><span class="sxs-lookup"><span data-stu-id="ceed5-118">The account should at least have <em>knowledge</em> role.</span></span> <span data-ttu-id="ceed5-119">[ServiceNow アカウントの役割を割り当てる方法について学習します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-119">[Learn how to assign role for ServiceNow accounts](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span>

>[!NOTE]
><span data-ttu-id="ceed5-120">Microsoft 検索結果のナレッジ 記事のアクセス許可を受け入れ、ユーザー ID とグループ ID をクロールする場合、アカウントは ServiceNow で次の表レコードを読み取るアクセス権を持つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-120">If you want to crawl user and group identities to honor access permissions of knowledge articles in Microsoft Search results, the account should have access to read the following table records in ServiceNow:</span></span>
>* <span data-ttu-id="ceed5-121">kb_uc_can_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="ceed5-121">kb_uc_can_contribute_mtom</span></span>
>* <span data-ttu-id="ceed5-122">kb_uc_can_read_mtom</span><span class="sxs-lookup"><span data-stu-id="ceed5-122">kb_uc_can_read_mtom</span></span>
>* <span data-ttu-id="ceed5-123">kb_uc_cannot_read_mtom</span><span class="sxs-lookup"><span data-stu-id="ceed5-123">kb_uc_cannot_read_mtom</span></span>
>* <span data-ttu-id="ceed5-124">kb_uc_cannot_contribute_mtom</span><span class="sxs-lookup"><span data-stu-id="ceed5-124">kb_uc_cannot_contribute_mtom</span></span>
>* <span data-ttu-id="ceed5-125">sys_user</span><span class="sxs-lookup"><span data-stu-id="ceed5-125">sys_user</span></span>
>* <span data-ttu-id="ceed5-126">sys_user_has_role</span><span class="sxs-lookup"><span data-stu-id="ceed5-126">sys_user_has_role</span></span>
>* <span data-ttu-id="ceed5-127">sys_user_grmember</span><span class="sxs-lookup"><span data-stu-id="ceed5-127">sys_user_grmember</span></span>
>* <span data-ttu-id="ceed5-128">user_criteria</span><span class="sxs-lookup"><span data-stu-id="ceed5-128">user_criteria</span></span>
>* <span data-ttu-id="ceed5-129">kb_knowledge_base</span><span class="sxs-lookup"><span data-stu-id="ceed5-129">kb_knowledge_base</span></span>  
> <span data-ttu-id="ceed5-130">Microsoft Search への接続に使用するアカウントの役割を作成して割り当てできます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-130">You can create and assign a role for the account you use to connect with Microsoft Search.</span></span> <span data-ttu-id="ceed5-131">テーブルへの読み取りアクセス権は、その役割に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-131">Read access to the tables can be assigned on that role.</span></span> <span data-ttu-id="ceed5-132">テーブル レコードへの読み取りアクセスを設定する方法については、「テーブル レコードの [セキュリティ保護」を参照してください](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-132">To learn about setting read access to table records, see [Securing Table Records](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls).</span></span>

<span data-ttu-id="ceed5-133">ServiceNow からコンテンツを認証および同期するには、次の 3 つの **サポートされている方法** のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-133">To authenticate and sync content from ServiceNow, choose **one of three** supported methods:</span></span>

1. <span data-ttu-id="ceed5-134">基本認証</span><span class="sxs-lookup"><span data-stu-id="ceed5-134">Basic authentication</span></span>
1. <span data-ttu-id="ceed5-135">ServiceNow OAuth (推奨)</span><span class="sxs-lookup"><span data-stu-id="ceed5-135">ServiceNow OAuth (recommended)</span></span>
1. <span data-ttu-id="ceed5-136">Azure AD OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="ceed5-136">Azure AD OpenID Connect</span></span>

### <a name="basic-authentication"></a><span data-ttu-id="ceed5-137">基本認証</span><span class="sxs-lookup"><span data-stu-id="ceed5-137">Basic authentication</span></span>

<span data-ttu-id="ceed5-138">インスタンスに対する認証を行うナレッジ ロールを持つ ServiceNow **アカウントのユーザー** 名とパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-138">Enter the username and password of ServiceNow account with **knowledge** role to authenticate to your instance.</span></span>

### <a name="servicenow-oauth"></a><span data-ttu-id="ceed5-139">ServiceNow OAuth</span><span class="sxs-lookup"><span data-stu-id="ceed5-139">ServiceNow OAuth</span></span>

<span data-ttu-id="ceed5-140">認証に ServiceNow OAuth を使用するには、ServiceNow インスタンスにエンドポイントをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-140">To use ServiceNow OAuth for authentication, provision an endpoint in your ServiceNow instance.</span></span> <span data-ttu-id="ceed5-141">Microsoft Search アプリは、このアプリを使用してインスタンスにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-141">The Microsoft Search app will use it to access the instance.</span></span> <span data-ttu-id="ceed5-142">詳細については、ServiceNow のドキュメントの「クライアントがインスタンスにアクセス [する](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) エンドポイントを作成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-142">To learn more, see [Create an endpoint for clients to access the instance](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) in the ServiceNow documentation.</span></span>

<span data-ttu-id="ceed5-143">次の表に、エンドポイント作成フォームに入力する方法のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-143">The following table provides guidance on how to fill out the endpoint creation form:</span></span>

<span data-ttu-id="ceed5-144">フィールド</span><span class="sxs-lookup"><span data-stu-id="ceed5-144">Field</span></span> | <span data-ttu-id="ceed5-145">説明</span><span class="sxs-lookup"><span data-stu-id="ceed5-145">Description</span></span> | <span data-ttu-id="ceed5-146">推奨値</span><span class="sxs-lookup"><span data-stu-id="ceed5-146">Recommended Value</span></span> 
--- | --- | ---
<span data-ttu-id="ceed5-147">名前</span><span class="sxs-lookup"><span data-stu-id="ceed5-147">Name</span></span> | <span data-ttu-id="ceed5-148">OAuth アクセスが必要なアプリケーションを識別する一意の値。</span><span class="sxs-lookup"><span data-stu-id="ceed5-148">Unique value that identifies the application that you require OAuth access for.</span></span> | <span data-ttu-id="ceed5-149">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="ceed5-149">Microsoft Search</span></span>
<span data-ttu-id="ceed5-150">クライアント ID</span><span class="sxs-lookup"><span data-stu-id="ceed5-150">Client ID</span></span> | <span data-ttu-id="ceed5-151">アプリケーションの読み取り専用で自動生成された一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ceed5-151">A read-only, auto generated unique ID for the application.</span></span> <span data-ttu-id="ceed5-152">インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-152">The instance uses the client ID when it requests an access token.</span></span> | <span data-ttu-id="ceed5-153">該当なし</span><span class="sxs-lookup"><span data-stu-id="ceed5-153">NA</span></span>
<span data-ttu-id="ceed5-154">クライアント シークレット</span><span class="sxs-lookup"><span data-stu-id="ceed5-154">Client secret</span></span> | <span data-ttu-id="ceed5-155">この共有シークレット文字列を使用すると、ServiceNow インスタンスと Microsoft Search は互いに通信を承認します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-155">With this shared secret string, the ServiceNow instance and Microsoft Search authorize communications with each other.</span></span> | <span data-ttu-id="ceed5-156">シークレットをパスワードとして扱って、セキュリティのベスト プラクティスに従います。</span><span class="sxs-lookup"><span data-stu-id="ceed5-156">Follow security best-practices by treating the secret as a password.</span></span>
<span data-ttu-id="ceed5-157">リダイレクト URL</span><span class="sxs-lookup"><span data-stu-id="ceed5-157">Redirect URL</span></span> | <span data-ttu-id="ceed5-158">承認サーバーがリダイレクトする必要なコールバック URL。</span><span class="sxs-lookup"><span data-stu-id="ceed5-158">A required callback URL that the authorization server redirects to.</span></span> | https://gcs.office.com/v1.0/admin/oauth/callback
<span data-ttu-id="ceed5-159">ロゴ URL</span><span class="sxs-lookup"><span data-stu-id="ceed5-159">Logo URL</span></span> | <span data-ttu-id="ceed5-160">アプリケーション ロゴのイメージを含む URL。</span><span class="sxs-lookup"><span data-stu-id="ceed5-160">A URL that contains the image for the application logo.</span></span> | <span data-ttu-id="ceed5-161">該当なし</span><span class="sxs-lookup"><span data-stu-id="ceed5-161">NA</span></span>
<span data-ttu-id="ceed5-162">有効</span><span class="sxs-lookup"><span data-stu-id="ceed5-162">Active</span></span> | <span data-ttu-id="ceed5-163">チェック ボックスをオンにして、アプリケーション レジストリをアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-163">Select the check box to make the application registry active.</span></span> | <span data-ttu-id="ceed5-164">アクティブに設定する</span><span class="sxs-lookup"><span data-stu-id="ceed5-164">Set to active</span></span>
<span data-ttu-id="ceed5-165">トークンのライフスパンの更新</span><span class="sxs-lookup"><span data-stu-id="ceed5-165">Refresh token lifespan</span></span> | <span data-ttu-id="ceed5-166">更新トークンが有効な秒の数。</span><span class="sxs-lookup"><span data-stu-id="ceed5-166">The number of seconds that a refresh token is valid.</span></span> <span data-ttu-id="ceed5-167">既定では、更新トークンの有効期限は 100 日 (8,640,000 秒) です。</span><span class="sxs-lookup"><span data-stu-id="ceed5-167">By default, refresh tokens expire in 100 days (8,640,000 seconds).</span></span> | <span data-ttu-id="ceed5-168">31,536,000 (1 年)</span><span class="sxs-lookup"><span data-stu-id="ceed5-168">31,536,000 (1 year)</span></span>
<span data-ttu-id="ceed5-169">アクセス トークンのライフスパン</span><span class="sxs-lookup"><span data-stu-id="ceed5-169">Access token lifespan</span></span> | <span data-ttu-id="ceed5-170">アクセス トークンが有効な秒の数。</span><span class="sxs-lookup"><span data-stu-id="ceed5-170">The number of seconds that an access token is valid.</span></span> | <span data-ttu-id="ceed5-171">43,200 (12 時間)</span><span class="sxs-lookup"><span data-stu-id="ceed5-171">43,200 (12 hours)</span></span>

<span data-ttu-id="ceed5-172">インスタンスに接続するクライアント ID とクライアント シークレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-172">Enter the client ID and client secret to connect to your instance.</span></span> <span data-ttu-id="ceed5-173">接続後、ServiceNow アカウント資格情報を使用してクロールするアクセス許可を認証します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-173">After connecting, use a ServiceNow account credential to authenticate permission to crawl.</span></span> <span data-ttu-id="ceed5-174">アカウントには、少なくともナレッジ ロール **が必要** です。</span><span class="sxs-lookup"><span data-stu-id="ceed5-174">The account should at least have **knowledge** role.</span></span>

### <a name="azure-ad-openid-connect"></a><span data-ttu-id="ceed5-175">Azure AD OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="ceed5-175">Azure AD OpenID Connect</span></span>

<span data-ttu-id="ceed5-176">認証に Azure AD OpenID Connectするには、以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ceed5-176">To use Azure AD OpenID Connect for authentication, follow the steps below.</span></span>

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a><span data-ttu-id="ceed5-177">手順 3.a: 新しいアプリケーションを新しいアプリケーションに登録Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ceed5-177">Step 3.a: Register a new application in Azure Active Directory</span></span>

<span data-ttu-id="ceed5-178">アプリケーションに新しいアプリケーションを登録する方法については、「Azure Active Directoryを登録する[」を参照してください](/azure/active-directory/develop/quickstart-register-app#register-an-application)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-178">To learn about registering a new application in Azure Active Directory, see [Register an application](/azure/active-directory/develop/quickstart-register-app#register-an-application).</span></span> <span data-ttu-id="ceed5-179">[単一テナントの組織ディレクトリ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-179">Select single tenant organizational directory.</span></span> <span data-ttu-id="ceed5-180">リダイレクト URI は不要です。</span><span class="sxs-lookup"><span data-stu-id="ceed5-180">Redirect URI isn't needed.</span></span> <span data-ttu-id="ceed5-181">登録後、アプリケーション (クライアント) ID とディレクトリ (テナント) ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-181">After registration, note down the Application (client) ID and Directory (tenant) ID.</span></span>

## <a name="step-3b-create-a-client-secret"></a><span data-ttu-id="ceed5-182">手順 3.b: クライアント シークレットを作成する</span><span class="sxs-lookup"><span data-stu-id="ceed5-182">Step 3.b: Create a client secret</span></span>

<span data-ttu-id="ceed5-183">クライアント シークレットの作成の詳細については、「クライアント シークレットの作成 [」を参照してください](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-183">To learn about creating a client secret, see [Creating a client secret](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret).</span></span> <span data-ttu-id="ceed5-184">クライアント シークレットをメモします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-184">Take a note of client secret.</span></span>

## <a name="step-3c-retrieve-service-principal-object-identifier"></a><span data-ttu-id="ceed5-185">手順 3.c: サービス プリンシパル オブジェクト識別子の取得</span><span class="sxs-lookup"><span data-stu-id="ceed5-185">Step 3.c: Retrieve Service Principal Object Identifier</span></span>

<span data-ttu-id="ceed5-186">手順に従ってサービス プリンシパル オブジェクト識別子を取得する</span><span class="sxs-lookup"><span data-stu-id="ceed5-186">Follow the steps to retrieve Service Principal Object Identifier</span></span>

1. <span data-ttu-id="ceed5-187">PowerShell を実行します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-187">Run PowerShell.</span></span>

2. <span data-ttu-id="ceed5-188">次のAzure PowerShellを使用してインストールします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-188">Install Azure PowerShell using the following command.</span></span>

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. <span data-ttu-id="ceed5-189">Connect Azure にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-189">Connect to Azure.</span></span>

   ```powershell
   Connect-AzAccount
   ```

4. <span data-ttu-id="ceed5-190">サービス プリンシパル オブジェクト識別子を取得します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-190">Get Service Principal Object Identifier.</span></span>

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   <span data-ttu-id="ceed5-191">手順 3.a で登録したアプリケーションの "Application-ID" をアプリケーション (クライアント) ID (引用符なし) に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-191">Replace "Application-ID" with Application (client) ID (without quotes) of the application you registered in step 3.a.</span></span> <span data-ttu-id="ceed5-192">PowerShell 出力からの ID オブジェクトの値に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-192">Note the value of ID object from PowerShell output.</span></span> <span data-ttu-id="ceed5-193">サービス プリンシパル ID です。</span><span class="sxs-lookup"><span data-stu-id="ceed5-193">It's the Service Principal ID.</span></span>

<span data-ttu-id="ceed5-194">これで、Azure portal で必要なすべての情報が取得されます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-194">Now you have all the information required from Azure portal.</span></span> <span data-ttu-id="ceed5-195">情報の簡単な概要を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-195">A quick summary of the information is given in the table below.</span></span>

<span data-ttu-id="ceed5-196">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ceed5-196">Property</span></span> | <span data-ttu-id="ceed5-197">説明</span><span class="sxs-lookup"><span data-stu-id="ceed5-197">Description</span></span> 
--- | ---
<span data-ttu-id="ceed5-198">ディレクトリ ID (テナント ID)</span><span class="sxs-lookup"><span data-stu-id="ceed5-198">Directory ID (Tenant ID)</span></span> | <span data-ttu-id="ceed5-199">手順 3.a から、Azure Active Directoryテナントの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ceed5-199">Unique ID of the Azure Active Directory tenant, from step 3.a.</span></span>
<span data-ttu-id="ceed5-200">アプリケーション ID (クライアント ID)</span><span class="sxs-lookup"><span data-stu-id="ceed5-200">Application ID (Client ID)</span></span> | <span data-ttu-id="ceed5-201">手順 3.a で登録されているアプリケーションの一意の ID。</span><span class="sxs-lookup"><span data-stu-id="ceed5-201">Unique ID of the application registered in step 3.a.</span></span>
<span data-ttu-id="ceed5-202">クライアントの秘密情報</span><span class="sxs-lookup"><span data-stu-id="ceed5-202">Client Secret</span></span> | <span data-ttu-id="ceed5-203">アプリケーションの秘密キー (手順 3.b から)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-203">The secret key of the application (from step 3.b).</span></span> <span data-ttu-id="ceed5-204">パスワードのように扱います。</span><span class="sxs-lookup"><span data-stu-id="ceed5-204">Treat it like a password.</span></span>
<span data-ttu-id="ceed5-205">サービス プリンシパル ID</span><span class="sxs-lookup"><span data-stu-id="ceed5-205">Service Principal ID</span></span> | <span data-ttu-id="ceed5-206">サービスとして実行されているアプリケーションの ID。</span><span class="sxs-lookup"><span data-stu-id="ceed5-206">An identity for the application running as a service.</span></span> <span data-ttu-id="ceed5-207">(手順 3.c から)</span><span class="sxs-lookup"><span data-stu-id="ceed5-207">(from step 3.c)</span></span>

## <a name="step-3d-register-servicenow-application"></a><span data-ttu-id="ceed5-208">手順 3.d: ServiceNow アプリケーションの登録</span><span class="sxs-lookup"><span data-stu-id="ceed5-208">Step 3.d: Register ServiceNow Application</span></span>

<span data-ttu-id="ceed5-209">ServiceNow インスタンスには、次の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="ceed5-209">The ServiceNow instance needs the following configuration:</span></span>

1. <span data-ttu-id="ceed5-210">新しい OAuth OIDC エンティティを登録します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-210">Register a new OAuth OIDC entity.</span></span> <span data-ttu-id="ceed5-211">詳細については [、「Create an OAuth OIDC provider」を参照してください](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-211">To learn, see [Create an OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).</span></span>

2. <span data-ttu-id="ceed5-212">次の表に、OIDC プロバイダー登録フォームに入力する方法のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-212">The following table provides guidance on how to fill out OIDC provider registration form</span></span>

   <span data-ttu-id="ceed5-213">フィールド</span><span class="sxs-lookup"><span data-stu-id="ceed5-213">Field</span></span> | <span data-ttu-id="ceed5-214">説明</span><span class="sxs-lookup"><span data-stu-id="ceed5-214">Description</span></span> | <span data-ttu-id="ceed5-215">推奨値</span><span class="sxs-lookup"><span data-stu-id="ceed5-215">Recommended Value</span></span>
   --- | --- | ---
   <span data-ttu-id="ceed5-216">名前</span><span class="sxs-lookup"><span data-stu-id="ceed5-216">Name</span></span> | <span data-ttu-id="ceed5-217">OAuth OIDC エンティティを識別する一意の名前。</span><span class="sxs-lookup"><span data-stu-id="ceed5-217">A unique name that identifies the OAuth OIDC entity.</span></span> | <span data-ttu-id="ceed5-218">Azure AD</span><span class="sxs-lookup"><span data-stu-id="ceed5-218">Azure AD</span></span>
   <span data-ttu-id="ceed5-219">クライアント ID</span><span class="sxs-lookup"><span data-stu-id="ceed5-219">Client ID</span></span> | <span data-ttu-id="ceed5-220">サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント ID。</span><span class="sxs-lookup"><span data-stu-id="ceed5-220">The client ID of the application registered in the third-party OAuth OIDC server.</span></span> <span data-ttu-id="ceed5-221">インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-221">The instance uses the client ID when requesting an access token.</span></span> | <span data-ttu-id="ceed5-222">手順 3.a のアプリケーション (クライアント) ID</span><span class="sxs-lookup"><span data-stu-id="ceed5-222">Application (Client) ID from step 3.a</span></span>
   <span data-ttu-id="ceed5-223">クライアントの秘密情報</span><span class="sxs-lookup"><span data-stu-id="ceed5-223">Client Secret</span></span> | <span data-ttu-id="ceed5-224">サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント シークレット。</span><span class="sxs-lookup"><span data-stu-id="ceed5-224">The client secret of the application registered in the third-party OAuth OIDC server.</span></span> | <span data-ttu-id="ceed5-225">手順 3.b のクライアント シークレット</span><span class="sxs-lookup"><span data-stu-id="ceed5-225">Client Secret from step 3.b</span></span>

   <span data-ttu-id="ceed5-226">その他の値はすべて既定で指定できます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-226">All other values can be default.</span></span>

3. <span data-ttu-id="ceed5-227">OIDC プロバイダー登録フォームで、新しい OIDC プロバイダー構成を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-227">In the OIDC provider registration form, you need to add a new OIDC provider configuration.</span></span> <span data-ttu-id="ceed5-228">*[OAuth OIDC* プロバイダー構成] フィールドに対して検索アイコンを選択して、OIDC 構成のレコードを開きます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-228">Select the search icon against *OAuth OIDC Provider Configuration* field to open the records of OIDC configurations.</span></span> <span data-ttu-id="ceed5-229">[新規]を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-229">Select New.</span></span>

4. <span data-ttu-id="ceed5-230">次の表に、OIDC プロバイダー構成フォームに入力する方法のガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-230">The following table provides guidance on how to fill out OIDC provider configuration form</span></span>

   <span data-ttu-id="ceed5-231">フィールド</span><span class="sxs-lookup"><span data-stu-id="ceed5-231">Field</span></span> | <span data-ttu-id="ceed5-232">推奨値</span><span class="sxs-lookup"><span data-stu-id="ceed5-232">Recommended Value</span></span>
   --- | ---
   <span data-ttu-id="ceed5-233">OIDC プロバイダー</span><span class="sxs-lookup"><span data-stu-id="ceed5-233">OIDC Provider</span></span> |  <span data-ttu-id="ceed5-234">Azure AD</span><span class="sxs-lookup"><span data-stu-id="ceed5-234">Azure AD</span></span>
   <span data-ttu-id="ceed5-235">OIDC メタデータ URL</span><span class="sxs-lookup"><span data-stu-id="ceed5-235">OIDC Metadata URL</span></span> | <span data-ttu-id="ceed5-236">URL は \: 、/.well known/openid-configuration login.microsoftonline.com/<https //login.microsoftonline.com/<tenandId">形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-236">The URL must be in the form https\://login.microsoftonline.com/<tenandId">/.well-known/openid-configuration</span></span> <br/><span data-ttu-id="ceed5-237">手順 3.a から "tenantID" をディレクトリ (テナント) ID に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-237">Replace "tenantID" with Directory (tenant) ID from step 3.a.</span></span>
   <span data-ttu-id="ceed5-238">OIDC 構成キャッシュのライフ スパン</span><span class="sxs-lookup"><span data-stu-id="ceed5-238">OIDC Configuration Cache Life Span</span></span> |  <span data-ttu-id="ceed5-239">120</span><span class="sxs-lookup"><span data-stu-id="ceed5-239">120</span></span>
   <span data-ttu-id="ceed5-240">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ceed5-240">Application</span></span> | <span data-ttu-id="ceed5-241">グローバル</span><span class="sxs-lookup"><span data-stu-id="ceed5-241">Global</span></span>
   <span data-ttu-id="ceed5-242">ユーザークレーム</span><span class="sxs-lookup"><span data-stu-id="ceed5-242">User Claim</span></span> | <span data-ttu-id="ceed5-243">sub</span><span class="sxs-lookup"><span data-stu-id="ceed5-243">sub</span></span>
   <span data-ttu-id="ceed5-244">ユーザー フィールド</span><span class="sxs-lookup"><span data-stu-id="ceed5-244">User Field</span></span> | <span data-ttu-id="ceed5-245">ユーザー ID</span><span class="sxs-lookup"><span data-stu-id="ceed5-245">User ID</span></span>
   <span data-ttu-id="ceed5-246">JTI クレーム検証を有効にする</span><span class="sxs-lookup"><span data-stu-id="ceed5-246">Enable JTI claim verification</span></span> | <span data-ttu-id="ceed5-247">無効</span><span class="sxs-lookup"><span data-stu-id="ceed5-247">Disabled</span></span>

5. <span data-ttu-id="ceed5-248">[OAuth OIDC エンティティ] フォームの [送信と更新] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-248">Select Submit and Update the OAuth OIDC Entity form.</span></span>

## <a name="step-3e-create-a-servicenow-account"></a><span data-ttu-id="ceed5-249">手順 3.e: ServiceNow アカウントを作成する</span><span class="sxs-lookup"><span data-stu-id="ceed5-249">Step 3.e: Create a ServiceNow account</span></span>

<span data-ttu-id="ceed5-250">手順を参照して ServiceNow アカウントを作成し [、ServiceNow でユーザーを作成します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-250">Refer the instructions to create a ServiceNow account, [create a user in ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).</span></span>

<span data-ttu-id="ceed5-251">次の表は、ServiceNow ユーザー アカウントの登録に記入する方法に関するガイダンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="ceed5-251">The following table provides guidance on how to fill out the ServiceNow user account registration</span></span>

<span data-ttu-id="ceed5-252">フィールド</span><span class="sxs-lookup"><span data-stu-id="ceed5-252">Field</span></span> | <span data-ttu-id="ceed5-253">推奨値</span><span class="sxs-lookup"><span data-stu-id="ceed5-253">Recommended Value</span></span>
--- | ---
<span data-ttu-id="ceed5-254">ユーザー ID</span><span class="sxs-lookup"><span data-stu-id="ceed5-254">User ID</span></span> | <span data-ttu-id="ceed5-255">手順 3.c のサービス プリンシパル ID</span><span class="sxs-lookup"><span data-stu-id="ceed5-255">Service Principal ID from step 3.c</span></span>
<span data-ttu-id="ceed5-256">Web サービス アクセスのみ</span><span class="sxs-lookup"><span data-stu-id="ceed5-256">Web service access only</span></span> | <span data-ttu-id="ceed5-257">Checked</span><span class="sxs-lookup"><span data-stu-id="ceed5-257">Checked</span></span>

<span data-ttu-id="ceed5-258">その他の値はすべて既定のままにできます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-258">All other values can be left to default.</span></span>

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a><span data-ttu-id="ceed5-259">手順 3.f: ServiceNow アカウントのナレッジ ロールを有効にする</span><span class="sxs-lookup"><span data-stu-id="ceed5-259">Step 3.f: Enable Knowledge role for the ServiceNow account</span></span>

<span data-ttu-id="ceed5-260">ServiceNow プリンシパル ID をユーザー ID として作成した ServiceNow アカウントにアクセスし、ナレッジ ロールを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="ceed5-260">Access the ServiceNow account you created with ServiceNow Principal ID as User ID, and assign the knowledge role.</span></span> <span data-ttu-id="ceed5-261">ServiceNow アカウントに役割を割り当てる手順については、ユーザーに役割を割り当 [てる方法をご覧ください](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-261">Instructions to assigning a role to a ServiceNow account can be found here: [assign a role to a user](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).</span></span>

<span data-ttu-id="ceed5-262">手順 3.a のクライアント ID としてアプリケーション ID を使用し、手順 3.b のクライアント シークレットを使用して、Azure AD OpenID を使用して ServiceNow インスタンスConnect。</span><span class="sxs-lookup"><span data-stu-id="ceed5-262">Use Application ID as Client ID from step 3.a, and Client secret from step 3.b, to authenticate to your ServiceNow instance using Azure AD OpenID Connect.</span></span>

## <a name="step-4-select-properties-and-filter-data"></a><span data-ttu-id="ceed5-263">手順 4: プロパティを選択し、データをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="ceed5-263">Step 4: Select properties and filter data</span></span>

<span data-ttu-id="ceed5-264">この手順では、ServiceNow データ ソースから使用可能なプロパティを追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-264">In this step, you can add or remove available properties from your ServiceNow data source.</span></span> <span data-ttu-id="ceed5-265">Microsoft 365では、いくつかのプロパティが既に選択されています。</span><span class="sxs-lookup"><span data-stu-id="ceed5-265">Microsoft 365 has already selected few properties by default.</span></span>

<span data-ttu-id="ceed5-266">ServiceNow クエリ文字列を使用すると、記事を同期する条件を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-266">With a ServiceNow query string, you can specify conditions for syncing articles.</span></span> <span data-ttu-id="ceed5-267">これは、Select ステートメント **の Where** **句SQLです**。</span><span class="sxs-lookup"><span data-stu-id="ceed5-267">It's like a **Where** clause in a **SQL Select** statement.</span></span> <span data-ttu-id="ceed5-268">たとえば、発行済みおよびアクティブな記事のみをインデックス化できます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-268">For example, you can choose to index only articles that are published and active.</span></span> <span data-ttu-id="ceed5-269">独自のクエリ文字列を作成する方法については、「フィルターを使用してエンコードされたクエリ文字列を [生成する」を参照してください](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-269">To learn about creating your own query string, see [Generate an encoded query string using a filter](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).</span></span>

<span data-ttu-id="ceed5-270">[プレビュー結果] ボタンを使用して、選択したプロパティとクエリ フィルターのサンプル値を確認します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-270">Use the preview results button to verify the sample values of the selected properties and query filter.</span></span>

## <a name="step-5-manage-search-permissions"></a><span data-ttu-id="ceed5-271">手順 5: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="ceed5-271">Step 5: Manage search permissions</span></span>

<span data-ttu-id="ceed5-272">ServiceNow コネクタは、[すべてのユーザー]または [このデータ ソースにアクセスできるユーザーのみ] に表示 **される検索アクセス許可をサポートしています**。</span><span class="sxs-lookup"><span data-stu-id="ceed5-272">The ServiceNow connector supports search permissions visible to **Everyone** or **Only people with access to this data source**.</span></span> <span data-ttu-id="ceed5-273">インデックス付きデータは検索結果に表示され、それぞれアクセス権を持つ組織内のユーザーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-273">Indexed data appears in the search results and is visible to users in the organization who have access to them respectively.</span></span> <span data-ttu-id="ceed5-274">ServiceNow Connector は、高度なスクリプトを使用せずに既定のユーザー条件のアクセス許可をサポートします。</span><span class="sxs-lookup"><span data-stu-id="ceed5-274">ServiceNow Connector supports default user criteria permissions without advanced scripts.</span></span> <span data-ttu-id="ceed5-275">コネクタが高度なスクリプトを使用してユーザー条件を見つけると、そのユーザー条件を使用しているすべてのデータが検索結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="ceed5-275">When the connector finds a user criteria with advanced script, all data using that user criteria won't be shown in search results.</span></span>

<span data-ttu-id="ceed5-276">[このデータソースへのアクセス権を持つユーザーのみ] を選択する場合は、ServiceNow インスタンスに Azure Active Directory (AAD) プロビジョニングされたユーザーまたは非 AAD ユーザーが含まれるかどうかをさらに選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-276">If you select **Only people with access to this data source**, you need to further choose whether your ServiceNow instance has Azure Active Directory (AAD) provisioned users or Non-AAD users.</span></span>

>[!NOTE]
><span data-ttu-id="ceed5-277">[このデータ ソースにアクセスできるユーザーのみ] を選択した場合、ServiceNow コネクタ **はプレビュー中です**。</span><span class="sxs-lookup"><span data-stu-id="ceed5-277">The ServiceNow connector is in **preview** if you choose **Only people with access to this data source**.</span></span>

>[!NOTE]
><span data-ttu-id="ceed5-278">ID ソースの種類として [AAD] を選択した場合は、ServiceNow の電子メール対象プロパティに UPN ソース プロパティを割り当ててみてください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-278">If you choose AAD as the type of identity source, make sure you are assigning UPN source property to email targeted property in ServiceNow.</span></span> <span data-ttu-id="ceed5-279">マッピングを確認または変更するには、「Azure Active Directory での SaaS アプリケーションのユーザー プロビジョニング属性マッピング[のカスタマイズ」を参照Azure Active Directory。](/azure/active-directory/app-provisioning/customize-application-attributes)</span><span class="sxs-lookup"><span data-stu-id="ceed5-279">To verify or change your mappings, see [Customizing user provisioning attribute-mappings for SaaS applications in Azure Active Directory](/azure/active-directory/app-provisioning/customize-application-attributes).</span></span>

<span data-ttu-id="ceed5-280">ServiceNow インスタンスから ACL を取り込み、ID の種類に対して "非 AAD" を選択した場合は [、「Map your Azure AD Identitys」](map-non-aad.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceed5-280">If you chose to ingest an ACL from your ServiceNow instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="managing-search-permissions-in-microsoft-search"></a><span data-ttu-id="ceed5-281">Microsoft Search での検索アクセス許可の管理</span><span class="sxs-lookup"><span data-stu-id="ceed5-281">Managing Search Permissions in Microsoft Search</span></span>

<span data-ttu-id="ceed5-282">次のビデオでは、Servicenow コネクタを使用してナレッジ記事のインデックスを作成し、ユーザー条件のアクセス許可を定義し、ServiceNow と Microsoft Search インデックスの間の変更をシームレスに同期する方法を確認できます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-282">In the following video you can see how to use the Servicenow connector to index knowledge articles, define user criteria permissions, and seamlessly synchronize the changes between ServiceNow and Microsoft Search index.</span></span>

> [!VIDEO https://www.youtube-nocookie.com/embed/TVSkJpk1RiE]

## <a name="step-6-assign-property-labels"></a><span data-ttu-id="ceed5-283">手順 6: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="ceed5-283">Step 6: Assign property labels</span></span>

<span data-ttu-id="ceed5-284">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-284">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a><span data-ttu-id="ceed5-285">手順 7: スキーマの管理</span><span class="sxs-lookup"><span data-stu-id="ceed5-285">Step 7: Manage schema</span></span>

<span data-ttu-id="ceed5-286">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-286">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a><span data-ttu-id="ceed5-287">手順 8: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="ceed5-287">Step 8: Choose refresh settings</span></span>

<span data-ttu-id="ceed5-288">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-288">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
><span data-ttu-id="ceed5-289">ID の場合は、スケジュールされたフル クロールだけが適用されます。</span><span class="sxs-lookup"><span data-stu-id="ceed5-289">For identities, only full crawl scheduled will be applied.</span></span>

## <a name="step-9-review-connection"></a><span data-ttu-id="ceed5-290">手順 9: 接続の確認</span><span class="sxs-lookup"><span data-stu-id="ceed5-290">Step 9: Review Connection</span></span>

<span data-ttu-id="ceed5-291">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-291">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="ceed5-292">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ceed5-292">Troubleshooting</span></span>

<span data-ttu-id="ceed5-293">接続を発行し、結果ページをカスタマイズした後、管理センターの [ **コネクタ** ] タブで状態を [確認できます](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-293">After publishing your connection, customizing the results page, you can review the status under the **Connectors** tab in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="ceed5-294">更新と削除を行う方法については、「コネクタの管理 [」を参照してください](manage-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="ceed5-294">To learn how to make updates and deletions, see [Manage your connector](manage-connector.md).</span></span>

## <a name="limitations"></a><span data-ttu-id="ceed5-295">制限事項</span><span class="sxs-lookup"><span data-stu-id="ceed5-295">Limitations</span></span>

<span data-ttu-id="ceed5-296">ServiceNow Graphコネクタには、最新のリリースで次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="ceed5-296">ServiceNow Graph connector has the following limitations in its latest release:</span></span>

- <span data-ttu-id="ceed5-297">組織内のすべてのユーザーが利用できるナレッジ 記事のインデックス作成は、一般的に利用できる機能です。</span><span class="sxs-lookup"><span data-stu-id="ceed5-297">Indexing knowledge articles available to everyone in an organization is a generally available feature.</span></span>
- <span data-ttu-id="ceed5-298">*[検索のアクセス許可の管理] ステップ* でこのデータ ソース機能にアクセスできるユーザーだけがプレビューに表示され、ユーザー条件 [のアクセス許可のみを](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 処理します。</span><span class="sxs-lookup"><span data-stu-id="ceed5-298">*Only people with access to this data source* feature under Manage Search permissions step is in preview and processes only [user criteria](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) permissions.</span></span> <span data-ttu-id="ceed5-299">その他の種類のアクセス許可は検索結果に適用されません。</span><span class="sxs-lookup"><span data-stu-id="ceed5-299">Any other type of access permissions won't be applied in the search results.</span></span>
- <span data-ttu-id="ceed5-300">高度なスクリプトを含むユーザー条件は、現在のプレビュー バージョンではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ceed5-300">User criteria with advanced scripts aren't supported in the current preview version.</span></span> <span data-ttu-id="ceed5-301">アクセス制限を持つナレッジ記事は、すべてのユーザーのアクセスを拒否してインデックスが作成され、サポートされるまで検索結果に表示されません。</span><span class="sxs-lookup"><span data-stu-id="ceed5-301">Knowledge articles with an access restriction will be indexed with deny everyone access, and won't appear in search results to any user until we support them.</span></span>