---
title: オンプレミスのエージェント
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
ROBOTS: NoIndex
description: オンプレミスエージェント
ms.openlocfilehash: 5dbca392fefdcc11de253fd244cc98a6adcee68a
ms.sourcegitcommit: e8d770fa72ac83e074a5de57098cb55d06d8db07
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588369"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="a9bd0-103">グラフコネクタエージェント</span><span class="sxs-lookup"><span data-stu-id="a9bd0-103">Graph connector agent</span></span>

<span data-ttu-id="a9bd0-104">オンプレミスのグラフコネクタを使用するには、 *graph connector エージェント* ソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="a9bd0-105">これにより、オンプレミスのデータと Graph connector Api との間でデータを安全に転送できます。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="a9bd0-106">この記事では、エージェントをインストールして構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="a9bd0-107">インストール</span><span class="sxs-lookup"><span data-stu-id="a9bd0-107">Installation</span></span>

<span data-ttu-id="a9bd0-108">Graph connector エージェントの最新バージョンをダウンロードし、インストールウィザードを使用してソフトウェアを [インストールします](https://aka.ms/gcadownload) 。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="a9bd0-109">以下に示すコンピューターの推奨構成を使用して、ソフトウェアは最大3つの接続を処理できます。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="a9bd0-110">その他の接続では、エージェント上のすべての接続のパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="a9bd0-111">推奨される構成:</span><span class="sxs-lookup"><span data-stu-id="a9bd0-111">Recommended configuration:</span></span>

* <span data-ttu-id="a9bd0-112">Windows 10、Windows Server 2016 R2 以降</span><span class="sxs-lookup"><span data-stu-id="a9bd0-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="a9bd0-113">.NET コアデスクトップランタイム 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="a9bd0-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="a9bd0-114">8コア、3 GHz</span><span class="sxs-lookup"><span data-stu-id="a9bd0-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="a9bd0-115">16 GB の RAM、2 GB のディスク領域</span><span class="sxs-lookup"><span data-stu-id="a9bd0-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="a9bd0-116">443を介したデータソースとインターネットへのネットワークアクセス</span><span class="sxs-lookup"><span data-stu-id="a9bd0-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="a9bd0-117">エージェント用のアプリを作成および構成する</span><span class="sxs-lookup"><span data-stu-id="a9bd0-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="a9bd0-118">エージェントを使用する前に、アプリを作成し、認証の詳細を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-118">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="a9bd0-119">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="a9bd0-119">Create an app</span></span>

1. <span data-ttu-id="a9bd0-120">[Azure portal](https://portal.azure.com)に移動し、テナントの管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-120">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="a9bd0-121">ナビゲーションウィンドウから [ **Azure Active Directory** アプリの登録] に移動し、  ->  **App registrations** [**新規登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-121">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="a9bd0-122">アプリの名前を指定して、[ **登録**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-122">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="a9bd0-123">アプリケーション (クライアント) ID をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-123">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="a9bd0-124">ナビゲーションウィンドウから [ **API アクセス許可** ] を開き、[ **アクセス許可の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-124">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="a9bd0-125">[ **Microsoft Graph** ]、[ **アプリケーションのアクセス許可**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-125">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="a9bd0-126">アクセス許可から "ExternalItem." および "all" を検索し、[ **アクセス許可の追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-126">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="a9bd0-127">**[[TenantName] に管理者の同意を付与する**] を選択し、[**はい**] を選択して確定します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-127">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="a9bd0-128">アクセス許可が "許可" 状態であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-128">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="a9bd0-129">![右側の列に緑色で付与されたアクセス許可が表示されます。](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="a9bd0-129">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="a9bd0-130">認証を構成する</span><span class="sxs-lookup"><span data-stu-id="a9bd0-130">Configure Authentication</span></span>

<span data-ttu-id="a9bd0-131">認証の詳細は、クライアントシークレットまたは証明書を使用して提供できます。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-131">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="a9bd0-132">任意の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-132">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="a9bd0-133">認証用にクライアントシークレットを構成する</span><span class="sxs-lookup"><span data-stu-id="a9bd0-133">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="a9bd0-134">[Azure portal](https://portal.azure.com)に移動し、テナントの管理者の資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-134">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="a9bd0-135">ナビゲーションウィンドウから **アプリの登録** を開いて、適切なアプリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-135">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="a9bd0-136">[ **管理**] で、[ **証明書とシークレット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-136">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="a9bd0-137">[ **新しいクライアントシークレット** ] を選択し、シークレットの有効期間を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-137">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="a9bd0-138">生成されたシークレットをコピーして、再度表示されないため、保存します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-138">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="a9bd0-139">このクライアントシークレットをアプリケーション ID と共に使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-139">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="a9bd0-140">エージェントの [ **名前** ] フィールドに空白文字を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-140">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="a9bd0-141">英数字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-141">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="a9bd0-142">認証に証明書を使用する</span><span class="sxs-lookup"><span data-stu-id="a9bd0-142">Using a certificate for authentication</span></span>

<span data-ttu-id="a9bd0-143">証明書ベースの認証を使用するには、次の3つの簡単な手順があります。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-143">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="a9bd0-144">証明書を作成または取得する</span><span class="sxs-lookup"><span data-stu-id="a9bd0-144">Create or obtain a certificate</span></span>
1. <span data-ttu-id="a9bd0-145">Azure portal に証明書をアップロードする</span><span class="sxs-lookup"><span data-stu-id="a9bd0-145">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="a9bd0-146">エージェントに証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9bd0-146">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="a9bd0-147">手順 1: 証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="a9bd0-147">Step 1: Get a certificate</span></span>

<span data-ttu-id="a9bd0-148">次のスクリプトを使用して、自己署名証明書を生成できます。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-148">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="a9bd0-149">組織で自己署名証明書が許可されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-149">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="a9bd0-150">その場合は、この情報を使用して要件を理解し、組織のポリシーに従って証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-150">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```Powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="a9bd0-151">手順 2: Azure portal で証明書をアップロードする</span><span class="sxs-lookup"><span data-stu-id="a9bd0-151">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="a9bd0-152">アプリケーションを開き、左側のウィンドウから [証明書とシークレット] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-152">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="a9bd0-153">[証明書のアップロード] を選択し、.cer ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-153">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="a9bd0-154">**アプリの登録** を開いて、ナビゲーションウィンドウから [**証明書とシークレット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-154">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="a9bd0-155">証明書の拇印をコピーします。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-155">Copy the certificate thumbprint.</span></span>

![左側のウィンドウで証明書とシークレットが選択されている場合の thumbrint 証明書の一覧](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="a9bd0-157">手順 3: エージェントに証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="a9bd0-157">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="a9bd0-158">サンプルスクリプトを使用して証明書を生成した場合は、スクリプトで識別された場所に PFX ファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-158">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="a9bd0-159">証明書 pfx ファイルをエージェントコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-159">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="a9bd0-160">Pfx ファイルをダブルクリックして、[証明書のインストール] ダイアログを起動します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-160">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="a9bd0-161">証明書のインストール時に保存場所として [ローカルコンピューター] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-161">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="a9bd0-162">証明書をインストールしたら、[スタート] メニューから [コンピューターの証明書の管理] を開きます。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-162">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="a9bd0-163">[Personal]-> ' Certificates ' の下に新しくインストールされた証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-163">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="a9bd0-164">証明書を右クリックして [すべてのタスク]-> [秘密キーの管理...] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-164">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="a9bd0-165">オプション</span><span class="sxs-lookup"><span data-stu-id="a9bd0-165">Option</span></span>
1. <span data-ttu-id="a9bd0-166">[アクセス許可] ダイアログで、[オプションの追加] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-166">In the permissions dialog, select add option.</span></span> <span data-ttu-id="a9bd0-167">[ユーザーの選択] ダイアログで、「NT Service\ gcahostservice」と入力して、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-167">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="a9bd0-168">[名前の確認] ボタンをクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-168">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="a9bd0-169">[アクセス許可] ダイアログボックスで [ok] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-169">Click okay on the permissions dialog.</span></span> <span data-ttu-id="a9bd0-170">エージェントコンピューターが、証明書を使用してトークンを生成するように構成されました。</span><span class="sxs-lookup"><span data-stu-id="a9bd0-170">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
