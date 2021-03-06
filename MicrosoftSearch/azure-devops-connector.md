---
title: Microsoft Search 用 Azure DevOps Graph コネクタ
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
description: Microsoft Search 用の Azure DevOps Graph コネクタをセットアップする
ms.openlocfilehash: 9307aabbf5ea1565e083abfefb90c590d356ae58
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508862"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a><span data-ttu-id="2b7fc-103">Azure DevOps Graph コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="2b7fc-103">Azure DevOps Graph connector (preview)</span></span>

<span data-ttu-id="2b7fc-104">Azure DevOps Graph コネクタを使用すると、組織は Azure DevOps サービスのインスタンス内の作業項目をインデックス化できます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-104">The Azure DevOps Graph connector allows your organization to index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="2b7fc-105">Azure DevOps からコネクタとインデックス コンテンツを構成した後、エンド ユーザーは Microsoft Search でそれらのアイテムを検索できます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="2b7fc-106">Graph コネクタ [**のセットアップの一**](configure-connector.md) 般的な手順については、Graph コネクタのセットアップに関する記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="2b7fc-107">この記事は、Azure DevOps Graph コネクタを構成、実行、監視するユーザー向けです。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-107">This article is for anyone who configures, runs, and monitors an Azure DevOps Graph connector.</span></span> <span data-ttu-id="2b7fc-108">一般的なセットアップ プロセスを補足し、Azure DevOps Graph コネクタにのみ適用される手順を示します。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-108">It supplements the general setup process, and shows instructions that apply only for the Azure DevOps Graph connector.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2b7fc-109">Azure DevOps コネクタは、Azure DevOps クラウド サービスのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-109">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="2b7fc-110">Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015、TFS 2013 は、このコネクタではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-110">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2b7fc-111">手順 1: Microsoft 365 管理センターに Graph コネクタを追加する</span><span class="sxs-lookup"><span data-stu-id="2b7fc-111">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="2b7fc-112">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-112">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="2b7fc-113">手順 2: 接続に名前を付け</span><span class="sxs-lookup"><span data-stu-id="2b7fc-113">Step 2: Name the connection</span></span>

<span data-ttu-id="2b7fc-114">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-114">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="2b7fc-115">手順 3: 接続設定を構成する</span><span class="sxs-lookup"><span data-stu-id="2b7fc-115">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="2b7fc-116">Azure DevOps インスタンスに接続するには、OAuth 認証用の Azure [DevOps](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) 組織名、そのアプリ ID、およびクライアント シークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-116">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="2b7fc-117">アプリを登録します</span><span class="sxs-lookup"><span data-stu-id="2b7fc-117">Register an app</span></span>

<span data-ttu-id="2b7fc-118">Microsoft Search アプリがインスタンスにアクセスできるよう、Azure DevOps にアプリを登録します。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-118">Register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="2b7fc-119">詳細については、アプリの登録方法に関する Azure DevOps [のドキュメントを参照してください](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-119">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true).</span></span>

<span data-ttu-id="2b7fc-120">次の表に、アプリ登録フォームに入力する方法に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-120">The following table provides guidance on how to fill out the app registration form:</span></span>

<span data-ttu-id="2b7fc-121">必須フィールド</span><span class="sxs-lookup"><span data-stu-id="2b7fc-121">Mandatory Fields</span></span> | <span data-ttu-id="2b7fc-122">説明</span><span class="sxs-lookup"><span data-stu-id="2b7fc-122">Description</span></span> | <span data-ttu-id="2b7fc-123">推奨値</span><span class="sxs-lookup"><span data-stu-id="2b7fc-123">Recommended Value</span></span>
--- | --- | ---
| <span data-ttu-id="2b7fc-124">Company Name</span><span class="sxs-lookup"><span data-stu-id="2b7fc-124">Company Name</span></span>         | <span data-ttu-id="2b7fc-125">会社の名前。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-125">The name of your company.</span></span> | <span data-ttu-id="2b7fc-126">適切な値を使用する</span><span class="sxs-lookup"><span data-stu-id="2b7fc-126">Use an appropriate value</span></span>   |
| <span data-ttu-id="2b7fc-127">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="2b7fc-127">Application name</span></span>     | <span data-ttu-id="2b7fc-128">承認するアプリケーションを識別する一意の値。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-128">A unique value that identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="2b7fc-129">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="2b7fc-129">Microsoft Search</span></span>     |
| <span data-ttu-id="2b7fc-130">アプリケーション Web サイト</span><span class="sxs-lookup"><span data-stu-id="2b7fc-130">Application website</span></span>  | <span data-ttu-id="2b7fc-131">コネクタのセットアップ中に Azure DevOps インスタンスへのアクセスを要求するアプリケーションの URL。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-131">The URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span> <span data-ttu-id="2b7fc-132">(必須)。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-132">(Required).</span></span>  | <span data-ttu-id="2b7fc-133"> https://<span>gcs.office.</span>com/</span><span class="sxs-lookup"><span data-stu-id="2b7fc-133">https://<span>gcs.office.</span>com/</span></span>
| <span data-ttu-id="2b7fc-134">承認コールバック URL</span><span class="sxs-lookup"><span data-stu-id="2b7fc-134">Authorization callback URL</span></span>        | <span data-ttu-id="2b7fc-135">承認サーバーがリダイレクトする必要なコールバック URL。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-135">A required callback URL that the authorization server redirects to.</span></span> | <span data-ttu-id="2b7fc-136"> https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span><span class="sxs-lookup"><span data-stu-id="2b7fc-136">https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback</span></span>|
| <span data-ttu-id="2b7fc-137">承認済みスコープ</span><span class="sxs-lookup"><span data-stu-id="2b7fc-137">Authorized scopes</span></span> | <span data-ttu-id="2b7fc-138">アプリケーションのアクセス範囲</span><span class="sxs-lookup"><span data-stu-id="2b7fc-138">The scope of access for the application</span></span> | <span data-ttu-id="2b7fc-139">次のスコープを選択します。ID (読み取り)、作業項目 (読み取り)、変数グループ (読み取り)、Project とチーム (読み取り)、グラフ (読み取り)</span><span class="sxs-lookup"><span data-stu-id="2b7fc-139">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="2b7fc-140">上記の詳細にアプリを登録すると、コネクタの構成に使用されるアプリ **ID** と **クライアント** シークレットが取得されます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-140">On registering the app with the details above, you'll get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="2b7fc-141">Azure DevOps に登録されているアプリへのアクセスを取り消す場合は、Azure DevOps インスタンスの右側にある [ユーザー設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-141">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="2b7fc-142">[プロファイル] を選択し、サイド ウィンドウの [セキュリティ] セクションで [承認] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-142">Select Profile and then select Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="2b7fc-143">承認された OAuth アプリにカーソルを合わせると、アプリの詳細の隅にある [失効] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-143">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="2b7fc-144">接続設定</span><span class="sxs-lookup"><span data-stu-id="2b7fc-144">Connection settings</span></span>

<span data-ttu-id="2b7fc-145">Microsoft Search アプリを Azure DevOps に登録したら、接続設定の手順を完了できます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-145">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="2b7fc-146">組織名、アプリ ID、およびクライアント シークレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-146">Enter your organization name, App ID, and Client secret.</span></span>

![接続アプリケーションの設定](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a><span data-ttu-id="2b7fc-148">データの構成: プロジェクトとフィールドの選択</span><span class="sxs-lookup"><span data-stu-id="2b7fc-148">Configure data: select projects and fields</span></span>

<span data-ttu-id="2b7fc-149">組織全体または特定のプロジェクトのインデックスを作成する接続を選択できます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-149">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="2b7fc-150">組織全体のインデックスを作成する場合、組織内のすべてのプロジェクト内のアイテムにインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-150">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="2b7fc-151">新しいプロジェクトとアイテムは、作成後の次回のクロール中にインデックスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-151">New projects and items will be indexed during the next crawl after they're created.</span></span>

<span data-ttu-id="2b7fc-152">個々のプロジェクトを選択すると、それらのプロジェクトの作業項目だけがインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-152">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![データの構成](media/ADO_Configure_data.png)

<span data-ttu-id="2b7fc-154">次に、接続でこれらのフィールドのデータにインデックスを付け、プレビューするフィールドを選択してから、次に進みます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-154">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![プロパティの選択](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="2b7fc-156">手順 4: 検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="2b7fc-156">Step 4: Manage search permissions</span></span>

<span data-ttu-id="2b7fc-157">Azure DevOps コネクタは、[このデータ ソースにアクセスできるユーザーのみ] または [すべてのユーザー] に表示される検索  **アクセス** 許可を **サポートしています**。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-157">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="2b7fc-158">[このデータソースにアクセスできるユーザーのみ] を選択すると、Azure DevOps の組織、プロジェクト、またはエリア パス レベルのユーザーまたはグループへのアクセス許可に基づいて、アクセス権を持つユーザーの検索結果にインデックス付きデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-158">If you choose **Only people with access to this data source**, indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="2b7fc-159">[すべてのユーザー] **を選択** すると、すべてのユーザーの検索結果にインデックス付きデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-159">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="2b7fc-160">手順 5: プロパティ ラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="2b7fc-160">Step 5: Assign property labels</span></span>

<span data-ttu-id="2b7fc-161">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-161">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="2b7fc-162">手順 6: スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="2b7fc-162">Step 6: Manage schema</span></span>

<span data-ttu-id="2b7fc-163">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-163">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="2b7fc-164">手順 7: 更新設定を選択する</span><span class="sxs-lookup"><span data-stu-id="2b7fc-164">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="2b7fc-165">Azure DevOps コネクタは、フル クロールと増分クロールの両方の更新スケジュールをサポートします。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-165">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span>
<span data-ttu-id="2b7fc-166">推奨されるスケジュールは、増分クロールの場合は 1 時間、フル クロールの場合は 1 日です。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-166">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="2b7fc-167">手順 8: 接続の確認</span><span class="sxs-lookup"><span data-stu-id="2b7fc-167">Step 8: Review connection</span></span>

<span data-ttu-id="2b7fc-168">一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。</span><span class="sxs-lookup"><span data-stu-id="2b7fc-168">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
