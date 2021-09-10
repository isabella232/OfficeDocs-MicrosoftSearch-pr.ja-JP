---
title: オンプレミス エージェント
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: On-prem Agent
ms.openlocfilehash: 9994b84c8db05b6b269edb6f5b6f463ab8da1529
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973563"
---
# <a name="microsoft-graph-connector-agent"></a>Microsoft Graph コネクタ エージェント

オンプレム コネクタを使用するには *、Microsoft Graphエージェント ソフトウェアをインストールする必要* があります。 これにより、オンプレミスのデータとコネクタ API 間の安全なデータ転送が可能です。 この記事では、エージェントのインストールと構成についてガイドします。

## <a name="installation"></a>インストール

インストール ウィザードを使用して、Graphコネクタ エージェントの最新バージョンをダウンロードし、 [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) ソフトウェアをインストールします。 以下で説明するコンピューターの推奨構成を使用して、ソフトウェアは最大 3 つの接続を処理できます。 それ以降の接続では、エージェント上のすべての接続のパフォーマンスが低下する可能性があります。

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

>[!NOTE]
>プロキシ認証はサポートされていません。 環境に認証が必要なプロキシがある場合は、コネクタ エージェントがプロキシをバイパスできます。

## <a name="create-and-configure-an-app-for-the-agent"></a>エージェント用のアプリを作成および構成する  

最初にサインインし、アカウントに必要な最小特権が検索管理者である点に注意してください。 その後、エージェントから認証の詳細を入力する要求が表示されます。 以下の手順を使用してアプリを作成し、必要な認証の詳細を生成します。

### <a name="create-an-app"></a>アプリを作成する

1. Azure portal に [移動し](https://portal.azure.com) 、テナントの管理者資格情報でサインインします。

2. ナビゲーション ウィンドウから **[Azure Active Directory**  ->  **登録**] に移動し、[新規登録]**を選択します**。

3. アプリの名前を指定し、[登録] を **選択します**。

4. アプリケーション (クライアント) ID をメモします。

5. ナビゲーション **ウィンドウから API アクセス許可** を開き、[アクセス許可の **追加] を選択します**。

6. [Microsoft **Graph] を選択** し、[**アプリケーションのアクセス許可] を選択します**。

7. アクセス許可から "ExternalItem.ReadWrite.All" と "Directory.Read.All" を検索し、[アクセス許可の追加 **] を選択します**。

8. **[TenantName] の [管理者の同意を許可する] を選択し、[** はい] を選択して確認 **します**。

9. アクセス許可が "許可された" 状態にあるか確認します。

    :::image type="content" alt-text="右側の列に緑で付与されたアクセス許可を示します。" source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

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
2. アップロード Azure portal に証明書を追加する
3. 証明書をエージェントに割り当てる

##### <a name="step-1-get-a-certificate"></a>手順 1: 証明書を取得する

以下のスクリプトを使用して、自己署名証明書を生成できます。 組織は自己署名証明書を許可しない場合があります。 その場合は、この情報を使用して要件を理解し、組織のポリシーに従って証明書を取得します。

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>手順 2: azure portal アップロード証明書を削除する

1. アプリケーションを開き、左側のウィンドウから [証明書とシークレット] セクションに移動します。

2. [証明書 **アップロード選択し**、.cer ファイルをアップロードします。

3. アプリ **の登録を開** き、 **ナビゲーション ウィンドウから [** 証明書とシークレット] を選択します。 証明書の拇印をコピーします。

:::image type="content" alt-text="左側のウィンドウで [証明書とシークレット] が選択されている場合の拇印証明書の一覧。" source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>手順 3: 証明書をエージェントに割り当てる

サンプル スクリプトを使用して証明書を生成した場合、PFX ファイルはスクリプトで識別された場所で見つけることができます。

1. 証明書 pfx ファイルをエージェント コンピューターにダウンロードします。

2. pfx ファイルをダブルクリックして、証明書のインストール ダイアログを起動します。

3. 証明書 **のインストール中に** ストアの場所として [ローカル コンピューター] を選択します。

4. 証明書をインストールした後、[コンピューター証明書の **管理]** を開きます。スタート メニュー。

5. [個人証明書] で新しくインストール **された証明書を**  >  **選択します**。

6. 証明書を右クリックし、[すべてのタスクの **プライベート キー** の  >  **管理] オプションを選択** します。

7. [アクセス許可] ダイアログで、[追加] オプションを選択します。 新しいウィンドウがポップアップします。 [場所] オプションを選択します。 表示されている場所の一覧からエージェントがインストールされているコンピューターを選択し **、[OK] をクリックします**。

8. ユーザー選択ダイアログで、NT **Service\GcaHostService と** 書き込み **、[OK] をクリックします**。 [名前の確認] **ボタンをクリック** しない。

9. [アクセス許可] ダイアログで [ok] をクリックします。 エージェント コンピューターが、証明書を使用してトークンを生成するようにエージェントが構成されました。

## <a name="troubleshooting"></a>トラブルシューティング

### <a name="installation-failure"></a>インストールエラー

インストールに失敗した場合は、msiexec/i "msi >\GcaInstaller.msi への < パス" /L*V "< 宛先パス >\install.log" を実行してインストール ログを確認します。 エラーが解決できない場合は、ログを使用して MicrosoftGraphConnectorsFeedback@service.microsoft.com サポートにアクセスします。

### <a name="registration-failure"></a>登録エラー

"サインインに失敗しました" というエラーが表示され、構成アプリへのサインインが失敗した場合。 [サインイン] ボタンをクリックしてもう一度やり直してください。 ブラウザー認証が成功した後でも、services.msc を開き、GcaHostService が実行されていないか確認します。 起動していない場合は、手動で開始します。

"ログオンエラーが原因でサービスが開始しなかった"というエラーでサービスが開始されない場合は、仮想アカウント NT Service\GcaHostService にコンピューター上のサービスとしてログオンする権限があるかどうか確認します。 手順 [については、この](/windows/security/threat-protection/security-policy-settings/log-on-as-a-service) リンクを確認してください。 ローカル ポリシー\User Rights Assignment でユーザーまたはグループを追加するオプションがグレー表示されている場合、このアカウントを追加しようとしているユーザーには、このコンピューターに管理者特権が付与されていないか、これを上書きするグループ ポリシーが存在します。 ホスト サービスがサービスとしてログオンするには、グループ ポリシーを更新する必要があります。

### <a name="connection-failure"></a>接続エラー

指定されたユーザー名とパスワードが正しい場合でも、エラー 「ユーザー名/パスワードとデータ ソース パスを確認してください」というエラーとの接続の作成中に '接続のテスト' アクションが失敗した場合は、ユーザー アカウントに Graph コネクタ エージェントがインストールされているコンピューターに対する対話型ログオン権限を持っている必要があります。 ログオン権限を確認するには [、ログオン ポリシー管理に関](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management) するドキュメントを参照してください。 また、データ ソースとエージェント コンピューターが同じネットワーク上に接続されている必要があります。

"1011: Graph コネクタ エージェントに到達できない"または "オフライン" というエラーで接続が失敗した場合は、エージェントがインストールされているコンピューターにログインし、まだ実行されていない場合はエージェント アプリケーションを起動します。 接続が引き続き失敗する場合は、登録中にエージェントに提供された証明書またはクライアント シークレットが期限切れで、必要なアクセス許可を持っている必要があります。
