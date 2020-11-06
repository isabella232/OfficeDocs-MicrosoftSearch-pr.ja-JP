---
title: Microsoft Search 用 Azure DevOps connector
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の Azure DevOps connector をセットアップする
ms.openlocfilehash: a0028c3b336c2b5e3d01bb14006ee0debb4524f2
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927191"
---
# <a name="azure-devops-connector"></a><span data-ttu-id="02e43-103">Azure DevOps コネクタ</span><span class="sxs-lookup"><span data-stu-id="02e43-103">Azure DevOps connector</span></span>

<span data-ttu-id="02e43-104">Azure DevOps コネクタを使用すると、組織は Azure DevOps service のインスタンスで作業項目のインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="02e43-104">With the Azure DevOps connector, your organization can index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="02e43-105">Azure DevOps からコネクタとインデックスコンテンツを構成すると、エンドユーザーは Microsoft Search でそれらのアイテムを検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="02e43-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

<span data-ttu-id="02e43-106">この記事は、Microsoft 365 管理者または Azure DevOps コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="02e43-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure DevOps connector.</span></span> <span data-ttu-id="02e43-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="02e43-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="02e43-108">Azure DevOps connector では、Azure DevOps cloud service のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="02e43-108">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="02e43-109">Azure DevOps Server 2019、TFS 2018、tfs 2017、tfs 2015、tfs 2013 は、このコネクタではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="02e43-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="02e43-110">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="02e43-110">Connect to a data source</span></span>

<span data-ttu-id="02e43-111">Azure DevOps インスタンスに接続するには、Azure DevOps [組織](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) 名、そのアプリ ID、および OAuth 認証のクライアントシークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="02e43-111">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="02e43-112">アプリを登録します</span><span class="sxs-lookup"><span data-stu-id="02e43-112">Register an app</span></span>

<span data-ttu-id="02e43-113">Microsoft Search アプリがインスタンスにアクセスできるようにするには、Azure DevOps でアプリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e43-113">You must register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="02e43-114">詳細については、「Azure DevOps のドキュメント」の「 [アプリを登録](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e43-114">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span></span>

<span data-ttu-id="02e43-115">次の表に、アプリ登録フォームに記入する方法についてのガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="02e43-115">The following table provides guidance on how to fill out the app registration form:</span></span>

 <span data-ttu-id="02e43-116">**必須フィールド**</span><span class="sxs-lookup"><span data-stu-id="02e43-116">**Mandatory Fields**</span></span> | <span data-ttu-id="02e43-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="02e43-117">**Description**</span></span>      | <span data-ttu-id="02e43-118">**推奨値**</span><span class="sxs-lookup"><span data-stu-id="02e43-118">**Recommended Value**</span></span>
--- | --- | ---
| <span data-ttu-id="02e43-119">Company Name</span><span class="sxs-lookup"><span data-stu-id="02e43-119">Company Name</span></span>         | <span data-ttu-id="02e43-120">これは会社の名前です。</span><span class="sxs-lookup"><span data-stu-id="02e43-120">This is the name of your company.</span></span> | <span data-ttu-id="02e43-121">適切な値を使用する</span><span class="sxs-lookup"><span data-stu-id="02e43-121">Use an appropriate value</span></span>   |
| <span data-ttu-id="02e43-122">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="02e43-122">Application name</span></span>     | <span data-ttu-id="02e43-123">この一意の値は、承認しているアプリケーションを識別します。</span><span class="sxs-lookup"><span data-stu-id="02e43-123">This unique value identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="02e43-124">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="02e43-124">Microsoft Search</span></span>     |
| <span data-ttu-id="02e43-125">アプリケーション web サイト</span><span class="sxs-lookup"><span data-stu-id="02e43-125">Application website</span></span>  | <span data-ttu-id="02e43-126">この必須フィールドは、コネクタのセットアップ時に Azure DevOps インスタンスへのアクセスを要求するアプリケーションの URL です。</span><span class="sxs-lookup"><span data-stu-id="02e43-126">This required field is the URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span>  | <https://gcs.office.com/>                |
| <span data-ttu-id="02e43-127">認証コールバック URL</span><span class="sxs-lookup"><span data-stu-id="02e43-127">Authorization callback URL</span></span>        | <span data-ttu-id="02e43-128">承認サーバーのリダイレクト先となる必要なコールバック URL。</span><span class="sxs-lookup"><span data-stu-id="02e43-128">A required callback URL that the authorization server redirects to.</span></span> | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| <span data-ttu-id="02e43-129">承認されたスコープ</span><span class="sxs-lookup"><span data-stu-id="02e43-129">Authorized scopes</span></span> | <span data-ttu-id="02e43-130">これは、アプリケーションへのアクセスの範囲です。</span><span class="sxs-lookup"><span data-stu-id="02e43-130">This is the scope of access for the application</span></span> | <span data-ttu-id="02e43-131">Id (読み取り)、作業項目 (読み取り)、変数グループ (読み取り)、プロジェクトとチーム (読み取り)、グラフ (読み取り) の各スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="02e43-131">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>|

<span data-ttu-id="02e43-132">上記の詳細を使用してアプリを登録する場合は、コネクタの構成に使用する **アプリ ID** と **クライアントシークレット** を取得します。</span><span class="sxs-lookup"><span data-stu-id="02e43-132">On registering the app with the details above, you will get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="02e43-133">Azure DevOps に登録されているすべてのアプリへのアクセスを取り消すには、Azure DevOps インスタンスの右上にある [ユーザーの設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="02e43-133">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="02e43-134">[プロファイル] をクリックし、作業ウィンドウの [セキュリティ] セクションで [承認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02e43-134">Click on Profile and then click on Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="02e43-135">承認済み OAuth アプリの上にカーソルを移動すると、アプリの詳細の隅にある [取り消し] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="02e43-135">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="02e43-136">接続設定</span><span class="sxs-lookup"><span data-stu-id="02e43-136">Connection settings</span></span>

<span data-ttu-id="02e43-137">Microsoft Search アプリを Azure DevOps に登録した後、接続設定の手順を完了できます。</span><span class="sxs-lookup"><span data-stu-id="02e43-137">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="02e43-138">組織名、アプリ ID、およびクライアントシークレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="02e43-138">Enter your organization name, App ID, and Client secret.</span></span>

![接続アプリケーションの設定](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a><span data-ttu-id="02e43-140">プロジェクトとフィールドの選択</span><span class="sxs-lookup"><span data-stu-id="02e43-140">Select projects and fields</span></span>

<span data-ttu-id="02e43-141">接続には、組織全体または特定のプロジェクトのいずれかにインデックスを作成するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="02e43-141">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="02e43-142">組織全体のインデックスを作成することを選択すると、組織内のすべてのプロジェクトの項目にインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="02e43-142">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="02e43-143">新しいプロジェクトとアイテムは、作成後に次のクロール中にインデックス処理されます。</span><span class="sxs-lookup"><span data-stu-id="02e43-143">New projects and items will be indexed during the next crawl after they are created.</span></span> <span data-ttu-id="02e43-144">個別のプロジェクトを選択した場合は、それらのプロジェクトの作業項目のみがインデックス作成されます。</span><span class="sxs-lookup"><span data-stu-id="02e43-144">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![データを構成する](media/ADO_Configure_data.png)

<span data-ttu-id="02e43-146">次に、接続するフィールドを選択して、次に進む前にこれらのフィールドにデータをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="02e43-146">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![プロパティの選択](media/ADO_choose_properties.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="02e43-148">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="02e43-148">Manage search permissions</span></span>

<span data-ttu-id="02e43-149">現時点では、Azure DevOps コネクタは、 **すべてのユーザーに表示される** 検索アクセス許可のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="02e43-149">The Azure DevOps connector currently only supports search permissions **Visible to Everyone**.</span></span> <span data-ttu-id="02e43-150">インデックスが作成されたデータは、すべてのユーザーの検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="02e43-150">Indexed data will appear in the search results for all users.</span></span>

## <a name="manage-search-schema"></a><span data-ttu-id="02e43-151">検索スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="02e43-151">Manage search schema</span></span>

<span data-ttu-id="02e43-152">検索スキーママッピングを構成します。</span><span class="sxs-lookup"><span data-stu-id="02e43-152">Configure the search schema mapping.</span></span> <span data-ttu-id="02e43-153">**クエリ** 可能にするかどうかを **選択し、** 検索可能で **検索** 可能なプロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="02e43-153">You can choose which properties to make **queryable** , **searchable** and **retrievable**.</span></span>


## <a name="set-refresh-schedule"></a><span data-ttu-id="02e43-154">更新スケジュールの設定</span><span class="sxs-lookup"><span data-stu-id="02e43-154">Set refresh schedule</span></span>

<span data-ttu-id="02e43-155">Azure DevOps コネクタは、フルクロールと増分クロールの両方の更新スケジュールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="02e43-155">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="02e43-156">フルクロールで、以前に Microsoft 検索インデックスと同期された削除済みの作業項目が検索されます。</span><span class="sxs-lookup"><span data-stu-id="02e43-156">A full crawl finds deleted work items that were previously synced to the Microsoft Search index.</span></span> <span data-ttu-id="02e43-157">フルクロールを実行して、すべての作業項目を同期します。</span><span class="sxs-lookup"><span data-stu-id="02e43-157">A full crawl runs to sync all the work items.</span></span> <span data-ttu-id="02e43-158">新しい作業項目と更新を既存の作業項目に同期するには、増分クロールをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02e43-158">To sync new work items and updates to existing work items, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="02e43-159">推奨されるスケジュールは、増分クロールの場合は1時間、フルクロールの場合は1日です。</span><span class="sxs-lookup"><span data-stu-id="02e43-159">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span>
