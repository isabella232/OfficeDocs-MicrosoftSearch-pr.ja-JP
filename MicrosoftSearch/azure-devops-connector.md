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
ms.openlocfilehash: b9c566e3e07bfca6d4d25b14915f0160f3928b15
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367552"
---
# <a name="azure-devops-connector-preview"></a><span data-ttu-id="5d323-103">Azure DevOps コネクタ (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="5d323-103">Azure DevOps connector (preview)</span></span>

<span data-ttu-id="5d323-104">Azure DevOps コネクタを使用すると、組織は Azure DevOps service のインスタンスで作業項目のインデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5d323-104">With the Azure DevOps connector, your organization can index work items in its instance of the Azure DevOps service.</span></span> <span data-ttu-id="5d323-105">Azure DevOps からコネクタとインデックスコンテンツを構成すると、エンドユーザーは Microsoft Search でそれらのアイテムを検索できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5d323-105">After you configure the connector and index content from Azure DevOps, end users can search for those items in Microsoft Search.</span></span>

<span data-ttu-id="5d323-106">この記事は、Microsoft 365 管理者または Azure DevOps コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="5d323-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors an Azure DevOps connector.</span></span> <span data-ttu-id="5d323-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5d323-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="5d323-108">Azure DevOps connector では、Azure DevOps cloud service のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d323-108">The Azure DevOps connector supports only the Azure DevOps cloud service.</span></span> <span data-ttu-id="5d323-109">Azure DevOps Server 2019、TFS 2018、tfs 2017、tfs 2015、tfs 2013 は、このコネクタではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5d323-109">Azure DevOps Server 2019, TFS 2018, TFS 2017, TFS 2015, and TFS 2013 are not supported by this connector.</span></span> 

## <a name="connect-to-a-data-source"></a><span data-ttu-id="5d323-110">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="5d323-110">Connect to a data source</span></span>

<span data-ttu-id="5d323-111">Azure DevOps インスタンスに接続するには、Azure DevOps [組織](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) 名、そのアプリ ID、および OAuth 認証のクライアントシークレットが必要です。</span><span class="sxs-lookup"><span data-stu-id="5d323-111">To connect to your Azure DevOps instance, you need your Azure DevOps [organization](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) name, its App ID, and client secret for OAuth authentication.</span></span>

### <a name="register-an-app"></a><span data-ttu-id="5d323-112">アプリを登録します</span><span class="sxs-lookup"><span data-stu-id="5d323-112">Register an app</span></span>

<span data-ttu-id="5d323-113">Microsoft Search アプリがインスタンスにアクセスできるようにするには、Azure DevOps でアプリを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d323-113">You must register an app in Azure DevOps so that the Microsoft Search app can access the instance.</span></span> <span data-ttu-id="5d323-114">詳細については、「Azure DevOps のドキュメント」の「 [アプリを登録](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app)する方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5d323-114">To learn more, see Azure DevOps documentation on how to [register an app](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app).</span></span> 

<span data-ttu-id="5d323-115">次の表に、アプリ登録フォームに記入する方法についてのガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="5d323-115">The following table provides guidance on how to fill out the app registration form:</span></span>

 <span data-ttu-id="5d323-116">**必須フィールド**</span><span class="sxs-lookup"><span data-stu-id="5d323-116">**Mandatory Fields**</span></span> | <span data-ttu-id="5d323-117">**説明**</span><span class="sxs-lookup"><span data-stu-id="5d323-117">**Description**</span></span>      | <span data-ttu-id="5d323-118">**推奨値**</span><span class="sxs-lookup"><span data-stu-id="5d323-118">**Recommended Value**</span></span> 
--- | --- | --- 
| <span data-ttu-id="5d323-119">Company Name</span><span class="sxs-lookup"><span data-stu-id="5d323-119">Company Name</span></span>         | <span data-ttu-id="5d323-120">これは会社の名前です。</span><span class="sxs-lookup"><span data-stu-id="5d323-120">This is the name of your company.</span></span> | <span data-ttu-id="5d323-121">適切な値を使用する</span><span class="sxs-lookup"><span data-stu-id="5d323-121">Use an appropriate value</span></span>   | 
| <span data-ttu-id="5d323-122">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="5d323-122">Application name</span></span>     | <span data-ttu-id="5d323-123">この一意の値は、承認しているアプリケーションを識別します。</span><span class="sxs-lookup"><span data-stu-id="5d323-123">This unique value identifies the application that you're authorizing.</span></span>    | <span data-ttu-id="5d323-124">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="5d323-124">Microsoft Search</span></span>     | 
| <span data-ttu-id="5d323-125">アプリケーション web サイト</span><span class="sxs-lookup"><span data-stu-id="5d323-125">Application website</span></span>  | <span data-ttu-id="5d323-126">この必須フィールドは、コネクタのセットアップ時に Azure DevOps インスタンスへのアクセスを要求するアプリケーションの URL です。</span><span class="sxs-lookup"><span data-stu-id="5d323-126">This required field is the URL of the application that will request access to your Azure DevOps instance during connector setup.</span></span>  | <https://gcs.office.com/>                | 
| <span data-ttu-id="5d323-127">認証コールバック URL</span><span class="sxs-lookup"><span data-stu-id="5d323-127">Authorization callback URL</span></span>        | <span data-ttu-id="5d323-128">承認サーバーのリダイレクト先となる必要なコールバック URL。</span><span class="sxs-lookup"><span data-stu-id="5d323-128">A required callback URL that the authorization server redirects to.</span></span> | <https://gcs.office.com/v1.0/admin/oauth/callback>| 
| <span data-ttu-id="5d323-129">承認されたスコープ</span><span class="sxs-lookup"><span data-stu-id="5d323-129">Authorized scopes</span></span> | <span data-ttu-id="5d323-130">これは、アプリケーションへのアクセスの範囲です。</span><span class="sxs-lookup"><span data-stu-id="5d323-130">This is the scope of access for the application</span></span> | <span data-ttu-id="5d323-131">Id (読み取り)、作業項目 (読み取り)、変数グループ (読み取り)、プロジェクトとチーム (読み取り)、グラフ (読み取り) の各スコープを選択します。</span><span class="sxs-lookup"><span data-stu-id="5d323-131">Select the following scopes: Identity (read), Work Items (read), Variable Groups (read), Project and team (read), Graph (read)</span></span>| 

<span data-ttu-id="5d323-132">上記の詳細を使用してアプリを登録する場合は、コネクタの構成に使用する **アプリ ID** と **クライアントシークレット** を取得します。</span><span class="sxs-lookup"><span data-stu-id="5d323-132">On registering the app with the details above, you will get the **App ID** and **Client Secret** that will be used to configure the connector.</span></span>

>[!NOTE]
><span data-ttu-id="5d323-133">Azure DevOps に登録されているすべてのアプリへのアクセスを取り消すには、Azure DevOps インスタンスの右上にある [ユーザーの設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="5d323-133">To revoke access to any app registered in Azure DevOps, go to User settings at the right top of your Azure DevOps instance.</span></span> <span data-ttu-id="5d323-134">[プロファイル] をクリックし、作業ウィンドウの [セキュリティ] セクションで [承認] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5d323-134">Click on Profile and then click on Authorizations in the Security section of the side pane.</span></span> <span data-ttu-id="5d323-135">承認済み OAuth アプリの上にカーソルを移動すると、アプリの詳細の隅にある [取り消し] ボタンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d323-135">Hover over an authorized OAuth app to see the Revoke button at the corner of the app details.</span></span>

### <a name="connection-settings"></a><span data-ttu-id="5d323-136">接続設定</span><span class="sxs-lookup"><span data-stu-id="5d323-136">Connection settings</span></span>

<span data-ttu-id="5d323-137">Microsoft Search アプリを Azure DevOps に登録した後、接続設定の手順を完了できます。</span><span class="sxs-lookup"><span data-stu-id="5d323-137">After registering the Microsoft Search app with Azure DevOps, you can complete the connection settings step.</span></span> <span data-ttu-id="5d323-138">組織名、アプリ ID、およびクライアントシークレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="5d323-138">Enter your organization name, App ID, and Client secret.</span></span>

![接続アプリケーションの設定](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a><span data-ttu-id="5d323-140">プロジェクトとフィールドの選択</span><span class="sxs-lookup"><span data-stu-id="5d323-140">Select projects and fields</span></span>

<span data-ttu-id="5d323-141">接続には、組織全体または特定のプロジェクトのいずれかにインデックスを作成するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="5d323-141">You can choose for the connection to index either the entire organization or specific projects.</span></span>

<span data-ttu-id="5d323-142">組織全体のインデックスを作成することを選択すると、組織内のすべてのプロジェクトの項目にインデックスが付けられます。</span><span class="sxs-lookup"><span data-stu-id="5d323-142">If you choose to index the entire organization, items in all projects in the organization will get indexed.</span></span> <span data-ttu-id="5d323-143">新しいプロジェクトとアイテムは、作成後に次のクロール中にインデックス処理されます。</span><span class="sxs-lookup"><span data-stu-id="5d323-143">New projects and items will be indexed during the next crawl after they are created.</span></span> <span data-ttu-id="5d323-144">個別のプロジェクトを選択した場合は、それらのプロジェクトの作業項目のみがインデックス作成されます。</span><span class="sxs-lookup"><span data-stu-id="5d323-144">If you choose individual projects, only work items in those projects will be indexed.</span></span>

![データを構成する](media/ADO_Configure_data.png)

<span data-ttu-id="5d323-146">次に、接続するフィールドを選択して、次に進む前にこれらのフィールドにデータをプレビューします。</span><span class="sxs-lookup"><span data-stu-id="5d323-146">Next, select which fields you want the connection to index and preview data in these fields before proceeding.</span></span>

![プロパティの選択](media/ADO_choose_properties.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="5d323-148">検索アクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="5d323-148">Manage search permissions</span></span>

<span data-ttu-id="5d323-149">Azure DevOps コネクタは、このデータソースまたは **すべて** のユーザーにアクセス権を  **持つユーザーのみ** に表示される検索アクセス許可をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5d323-149">The Azure DevOps connector supports search permissions visible to  **Only people with access to this data source** or **Everyone**.</span></span> <span data-ttu-id="5d323-150">**このデータソースへのアクセス** 権を持つユーザーのみを選択した場合は、Azure DevOps の組織、プロジェクト、またはエリアのパスレベルで、ユーザーまたはグループに対するアクセス許可に基づいて、インデックス付きのデータが検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d323-150">If you choose **Only people with access to this data source**,indexed data will appear in the search results for users who have access to them based on permissions to users or groups at the Organization, Project or Area path level in Azure DevOps.</span></span> <span data-ttu-id="5d323-151">[すべてのユーザー] を選択すると、すべてのユーザーの検索結果にインデックス **付きのデータ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5d323-151">If you choose **Everyone**, indexed data will appear in the search results for all users.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="5d323-152">プロパティのラベルを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5d323-152">Assign property labels</span></span>

<span data-ttu-id="5d323-153">各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。</span><span class="sxs-lookup"><span data-stu-id="5d323-153">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="5d323-154">この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="5d323-154">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="5d323-155">スキーマを管理する</span><span class="sxs-lookup"><span data-stu-id="5d323-155">Manage schema</span></span>

<span data-ttu-id="5d323-156">[**スキーマの管理**] 画面で、プロパティに関連付けられているスキーマの属性 (**クエリ** 可能、**検索\*\*\*\*可能、取得可能、および\*\*\*\*絞り込み可能な**) を変更し、オプションのエイリアスを追加して、 **Content** プロパティを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="5d323-156">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="5d323-157">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="5d323-157">Set the refresh schedule</span></span>

<span data-ttu-id="5d323-158">Azure DevOps コネクタは、フルクロールと増分クロールの両方の更新スケジュールをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5d323-158">The Azure DevOps connector supports refresh schedules for both full and incremental crawls.</span></span> <span data-ttu-id="5d323-159">フルクロールで、以前に Microsoft 検索インデックスと同期された削除済みの作業項目が検索されます。</span><span class="sxs-lookup"><span data-stu-id="5d323-159">A full crawl finds deleted work items that were previously synced to the Microsoft Search index.</span></span> <span data-ttu-id="5d323-160">フルクロールを実行して、すべての作業項目を同期します。</span><span class="sxs-lookup"><span data-stu-id="5d323-160">A full crawl runs to sync all the work items.</span></span> <span data-ttu-id="5d323-161">新しい作業項目と更新を既存の作業項目に同期するには、増分クロールをスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d323-161">To sync new work items and updates to existing work items, you need to schedule incremental crawls.</span></span>

<span data-ttu-id="5d323-162">推奨されるスケジュールは、増分クロールの場合は1時間、フルクロールの場合は1日です。</span><span class="sxs-lookup"><span data-stu-id="5d323-162">The recommended schedule is one hour for an incremental crawl and one day for a full crawl.</span></span> 