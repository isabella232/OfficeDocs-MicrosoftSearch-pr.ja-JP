---
title: セットの既定のブラウザー
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Microsoft の検索を使用して、会社の既定のブラウザーを構成する方法について説明します。
ms.openlocfilehash: 13a0a878b3288abeb7b07defdab839a158adc2ac
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379038"
---
# <a name="set-default-browser"></a><span data-ttu-id="c4c5d-103">セットの既定のブラウザー</span><span class="sxs-lookup"><span data-stu-id="c4c5d-103">Set default browser</span></span>

<span data-ttu-id="c4c5d-104">既定のブラウザー、既定の検索エンジン、および既定のホーム ページを構成するがように、Microsoft 検索機能、複数の使用法をお勧めを見つけてより滑らかなエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="c4c5d-105">組織の既定のブラウザーを設定するのには以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="c4c5d-106">Windows 8 以降</span><span class="sxs-lookup"><span data-stu-id="c4c5d-106">Windows 8 and above</span></span>

<span data-ttu-id="c4c5d-107">既定のブラウザーとして Internet Explorer または Microsoft のエッジを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="c4c5d-108">デフォルトの関連付けファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-108">Create default associations file</span></span>

1. <span data-ttu-id="c4c5d-109">管理の PowerShell コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="c4c5d-110">次の手順は、ドメイン コント ローラーの SYSVOL フォルダーの既定の関連付けのファイルを作成してください。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="c4c5d-111">追加または既定の関連付けのファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="c4c5d-112">(.Htm、.html、http、https) は、次のエントリを編集し、必要ない場合は、他のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="c4c5d-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="c4c5d-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="c4c5d-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="c4c5d-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="c4c5d-115">グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="c4c5d-116">**コンピューターの構成 \ 管理用テンプレート Components\File エクスプ ローラー**に移動します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="c4c5d-117">**既定の関連付けの構成ファイルの設定**] をダブルクリック、 **[有効**] に設定し、AppAssoc.xml へのパスを入力 (たとえば %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="c4c5d-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="c4c5d-118">適切なドメインにリンクすることによって、結果の GPO を適用します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="c4c5d-119">ユーザーはこのポリシーを設定した後にブラウザーを変更することになります。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="c4c5d-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="c4c5d-120">Windows 7</span></span>

1. <span data-ttu-id="c4c5d-121">GPO の設定を使用するローカル コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="c4c5d-122">**コントロール Panel\Programs\Default Programs\Set の既定のプログラム**を開くし、Internet Explorer を既定として設定します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="c4c5d-123">グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="c4c5d-124">移動**\<コンピューター/ユーザー\> Configuration\Policies\Preferences\Windows 設定**。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="c4c5d-125">**Registry\New**を右クリックし、[**レジストリ ウィザード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="c4c5d-126">レジストリのブラウザーのウィンドウからは、**ローカル コンピューター**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="c4c5d-p101">**HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**に移動し、ProgId の値を選択します。値は次のような外観を確認します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![ProgID の値を選択して [文字列の編集](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="c4c5d-p102">**HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**に移動し、ProgId の値を選択します。行います。 値が、いずれかのようになっていることを確認して下</span><span class="sxs-lookup"><span data-stu-id="c4c5d-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![編集文字列での HTTPS のプログラム Id を選択します](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="c4c5d-133">適切なドメインにリンクすることによって、結果の GPO を適用します。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="c4c5d-134">ユーザーはこのポリシーを設定した後にブラウザーを変更することになります。</span><span class="sxs-lookup"><span data-stu-id="c4c5d-134">Users will be able to change the browser after this policy is set.</span></span>