---
title: Microsoft Search のファイル共有コネクタ
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用のファイル共有コネクタを設定します。
ms.openlocfilehash: d5fbc1af2868ce7baa70017f617a9731340fb19a
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949907"
---
# <a name="file-share-connector"></a>ファイル共有コネクタ

ファイル共有コネクタを使用すると、組織内のユーザーはオンプレミスのファイル共有を検索できます。 これらの共有からの検索結果は、SharePoint および Microsoft OneDrive for Business からの結果とマージされます。

この記事は、Microsoft 365 管理者またはファイル共有コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

## <a name="install-a-data-gateway"></a>Data gateway をインストールする
サードパーティのデータにアクセスするためには、Microsoft Power BI ゲートウェイをインストールして構成する必要があります。 詳細については[、「Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) 」を参照してください。  

## <a name="connect-to-a-data-source"></a>データソースへの接続
[**データソースへの接続**] ページで、フォルダーを作成し、ファイル共有へのパスを指定します。 次に、以前にインストールしたゲートウェイを選択します。 共有内のすべてのファイルに対する**読み取りアクセス権**を持つ Windows ユーザーアカウントの資格情報を入力します。 その後、共有に存在するファイルを確認して、すべてのフェッチされたメタデータを表示できます。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する
ファイル共有コネクタは、**すべてのユーザー**に表示される検索アクセス許可のみをサポートします。 インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する
推奨される既定の更新スケジュール間隔は15分ですが、希望する別の間隔に変更することができます。

## <a name="set-up-your-search-results-page"></a>検索結果ページを設定する
[**すべて**] タブおよび [**ファイル**] タブに異なるファイル接続の結果を表示するには、SharePoint 検索エンジンの結果ページを設定する必要があります。
- [**すべて**] の表には、ファイル接続、sharepoint ファイル、OneDrive ファイル、および SharePoint サイトからの結果が表示されます。 
- [**ファイル**(縦)] には、接続、SharePoint、および OneDrive からのすべてのファイル結果が表示されます。
ファイル接続の結果は、[**すべて**の業種] および [**ファイル**] の両方の既存の結果に追加されます。

検索結果ページを設定するには、次の手順を実行します。
1. モダン検索ページを使用して SharePoint サイトコレクションを作成します。

2. [SharePoint Online 管理シェル](https://www.microsoft.com/download/details.aspx?id=35588)をインストールします。

3. SharePoint Online 管理シェルを管理者として開き、に`C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`ある**Microsoft sharepoint. .dll**モジュールをインポートします。

> [!NOTE]
> このパスは、すべてのユーザーに対して同じであるとは限りません。

モジュールをインポートするには、SharePoint Online 管理シェルで次のコマンドを実行します。
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. ここで、次のスクリプトを実行します。
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. [組織名]、[ユーザー名]、[パスワード]、[サイトの URL] など、必要な値を PowerShell に入力します。 **たとえば**、管理者の資格情報が`admin@a830edad9050849823J19081300.onmicrosoft.com`の場合、組織名は**a830edad9050849823J19081300**になり、サイトの URL は`https:// a830edad9050849823J19081300.sharepoint.com`になります。

> [!NOTE]
> **Allproperties**の設定は、サイトコレクションレベル (Teams/Comms サイト) でのみ実行できます。

6. これで、インデックスが作成されたファイルを検索し、結果を [**すべて**] タブと [**ファイル**] タブの両方に表示できます。

## <a name="search-for-file-share-content-in-the-search-results-page"></a>検索結果ページでファイル共有コンテンツを検索する
インデックスが作成されたコンテンツを検索するには、テストテナントの SharePoint ホームページに移動します。 結果は [**すべて**] タブおよび [**ファイル**] タブに表示されます。

ブラウザーの制限により、ファイルの結果を選択して、ローカルファイル共有検索からファイルを表示または開くことができません。 これらのファイルを開くには、ファイルの結果のリンクをコピーして、システムのブラウザーのアドレスバーに貼り付けます。 Windows の場合は、エクスプローラーを使用します。 その後、システムでファイルを開くことができます。

![[リンクのコピー] ダイアログボックスを開いた SharePoint 検索。](media/fileshare-search.png)

## <a name="troubleshooting"></a>トラブルシューティング
接続で重大な問題が発生した場合は、その状態が [**失敗**] と表示されます。 3種類のエラーについての詳細を確認するには、[**エラーの詳細**] ページに移動し、失敗している接続を選択します。 詳細については[、「コネクタの管理](manage-connector.md)」を参照してください。
1. **ゲートウェイに到達できません (エラーコード:11)**。 接続のゲートウェイコンピューターがダウンしています。 ゲートウェイコンピューターで Microsoft Power BI プロセスが実行されているかどうかを確認します。
2. **認証エラー (エラーコード:12)**。 接続の作成に使用された資格情報が有効期限切れになっているか、無効になっています。 このエラーを解決するには、有効な資格情報を入力します。
3. **内部エラー (エラーコード:11 または12以外のもの)**。 コネクタインフラストラクチャにエラーがあります。 これらのエラーを報告する方法については、[フィードバック](connectors-feedback.md)記事を参照してください。

## <a name="limitations"></a>制限事項
ファイル共有コネクタには、次のようなプレビューリリースの制限があります。
* カスタムプロパティを持つファイルではなく、固定プロパティを持つファイルのみをインデックス作成できます。
* ファイル共有アクセス制御リスト (Acl) は現在サポートされていません。
* 外部 id はサポートされていません。 Azure Active Directory の id にマップする必要があります。