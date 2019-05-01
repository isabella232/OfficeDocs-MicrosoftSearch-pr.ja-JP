---
title: 既定のブラウザーの設定
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Microsoft Search を使用して、会社の既定のブラウザーを構成する方法について説明します。
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508999"
---
# <a name="set-default-browser"></a><span data-ttu-id="21a4e-103">既定のブラウザーの設定</span><span class="sxs-lookup"><span data-stu-id="21a4e-103">Set default browser</span></span>

<span data-ttu-id="21a4e-104">既定のブラウザー、検索エンジン、ホームページを構成すると、ユーザーが Microsoft Search 機能を把握したり、使用を促進したり、円滑なエクスペリエンスを提供したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="21a4e-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="21a4e-105">組織の既定のブラウザーを設定するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="21a4e-106">Windows 8 以上</span><span class="sxs-lookup"><span data-stu-id="21a4e-106">Windows 8 and above</span></span>

<span data-ttu-id="21a4e-107">Internet Explorer または Microsoft Edge を既定のブラウザーとして設定するには、以下のいずれかのステップを実行します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="21a4e-108">既定の関連付けファイルの作成</span><span class="sxs-lookup"><span data-stu-id="21a4e-108">Create default associations file</span></span>

1. <span data-ttu-id="21a4e-109">管理者 PowerShell コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="21a4e-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="21a4e-110">これらの手順では、ドメイン コントローラーの SYSVOL フォルダーに既定の関連付けファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="21a4e-111">既定の関連付けファイルの追加または編集</span><span class="sxs-lookup"><span data-stu-id="21a4e-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="21a4e-112">以下のエントリ (.htm、.html、http、https) を編集し、必要ない場合はその他のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="21a4e-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="21a4e-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="21a4e-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="21a4e-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="21a4e-115">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="21a4e-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="21a4e-116">**[コンピューターの構成]、[管理用テンプレート]、[Windows コンポーネント]、[エクスプローラー]** と移動します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="21a4e-117">**[既定の関連付け構成ファイルを設定する]** をダブルクリックして、**[有効]** に設定して、AppAssoc.xml へのパス (たとえば %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) を入力します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="21a4e-118">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="21a4e-119">ユーザーは、このポリシーの設定後にブラウザーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="21a4e-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="21a4e-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="21a4e-120">Windows 7</span></span>

1. <span data-ttu-id="21a4e-121">GPO を設定するのに使用するローカル マシンを構成します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="21a4e-122">**[コントロール パネル]、[プログラム]、[既定のプログラム]、[既定のプログラムを設定する]** を開き、Internet Explorer を既定として設定します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="21a4e-123">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="21a4e-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="21a4e-124">**[\<コンピューター/ユーザー\> の構成]、[ポリシー]、[基本設定]、[Windows の設定]** と移動します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="21a4e-125">**[レジストリ]、[新規]** を右クリックし、**[レジストリ ウィザード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="21a4e-126">[レジストリ ブラウザー] ウィンドウで、**[ローカル コンピューター]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="21a4e-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="21a4e-p101">**HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** に移動し、ProgId の値を選択します。次のような値になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![[文字列の編集] で ProgID 値を選択する](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="21a4e-p102">**HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** に移動し、ProgId の値を選択します。次のような値になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![[文字列の編集] で HTTPS の ProgID を選択する](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="21a4e-133">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="21a4e-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="21a4e-134">ユーザーは、このポリシーの設定後にブラウザーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="21a4e-134">Users will be able to change the browser after this policy is set.</span></span>