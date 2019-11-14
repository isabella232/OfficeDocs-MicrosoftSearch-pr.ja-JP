---
title: Microsoft Search のファイル共有コネクタ
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用のファイル共有コネクタを設定します。
ms.openlocfilehash: 9791ee3460eb174fd7a478baa6a9beb45f1b1aab
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2019
ms.locfileid: "38310718"
---
# <a name="file-share-connector"></a><span data-ttu-id="e0a8e-103">ファイル共有コネクタ</span><span class="sxs-lookup"><span data-stu-id="e0a8e-103">File share connector</span></span>

<span data-ttu-id="e0a8e-104">ファイル共有コネクタを使用すると、組織内のユーザーはオンプレミスのファイル共有を検索できます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-104">With the File share connector, users in your organization can search on-premises file shares.</span></span> <span data-ttu-id="e0a8e-105">これらの共有からの検索結果は、SharePoint および Microsoft OneDrive for Business からの結果とマージされます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-105">The search results from these shares merge with the results from SharePoint and Microsoft OneDrive for Business.</span></span>

<span data-ttu-id="e0a8e-106">この記事は、Microsoft 365 管理者またはファイル共有コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a File share connector.</span></span> <span data-ttu-id="e0a8e-107">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-a-data-gateway"></a><span data-ttu-id="e0a8e-108">Data gateway をインストールする</span><span class="sxs-lookup"><span data-stu-id="e0a8e-108">Install a data gateway</span></span>
<span data-ttu-id="e0a8e-109">サードパーティのデータにアクセスするためには、Microsoft Power BI ゲートウェイをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-109">In order to access your third-party data, you must install and configure a Microsoft Power BI gateway.</span></span> <span data-ttu-id="e0a8e-110">詳細について[は、「オンプレミスゲートウェイをインストール](https://docs.microsoft.com/data-integration/gateway/service-gateway-install)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-110">See [Install an on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) to learn more.</span></span>  

## <a name="content-requirements"></a><span data-ttu-id="e0a8e-111">コンテンツの要件</span><span class="sxs-lookup"><span data-stu-id="e0a8e-111">Content requirements</span></span>
<span data-ttu-id="e0a8e-112">**ファイルの種類**。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-112">**File types**.</span></span> <span data-ttu-id="e0a8e-113">これらの形式のファイルのみにインデックスを作成して検索できます。 DOC、.DOCM、.DOCX、ドット、.DOTX、EML、GIF、HTML、JPEG、.MHT、MHTML、MSG、NWS、OBD、OBD、ODP、XLB、PPT、PPTM、.PPTX、TXT、、XLC、.XLSB、XLS、.XLSX、、XLXM、XML、XPS、および ZIP。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-113">Only files in these formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="e0a8e-114">これらの書式のテキストの内容のみがインデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-114">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="e0a8e-115">すべてのマルチメディアコンテンツは無視されます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-115">All multimedia content is ignored.</span></span>
 
<span data-ttu-id="e0a8e-116">**ファイルサイズの制限**。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-116">**File size limits**.</span></span> <span data-ttu-id="e0a8e-117">サポートされているファイルの最大サイズは 100 MB です。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="e0a8e-118">100 MB を超えるファイルはインデックス作成からスキップされます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-118">Files that exceed 100 MB are skipped from indexing.</span></span> <span data-ttu-id="e0a8e-119">処理後の最大サイズ制限は 4 MB です。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="e0a8e-120">ファイルのサイズが 4 MB に達すると、処理は停止します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="e0a8e-121">そのため、ファイル内に存在する語句が検索に使用できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-121">As a result, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="e0a8e-122">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="e0a8e-122">Connect to a data source</span></span>
<span data-ttu-id="e0a8e-123">[**データソースへの接続**] ページで、[**ファイル共有**] を選択し、名前、接続 ID、および説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-123">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="e0a8e-124">次のページで、ファイル共有へのパスを指定し、以前にインストールしたゲートウェイを選択します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-124">In the next page, provide the path to the file share and select your previously installed gateway.</span></span> <span data-ttu-id="e0a8e-125">共有内のすべてのファイルに対する読み取りアクセス権を持つ Windows ユーザーアカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-125">Enter the credentials for a Windows user account with read access to all the files in the share.</span></span> <span data-ttu-id="e0a8e-126">残りの設定に進み、接続を公開します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-126">Go through the rest of the settings and publish the connection.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="e0a8e-127">更新スケジュールを設定する</span><span class="sxs-lookup"><span data-stu-id="e0a8e-127">Set the refresh schedule</span></span>
<span data-ttu-id="e0a8e-128">推奨される既定の更新スケジュール間隔は15分ですが、希望する別の間隔に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-128">The recommended default refresh schedule interval is 15 minutes, but you can change it to another interval that you prefer.</span></span>

## <a name="set-up-your-search-results-page"></a><span data-ttu-id="e0a8e-129">検索結果ページを設定する</span><span class="sxs-lookup"><span data-stu-id="e0a8e-129">Set up your search results page</span></span>
<span data-ttu-id="e0a8e-130">[**すべて**] タブおよび [**ファイル**] タブに異なるファイル接続の結果を表示するには、SharePoint 検索エンジンの結果ページを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-130">To display different file connection results in the **All** and **Files** tabs, you need to set up a SharePoint search engine results page:</span></span>
- <span data-ttu-id="e0a8e-131">[**すべて**] の表には、ファイル接続、sharepoint ファイル、OneDrive ファイル、および SharePoint サイトからの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-131">The **All** table shows combined results from your file connections, SharePoint files, OneDrive files, and SharePoint sites.</span></span> 
- <span data-ttu-id="e0a8e-132">[**ファイル**(縦)] には、接続、SharePoint、および OneDrive からのすべてのファイル結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-132">The **Files** vertical shows all file results from your connections, SharePoint, and OneDrive.</span></span>
<span data-ttu-id="e0a8e-133">ファイル接続の結果は、[**すべて**の業種] および [**ファイル**] の両方の既存の結果に追加されます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-133">Results from file connections are added to already existing results in both the **All** and **Files** verticals.</span></span>

<span data-ttu-id="e0a8e-134">検索結果ページを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-134">To set up your search results page, take these steps:</span></span>
1. <span data-ttu-id="e0a8e-135">モダン検索ページを使用して SharePoint サイトコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-135">Create a SharePoint site collection with a modern search page.</span></span>

2. <span data-ttu-id="e0a8e-136">[SharePoint Online 管理シェル](https://www.microsoft.com/download/details.aspx?id=35588)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-136">Install a [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

3. <span data-ttu-id="e0a8e-137">SharePoint Online 管理シェルを管理者として開き、に`C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`ある**Microsoft sharepoint. .dll**モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-137">Open SharePoint Online Management Shell as an administrator and import the **Microsoft.SharePoint.Client.dll** module present at `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span></span>

> [!NOTE]
> <span data-ttu-id="e0a8e-138">このパスは、すべてのユーザーに対して同じであるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-138">This path might not be the same for all users.</span></span>

<span data-ttu-id="e0a8e-139">モジュールをインポートするには、SharePoint Online 管理シェルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-139">To import the module, run this command in SharePoint Online Management Shell:</span></span>
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. <span data-ttu-id="e0a8e-140">ここで、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-140">Now run this script:</span></span>
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

5. <span data-ttu-id="e0a8e-141">[組織名]、[ユーザー名]、[パスワード]、[サイトの URL] など、必要な値を PowerShell に入力します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-141">Enter the required values in PowerShell, such as organization name, username, password, and site URL.</span></span> <span data-ttu-id="e0a8e-142">**たとえば**、管理者の資格情報が`admin@a830edad9050849823J19081300.onmicrosoft.com`の場合、組織名は**a830edad9050849823J19081300**になり、サイトの URL は`https:// a830edad9050849823J19081300.sharepoint.com`になります。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-142">As an **example**, if your admin credentials are `admin@a830edad9050849823J19081300.onmicrosoft.com`, then your organization name is **a830edad9050849823J19081300**, and your site URL is `https:// a830edad9050849823J19081300.sharepoint.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="e0a8e-143">**Allproperties**の設定は、サイトコレクションレベル (Teams/Comms サイト) でのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-143">The **AllProperties** setting can only be done at a site collection level (Teams/Comms site).</span></span>

6. <span data-ttu-id="e0a8e-144">これで、インデックスが作成されたファイルを検索し、結果を [**すべて**] タブと [**ファイル**] タブの両方に表示できます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-144">Now you can search for indexed files and see results in both the **All** and **Files** tabs.</span></span>

## <a name="search-for-file-share-content-in-the-search-results-page"></a><span data-ttu-id="e0a8e-145">検索結果ページでファイル共有コンテンツを検索する</span><span class="sxs-lookup"><span data-stu-id="e0a8e-145">Search for file share content in the search results page</span></span>
<span data-ttu-id="e0a8e-146">インデックスが作成されたコンテンツを検索するには、テストテナントの SharePoint ホームページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-146">To search for indexed content, go to the SharePoint home page of your test tenant.</span></span> <span data-ttu-id="e0a8e-147">結果は [**すべて**] タブおよび [**ファイル**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-147">Results will be displayed in the **All** and **Files** tabs.</span></span>

<span data-ttu-id="e0a8e-148">ブラウザーの制限により、ファイルの結果を選択して、ローカルファイル共有検索からファイルを表示または開くことができません。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-148">Because of browser restrictions, you can't select a file result to view or open files from local file share searches.</span></span> <span data-ttu-id="e0a8e-149">これらのファイルを開くには、ファイルの結果のリンクをコピーして、システムのブラウザーのアドレスバーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-149">To open these files, copy the file result's link and paste it into the address bar of your system's browser.</span></span> <span data-ttu-id="e0a8e-150">Windows の場合は、エクスプローラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-150">For Windows, use Windows Explorer.</span></span> <span data-ttu-id="e0a8e-151">その後、システムでファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-151">Then you can open the file on your system.</span></span>

![[リンクのコピー] ダイアログボックスを開いた SharePoint 検索。](media/fileshare-search.png)

## <a name="troubleshooting"></a><span data-ttu-id="e0a8e-153">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e0a8e-153">Troubleshooting</span></span>
<span data-ttu-id="e0a8e-154">接続で重大な問題が発生した場合は、その状態が [**失敗**] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-154">If something is critically wrong with a connection, its status shows as **failed**.</span></span> <span data-ttu-id="e0a8e-155">3種類のエラーについての詳細を確認するには、[**エラーの詳細**] ページに移動し、失敗している接続を選択します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-155">To get more information on the three types of errors, go to the **error details** page and select the failing connection.</span></span> <span data-ttu-id="e0a8e-156">詳細については[、「コネクタの管理](manage-connector.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-156">See [Manage your connector](manage-connector.md) to learn more.</span></span>
1. <span data-ttu-id="e0a8e-157">**ゲートウェイに到達できません (エラーコード:11)**。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-157">**Gateway not reachable (error code: 11)**.</span></span> <span data-ttu-id="e0a8e-158">接続のゲートウェイコンピューターがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-158">The gateway machine for the connection is down.</span></span> <span data-ttu-id="e0a8e-159">ゲートウェイコンピューターで Microsoft Power BI プロセスが実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-159">Verify if the Microsoft Power BI process runs on the gateway machine.</span></span>
2. <span data-ttu-id="e0a8e-160">**認証エラー (エラーコード:12)**。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-160">**Authentication error (error code: 12)**.</span></span> <span data-ttu-id="e0a8e-161">接続の作成に使用された資格情報が有効期限切れになっているか、無効になっています。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-161">The credentials that were used for creating the connection expired or are no longer valid.</span></span> <span data-ttu-id="e0a8e-162">このエラーを解決するには、有効な資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-162">To resolve this error, enter valid credentials.</span></span>
3. <span data-ttu-id="e0a8e-163">**内部エラー (エラーコード:11 または12以外のもの)**。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-163">**Internal error (error code: anything other than 11 or 12)**.</span></span> <span data-ttu-id="e0a8e-164">コネクタインフラストラクチャにエラーがあります。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-164">There's an error in the connector infrastructure.</span></span> <span data-ttu-id="e0a8e-165">これらのエラーを報告する方法については、[フィードバック](connectors-feedback.md)記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-165">See the [Feedback](connectors-feedback.md) article to find out how to report these errors.</span></span>

## <a name="limitations"></a><span data-ttu-id="e0a8e-166">制限事項</span><span class="sxs-lookup"><span data-stu-id="e0a8e-166">Limitations</span></span>
<span data-ttu-id="e0a8e-167">ファイル共有コネクタには、次のようなプレビューリリースの制限があります。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-167">The File share connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="e0a8e-168">カスタムプロパティを持つファイルではなく、固定プロパティを持つファイルのみをインデックス作成できます。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-168">You can only index files with fixed properties, not files with custom properties.</span></span>
* <span data-ttu-id="e0a8e-169">ファイル共有アクセス制御リスト (Acl) は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-169">File share Access Control Lists (ACLs) aren't currently supported.</span></span> <span data-ttu-id="e0a8e-170">ファイル NTFS Acl のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-170">Only file NTFS ACLs are supported.</span></span>
* <span data-ttu-id="e0a8e-171">外部 id はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-171">External identities aren't supported.</span></span> <span data-ttu-id="e0a8e-172">Azure Active Directory の id にマップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0a8e-172">They must be mapped to Azure Active Directory identities.</span></span>
