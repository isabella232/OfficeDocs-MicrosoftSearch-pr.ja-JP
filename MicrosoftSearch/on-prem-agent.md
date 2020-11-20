---
title: オンプレミスエージェント
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
description: オンプレミスエージェント
ms.openlocfilehash: 30ddf0ac8c6df76d1c598606754066b3d2e93615
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367755"
---
# <a name="on-prem-agent"></a><span data-ttu-id="4bace-103">オンプレミスエージェント</span><span class="sxs-lookup"><span data-stu-id="4bace-103">On-Prem Agent</span></span>

## <a name="graph-connector-agent"></a><span data-ttu-id="4bace-104">グラフコネクタエージェント</span><span class="sxs-lookup"><span data-stu-id="4bace-104">Graph connector agent</span></span>

<span data-ttu-id="4bace-105">オンプレミスのグラフコネクタでは、 *Graph connector エージェント* ソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-105">On-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="4bace-106">オンプレミスのデータとクラウドサービス間で、迅速かつ安全なデータ転送が可能になります。</span><span class="sxs-lookup"><span data-stu-id="4bace-106">It allows quick and secure data transfer between on-premises data and cloud services.</span></span> <span data-ttu-id="4bace-107">この記事では、ソフトウェアのインストールと構成の手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bace-107">This article guides you through the steps of installing and configuring the software.</span></span> <span data-ttu-id="4bace-108">構成すると、 [Microsoft 365 管理センター](https://admin.microsoft.com)からオンプレミスのデータソースへの接続を作成できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4bace-108">Once configured, it will be available for creating connections to your on-prem data sources from the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

## <a name="installation"></a><span data-ttu-id="4bace-109">インストール</span><span class="sxs-lookup"><span data-stu-id="4bace-109">Installation</span></span>

<span data-ttu-id="4bace-110">[このリンク](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi)を使用して、Graph connector エージェントの最新バージョンをダウンロードし、インストールウィザードを使用してソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4bace-110">Download the latest version of Graph connector agent using [this link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) and install the software using the installation wizard.</span></span> <span data-ttu-id="4bace-111">以下に示すコンピューターの推奨構成を使用すると、ソフトウェアは最大3つの接続をシームレスに処理できます。</span><span class="sxs-lookup"><span data-stu-id="4bace-111">With the recommended configuration of the machine described below, the software can seamlessly handle up to three connections.</span></span> <span data-ttu-id="4bace-112">その他の接続では、パフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-112">Any connections beyond that might degrade the performance.</span></span>

<span data-ttu-id="4bace-113">推奨される構成:</span><span class="sxs-lookup"><span data-stu-id="4bace-113">Recommended configuration:</span></span>

* <span data-ttu-id="4bace-114">Windows 10、Windows Server 2012 R2 以降</span><span class="sxs-lookup"><span data-stu-id="4bace-114">Windows 10, Windows Server 2012 R2 and above</span></span>
* <span data-ttu-id="4bace-115">8コア、3GHz</span><span class="sxs-lookup"><span data-stu-id="4bace-115">8 cores, 3GHz</span></span>
* <span data-ttu-id="4bace-116">16 GB の RAM、1GB のディスク容量</span><span class="sxs-lookup"><span data-stu-id="4bace-116">16GB RAM, 1GB Disk Space</span></span>
* <span data-ttu-id="4bace-117">443を介したデータソースとインターネットへのネットワークアクセス</span><span class="sxs-lookup"><span data-stu-id="4bace-117">Network access to data source and internet through 443</span></span>

## <a name="creating-app-for-the-agent"></a><span data-ttu-id="4bace-118">エージェント用のアプリを作成する</span><span class="sxs-lookup"><span data-stu-id="4bace-118">Creating App for the agent</span></span>  

<span data-ttu-id="4bace-119">接続を作成する前に、エージェントインスタンスに重要なパラメーターをいくつか設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-119">The agent instance needs to be fed few critical parameters before you create connections.</span></span> <span data-ttu-id="4bace-120">これらのパラメーターには、Graph の取り込み Api を使用するために必要な認証の詳細が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4bace-120">These parameters include authentication details required for using Graph ingestion APIs.</span></span>  

<span data-ttu-id="4bace-121">エージェント用のアプリを作成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bace-121">Steps for creating App for the agent.</span></span>

1. <span data-ttu-id="4bace-122">[Azure portal](https://portal.azure.com)に移動し、テナントの管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="4bace-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="4bace-123">ナビゲーションウィンドウから [ **Azure Active Directory** アプリの登録] に移動し、  ->  **App registrations** [**新規登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="4bace-124">アプリの名前を指定して、[ **登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="4bace-125">アプリケーション (クライアント) ID をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="4bace-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="4bace-126">ナビゲーションウィンドウから [ **API アクセス許可** ] を開き、[ **アクセス許可の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="4bace-127">[ **Microsoft Graph** ]、[ **アプリケーションのアクセス許可**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="4bace-128">アクセス許可から "ExternalItem." および "all" を検索し、[ **アクセス許可の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="4bace-129">**[[TenantName] に管理者の同意を付与する**] を選択し、[**はい**] を選択して確定します。</span><span class="sxs-lookup"><span data-stu-id="4bace-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="4bace-130">権限が許可されている状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="4bace-130">Check that the permissions are in the granted state.</span></span>
     <span data-ttu-id="4bace-131">![右側の列に緑色で付与されたアクセス許可が表示されます。](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="4bace-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

## <a name="configuring-graph-connector-agent"></a><span data-ttu-id="4bace-132">Graph connector エージェントを構成する</span><span class="sxs-lookup"><span data-stu-id="4bace-132">Configuring Graph connector agent</span></span>

<span data-ttu-id="4bace-133">エージェント用のアプリを作成したら、適切な認証の詳細を使用してエージェントを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bace-133">Once you have created the App for the agent, you must configure the agent with appropriate authentication details.</span></span>

<span data-ttu-id="4bace-134">認証の詳細は、次のいずれかの形式で提供されます。</span><span class="sxs-lookup"><span data-stu-id="4bace-134">Authentication details can be provided in one of the following forms.</span></span>

### <a name="configuring-the-client-secret-for-authentation"></a><span data-ttu-id="4bace-135">認証のためにクライアントシークレットを構成する</span><span class="sxs-lookup"><span data-stu-id="4bace-135">Configuring the client secret for authentation</span></span>

1. <span data-ttu-id="4bace-136">[Azure portal](https://portal.azure.com)に移動し、テナントの管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="4bace-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="4bace-137">ナビゲーションウィンドウから **アプリの登録** を開いて、適切なアプリに移動します。</span><span class="sxs-lookup"><span data-stu-id="4bace-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="4bace-138">[ **管理**] で、[ **証明書とシークレット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="4bace-139">[ **新しいクライアントシークレット** ] を選択し、シークレットの有効期間を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="4bace-140">生成されたシークレットをコピーして、再度表示されないため、保存します。</span><span class="sxs-lookup"><span data-stu-id="4bace-140">Copy the generated secret and save it because it will not be shown again.</span></span>
4. <span data-ttu-id="4bace-141">このクライアントシークレットをアプリケーション ID と共に使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="4bace-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="4bace-142">エージェントの [ **名前** ] フィールドに空白文字を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="4bace-142">Do not use any blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="4bace-143">英数字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4bace-143">Alpha numeric characters are accepted.</span></span>

## <a name="using-thumbprint-certificate-for-authentication"></a><span data-ttu-id="4bace-144">認証に拇印証明書を使用する</span><span class="sxs-lookup"><span data-stu-id="4bace-144">Using thumbprint certificate for authentication</span></span>

<span data-ttu-id="4bace-145">認証の詳細を既に構成している場合は、認証 [のためにクライアントシークレットを構成](#Configuring-the-client-secret-for-authentication) する必要があります。その後、 [セットアップの概要](configure-connector.md)にジャンプできます。</span><span class="sxs-lookup"><span data-stu-id="4bace-145">If you have already configured the authentication details by following [Configuring the client secret for authentation](#Configuring-the-client-secret-for-authentication) , then you can jump directy to [Setup overview](configure-connector.md).</span></span>

1. <span data-ttu-id="4bace-146">**アプリの登録** を開いて、ナビゲーションウィンドウから [**証明書とシークレット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4bace-146">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="4bace-147">証明書の拇印をコピーします。</span><span class="sxs-lookup"><span data-stu-id="4bace-147">Copy the certificate thumbprint.</span></span>
<span data-ttu-id="4bace-148">![左側のウィンドウで証明書とシークレットが選択されている場合の thumbrint 証明書の一覧](media/onprem-agent/certificates.png)</span><span class="sxs-lookup"><span data-stu-id="4bace-148">![List of thumbrint certificates when Certificates and secrets is selected in the left pane](media/onprem-agent/certificates.png)</span></span>
2. <span data-ttu-id="4bace-149">Graph connector エージェントを登録するには、クライアントシークレットまたは拇印のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="4bace-149">Use either the client secret or thumbprint to register the Graph connector agent.</span></span>
<span data-ttu-id="4bace-150">![Register form が名前、アプリ id、資格情報の種類、および証明書を確認する](media/onprem-agent/register.png)</span><span class="sxs-lookup"><span data-stu-id="4bace-150">![Register form asking for name, app id, credential type, and certificate](media/onprem-agent/register.png)</span></span>
