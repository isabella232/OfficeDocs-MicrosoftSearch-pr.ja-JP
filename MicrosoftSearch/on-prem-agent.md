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
ms.openlocfilehash: 5134c0c4459f9d38825451f274e67469956756d2
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508807"
---
# <a name="graph-connector-agent"></a>グラフ コネクタ エージェント

On-prem Graph コネクタを使用するには、Graph コネクタ エージェント *ソフトウェアをインストールする必要* があります。 これにより、オンプレミスのデータと Graph コネクタ API 間の安全なデータ転送が可能です。 この記事では、エージェントのインストールと構成についてガイドします。

## <a name="installation"></a>インストール

Graph コネクタ エージェントの最新バージョンをここに [ダウンロードし](https://aka.ms/gcadownload) 、インストール ウィザードを使用してソフトウェアをインストールします。 以下で説明するコンピューターの推奨構成を使用して、ソフトウェアは最大 3 つの接続を処理できます。 それ以降の接続では、エージェント上のすべての接続のパフォーマンスが低下する可能性があります。

推奨される構成:

* Windows 10、Windows Server 2016 R2 以上
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 コア、3 GHz
* 16 GB RAM、2 GB のディスク領域
* 443 を介したデータ ソースとインターネットへのネットワーク アクセス

エージェントをインストールした後、組織のプロキシ サーバーまたはファイアウォールが不明なドメインへの通信をブロックする場合は、許可リストに以下のドメインを追加してください。

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline.</span>com
4. https://<span>gcs.office.</span>com/
5. https://<span>graph.microsoft.</span>com/


## <a name="create-and-configure-an-app-for-the-agent"></a>エージェント用のアプリを作成および構成する  

最初にサインインし、アカウントに必要な最小特権が検索管理者である点に注意してください。 その後、エージェントから認証の詳細を入力する要求が表示されます。 以下の手順を使用してアプリを作成し、必要な認証の詳細を生成します。

### <a name="create-an-app"></a>アプリを作成する

1. Azure portal に [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。
2. ナビゲーション ウィンドウから **Azure Active Directory**  ->  **アプリの登録** に移動し、[新規登録]**を選択します**。
3. アプリの名前を指定し、[登録] を **選択します**。
4. アプリケーション (クライアント) ID をメモします。
5. ナビゲーション **ウィンドウから API アクセス許可** を開き、[アクセス許可の **追加] を選択します**。
6. [Microsoft **Graph] を選択し** 、[ **アプリケーションのアクセス許可] を選択します**。
7. アクセス許可から "ExternalItem.ReadWrite.All" と "Directory.Read.All" を検索し、[アクセス許可の追加 **] を選択します**。
8. **[TenantName] の [管理者の同意を許可する] を選択し、[** はい] を選択して確認 **します**。
9. アクセス許可が "許可された" 状態にあるか確認します。
     ![右側の列に緑で付与されたアクセス許可を示します。](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>認証を構成する

認証の詳細は、クライアント シークレットまたは証明書を使用して提供できます。 選択した手順に従います。

#### <a name="configuring-the-client-secret-for-authentication"></a>認証用にクライアント シークレットを構成する

1. Azure portal に [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。
2. ナビゲーション **ウィンドウから [アプリ** の登録] を開き、適切なアプリに移動します。 [管理 **] で**、[ **証明書とシークレット] を選択します**。
3. [ **新しいクライアント シークレット] を** 選択し、シークレットの有効期限を選択します。 生成されたシークレットをコピーし、再度表示しないので保存します。
4. このクライアント シークレットとアプリケーション ID を使用してエージェントを構成します。 エージェントの [名前] フィールド **に空白を** 使用することはできません。 英数字を使用できます。

#### <a name="using-a-certificate-for-authentication"></a>認証に証明書を使用する

証明書ベースの認証を使用するには、次の 3 つの簡単な手順があります。

1. 証明書を作成または取得する
1. 証明書を Azure portal にアップロードする
1. 証明書をエージェントに割り当てる

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
1. アプリ **の登録を開** き、 **ナビゲーション ウィンドウから [** 証明書とシークレット] を選択します。 証明書の拇印をコピーします。

![左側のウィンドウで [証明書とシークレット] が選択されている場合の thumbrint 証明書の一覧](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>手順 3: 証明書をエージェントに割り当てる

サンプル スクリプトを使用して証明書を生成した場合、PFX ファイルはスクリプトで識別された場所で見つけることができます。

1. 証明書 pfx ファイルをエージェント コンピューターにダウンロードします。
1. pfx ファイルをダブルクリックして、証明書のインストール ダイアログを起動します。
1. 証明書のインストール中にストアの場所として [ローカル コンピューター] を選択します。
1. 証明書をインストールした後、[スタート] メニューから [コンピューター証明書の管理] を開きます。
1. [個人用] - [証明書] で新しくインストール>選択します。
1. 証明書を右クリックし、[すべてのタスク] -> [プライベート キーの管理...] を選択します。 オプション
1. [アクセス許可] ダイアログで、[追加] オプションを選択します。 ユーザー選択ダイアログで、「NT Service\GcaHostService」と入力し、[OK] をクリックします。 [名前の確認] ボタンをクリックしない。
1. [アクセス許可] ダイアログで [ok] をクリックします。 エージェント コンピューターが、証明書を使用してトークンを生成するようにエージェントが構成されました。

## <a name="troubleshooting"></a>トラブルシューティング
1. エラー '1011: Graph コネクタ エージェントに到達できない、またはオフラインで接続が失敗した場合は、エージェントがインストールされているコンピューターにログインし、まだ実行されていない場合はエージェント アプリケーションを起動します。 接続が引き続き失敗する場合は、登録中にエージェントに提供された証明書またはクライアント シークレットが期限切れで、必要なアクセス許可を持っている必要があります。
