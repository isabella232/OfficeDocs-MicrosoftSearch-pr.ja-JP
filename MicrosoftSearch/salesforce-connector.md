---
title: Microsoft Search の Salesforce connector
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の Salesforce connector をセットアップする
ms.openlocfilehash: 149d1d9a297e09e9b895aeb0947c7ff4a3cbdf84
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367651"
---
# <a name="salesforce-connector-preview"></a><span data-ttu-id="4b3af-103">Salesforce コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="4b3af-103">Salesforce connector (preview)</span></span>

<span data-ttu-id="4b3af-104">Salesforce Graph コネクタを使用すると、組織は Salesforce インスタンスの連絡先、営業案件、潜在顧客、およびアカウントのオブジェクトにインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-104">With the Salesforce Graph connector, your organization can index Contacts, Opportunities, Leads and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="4b3af-105">Salesforce からコネクタとインデックスコンテンツを構成した後は、エンドユーザーは任意の Microsoft 検索クライアントからこれらのアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

<span data-ttu-id="4b3af-106">この記事は、 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理者、または Salesforce コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="4b3af-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors a Salesforce connector.</span></span> <span data-ttu-id="4b3af-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4b3af-108">現在、Salesforce Graph コネクタは夏の ' 19 以降をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="4b3af-108">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="connection-settings"></a><span data-ttu-id="4b3af-109">接続設定</span><span class="sxs-lookup"><span data-stu-id="4b3af-109">Connection settings</span></span>

<span data-ttu-id="4b3af-110">Salesforce インスタンスに接続するには、Salesforce インスタンスの URL、クライアント ID、および OAuth 認証のクライアントシークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="4b3af-110">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="4b3af-111">次の手順では、ユーザーまたは Salesforce 管理者が Salesforce アカウントからこの情報を取得する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-111">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="4b3af-112">Salesforce インスタンスにログインして、[セットアップ] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-112">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="4b3af-113">[アプリ-> App Manager に移動します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-113">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="4b3af-114">[ **新しい接続済みアプリ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-114">Select **New connected app**.</span></span>

- <span data-ttu-id="4b3af-115">API セクションを次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-115">Complete the API section as follows:</span></span>

    - <span data-ttu-id="4b3af-116">[ **Oauth 設定を有効にする**] のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4b3af-116">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="4b3af-117">コールバック URL を次のように指定します。 [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="4b3af-117">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="4b3af-118">必要な OAuth スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-118">Select these required OAuth scopes.</span></span> 

        - <span data-ttu-id="4b3af-119">データにアクセスして管理する (api)</span><span class="sxs-lookup"><span data-stu-id="4b3af-119">Access and manage your data (api)</span></span> 

        - <span data-ttu-id="4b3af-120">任意のタイミングで (refresh_token、offline_access)、自分の代理で要求を実行する</span><span class="sxs-lookup"><span data-stu-id="4b3af-120">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span> 

    - <span data-ttu-id="4b3af-121">[ **Web サーバーフローにシークレットを必要と** する] のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4b3af-121">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="4b3af-122">アプリを保存します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-122">Save the app.</span></span>
    
      ![管理者が上記のすべての必要な構成を入力した後の、Salesforce インスタンスの API セクション。](media/salesforce-connector/sf1.png)

- <span data-ttu-id="4b3af-124">コンシューマーキーとコンシューマーシークレットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="4b3af-124">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="4b3af-125">これらは、Microsoft 365 管理ポータルで Graph コネクタの接続設定を構成する際に、クライアント ID とクライアントシークレットとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-125">These will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  ![管理者が必要なすべての構成を送信した後に、Salesforce インスタンスの [API] セクションによって返された結果。](media/salesforce-connector/clientsecret.png)
- <span data-ttu-id="4b3af-128">Salesforce インスタンスを閉じる前に、次の手順を実行して、更新トークンの有効期限が切れないようにします。</span><span class="sxs-lookup"><span data-stu-id="4b3af-128">Before closing your Salesforce instance, perform the following steps to ensure that refresh tokens do not expire:</span></span>
    - <span data-ttu-id="4b3af-129">[アプリ-> アプリマネージャー] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-129">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="4b3af-130">作成したばかりのアプリを見つけ、右側のドロップダウンを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-130">Find the app you just created and select the drop down on the right.</span></span> <span data-ttu-id="4b3af-131">[**管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-131">Select **Manage**</span></span>
    - <span data-ttu-id="4b3af-132">[**ポリシーの編集**] を選択する</span><span class="sxs-lookup"><span data-stu-id="4b3af-132">Select **edit policies**</span></span>
    - <span data-ttu-id="4b3af-133">更新トークンポリシーの場合、[**トークンの更新は取り消されるまで有効です**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-133">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  ![[更新トークンは取り消されるまで有効です] という名前の更新トークンポリシーを選択します。](media/salesforce-connector/oauthpolicies.png)

<span data-ttu-id="4b3af-135">[M365 管理センター](https://admin.microsoft.com/)を使用して、Graph connector のセットアッププロセスを完了することができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4b3af-135">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>  

<span data-ttu-id="4b3af-136">Graph connector の接続設定を次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-136">Configure the Connection settings for your Graph connector as follows:</span></span>

- <span data-ttu-id="4b3af-137">インスタンス URL の場合は、https を使用します。ここで、domain は組織の Salesforce ドメインになります。</span><span class="sxs-lookup"><span data-stu-id="4b3af-137">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span> 
- <span data-ttu-id="4b3af-138">Salesforce インスタンスから取得したクライアント ID とクライアントシークレットを入力し、[サインイン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-138">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>
- <span data-ttu-id="4b3af-139">この設定を使用して初めてサインインを試みた場合は、管理者のユーザー名とパスワードを使用して、Salesforce にログインするように求めるポップアップが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-139">If this is the first time you have attempted to Sign in with these settings, you will get a pop up asking you to login to Salesforce with your admin username and password.</span></span> <span data-ttu-id="4b3af-140">次のスクリーンショットは、ポップアップを示しています。</span><span class="sxs-lookup"><span data-stu-id="4b3af-140">The screenshot below shows the popup.</span></span> <span data-ttu-id="4b3af-141">資格情報を入力して、[ログイン] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-141">Enter your credentials and select Log in.</span></span>

  ![ユーザー名とパスワードの入力を求めるログインポップアップ。](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="4b3af-143">ポップアップが表示されない場合は、ブラウザーでブロックされる可能性があるので、ポップアップとリダイレクトを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b3af-143">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

  >[!NOTE]
  ><span data-ttu-id="4b3af-144">組織でシングルサインオン (SSO) を使用している場合は、ログインインターフェイスの右下隅にある [ **カスタムドメインの使用** ] を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-144">If your organization uses single sign-on (SSO), you can select **Use Custom Domain** in the bottom, right-hand corner of the login interface.</span></span> <span data-ttu-id="4b3af-145">ドメインを入力し、[ **続行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-145">Enter the domain and then select **Continue**.</span></span> <span data-ttu-id="4b3af-146">これにより、SSO を使用してログインするオプションを持つ、組織固有のログインページに移動します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-146">It will go to your organization specific login page where you will have an option to login with SSO.</span></span>

- <span data-ttu-id="4b3af-147">次のスクリーンショットに示されているように、「接続が成功しました」という緑色のバナーを検索して、接続が成功したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-147">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  ![成功したログインのスクリーンショット。](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="4b3af-150">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="4b3af-150">Manage search permissions</span></span>
<span data-ttu-id="4b3af-151">このデータソースからの検索結果を表示するユーザーを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b3af-151">You will need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="4b3af-152">特定の Azure Active Directory (Azure AD) または非 Azure AD ユーザーのみが検索結果を表示できるようにする場合は、id をマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4b3af-152">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, you will then need to map the identities.</span></span>

### <a name="select-permissions"></a><span data-ttu-id="4b3af-153">アクセス許可の選択</span><span class="sxs-lookup"><span data-stu-id="4b3af-153">Select Permissions</span></span>
<span data-ttu-id="4b3af-154">アクセス制御リスト (Acl) を Salesforce インスタンスから取り込み、または組織内のすべてのユーザーがこのデータソースからの検索結果を表示できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-154">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or you can allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="4b3af-155">Acl には、Azure Active Directory (AAD) id (Azure AD から Salesforce にフェデレーションされるユーザー)、非 Azure AD id (Azure AD で対応する id を持つネイティブの Salesforce ユーザー)、またはその両方を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-155">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

![管理者によって完了したアクセス許可の選択画面。管理者が [このデータソースへのアクセス権を持つユーザーのみ] オプションを選択し、さらに id タイプのドロップダウンメニューから [AAD] を選択しました。](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a><span data-ttu-id="4b3af-157">AAD 以外の id をマップする</span><span class="sxs-lookup"><span data-stu-id="4b3af-157">Map non-AAD identities</span></span> 
<span data-ttu-id="4b3af-158">Salesforce インスタンスから ACL を取り込み、id の種類として "非 AAD" を選択した場合は、id のマッピングの手順について「 [非 AZURE AD id をマップ](map-non-aad.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b3af-158">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="map-aad-identities"></a><span data-ttu-id="4b3af-159">AAD id をマップする</span><span class="sxs-lookup"><span data-stu-id="4b3af-159">Map AAD identities</span></span>
<span data-ttu-id="4b3af-160">Salesforce インスタンスから ACL を取り込み、id の種類として "AAD" を選択した場合は、id のマッピングの手順について「 [AZURE AD id をマップ](map-aad.md) する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b3af-160">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="4b3af-161">Salesforce の Azure AD SSO をセットアップする方法については、この [チュートリアル](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b3af-161">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="4b3af-162">プロパティのラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="4b3af-162">Assign property labels</span></span> 
<span data-ttu-id="4b3af-163">各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-163">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="4b3af-164">この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="4b3af-164">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span> <span data-ttu-id="4b3af-165">既定では、"Title"、"URL"、"CreatedBy"、"Last" などの一部のラベルには、既に source プロパティが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="4b3af-165">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

![既定のソースプロパティを示すプロパティのラベルの割り当て画面。](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a><span data-ttu-id="4b3af-167">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="4b3af-167">Manage Schema</span></span>
<span data-ttu-id="4b3af-168">インデックスを作成するソースプロパティを選択して、検索結果に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-168">You can select what source properties should be indexed so that they can show up in search results.</span></span> <span data-ttu-id="4b3af-169">接続ウィザードは、既定で、ソースプロパティのセットに基づいて検索スキーマを選択します。</span><span class="sxs-lookup"><span data-stu-id="4b3af-169">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="4b3af-170">[検索スキーマ] ページで各プロパティと属性のチェックボックスをオンにすることによって、これを変更できます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-170">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="4b3af-171">検索スキーマの属性には、検索、クエリ、取得、および絞り込みがあります。</span><span class="sxs-lookup"><span data-stu-id="4b3af-171">Search schema attributes include Search, Query, Retrieve and Refine.</span></span> <span data-ttu-id="4b3af-172">[絞り込み] 検索機能でカスタムの絞り込み条件またはフィルターとして後で使用できるプロパティを定義できます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-172">Refine allows you to define the properties which can be later used as custom refiners or filters in the search experience.</span></span>  

![各ソースプロパティのスキーマを選択します。](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="4b3af-175">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="4b3af-175">Set the refresh schedule</span></span>

<span data-ttu-id="4b3af-176">Salesforce コネクタは、現在、フルクロールの更新スケジュールのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4b3af-176">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4b3af-177">フルクロールでは、削除されたオブジェクトと、以前に Microsoft 検索インデックスに同期されたユーザーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-177">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="4b3af-178">推奨されるスケジュールは、フルクロールで1週間です。</span><span class="sxs-lookup"><span data-stu-id="4b3af-178">The recommended schedule is one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="4b3af-179">制限事項</span><span class="sxs-lookup"><span data-stu-id="4b3af-179">Limitations</span></span>

- <span data-ttu-id="4b3af-180">Graph connector は現在、Salesforce からの個人グループを使用した Apex ベースの領土ベースの共有と共有をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="4b3af-180">The Graph connector does not currently support Apex based , territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="4b3af-181">Salesforce API に既知のバグがあります。グラフコネクタで使用されるのは、潜在顧客に対するプライベートな組織全体の既定値が現在有効になっていない場合です。</span><span class="sxs-lookup"><span data-stu-id="4b3af-181">There is a known bug in the Salesforce API that the Graph connector uses where the private org wide defaults for leads is not honored currently.</span></span>  
- <span data-ttu-id="4b3af-182">フィールドがプロファイルに対してフィールドレベルセキュリティ (FLS) が設定されている場合、Graph connector は、その Salesforce 組織のプロファイルに対してそのフィールドを取り込みません。そのため、ユーザーは、これらのフィールドの値を検索することはできません。結果には表示されません。</span><span class="sxs-lookup"><span data-stu-id="4b3af-182">If a field has field level security (FLS) set for a profile, the Graph connector will not ingest that field for any profiles in that Salesforce org. Users will thus not be able to search on values for those fields, nor will it  show up in the results.</span></span>  
- <span data-ttu-id="4b3af-183">[スキーマの管理] 画面には、これらの共通の標準プロパティの名前が1回表示され、それらをクエリ可能にするために実行した選択内容、検索可能で取得可能です。すべてまたはなしに適用されます。</span><span class="sxs-lookup"><span data-stu-id="4b3af-183">In the Manage Schema screen these common standard property names are listed once and the selection done to make them queryable, searchable and retrievable apply to all or none.</span></span>
    - <span data-ttu-id="4b3af-184">Name</span><span class="sxs-lookup"><span data-stu-id="4b3af-184">Name</span></span>
    - <span data-ttu-id="4b3af-185">Url</span><span class="sxs-lookup"><span data-stu-id="4b3af-185">Url</span></span> 
    - <span data-ttu-id="4b3af-186">Description</span><span class="sxs-lookup"><span data-stu-id="4b3af-186">Description</span></span>
    - <span data-ttu-id="4b3af-187">FAX</span><span class="sxs-lookup"><span data-stu-id="4b3af-187">Fax</span></span>
    - <span data-ttu-id="4b3af-188">Phone</span><span class="sxs-lookup"><span data-stu-id="4b3af-188">Phone</span></span>
    - <span data-ttu-id="4b3af-189">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="4b3af-189">MobilePhone</span></span>
    - <span data-ttu-id="4b3af-190">メール</span><span class="sxs-lookup"><span data-stu-id="4b3af-190">Email</span></span>
    - <span data-ttu-id="4b3af-191">種類</span><span class="sxs-lookup"><span data-stu-id="4b3af-191">Type</span></span>
    - <span data-ttu-id="4b3af-192">タイトル</span><span class="sxs-lookup"><span data-stu-id="4b3af-192">Title</span></span>
    - <span data-ttu-id="4b3af-193">AccountId</span><span class="sxs-lookup"><span data-stu-id="4b3af-193">AccountId</span></span>
    - <span data-ttu-id="4b3af-194">AccountName</span><span class="sxs-lookup"><span data-stu-id="4b3af-194">AccountName</span></span>
    - <span data-ttu-id="4b3af-195">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="4b3af-195">AccountUrl</span></span>
    - <span data-ttu-id="4b3af-196">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="4b3af-196">AccountOwner</span></span>
    - <span data-ttu-id="4b3af-197">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="4b3af-197">AccountOwnerUrl</span></span>
    - <span data-ttu-id="4b3af-198">Owner</span><span class="sxs-lookup"><span data-stu-id="4b3af-198">Owner</span></span>
    - <span data-ttu-id="4b3af-199">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="4b3af-199">OwnerUrl</span></span>
    - <span data-ttu-id="4b3af-200">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="4b3af-200">CreatedBy</span></span> 
    - <span data-ttu-id="4b3af-201">新規の Url</span><span class="sxs-lookup"><span data-stu-id="4b3af-201">CreatedByUrl</span></span> 
    - <span data-ttu-id="4b3af-202">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="4b3af-202">LastModifiedBy</span></span> 
    - <span data-ttu-id="4b3af-203">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="4b3af-203">LastModifiedByUrl</span></span> 
    - <span data-ttu-id="4b3af-204">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="4b3af-204">LastModifiedDate</span></span>
    - <span data-ttu-id="4b3af-205">ObjectName</span><span class="sxs-lookup"><span data-stu-id="4b3af-205">ObjectName</span></span> 
