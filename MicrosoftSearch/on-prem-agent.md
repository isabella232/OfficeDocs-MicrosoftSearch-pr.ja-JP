---
title: オンプレミス エージェント
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: On-prem Agent
ms.openlocfilehash: d6dabbbb5ee34acedd92166564f560bbc64c7da7
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230927"
---
# <a name="microsoft-graph-connector-agent"></a><span data-ttu-id="f9d0a-103">Microsoft Graph コネクタ エージェント</span><span class="sxs-lookup"><span data-stu-id="f9d0a-103">Microsoft Graph connector agent</span></span>

<span data-ttu-id="f9d0a-104">オンプレム コネクタを使用するには *、Microsoft Graphエージェント ソフトウェアをインストールする必要* があります。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-104">Using on-prem connectors require you to install *Microsoft Graph connector agent* software.</span></span> <span data-ttu-id="f9d0a-105">これにより、オンプレミスのデータとコネクタ API 間の安全なデータ転送が可能です。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-105">It allows for secure data transfer between on-premises data and the connector APIs.</span></span> <span data-ttu-id="f9d0a-106">この記事では、エージェントのインストールと構成についてガイドします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="f9d0a-107">インストール</span><span class="sxs-lookup"><span data-stu-id="f9d0a-107">Installation</span></span>

<span data-ttu-id="f9d0a-108">インストール ウィザードを使用して、Graphコネクタ エージェントの最新バージョンをダウンロードし、 [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) ソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-108">Download the latest version of the Graph connector agent from [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) and install the software by using the installation wizard.</span></span> <span data-ttu-id="f9d0a-109">以下で説明するコンピューターの推奨構成を使用して、ソフトウェアは最大 3 つの接続を処理できます。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="f9d0a-110">それ以降の接続では、エージェント上のすべての接続のパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="f9d0a-111">推奨される構成:</span><span class="sxs-lookup"><span data-stu-id="f9d0a-111">Recommended configuration:</span></span>

* <span data-ttu-id="f9d0a-112">Windows 10、Windows Server 2016 R2 以上</span><span class="sxs-lookup"><span data-stu-id="f9d0a-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="f9d0a-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="f9d0a-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="f9d0a-114">8 コア、3 GHz</span><span class="sxs-lookup"><span data-stu-id="f9d0a-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="f9d0a-115">16 GB RAM、2 GB のディスク領域</span><span class="sxs-lookup"><span data-stu-id="f9d0a-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="f9d0a-116">443 を介したデータ ソースとインターネットへのネットワーク アクセス</span><span class="sxs-lookup"><span data-stu-id="f9d0a-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="f9d0a-117">エージェントをインストールした後、組織のプロキシ サーバーまたはファイアウォールが不明なドメインへの通信をブロックする場合は、許可リストに以下のドメインを追加してください。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="f9d0a-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="f9d0a-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="f9d0a-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f9d0a-119">\*.events.data.microsoft.com</span></span>
3. <span data-ttu-id="f9d0a-120"> https://<span>login.microsoftonline.</span>com</span><span class="sxs-lookup"><span data-stu-id="f9d0a-120">https://<span>login.microsoftonline.</span>com</span></span>
4. <span data-ttu-id="f9d0a-121"> https://<span>gcs.office.</span>com/</span><span class="sxs-lookup"><span data-stu-id="f9d0a-121">https://<span>gcs.office.</span>com/</span></span>
5. <span data-ttu-id="f9d0a-122"> https://<span>graph.microsoft.</span>com/</span><span class="sxs-lookup"><span data-stu-id="f9d0a-122">https://<span>graph.microsoft.</span>com/</span></span>


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="f9d0a-123">エージェント用のアプリを作成および構成する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-123">Create and configure an App for the agent</span></span>  

<span data-ttu-id="f9d0a-124">最初にサインインし、アカウントに必要な最小特権が検索管理者である点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-124">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="f9d0a-125">その後、エージェントから認証の詳細を入力する要求が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-125">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="f9d0a-126">以下の手順を使用してアプリを作成し、必要な認証の詳細を生成します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-126">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="f9d0a-127">アプリを作成する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-127">Create an app</span></span>

1. <span data-ttu-id="f9d0a-128">Azure portal に [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-128">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>

2. <span data-ttu-id="f9d0a-129">ナビゲーション ウィンドウから **[Azure Active Directory**  ->  **登録**] に移動し、[新規登録]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-129">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>

3. <span data-ttu-id="f9d0a-130">アプリの名前を指定し、[登録] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-130">Provide a name for the app and select **Register**.</span></span>

4. <span data-ttu-id="f9d0a-131">アプリケーション (クライアント) ID をメモします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-131">Make a note of the Application (client) ID.</span></span>

5. <span data-ttu-id="f9d0a-132">ナビゲーション **ウィンドウから API アクセス許可** を開き、[アクセス許可の **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-132">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>

6. <span data-ttu-id="f9d0a-133">[Microsoft **Graph] を選択** し、[**アプリケーションのアクセス許可] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-133">Select **Microsoft Graph** and then **Application permissions**.</span></span>

7. <span data-ttu-id="f9d0a-134">アクセス許可から "ExternalItem.ReadWrite.All" と "Directory.Read.All" を検索し、[アクセス許可の追加 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-134">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>

8. <span data-ttu-id="f9d0a-135">**[TenantName] の [管理者の同意を許可する] を選択し、[** はい] を選択して確認 **します**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-135">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>

9. <span data-ttu-id="f9d0a-136">アクセス許可が "許可された" 状態にあるか確認します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-136">Check that the permissions are in the "granted" state.</span></span>

    :::image type="content" alt-text="右側の列に緑で付与されたアクセス許可を示します。" source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

### <a name="configure-authentication"></a><span data-ttu-id="f9d0a-138">認証を構成する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-138">Configure Authentication</span></span>

<span data-ttu-id="f9d0a-139">認証の詳細は、クライアント シークレットまたは証明書を使用して提供できます。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-139">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="f9d0a-140">選択した手順に従います。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-140">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="f9d0a-141">認証用にクライアント シークレットを構成する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-141">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="f9d0a-142">Azure portal に [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-142">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>

2. <span data-ttu-id="f9d0a-143">ナビゲーション **ウィンドウから [アプリ** の登録] を開き、適切なアプリに移動します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-143">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="f9d0a-144">[管理 **] で**、[ **証明書とシークレット] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-144">Under **Manage**, select **Certificates and secrets**.</span></span>

3. <span data-ttu-id="f9d0a-145">[ **新しいクライアント シークレット] を** 選択し、シークレットの有効期限を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-145">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="f9d0a-146">生成されたシークレットをコピーし、再度表示しないので保存します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-146">Copy the generated secret and save it because it won't be shown again.</span></span>

4. <span data-ttu-id="f9d0a-147">このクライアント シークレットとアプリケーション ID を使用してエージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-147">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="f9d0a-148">エージェントの [名前] フィールド **に空白を** 使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-148">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="f9d0a-149">英数字を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-149">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="f9d0a-150">認証に証明書を使用する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-150">Using a certificate for authentication</span></span>

<span data-ttu-id="f9d0a-151">証明書ベースの認証を使用するには、次の 3 つの簡単な手順があります。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-151">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="f9d0a-152">証明書を作成または取得する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-152">Create or obtain a certificate</span></span>
1. <span data-ttu-id="f9d0a-153">アップロード Azure portal に証明書を追加する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-153">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="f9d0a-154">証明書をエージェントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9d0a-154">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="f9d0a-155">手順 1: 証明書を取得する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-155">Step 1: Get a certificate</span></span>

<span data-ttu-id="f9d0a-156">以下のスクリプトを使用して、自己署名証明書を生成できます。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-156">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="f9d0a-157">組織は自己署名証明書を許可しない場合があります。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-157">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="f9d0a-158">その場合は、この情報を使用して要件を理解し、組織のポリシーに従って証明書を取得します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-158">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```powershell
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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="f9d0a-159">手順 2: azure portal アップロード証明書を削除する</span><span class="sxs-lookup"><span data-stu-id="f9d0a-159">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="f9d0a-160">アプリケーションを開き、左側のウィンドウから [証明書とシークレット] セクションに移動します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-160">Open the application and navigate to certificates and secrets section from left pane.</span></span>

1. <span data-ttu-id="f9d0a-161">[証明書 **アップロード選択し**、.cer ファイルをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-161">Select **Upload certificate** and upload the .cer file.</span></span>

1. <span data-ttu-id="f9d0a-162">アプリ **の登録を開** き、 **ナビゲーション ウィンドウから [** 証明書とシークレット] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-162">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="f9d0a-163">証明書の拇印をコピーします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-163">Copy the certificate thumbprint.</span></span>

:::image type="content" alt-text="左側のウィンドウで [証明書とシークレット] が選択されている場合の thumbrint 証明書の一覧" source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="f9d0a-165">手順 3: 証明書をエージェントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="f9d0a-165">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="f9d0a-166">サンプル スクリプトを使用して証明書を生成した場合、PFX ファイルはスクリプトで識別された場所で見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-166">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="f9d0a-167">証明書 pfx ファイルをエージェント コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-167">Download the certificate pfx file onto the Agent machine.</span></span>

1. <span data-ttu-id="f9d0a-168">pfx ファイルをダブルクリックして、証明書のインストール ダイアログを起動します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-168">Double-click the pfx file to launch the certificate installation dialog.</span></span>

1. <span data-ttu-id="f9d0a-169">証明書 **のインストール中に** ストアの場所として [ローカル コンピューター] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-169">Select **Local Machine** for store location while installing the certificate.</span></span>

1. <span data-ttu-id="f9d0a-170">証明書をインストールした後、[コンピューター証明書の **管理]** を開きます。スタート メニュー。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-170">After installing the certificate, open **Manage computer certificates** through Start menu.</span></span>

1. <span data-ttu-id="f9d0a-171">[個人証明書] で新しくインストール **された証明書を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-171">Select the newly installed certificate under **Personal** > **Certificates**.</span></span>

1. <span data-ttu-id="f9d0a-172">証明書を右クリックし、[すべてのタスクの **プライベート キー** の  >  **管理] オプションを選択** します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-172">Right click on the cert and select **All Tasks** > **Manage Private Keys** Option.</span></span>

1. <span data-ttu-id="f9d0a-173">[アクセス許可] ダイアログで、[追加] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-173">In the permissions dialog, select add option.</span></span> <span data-ttu-id="f9d0a-174">ユーザー選択ダイアログで、NT **Service\GcaHostService と** 書き込み **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-174">In the user selection dialog, write: **NT Service\GcaHostService** and click **OK**.</span></span> <span data-ttu-id="f9d0a-175">[名前の確認] **ボタンをクリック** しない。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-175">Don't click the **Check Names** button.</span></span>

1. <span data-ttu-id="f9d0a-176">[アクセス許可] ダイアログで [ok] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-176">Click okay on the permissions dialog.</span></span> <span data-ttu-id="f9d0a-177">エージェント コンピューターが、証明書を使用してトークンを生成するようにエージェントが構成されました。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-177">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f9d0a-178">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f9d0a-178">Troubleshooting</span></span>

1. <span data-ttu-id="f9d0a-179">"1011: Graph コネクタ エージェントに到達できない"または "オフライン" というエラーで接続が失敗した場合は、エージェントがインストールされているコンピューターにログインし、まだ実行されていない場合はエージェント アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-179">If a connection fails with the error "1011: The Graph connector agent is not reachable or offline.", log in to the machine where agent is installed and start the agent application if it isn't running already.</span></span> <span data-ttu-id="f9d0a-180">接続が引き続き失敗する場合は、登録中にエージェントに提供された証明書またはクライアント シークレットが期限切れで、必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f9d0a-180">If the connection continues to fail, verify that the certificate or client secret provided to the agent during registration hasn't expired and has required permissions.</span></span>
