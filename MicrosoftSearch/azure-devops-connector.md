---
title: Azure DevOps Graphのコネクタ
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
description: Microsoft Search のAzure DevOps Graphコネクタをセットアップする
ms.openlocfilehash: bfe04a022360a968424b673ad03ba05f27c8c333
ms.sourcegitcommit: 1b154441f3a3abba0f2719e66a767432bc9506ca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2021
ms.locfileid: "52720954"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="d6e54-103">Azure DevOps Graph コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="d6e54-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="d6e54-104">このAzure DevOps Graphコネクタを使用すると、組織は、そのサービスのインスタンス内の作業項目Azure DevOpsできます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="d6e54-105">コネクタとインデックス コンテンツを構成した後、Azure DevOpsユーザーは Microsoft Search でそれらのアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="d6e54-106">一般的な [**コネクタのセットアップGraph**](configure-connector.md) Graphについては、「Graphコネクタのセットアップ」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6e54-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="d6e54-107">この記事は、コネクタの構成、実行、および監視を行うAzure DevOps Graphです。</span><span class="sxs-lookup"><span data-stu-id="d6e54-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="d6e54-108">これは、一般的なセットアップ プロセスを補足し、コネクタに対してのみ適用される手順Azure DevOps Graphします。</span><span class="sxs-lookup"><span data-stu-id="d6e54-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d6e54-109">このAzure DevOpsは、クラウド サービスAzure DevOpsサポートします。</span><span class="sxs-lookup"><span data-stu-id="d6e54-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="d6e54-110">Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015、および TFS 2013 は、このコネクタではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d6e54-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d6e54-111">手順 1: 管理センター GraphコネクタをMicrosoft 365する</span><span class="sxs-lookup"><span data-stu-id="d6e54-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="d6e54-112">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="d6e54-112">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="d6e54-113">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="d6e54-113">Step 2: Name the connection</span></span>

<span data-ttu-id="d6e54-114">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="d6e54-114">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="d6e54-115">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d6e54-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="d6e54-116">クライアント インスタンスにAzure DevOpsするには、OAuth 認証Azure DevOps組織名、その[](/azure/devops/organizations/accounts/create-organization)アプリ ID、およびクライアント シークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="d6e54-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="d6e54-117">アプリを登録します</span><span class="sxs-lookup"><span data-stu-id="d6e54-117">Register an app</span></span>

<span data-ttu-id="d6e54-118">Microsoft Search アプリがインスタンスAzure DevOpsアクセスできるよう、アプリをアプリに登録します。</span><span class="sxs-lookup"><span data-stu-id="d6e54-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="d6e54-119">詳細については、「アプリの登録Azure DevOpsドキュメント」[を参照してください](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)。</span><span class="sxs-lookup"><span data-stu-id="d6e54-119">To learn more, see Azure DevOps documentation on how to [register an app](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="d6e54-120">次の表に、アプリ登録フォームに入力する方法に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="d6e54-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="d6e54-121">必須フィールド</span><span class="sxs-lookup"><span data-stu-id="d6e54-121">Mandatory Fields</span></span> | <span data-ttu-id="d6e54-122">説明</span><span class="sxs-lookup"><span data-stu-id="d6e54-122">Description</span></span> | <span data-ttu-id="d6e54-123">推奨値</span><span class="sxs-lookup"><span data-stu-id="d6e54-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="d6e54-124">Company Name</span><span class="sxs-lookup"><span data-stu-id="d6e54-124">Company Name</span></span>         | <span data-ttu-id="d6e54-125">会社の名前。</span><span class="sxs-lookup"><span data-stu-id="d6e54-125">The name of your company.</span></span> | <span data-ttu-id="d6e54-126">適切な値を使用する</span><span class="sxs-lookup"><span data-stu-id="d6e54-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="d6e54-127">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="d6e54-127">Application name</span></span>     | <span data-ttu-id="d6e54-128">承認するアプリケーションを識別する一意の値。</span><span class="sxs-lookup"><span data-stu-id="d6e54-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="d6e54-129">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="d6e54-129">Microsoft Search</span></span>     |
| <span data-ttu-id="d6e54-130">アプリケーション Web サイト</span><span class="sxs-lookup"><span data-stu-id="d6e54-130">Application website</span></span>  | <span data-ttu-id="d6e54-131">コネクタのセットアップ中にアプリケーション インスタンスへのアクセスを要求Azure DevOpsの URL。</span><span class="sxs-lookup"><span data-stu-id="d6e54-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="d6e54-132">(必須)。</span><span class="sxs-lookup"><span data-stu-id="d6e54-132">(Required).</span></span>  | <span data-ttu-id="d6e54-133"> https://<span>gcs.office.</span>com/</span><span class="sxs-lookup"><span data-stu-id="d6e54-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="d6e54-134">承認コールバック URL</span><span class="sxs-lookup"><span data-stu-id="d6e54-134">Authorization callback URL</span></span>        | <span data-ttu-id="d6e54-135">承認サーバーがリダイレクトする必要なコールバック URL。</span><span class="sxs-lookup"><span data-stu-id="d6e54-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="d6e54-136"> https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="d6e54-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="d6e54-137">承認済みスコープ</span><span class="sxs-lookup"><span data-stu-id="d6e54-137">Authorized scopes</span></span> | <span data-ttu-id="d6e54-138">アプリケーションのアクセス範囲</span><span class="sxs-lookup"><span data-stu-id="d6e54-138">The scope of access for the application</span></span> | <span data-ttu-id="d6e54-139">ID (読み取り)、ワーク アイテム (読み取り)、変数グループ (読み取り)、Projectチーム (読み取り)、Graph (読み取り) の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6e54-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

>[!IMPORTANT]
><span data-ttu-id="d6e54-140">アプリに対して選択する承認済みスコープは、上記の範囲と完全に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6e54-140">The authorized scopes that you select for the app should match the scopes exactly as listed above.</span></span> <span data-ttu-id="d6e54-141">リスト内のいずれかの承認済みスコープを省略するか、別のスコープを追加すると、承認は失敗します。</span><span class="sxs-lookup"><span data-stu-id="d6e54-141">If you omit one of the authorized scopes in the list, or add another scope, the authorization will fail.</span></span>

<span data-ttu-id="d6e54-142">上記の詳細にアプリを登録すると、コネクタの構成に使用されるアプリ **ID** と **クライアント** シークレットが取得されます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-142">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="d6e54-143">アプリに登録されているアプリへのアクセスを取り消Azure DevOps、ユーザー インスタンスの右側にある [ユーザー設定] にAzure DevOpsします。</span><span class="sxs-lookup"><span data-stu-id="d6e54-143">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="d6e54-144">[プロファイル] を選択し、サイド ウィンドウの [セキュリティ] セクションで [承認] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d6e54-144">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="d6e54-145">承認された OAuth アプリにカーソルを合わせると、アプリの詳細の隅にある [失効] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-145">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="d6e54-146">接続設定</span><span class="sxs-lookup"><span data-stu-id="d6e54-146">Connection settings</span></span>

<span data-ttu-id="d6e54-147">Microsoft Search アプリをアプリに登録Azure DevOps、接続設定の手順を完了できます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-147">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="d6e54-148">組織名、アプリ ID、およびクライアント シークレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="d6e54-148">Enter your organization name, App ID, and Client secret.</span></span>

![接続アプリケーション 設定](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="d6e54-150">データの構成: プロジェクトとフィールドの選択</span><span class="sxs-lookup"><span data-stu-id="d6e54-150">Configure data: select projects and fields</span></span>

<span data-ttu-id="d6e54-151">組織全体または特定のプロジェクトのインデックスを作成する接続を選択できます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-151">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="d6e54-152">組織全体のインデックスを作成する場合、組織内のすべてのプロジェクト内のアイテムにインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-152">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="d6e54-153">新しいプロジェクトとアイテムは、作成後の次回のクロール中にインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-153">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="d6e54-154">個々のプロジェクトを選択すると、それらのプロジェクトの作業項目だけがインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-154">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![データの構成](media/ADO_Configure_data.png)

<span data-ttu-id="d6e54-156">次に、接続でこれらのフィールドのデータにインデックスを付け、プレビューするフィールドを選択してから、次に進みます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-156">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![プロパティの選択](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="d6e54-158">手順 4: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="d6e54-158">Step 4: Manage search permissions</span></span>

<span data-ttu-id="d6e54-159">[Azure DevOps コネクタは、[このデータ ソースにアクセスできるユーザーのみ] または [すべてのユーザー] に表示される検索アクセス  **許可を\*\*\*\*サポートします**。</span><span class="sxs-lookup"><span data-stu-id="d6e54-159">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="d6e54-160">[このデータソースにアクセスできるユーザーのみ] を選択すると、Azure DevOps の [組織]、Project、またはエリア パス レベルのユーザーまたはグループへのアクセス許可に基づいてアクセス権を持つユーザーの検索結果にインデックス付きデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-160">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="d6e54-161">[すべてのユーザー] **を選択** すると、すべてのユーザーの検索結果にインデックス付きデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-161">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="d6e54-162">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="d6e54-162">Step 5: Assign property labels</span></span>

<span data-ttu-id="d6e54-163">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="d6e54-163">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="d6e54-164">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="d6e54-164">Step 6: Manage schema</span></span>

<span data-ttu-id="d6e54-165">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="d6e54-165">Follow the general [setup instructions](./configure-connector.md).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="d6e54-166">手順 7: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="d6e54-166">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="d6e54-167">このAzure DevOpsは、フル クロールと増分クロールの両方の更新スケジュールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d6e54-167">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="d6e54-168">推奨されるスケジュールは、増分クロールの場合は 1 時間、フル クロールの場合は 1 日です。</span><span class="sxs-lookup"><span data-stu-id="d6e54-168">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="d6e54-169">手順 8: 接続の確認</span><span class="sxs-lookup"><span data-stu-id="d6e54-169">Step 8: Review connection</span></span>

<span data-ttu-id="d6e54-170">一般的なセットアップ [手順に従います](./configure-connector.md)。</span><span class="sxs-lookup"><span data-stu-id="d6e54-170">Follow the general [setup instructions](./configure-connector.md).</span></span>

>[!TIP]
><span data-ttu-id="d6e54-171">**既定の結果の種類**</span><span class="sxs-lookup"><span data-stu-id="d6e54-171">**Default Result type**</span></span>
>* <span data-ttu-id="d6e54-172">コネクタAzure DevOps発行すると、[結果の種類](./customize-search-page.md#step-2-create-the-result-types)が自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-172">The Azure DevOps connector automatically registers a [result type](./customize-search-page.md#step-2-create-the-result-types) once the connector is published.</span></span> <span data-ttu-id="d6e54-173">結果の種類は、手順 3 で選択したフィールドに基づいて動的に生成された結果レイアウトを使用します。 [](./customize-results-layout.md)</span><span class="sxs-lookup"><span data-stu-id="d6e54-173">The result type uses a dynamically generated [result layout](./customize-results-layout.md) based on the fields selected in step 3.</span></span> 
>* <span data-ttu-id="d6e54-174">結果の種類は、管理センターの [**[**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)結果の種類] に移動Microsoft 365 [管理できます](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="d6e54-174">You can manage the result type by navigating to [**Result types**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="d6e54-175">既定の結果の種類には"Default" という名前が `ConnectionId` 付けられます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-175">The default result type will be named as "`ConnectionId`Default".</span></span> <span data-ttu-id="d6e54-176">たとえば、接続 ID がである場合、結果レイアウトの名前は `AzureDevOps` "AzureDevOpsDefault" になります。</span><span class="sxs-lookup"><span data-stu-id="d6e54-176">For example, if your connection id is `AzureDevOps`, your result layout will be named: "AzureDevOpsDefault"</span></span>
>* <span data-ttu-id="d6e54-177">また、必要に応じて、独自の結果の種類を作成できます。</span><span class="sxs-lookup"><span data-stu-id="d6e54-177">Also, you can choose to create your own result type if needed.</span></span>

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->