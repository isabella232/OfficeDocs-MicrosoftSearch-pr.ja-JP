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
# <a name="graph-connector-agent"></a>Graph コネクタ エージェント

オンプレム Graph コネクタを使用するには、Graph コネクタ エージェント *ソフトウェアをインストールする必要* があります。 これにより、オンプレミス のデータと Graph コネクタ API の間でセキュリティで保護されたデータ転送が可能です。 この記事では、エージェントのインストールと構成について手順を示します。

## <a name="installation"></a>インストール

ここに最新バージョンの Graph コネクタ エージェントを [ダウンロードし](https://aka.ms/gcadownload) 、インストール ウィザードを使用してソフトウェアをインストールします。 以下で説明するコンピューターの推奨構成を使用して、ソフトウェアは最大 3 つの接続を処理できます。 それ以降の接続では、エージェント上のすべての接続のパフォーマンスが低下する可能性があります。

推奨される構成:

* Windows 10、Windows Server 2016 R2 以上
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 コア、3 GHz
* 16 GB RAM、2 GB のディスク領域
* 443 を介したデータ ソースとインターネットへのネットワーク アクセス

## <a name="create-and-configure-an-app-for-the-agent"></a>エージェント用のアプリを作成して構成する  

最初にサインインし、アカウントに最低限必要な権限は検索管理者です。 エージェントは、認証の詳細を入力する必要があります。 以下の手順を使用して、アプリを作成し、必要な認証の詳細を生成します。

### <a name="create-an-app"></a>アプリを作成する

1. Azure ポータルに [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。
2. ナビゲーション ウィンドウ **から Azure Active Directory**  ->  **アプリの登録** に移動し、[新規登録]**を選択します**。
3. アプリの名前を入力し、[登録] を選択 **します**。
4. アプリケーション (クライアント) ID をメモします。
5. ナビゲーション **ウィンドウから API のアクセス許可** を開き、[アクセス許可の **追加] を選択します**。
6. **[Microsoft Graph] を選択** し、[アプリケーションのアクセス **許可] を選択します**。
7. アクセス許可から "ExternalItem.ReadWrite.All" と "Directory.Read.All" を検索し、[アクセス許可の追加] **を選択します**。
8. Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.
9. アクセス許可が "付与" 状態にあるか確認します。
     ![右側の列に緑色で付与されたアクセス許可が表示されます。](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>認証を構成する

認証の詳細は、クライアント シークレットまたは証明書を使用して提供できます。 選択した手順に従います。

#### <a name="configuring-the-client-secret-for-authentication"></a>認証用のクライアント シークレットの構成

1. Azure ポータルに [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。
2. ナビゲーション **ウィンドウから [** アプリの登録] を開き、適切なアプリに移動します。 [ **管理] で**、[ **証明書とシークレット] を選択します**。
3. [ **新しいクライアント シークレット] を** 選択し、シークレットの有効期限を選択します。 生成されたシークレットをコピーして保存します。これは、再び表示されません。
4. このクライアント シークレットをアプリケーション ID と共に使用して、エージェントを構成します。 エージェントの Name フィールドに空白 **を** 使用することはできません。 英数字を使用できます。

#### <a name="using-a-certificate-for-authentication"></a>認証に証明書を使用する

証明書ベースの認証を使用するには、次の 3 つの簡単な手順があります。

1. 証明書を作成または取得する
1. Azure Portal に証明書をアップロードする
1. エージェントに証明書を割り当てる

##### <a name="step-1-get-a-certificate"></a>手順 1: 証明書を取得する

以下のスクリプトを使用して、自己署名証明書を生成できます。 組織は自己署名証明書を許可しない場合があります。 その場合は、この情報を使用して要件を理解し、組織のポリシーに従って証明書を取得します。

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>手順 2: Azure portal で証明書をアップロードする

1. アプリケーションを開き、左側のウィンドウから [証明書とシークレット] セクションに移動します。
1. [証明書のアップロード] を選択し、.cer ファイルをアップロードします。
1. アプリ **の登録を** 開き、ナビゲーション ウィンドウから **[** 証明書とシークレット] を選択します。 証明書の拇印をコピーします。

![左側のウィンドウで [証明書とシークレット] が選択されている場合の拇印証明書の一覧](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>手順 3: エージェントに証明書を割り当てる

サンプル スクリプトを使用して証明書を生成した場合、PFX ファイルはスクリプト内で識別された場所に見つけることができます。

1. エージェント コンピューターに証明書 pfx ファイルをダウンロードします。
1. pfx ファイルをダブルクリックして、証明書のインストール ダイアログを起動します。
1. 証明書のインストール中に、ストアの場所として [ローカル コンピューター] を選択します。
1. 証明書をインストールした後、[スタート] メニューから [コンピューター証明書の管理] を開きます。
1. [個人] ->の下で新しくインストールされた証明書を選択します。
1. 証明書を右クリックし、[すべてのタスク] -> 'Manage Private Keys...' を選択します。 オプション
1. アクセス許可ダイアログで、[追加] オプションを選択します。 ユーザー選択ダイアログで、「NT Service\GcaHostService」と入力し、[OK] をクリックします。 [名前の確認] ボタンをクリックしない。
1. [アクセス許可] ダイアログで [問題ありません] をクリックします。 これで、エージェント マシンは、証明書を使用してトークンを生成するようにエージェントが構成されました。
