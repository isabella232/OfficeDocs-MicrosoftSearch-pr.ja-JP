---
title: オンプレミス エージェント
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
description: オンプレム エージェント
ms.openlocfilehash: 31220196849fe90ab2611e9c2b83a1cec0a02b34
ms.sourcegitcommit: a04f1df14a3221776ccd141f6060328612d80e06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876500"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="fe1e5-103">Graph コネクタ エージェント</span><span class="sxs-lookup"><span data-stu-id="fe1e5-103">Graph connector agent</span></span>

<span data-ttu-id="fe1e5-104">オンプレム Graph コネクタを使用するには、Graph コネクタ エージェント *ソフトウェアをインストールする必要* があります。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="fe1e5-105">これにより、オンプレミス のデータと Graph コネクタ API の間でセキュリティで保護されたデータ転送が可能です。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="fe1e5-106">この記事では、エージェントのインストールと構成について手順を示します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="fe1e5-107">インストール</span><span class="sxs-lookup"><span data-stu-id="fe1e5-107">Installation</span></span>

<span data-ttu-id="fe1e5-108">ここに最新バージョンの Graph コネクタ エージェントを [ダウンロードし](https://aka.ms/gcadownload) 、インストール ウィザードを使用してソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="fe1e5-109">以下で説明するコンピューターの推奨構成を使用して、ソフトウェアは最大 3 つの接続を処理できます。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="fe1e5-110">それ以降の接続では、エージェント上のすべての接続のパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="fe1e5-111">推奨される構成:</span><span class="sxs-lookup"><span data-stu-id="fe1e5-111">Recommended configuration:</span></span>

* <span data-ttu-id="fe1e5-112">Windows 10、Windows Server 2016 R2 以上</span><span class="sxs-lookup"><span data-stu-id="fe1e5-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="fe1e5-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="fe1e5-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="fe1e5-114">8 コア、3 GHz</span><span class="sxs-lookup"><span data-stu-id="fe1e5-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="fe1e5-115">16 GB RAM、2 GB のディスク領域</span><span class="sxs-lookup"><span data-stu-id="fe1e5-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="fe1e5-116">443 を介したデータ ソースとインターネットへのネットワーク アクセス</span><span class="sxs-lookup"><span data-stu-id="fe1e5-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="fe1e5-117">エージェント用のアプリを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="fe1e5-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="fe1e5-118">最初にサインインし、アカウントに最低限必要な権限は検索管理者です。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-118">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="fe1e5-119">エージェントは、認証の詳細を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-119">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="fe1e5-120">以下の手順を使用して、アプリを作成し、必要な認証の詳細を生成します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-120">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="fe1e5-121">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="fe1e5-121">Create an app</span></span>

1. <span data-ttu-id="fe1e5-122">Azure ポータルに [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="fe1e5-123">ナビゲーション ウィンドウ **から Azure Active Directory**  ->  **アプリの登録** に移動し、[新規登録]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="fe1e5-124">アプリの名前を入力し、[登録] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="fe1e5-125">アプリケーション (クライアント) ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="fe1e5-126">ナビゲーション **ウィンドウから API のアクセス許可** を開き、[アクセス許可の **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="fe1e5-127">**[Microsoft Graph] を選択** し、[アプリケーションのアクセス **許可] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="fe1e5-128">アクセス許可から "ExternalItem.ReadWrite.All" と "Directory.Read.All" を検索し、[アクセス許可の追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="fe1e5-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span><span class="sxs-lookup"><span data-stu-id="fe1e5-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="fe1e5-130">アクセス許可が "付与" 状態にあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-130">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="fe1e5-131">![右側の列に緑色で付与されたアクセス許可が表示されます。](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="fe1e5-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="fe1e5-132">認証を構成する</span><span class="sxs-lookup"><span data-stu-id="fe1e5-132">Configure Authentication</span></span>

<span data-ttu-id="fe1e5-133">認証の詳細は、クライアント シークレットまたは証明書を使用して提供できます。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-133">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="fe1e5-134">選択した手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-134">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="fe1e5-135">認証用のクライアント シークレットの構成</span><span class="sxs-lookup"><span data-stu-id="fe1e5-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="fe1e5-136">Azure ポータルに [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="fe1e5-137">ナビゲーション **ウィンドウから [** アプリの登録] を開き、適切なアプリに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="fe1e5-138">[ **管理] で**、[ **証明書とシークレット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="fe1e5-139">[ **新しいクライアント シークレット] を** 選択し、シークレットの有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="fe1e5-140">生成されたシークレットをコピーして保存します。これは、再び表示されません。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-140">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="fe1e5-141">このクライアント シークレットをアプリケーション ID と共に使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="fe1e5-142">エージェントの Name フィールドに空白 **を** 使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-142">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="fe1e5-143">英数字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-143">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="fe1e5-144">認証に証明書を使用する</span><span class="sxs-lookup"><span data-stu-id="fe1e5-144">Using a certificate for authentication</span></span>

<span data-ttu-id="fe1e5-145">証明書ベースの認証を使用するには、次の 3 つの簡単な手順があります。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-145">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="fe1e5-146">証明書を作成または取得する</span><span class="sxs-lookup"><span data-stu-id="fe1e5-146">Create or obtain a certificate</span></span>
1. <span data-ttu-id="fe1e5-147">Azure Portal に証明書をアップロードする</span><span class="sxs-lookup"><span data-stu-id="fe1e5-147">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="fe1e5-148">エージェントに証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fe1e5-148">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="fe1e5-149">手順 1: 証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="fe1e5-149">Step 1: Get a certificate</span></span>

<span data-ttu-id="fe1e5-150">以下のスクリプトを使用して、自己署名証明書を生成できます。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-150">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="fe1e5-151">組織は自己署名証明書を許可しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-151">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="fe1e5-152">その場合は、この情報を使用して要件を理解し、組織のポリシーに従って証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-152">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="fe1e5-153">手順 2: Azure portal で証明書をアップロードする</span><span class="sxs-lookup"><span data-stu-id="fe1e5-153">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="fe1e5-154">アプリケーションを開き、左側のウィンドウから [証明書とシークレット] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-154">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="fe1e5-155">[証明書のアップロード] を選択し、.cer ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-155">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="fe1e5-156">アプリ **の登録を** 開き、ナビゲーション ウィンドウから **[** 証明書とシークレット] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-156">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="fe1e5-157">証明書の拇印をコピーします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-157">Copy the certificate thumbprint.</span></span>

![左側のウィンドウで [証明書とシークレット] が選択されている場合の拇印証明書の一覧](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="fe1e5-159">手順 3: エージェントに証明書を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fe1e5-159">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="fe1e5-160">サンプル スクリプトを使用して証明書を生成した場合、PFX ファイルはスクリプト内で識別された場所に見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-160">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="fe1e5-161">エージェント コンピューターに証明書 pfx ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-161">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="fe1e5-162">pfx ファイルをダブルクリックして、証明書のインストール ダイアログを起動します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-162">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="fe1e5-163">証明書のインストール中に、ストアの場所として [ローカル コンピューター] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-163">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="fe1e5-164">証明書をインストールした後、[スタート] メニューから [コンピューター証明書の管理] を開きます。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-164">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="fe1e5-165">[個人] ->の下で新しくインストールされた証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-165">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="fe1e5-166">証明書を右クリックし、[すべてのタスク] -> 'Manage Private Keys...' を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-166">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="fe1e5-167">オプション</span><span class="sxs-lookup"><span data-stu-id="fe1e5-167">Option</span></span>
1. <span data-ttu-id="fe1e5-168">アクセス許可ダイアログで、[追加] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-168">In the permissions dialog, select add option.</span></span> <span data-ttu-id="fe1e5-169">ユーザー選択ダイアログで、「NT Service\GcaHostService」と入力し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-169">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="fe1e5-170">[名前の確認] ボタンをクリックしない。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-170">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="fe1e5-171">[アクセス許可] ダイアログで [問題ありません] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-171">Click okay on the permissions dialog.</span></span> <span data-ttu-id="fe1e5-172">これで、エージェント マシンは、証明書を使用してトークンを生成するようにエージェントが構成されました。</span><span class="sxs-lookup"><span data-stu-id="fe1e5-172">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
