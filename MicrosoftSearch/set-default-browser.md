---
title: 既定のブラウザーを設定する
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Microsoft Search ユーザーの Microsoft Edge または Internet Explorer に既定のブラウザーを設定します。
ms.openlocfilehash: b99127411d070b37fe34a4f8468449f2354cb6be
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626938"
---
# <a name="make-microsoft-edge-the-default-browser"></a><span data-ttu-id="068de-103">Microsoft Edge を既定のブラウザーにする</span><span class="sxs-lookup"><span data-stu-id="068de-103">Make Microsoft Edge the default browser</span></span>
  
<span data-ttu-id="068de-104">Microsoft Search のエクスペリエンスを最善にするためには、Microsoft Edge を既定のブラウザーにします。</span><span class="sxs-lookup"><span data-stu-id="068de-104">To give your users the best experience with Microsoft Search, you can make Microsoft Edge the default browser.</span></span> <span data-ttu-id="068de-105">これにより、組織のユーザーの既定のブラウザーとして Microsoft Edge の設定のみを行えます。それでも個々のユーザーは、別のブラウザーを選択できます。</span><span class="sxs-lookup"><span data-stu-id="068de-105">This will only set Microsoft Edge as the default browser for users in your org, individual users can still select a different browser.</span></span>
  
  
## <a name="windows-8-and-later"></a><span data-ttu-id="068de-106">Windows 8 以降</span><span class="sxs-lookup"><span data-stu-id="068de-106">Windows 8 and later</span></span>

<span data-ttu-id="068de-107">以下の手順では、Windows 8 以降を実行しているコンピューター向けに、既定のブラウザーとして Microsoft Edge または Internet Explorer を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="068de-107">These instructions show you how to make Microsoft Edge or Internet Explorer as the default browser for computers running Windows 8 or later.</span></span> <span data-ttu-id="068de-108">ユーザーは、このポリシーの設定後にブラウザーを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="068de-108">Users will be able to change the browser after this policy is set.</span></span>
  
### <a name="step-1-create-the-default-associations-file"></a><span data-ttu-id="068de-109">手順 1: 既定の関連付けファイルの作成</span><span class="sxs-lookup"><span data-stu-id="068de-109">STEP 1: Create the default associations file</span></span>
<span data-ttu-id="068de-110">ドメイン コントローラーの SYSVOL フォルダーに既定の関連付けファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="068de-110">Create the default associations file in the SYSVOL folder of the domain controller.</span></span>

1. <span data-ttu-id="068de-111">管理者 PowerShell コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="068de-111">Open an administrative PowerShell console.</span></span>
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a><span data-ttu-id="068de-112">手順 2.</span><span class="sxs-lookup"><span data-stu-id="068de-112">STEP 2.</span></span> <span data-ttu-id="068de-113">既定の関連付けファイルの追加または編集</span><span class="sxs-lookup"><span data-stu-id="068de-113">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. <span data-ttu-id="068de-114">以下のエントリ (.htm、.html、http、https) を編集し、必要ない場合はその他のエントリを削除します。</span><span class="sxs-lookup"><span data-stu-id="068de-114">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
  - <span data-ttu-id="068de-115">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="068de-115">**Microsoft Edge**</span></span>
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="068de-116">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="068de-116">**Internet Explorer**</span></span>
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a><span data-ttu-id="068de-117">手順 3. </span><span class="sxs-lookup"><span data-stu-id="068de-117">Step 3.</span></span> <span data-ttu-id="068de-118">グループ ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="068de-118">Edit the Group Policy</span></span>

1. <span data-ttu-id="068de-119">**グループ ポリシー管理コンソール** (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="068de-119">Open **Group Policy Management Console** (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="068de-120">**[コンピューターの構成]、[管理用テンプレート]、[Windows コンポーネント]、[エクスプローラー]** と移動します。</span><span class="sxs-lookup"><span data-stu-id="068de-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**.</span></span>
1. <span data-ttu-id="068de-121">**[既定の関連付け構成ファイルを設定する]** をダブルクリックし、**[有効]** に設定して、AppAssoc.xml へのパス (例: %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) を入力します。設定を行った GPO を適切なドメインにリンクして適用します。</span><span class="sxs-lookup"><span data-stu-id="068de-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="windows-7"></a><span data-ttu-id="068de-122">Windows 7</span><span class="sxs-lookup"><span data-stu-id="068de-122">Windows 7</span></span>

1. <span data-ttu-id="068de-123">GPO を設定するのに使用するローカル マシンを構成します。</span><span class="sxs-lookup"><span data-stu-id="068de-123">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="068de-124">**[コントロール パネル]、[プログラム]、[既定のプログラム]、[既定のプログラムを設定する]** を開き、Internet Explorer を既定として設定します。</span><span class="sxs-lookup"><span data-stu-id="068de-124">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="068de-125">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="068de-125">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="068de-126">**[\<コンピューター/ユーザー\> の構成]、[ポリシー]、[基本設定]、[Windows の設定]** と移動します。</span><span class="sxs-lookup"><span data-stu-id="068de-126">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="068de-127">**[レジストリ]、[新規]** を右クリックし、**[レジストリ ウィザード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="068de-127">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="068de-128">[レジストリ ブラウザー] ウィンドウで、**[ローカル コンピューター]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="068de-128">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="068de-p105">**HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** に移動し、ProgId の値を選択します。次のような値になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="068de-p105">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![[文字列の編集] で ProgID 値を選択する](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="068de-p106">**HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** に移動し、ProgId の値を選択します。次のような値になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="068de-p106">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![[文字列の編集] で HTTPS の ProgID を選択する](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="068de-135">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="068de-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
