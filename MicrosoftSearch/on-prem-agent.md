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
# <a name="graph-connector-agent"></a>グラフコネクタエージェント

オンプレミスのグラフコネクタを使用するには、 *graph connector エージェント* ソフトウェアをインストールする必要があります。 これにより、オンプレミスのデータと Graph connector Api との間でデータを安全に転送できます。 この記事では、エージェントをインストールして構成する方法について説明します。

## <a name="installation"></a>インストール

Graph connector エージェントの最新バージョンをダウンロードし、インストールウィザードを使用してソフトウェアを [インストールします](https://aka.ms/gcadownload) 。 以下に示すコンピューターの推奨構成を使用して、ソフトウェアは最大3つの接続を処理できます。 その他の接続では、エージェント上のすべての接続のパフォーマンスが低下する可能性があります。

推奨される構成:

* Windows 10、Windows Server 2016 R2 以降
* [.NET コアデスクトップランタイム 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8コア、3 GHz
* 16 GB の RAM、2 GB のディスク領域
* 443を介したデータソースとインターネットへのネットワークアクセス

## <a name="create-and-configure-an-app-for-the-agent"></a>エージェント用のアプリを作成および構成する  

エージェントを使用する前に、アプリを作成し、認証の詳細を構成する必要があります。

### <a name="create-an-app"></a>アプリを作成する

1. [Azure portal](https://portal.azure.com)に移動し、テナントの管理者の資格情報でサインインします。
2. ナビゲーションウィンドウから [ **Azure Active Directory** アプリの登録] に移動し、  ->  **App registrations** [**新規登録**] を選択します。
3. アプリの名前を指定して、[ **登録**] を選択します。
4. アプリケーション (クライアント) ID をメモしておきます。
5. ナビゲーションウィンドウから [ **API アクセス許可** ] を開き、[ **アクセス許可の追加**] を選択します。
6. [ **Microsoft Graph** ]、[ **アプリケーションのアクセス許可**] の順に選択します。
7. アクセス許可から "ExternalItem." および "all" を検索し、[ **アクセス許可の追加**] を選択します。
8. **[[TenantName] に管理者の同意を付与する**] を選択し、[**はい**] を選択して確定します。
9. アクセス許可が "許可" 状態であることを確認します。
     ![右側の列に緑色で付与されたアクセス許可が表示されます。](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>認証を構成する

認証の詳細は、クライアントシークレットまたは証明書を使用して提供できます。 任意の手順を実行します。

#### <a name="configuring-the-client-secret-for-authentication"></a>認証用にクライアントシークレットを構成する

1. [Azure portal](https://portal.azure.com)に移動し、テナントの管理者の資格情報でサインインします。
2. ナビゲーションウィンドウから **アプリの登録** を開いて、適切なアプリに移動します。 [ **管理**] で、[ **証明書とシークレット**] を選択します。
3. [ **新しいクライアントシークレット** ] を選択し、シークレットの有効期間を選択します。 生成されたシークレットをコピーして、再度表示されないため、保存します。
4. このクライアントシークレットをアプリケーション ID と共に使用して、エージェントを構成します。 エージェントの [ **名前** ] フィールドに空白文字を使用することはできません。 英数字を使用できます。

#### <a name="using-a-certificate-for-authentication"></a>認証に証明書を使用する

証明書ベースの認証を使用するには、次の3つの簡単な手順があります。

1. 証明書を作成または取得する
1. Azure portal に証明書をアップロードする
1. エージェントに証明書を割り当てる

##### <a name="step-1-get-a-certificate"></a>手順 1: 証明書を取得する

次のスクリプトを使用して、自己署名証明書を生成できます。 組織で自己署名証明書が許可されていない可能性があります。 その場合は、この情報を使用して要件を理解し、組織のポリシーに従って証明書を取得します。

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
1. **アプリの登録** を開いて、ナビゲーションウィンドウから [**証明書とシークレット**] を選択します。 証明書の拇印をコピーします。

![左側のウィンドウで証明書とシークレットが選択されている場合の thumbrint 証明書の一覧](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>手順 3: エージェントに証明書を割り当てる

サンプルスクリプトを使用して証明書を生成した場合は、スクリプトで識別された場所に PFX ファイルがあります。

1. 証明書 pfx ファイルをエージェントコンピューターにダウンロードします。
1. Pfx ファイルをダブルクリックして、[証明書のインストール] ダイアログを起動します。
1. 証明書のインストール時に保存場所として [ローカルコンピューター] を選択します。
1. 証明書をインストールしたら、[スタート] メニューから [コンピューターの証明書の管理] を開きます。
1. [Personal]-> ' Certificates ' の下に新しくインストールされた証明書を選択します。
1. 証明書を右クリックして [すべてのタスク]-> [秘密キーの管理...] を選択します。 オプション
1. [アクセス許可] ダイアログで、[オプションの追加] を選択します。 [ユーザーの選択] ダイアログで、「NT Service\ gcahostservice」と入力して、[OK] をクリックします。 [名前の確認] ボタンをクリックしないでください。
1. [アクセス許可] ダイアログボックスで [ok] をクリックします。 エージェントコンピューターが、証明書を使用してトークンを生成するように構成されました。
