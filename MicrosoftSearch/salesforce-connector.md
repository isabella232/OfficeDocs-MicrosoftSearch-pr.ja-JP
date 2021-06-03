---
title: Microsoft Search Graph Salesforce コネクタ
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
description: Microsoft Search 用の Salesforce Graphコネクタをセットアップする
ms.openlocfilehash: d4d19c05f82ddb28c4dc3e6719bf8ea8d7284cc3
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720990"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="91c90-103">Salesforce Graph コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="91c90-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="91c90-104">Salesforce Graphコネクタを使用すると、組織は Salesforce インスタンスの連絡先、機会、見込み客、およびアカウント オブジェクトをインデックス化できます。</span><span class="sxs-lookup"><span data-stu-id="91c90-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="91c90-105">Salesforce からコネクタとインデックス コンテンツを構成した後、エンド ユーザーは任意の Microsoft Search クライアントからそれらのアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="91c90-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="91c90-106">一般的な [**コネクタのセットアップGraph**](configure-connector.md) Graphについては、「Graphコネクタのセットアップ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="91c90-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="91c90-107">この記事は、Salesforce クライアント コネクタを構成、実行、および監視するGraphです。</span><span class="sxs-lookup"><span data-stu-id="91c90-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="91c90-108">これは、一般的なセットアップ プロセスを補足し、Salesforce アプリケーション コネクタにのみ適用される手順Graphします。</span><span class="sxs-lookup"><span data-stu-id="91c90-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="91c90-109">この記事には、制限に関する [情報も含まれています](#limitations)。</span><span class="sxs-lookup"><span data-stu-id="91c90-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="91c90-110">Salesforce Graphコネクタは現在、Summer '19 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="91c90-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="91c90-111">使用を開始する前に</span><span class="sxs-lookup"><span data-stu-id="91c90-111">Before you get started</span></span>

<span data-ttu-id="91c90-112">Salesforce インスタンスに接続するには、OAuth 認証用の Salesforce インスタンス URL、クライアント ID、およびクライアント シークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="91c90-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="91c90-113">次の手順では、自分または Salesforce 管理者が Salesforce アカウントからこの情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="91c90-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="91c90-114">Salesforce インスタンスにログインし、[セットアップ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="91c90-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="91c90-115">[アプリ] ->に移動します。</span><span class="sxs-lookup"><span data-stu-id="91c90-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="91c90-116">[新 **しい接続アプリ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="91c90-116">Select **New connected app**.</span></span>

- <span data-ttu-id="91c90-117">次のように API セクションを完了します。</span><span class="sxs-lookup"><span data-stu-id="91c90-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="91c90-118">[Oauth を有効にする **] チェック ボックスをオン設定。**</span><span class="sxs-lookup"><span data-stu-id="91c90-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="91c90-119">コールバック URL を次のように指定します。 [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="91c90-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="91c90-120">これらの必須の OAuth スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="91c90-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="91c90-121">データへのアクセスと管理 (api)</span><span class="sxs-lookup"><span data-stu-id="91c90-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="91c90-122">いつでも代理で要求を実行する (refresh_token、offline_access)</span><span class="sxs-lookup"><span data-stu-id="91c90-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="91c90-123">[Web サーバー フローにシークレット **を要求する] チェック ボックスをオンにします**。</span><span class="sxs-lookup"><span data-stu-id="91c90-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="91c90-124">アプリを保存します。</span><span class="sxs-lookup"><span data-stu-id="91c90-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="91c90-125">![管理者が上記のすべての必須構成を入力した後の Salesforce インスタンスの API セクション。](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="91c90-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="91c90-126">コンシューマー キーとコンシューマー シークレットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="91c90-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="91c90-127">この情報は、管理ポータルで 設定 コネクタの接続設定 Graphを構成するときに、クライアント ID とクライアント シークレットMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="91c90-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="91c90-128">![管理者が必要なすべての構成を送信した後、Salesforce インスタンスの API セクションによって返される結果。</span><span class="sxs-lookup"><span data-stu-id="91c90-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="91c90-129">コンシューマー キーは左側の列の上部に、コンシューマー シークレットは右列の上部に表示されます。](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="91c90-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="91c90-130">Salesforce インスタンスを閉じる前に、次の手順に従って更新トークンの有効期限が切れなかってください。</span><span class="sxs-lookup"><span data-stu-id="91c90-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="91c90-131">[アプリ] -> マネージャーに移動します。</span><span class="sxs-lookup"><span data-stu-id="91c90-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="91c90-132">作成したアプリを見つけて、右側のドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="91c90-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="91c90-133">[管理] **の選択**</span><span class="sxs-lookup"><span data-stu-id="91c90-133">Select **Manage**</span></span>
    - <span data-ttu-id="91c90-134">ポリシー **の編集を選択する**</span><span class="sxs-lookup"><span data-stu-id="91c90-134">Select **edit policies**</span></span>
    - <span data-ttu-id="91c90-135">更新トークン ポリシーの場合、[更新トークン **は失効するまで有効です] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="91c90-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="91c90-136">!["Refresh token is valid is valid until revoked" という名前の Refresh Token Policy を選択します。](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="91c90-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="91c90-137">[これで、M365 管理センターを](https://admin.microsoft.com/)使用して、このコネクタのセットアップ プロセスの残りのGraphできます。</span><span class="sxs-lookup"><span data-stu-id="91c90-137">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="91c90-138">手順 1: 管理センター GraphコネクタをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="91c90-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="91c90-139">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="91c90-139">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="91c90-140">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="91c90-140">Step 2: Name the connection</span></span>

<span data-ttu-id="91c90-141">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="91c90-141">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="91c90-142">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="91c90-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="91c90-143">インスタンス URL の場合は、https://[domain].my.salesforce.com を使用します。ドメインは組織の Salesforce ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="91c90-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="91c90-144">Salesforce インスタンスから取得したクライアント ID とクライアント シークレットを入力し、[サインイン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="91c90-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="91c90-145">これらの設定で初めてサインインしようとすると、管理者のユーザー名とパスワードを使用して Salesforce にログインするためのポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91c90-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="91c90-146">次のスクリーンショットは、ポップアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="91c90-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="91c90-147">資格情報を入力し、[ログイン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="91c90-147">Enter your credentials and select "Log In".</span></span>

  ![ユーザー名とパスワードを求めるログイン ポップアップ。](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="91c90-149">ポップアップが表示されない場合は、ブラウザーでブロックされている可能性があります。ポップアップとリダイレクトを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91c90-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="91c90-150">下のスクリーンショットに示すように、「接続が成功しました」という緑色のバナーを検索して、接続が成功したと確認します。</span><span class="sxs-lookup"><span data-stu-id="91c90-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="91c90-151">![成功したログインのスクリーンショット。</span><span class="sxs-lookup"><span data-stu-id="91c90-151">![Screenshot of successful login.</span></span> <span data-ttu-id="91c90-152">「接続が成功しました」という緑色のバナーが、Salesforce インスタンス URL のフィールドの下に表示されます。](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="91c90-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="91c90-153">手順 4: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="91c90-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="91c90-154">このデータ ソースから検索結果を表示するユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91c90-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="91c90-155">特定のユーザー (Azure Azure Active Directory) AD または非 Azure AD ユーザーに検索結果の表示のみを許可する場合は、ID をマップしてください。</span><span class="sxs-lookup"><span data-stu-id="91c90-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

### <a name="step-4a-select-permissions"></a><span data-ttu-id="91c90-156">手順 4.a: アクセス許可の選択</span><span class="sxs-lookup"><span data-stu-id="91c90-156">Step 4.a: Select permissions</span></span>

<span data-ttu-id="91c90-157">Salesforce インスタンスからアクセス制御リスト (ACL) を取り込むか、組織内のすべてのユーザーにこのデータ ソースからの検索結果を表示できます。</span><span class="sxs-lookup"><span data-stu-id="91c90-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="91c90-158">ACL には、Azure Active Directory (AAD) ID (Azure AD から Salesforce にフェデレーションされているユーザー)、Azure AD 以外の ID (Azure AD で対応する ID を持つネイティブ Salesforce ユーザー)、または両方が含まれます。</span><span class="sxs-lookup"><span data-stu-id="91c90-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="91c90-159">Ping ID や secureAuth などのサードパーティ ID プロバイダーを使用する場合は、ID の種類として "非 AAD" を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91c90-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91c90-160">![管理者が完了した [アクセス許可] 画面を選択します。管理者は[このデータ ソースにアクセスできるユーザーのみ] オプションを選択し、ID の種類のドロップダウン メニューから [AAD] も選択しています。](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="91c90-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="91c90-161">Salesforce インスタンスから ACL を取り込み、ID の種類として [非 AAD] を選択した場合は、「Id のマッピング方法については [、「Map your Azure AD Identitys」](map-non-aad.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91c90-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="step-4b-map-aad-identities"></a><span data-ttu-id="91c90-162">手順 4.b: AAD ID のマップ</span><span class="sxs-lookup"><span data-stu-id="91c90-162">Step 4.b: Map AAD identities</span></span>

<span data-ttu-id="91c90-163">Salesforce インスタンスから ACL を取り込み、ID の種類として [AAD] を選択した場合は、「Id のマッピング方法については [、「Map your Azure AD Identitys」](map-aad.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91c90-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="91c90-164">Azure AD SSO を設定する方法については、このチュートリアルを参照 [してください](/azure/active-directory/saas-apps/salesforce-tutorial)。</span><span class="sxs-lookup"><span data-stu-id="91c90-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

### <a name="apply-user-mapping-to-sync-your-salesforce-identities-to-azure-ad-identities"></a><span data-ttu-id="91c90-165">ユーザー マッピングを適用して、Salesforce ID を Azure ID AD同期する</span><span class="sxs-lookup"><span data-stu-id="91c90-165">Apply user mapping to sync your Salesforce identities to Azure AD identities</span></span>

<span data-ttu-id="91c90-166">このビデオでは、Salesforce インスタンスに対する認証プロセスを確認し、Azure Active Directory 以外の ID を Azure Active Directory ID に同期し、適切なセキュリティ トリミングを Salesforce アイテムに適用できます。</span><span class="sxs-lookup"><span data-stu-id="91c90-166">In this video you can see the process to authenticate to your Salesforce instance, sync your non-Azure Active Directory identities to your Azure Active Directory identities, and apply the proper security trimmings to your Salesforce items.</span></span>

> [!VIDEO https://www.youtube.com/watch?v=SZYiFxZMKcM]

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="91c90-167">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="91c90-167">Step 5: Assign property labels</span></span>

<span data-ttu-id="91c90-168">各ラベルにソース プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="91c90-168">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="91c90-169">この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果が向上します。</span><span class="sxs-lookup"><span data-stu-id="91c90-169">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="91c90-170">既定では、"Title"、"URL"、"CreatedBy"、"LastModifiedBy" のような一部のラベルには、ソース プロパティが既に割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="91c90-170">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="91c90-171">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="91c90-171">Step 6: Manage schema</span></span>

<span data-ttu-id="91c90-172">インデックスを作成するソース プロパティを選択して、検索結果に表示できます。</span><span class="sxs-lookup"><span data-stu-id="91c90-172">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="91c90-173">既定では、接続ウィザードは、一連のソース プロパティに基づいて検索スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="91c90-173">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="91c90-174">検索スキーマ ページの各プロパティと属性のチェック ボックスをオンにすると、変更できます。</span><span class="sxs-lookup"><span data-stu-id="91c90-174">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="91c90-175">検索スキーマ属性には、検索、クエリ、取得、絞り込みがあります。</span><span class="sxs-lookup"><span data-stu-id="91c90-175">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="91c90-176">絞り込みでは、後で検索エクスペリエンスでカスタム絞り込み条件またはフィルターとして使用できるプロパティを定義できます。</span><span class="sxs-lookup"><span data-stu-id="91c90-176">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91c90-177">![各ソース プロパティのスキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="91c90-177">![Select the schema for each source property.</span></span> <span data-ttu-id="91c90-178">オプションは、クエリ、検索、取得、絞り込みです。](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="91c90-178">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="91c90-179">手順 7: 更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="91c90-179">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="91c90-180">Salesforce コネクタは現在、フル クロールの更新スケジュールのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="91c90-180">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="91c90-181">フル クロールでは、削除されたオブジェクトと、以前に Microsoft Search インデックスに同期されたユーザーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="91c90-181">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="91c90-182">推奨されるスケジュールは、フル クロールの場合は 1 週間です。</span><span class="sxs-lookup"><span data-stu-id="91c90-182">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="91c90-183">手順 8: 接続の確認</span><span class="sxs-lookup"><span data-stu-id="91c90-183">Step 8: Review connection</span></span>

<span data-ttu-id="91c90-184">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="91c90-184">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="91c90-185">制限事項</span><span class="sxs-lookup"><span data-stu-id="91c90-185">Limitations</span></span>

- <span data-ttu-id="91c90-186">現在Graphは、Salesforce の個人グループを使用した、地域ベースの Apex ベースの共有と共有をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="91c90-186">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="91c90-187">Salesforce API には、Graph コネクタが使用する既知のバグがあります。この場合、現在、リードのプライベート組織全体の既定値は適用されません。</span><span class="sxs-lookup"><span data-stu-id="91c90-187">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="91c90-188">フィールドにプロファイルに対してフィールド レベルセキュリティ (FLS) が設定されている場合、Graph コネクタは、その Salesforce 組織のプロファイルに対してそのフィールドを取り込む必要があります。その結果、ユーザーはそれらのフィールドの値を検索したり、結果に表示したりしなかることができます。</span><span class="sxs-lookup"><span data-stu-id="91c90-188">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="91c90-189">[スキーマの管理] 画面で、これらの一般的な標準プロパティ名が 1 回表示され、オプションは **クエリ**、**検索**、取得、絞り込み、すべてまたはなしに適用されます。</span><span class="sxs-lookup"><span data-stu-id="91c90-189">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="91c90-190">名前</span><span class="sxs-lookup"><span data-stu-id="91c90-190">Name</span></span>
    - <span data-ttu-id="91c90-191">Url</span><span class="sxs-lookup"><span data-stu-id="91c90-191">Url</span></span>
    - <span data-ttu-id="91c90-192">説明</span><span class="sxs-lookup"><span data-stu-id="91c90-192">Description</span></span>
    - <span data-ttu-id="91c90-193">FAX</span><span class="sxs-lookup"><span data-stu-id="91c90-193">Fax</span></span>
    - <span data-ttu-id="91c90-194">Phone</span><span class="sxs-lookup"><span data-stu-id="91c90-194">Phone</span></span>
    - <span data-ttu-id="91c90-195">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="91c90-195">MobilePhone</span></span>
    - <span data-ttu-id="91c90-196">メール</span><span class="sxs-lookup"><span data-stu-id="91c90-196">Email</span></span>
    - <span data-ttu-id="91c90-197">型</span><span class="sxs-lookup"><span data-stu-id="91c90-197">Type</span></span>
    - <span data-ttu-id="91c90-198">タイトル</span><span class="sxs-lookup"><span data-stu-id="91c90-198">Title</span></span>
    - <span data-ttu-id="91c90-199">AccountId</span><span class="sxs-lookup"><span data-stu-id="91c90-199">AccountId</span></span>
    - <span data-ttu-id="91c90-200">AccountName</span><span class="sxs-lookup"><span data-stu-id="91c90-200">AccountName</span></span>
    - <span data-ttu-id="91c90-201">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="91c90-201">AccountUrl</span></span>
    - <span data-ttu-id="91c90-202">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="91c90-202">AccountOwner</span></span>
    - <span data-ttu-id="91c90-203">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="91c90-203">AccountOwnerUrl</span></span>
    - <span data-ttu-id="91c90-204">所有者</span><span class="sxs-lookup"><span data-stu-id="91c90-204">Owner</span></span>
    - <span data-ttu-id="91c90-205">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="91c90-205">OwnerUrl</span></span>
    - <span data-ttu-id="91c90-206">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="91c90-206">CreatedBy</span></span>
    - <span data-ttu-id="91c90-207">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="91c90-207">CreatedByUrl</span></span>
    - <span data-ttu-id="91c90-208">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="91c90-208">LastModifiedBy</span></span>
    - <span data-ttu-id="91c90-209">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="91c90-209">LastModifiedByUrl</span></span>
    - <span data-ttu-id="91c90-210">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="91c90-210">LastModifiedDate</span></span>
    - <span data-ttu-id="91c90-211">ObjectName</span><span class="sxs-lookup"><span data-stu-id="91c90-211">ObjectName</span></span>
