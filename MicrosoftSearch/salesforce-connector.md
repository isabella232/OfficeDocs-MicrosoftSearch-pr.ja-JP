---
title: Microsoft Search の Salesforce Graph コネクタ
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
description: Microsoft Search の Salesforce Graph コネクタをセットアップする
ms.openlocfilehash: 59cc321a40655a1c1e5edf615dd43a2a56c8ddbc
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031685"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="b4b05-103">Salesforce Graph コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="b4b05-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="b4b05-104">Salesforce Graph コネクタを使用すると、組織は Salesforce インスタンスの連絡先、商談、見込み客、およびアカウント オブジェクトのインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="b4b05-105">Salesforce からコネクタとインデックス コンテンツを構成した後、エンド ユーザーは任意の Microsoft Search クライアントからそれらのアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="b4b05-106">Graph コネクタ [**のセットアップの一**](configure-connector.md) 般的な手順については、Graph コネクタのセットアップに関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b4b05-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="b4b05-107">この記事は、Salesforce Graph コネクタを構成、実行、および監視するユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="b4b05-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="b4b05-108">これは、一般的なセットアップ プロセスを補足し、Salesforce Graph コネクタにのみ適用される手順を示します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="b4b05-109">この記事には、制限に関する [情報も含まれています](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="b4b05-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="b4b05-110">Salesforce Graph コネクタは現在、Summer '19 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b4b05-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="b4b05-111">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="b4b05-111">Before you get started</span></span>

<span data-ttu-id="b4b05-112">Salesforce インスタンスに接続するには、OAuth 認証用の Salesforce インスタンス URL、クライアント ID、およびクライアント シークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="b4b05-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="b4b05-113">次の手順では、自分または Salesforce 管理者が Salesforce アカウントからこの情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="b4b05-114">Salesforce インスタンスにログインし、[セットアップ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="b4b05-115">[アプリ] ->に移動します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="b4b05-116">[新 **しい接続アプリ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b4b05-116">Select **New connected app**.</span></span>

- <span data-ttu-id="b4b05-117">次のように API セクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="b4b05-118">[Oauth 設定を有効 **にする] のチェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="b4b05-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="b4b05-119">コールバック URL を次のように指定します。 [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="b4b05-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="b4b05-120">これらの必須の OAuth スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="b4b05-121">データへのアクセスと管理 (api)</span><span class="sxs-lookup"><span data-stu-id="b4b05-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="b4b05-122">いつでも代理で要求を実行する (refresh_token、offline_access)</span><span class="sxs-lookup"><span data-stu-id="b4b05-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="b4b05-123">[Web サーバー フローにシークレット **を要求する] チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="b4b05-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="b4b05-124">アプリを保存します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b4b05-125">![管理者が上記のすべての必須構成を入力した後の Salesforce インスタンスの API セクション。](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="b4b05-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="b4b05-126">コンシューマー キーとコンシューマー シークレットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="b4b05-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="b4b05-127">この情報は、Microsoft 365 管理ポータルでグラフ コネクタの接続設定を構成するときに、クライアント ID とクライアント シークレットとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="b4b05-128">![管理者が必要なすべての構成を送信した後、Salesforce インスタンスの API セクションによって返される結果。</span><span class="sxs-lookup"><span data-stu-id="b4b05-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="b4b05-129">コンシューマー キーは左側の列の上部に、コンシューマー シークレットは右列の上部に表示されます。](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="b4b05-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="b4b05-130">Salesforce インスタンスを閉じる前に、次の手順に従って更新トークンの有効期限が切れなかってください。</span><span class="sxs-lookup"><span data-stu-id="b4b05-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="b4b05-131">[アプリ] -> マネージャーに移動します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="b4b05-132">作成したアプリを見つけて、右側のドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="b4b05-133">[管理] **の選択**</span><span class="sxs-lookup"><span data-stu-id="b4b05-133">Select **Manage**</span></span>
    - <span data-ttu-id="b4b05-134">ポリシー **の編集を選択する**</span><span class="sxs-lookup"><span data-stu-id="b4b05-134">Select **edit policies**</span></span>
    - <span data-ttu-id="b4b05-135">更新トークン ポリシーの場合、[更新トークン **は失効するまで有効です] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="b4b05-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="b4b05-136">!["Refresh token is valid is valid until revoked" という名前の Refresh Token Policy を選択します。](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="b4b05-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="b4b05-137">[これで、M365 管理センターを](https://admin.microsoft.com/)使用して、Graph コネクタのセットアップ プロセスの残りの部分を完了できます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-137">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b4b05-138">手順 1: Microsoft 365 管理センターに Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="b4b05-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b4b05-139">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="b4b05-139">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="b4b05-140">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="b4b05-140">Step 2: Name the connection</span></span>

<span data-ttu-id="b4b05-141">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="b4b05-141">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="b4b05-142">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="b4b05-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="b4b05-143">インスタンス URL の場合は、https://[domain].my.salesforce.com を使用します。ドメインは組織の Salesforce ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="b4b05-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="b4b05-144">Salesforce インスタンスから取得したクライアント ID とクライアント シークレットを入力し、[サインイン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="b4b05-145">これらの設定で初めてサインインしようとすると、管理者のユーザー名とパスワードを使用して Salesforce にログインするためのポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="b4b05-146">次のスクリーンショットは、ポップアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="b4b05-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="b4b05-147">資格情報を入力し、[ログイン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-147">Enter your credentials and select "Log In".</span></span>

  ![ユーザー名とパスワードを求めるログイン ポップアップ。](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="b4b05-149">ポップアップが表示されない場合は、ブラウザーでブロックされている可能性があります。ポップアップとリダイレクトを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4b05-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="b4b05-150">下のスクリーンショットに示すように、「接続が成功しました」という緑色のバナーを検索して、接続が成功したと確認します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="b4b05-151">![成功したログインのスクリーンショット。</span><span class="sxs-lookup"><span data-stu-id="b4b05-151">![Screenshot of successful login.</span></span> <span data-ttu-id="b4b05-152">「接続が成功しました」という緑色のバナーが、Salesforce インスタンス URL のフィールドの下に表示されます。](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="b4b05-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="b4b05-153">手順 4: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="b4b05-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="b4b05-154">このデータ ソースから検索結果を表示するユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4b05-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="b4b05-155">特定の Azure Active Directory (Azure AD) または Azure 以外のユーザー AD検索結果の表示のみを許可する場合は、ID をマップしてください。</span><span class="sxs-lookup"><span data-stu-id="b4b05-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

## <a name="step-4a-select-permissions"></a><span data-ttu-id="b4b05-156">手順 4a: アクセス許可の選択</span><span class="sxs-lookup"><span data-stu-id="b4b05-156">Step 4a: Select permissions</span></span>

<span data-ttu-id="b4b05-157">Salesforce インスタンスからアクセス制御リスト (ACL) を取り込むか、組織内のすべてのユーザーにこのデータ ソースからの検索結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="b4b05-158">ACL には、Azure Active Directory (AAD) ID (Azure AD から Salesforce にフェデレーションされているユーザー)、Azure AD 以外の ID (Azure AD で対応する ID を持つネイティブ Salesforce ユーザー)、または両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="b4b05-159">Ping ID や secureAuth などのサードパーティ ID プロバイダーを使用する場合は、ID の種類として "非 AAD" を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4b05-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b4b05-160">![管理者が完了した [アクセス許可] 画面を選択します。管理者は[このデータ ソースにアクセスできるユーザーのみ] オプションを選択し、ID の種類のドロップダウン メニューから [AAD] も選択しています。](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="b4b05-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="b4b05-161">Salesforce インスタンスから ACL を取り込み、ID の種類として [非 AAD] を選択した場合は、「Id のマッピング方法については [、「Map your Azure AD Identitys」](map-non-aad.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4b05-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

## <a name="step-4b-map-aad-identities"></a><span data-ttu-id="b4b05-162">手順 4b: AAD ID のマップ</span><span class="sxs-lookup"><span data-stu-id="b4b05-162">Step 4b: Map AAD identities</span></span>

<span data-ttu-id="b4b05-163">Salesforce インスタンスから ACL を取り込み、ID の種類として [AAD] を選択した場合は、「Id のマッピング方法については [、「Map your Azure AD Identitys」](map-aad.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b4b05-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="b4b05-164">Azure AD SSO を設定する方法については、このチュートリアルを参照 [してください](/azure/active-directory/saas-apps/salesforce-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="b4b05-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="b4b05-165">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b4b05-165">Step 5: Assign property labels</span></span>

<span data-ttu-id="b4b05-166">各ラベルにソース プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-166">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="b4b05-167">この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果が向上します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-167">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="b4b05-168">既定では、"Title"、"URL"、"CreatedBy"、"LastModifiedBy" のような一部のラベルには、ソース プロパティが既に割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="b4b05-168">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="b4b05-169">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="b4b05-169">Step 6: Manage schema</span></span>

<span data-ttu-id="b4b05-170">インデックスを作成するソース プロパティを選択して、検索結果に表示できます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-170">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="b4b05-171">既定では、接続ウィザードは、一連のソース プロパティに基づいて検索スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-171">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="b4b05-172">検索スキーマ ページの各プロパティと属性のチェック ボックスをオンにすると、変更できます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-172">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="b4b05-173">検索スキーマ属性には、検索、クエリ、取得、絞り込みがあります。</span><span class="sxs-lookup"><span data-stu-id="b4b05-173">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="b4b05-174">絞り込みでは、後で検索エクスペリエンスでカスタム絞り込み条件またはフィルターとして使用できるプロパティを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-174">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b4b05-175">![各ソース プロパティのスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4b05-175">![Select the schema for each source property.</span></span> <span data-ttu-id="b4b05-176">オプションは、クエリ、検索、取得、絞り込みです。](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="b4b05-176">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="b4b05-177">手順 7: 更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="b4b05-177">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="b4b05-178">Salesforce コネクタは現在、フル クロールの更新スケジュールのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b4b05-178">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b4b05-179">フル クロールでは、削除されたオブジェクトと、以前に Microsoft Search インデックスに同期されたユーザーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-179">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="b4b05-180">推奨されるスケジュールは、フル クロールの場合は 1 週間です。</span><span class="sxs-lookup"><span data-stu-id="b4b05-180">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="b4b05-181">手順 8: 接続の確認</span><span class="sxs-lookup"><span data-stu-id="b4b05-181">Step 8: Review connection</span></span>

<span data-ttu-id="b4b05-182">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="b4b05-182">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="b4b05-183">制限事項</span><span class="sxs-lookup"><span data-stu-id="b4b05-183">Limitations</span></span>

- <span data-ttu-id="b4b05-184">Graph コネクタは現在、Salesforce の個人グループを使用した Apex ベースの地域ベースの共有と共有をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b4b05-184">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="b4b05-185">Graph コネクタが使用する Salesforce API には既知のバグがあります。現在、リードのプライベート組織全体の既定値は適用されません。</span><span class="sxs-lookup"><span data-stu-id="b4b05-185">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="b4b05-186">フィールドにプロファイルのフィールド レベルセキュリティ (FLS) が設定されている場合、グラフ コネクタは、その Salesforce 組織のプロファイルに対してそのフィールドを取り込む必要があります。その結果、ユーザーはそれらのフィールドの値を検索したり、結果に表示したりしなかることができます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-186">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="b4b05-187">[スキーマの管理] 画面で、これらの一般的な標準プロパティ名が 1 回表示され、オプションは **クエリ**、**検索**、取得、絞り込み、すべてまたはなしに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b4b05-187">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="b4b05-188">名前</span><span class="sxs-lookup"><span data-stu-id="b4b05-188">Name</span></span>
    - <span data-ttu-id="b4b05-189">Url</span><span class="sxs-lookup"><span data-stu-id="b4b05-189">Url</span></span>
    - <span data-ttu-id="b4b05-190">説明</span><span class="sxs-lookup"><span data-stu-id="b4b05-190">Description</span></span>
    - <span data-ttu-id="b4b05-191">FAX</span><span class="sxs-lookup"><span data-stu-id="b4b05-191">Fax</span></span>
    - <span data-ttu-id="b4b05-192">Phone</span><span class="sxs-lookup"><span data-stu-id="b4b05-192">Phone</span></span>
    - <span data-ttu-id="b4b05-193">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="b4b05-193">MobilePhone</span></span>
    - <span data-ttu-id="b4b05-194">メール</span><span class="sxs-lookup"><span data-stu-id="b4b05-194">Email</span></span>
    - <span data-ttu-id="b4b05-195">型</span><span class="sxs-lookup"><span data-stu-id="b4b05-195">Type</span></span>
    - <span data-ttu-id="b4b05-196">Title</span><span class="sxs-lookup"><span data-stu-id="b4b05-196">Title</span></span>
    - <span data-ttu-id="b4b05-197">AccountId</span><span class="sxs-lookup"><span data-stu-id="b4b05-197">AccountId</span></span>
    - <span data-ttu-id="b4b05-198">AccountName</span><span class="sxs-lookup"><span data-stu-id="b4b05-198">AccountName</span></span>
    - <span data-ttu-id="b4b05-199">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="b4b05-199">AccountUrl</span></span>
    - <span data-ttu-id="b4b05-200">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="b4b05-200">AccountOwner</span></span>
    - <span data-ttu-id="b4b05-201">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="b4b05-201">AccountOwnerUrl</span></span>
    - <span data-ttu-id="b4b05-202">Owner</span><span class="sxs-lookup"><span data-stu-id="b4b05-202">Owner</span></span>
    - <span data-ttu-id="b4b05-203">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="b4b05-203">OwnerUrl</span></span>
    - <span data-ttu-id="b4b05-204">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="b4b05-204">CreatedBy</span></span>
    - <span data-ttu-id="b4b05-205">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="b4b05-205">CreatedByUrl</span></span>
    - <span data-ttu-id="b4b05-206">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="b4b05-206">LastModifiedBy</span></span>
    - <span data-ttu-id="b4b05-207">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="b4b05-207">LastModifiedByUrl</span></span>
    - <span data-ttu-id="b4b05-208">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="b4b05-208">LastModifiedDate</span></span>
    - <span data-ttu-id="b4b05-209">ObjectName</span><span class="sxs-lookup"><span data-stu-id="b4b05-209">ObjectName</span></span>