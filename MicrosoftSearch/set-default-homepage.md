---
title: 既定のホーム ページの設定
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
ROBOTS: NOINDEX
description: Microsoft Search を使用して、会社の既定のホーム ページとして Bing を設定する方法について説明します。
ms.openlocfilehash: 707b6fefe1bd3e096f758df92fedca28f3f1530a
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639831"
---
# <a name="make-bingcom-the-default-home-page"></a><span data-ttu-id="74d4b-103">Bing.com を既定のホーム ページにする</span><span class="sxs-lookup"><span data-stu-id="74d4b-103">Make Bing.com the default home page</span></span>

<span data-ttu-id="74d4b-104">この記事では、Bing.com を Microsoft Edge、Google Chrome、Internet Explorer ブラウザーの規定のホームページとして設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-104">This article explains how to set Bing.com as the default home page for Microsoft Edge, Google Chrome, and Internet Explorer browsers.</span></span> 
  
 
## <a name="microsoft-edge-on-windows-10-version-1511-or-later"></a><span data-ttu-id="74d4b-105">Windows 10 バージョン 1511 以降の Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="74d4b-105">Microsoft Edge on Windows 10, Version 1511 or later</span></span>

<span data-ttu-id="74d4b-106">ユーザーは、このポリシーを設定した後に変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="74d4b-106">Users won't be able to change the search provider after this policy is set.</span></span> 

1. <span data-ttu-id="74d4b-107">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="74d4b-107">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span> 
1. <span data-ttu-id="74d4b-108">**[管理用テンプレート]、[Windows コンポーネント]、[Microsoft Edge]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-108">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>    
1. <span data-ttu-id="74d4b-109">**[スタート ページを構成する]** をダブルクリックして **[Enabled (有効)]** に設定し、「`https://www.bing.com/business`」と入力します</span><span class="sxs-lookup"><span data-stu-id="74d4b-109">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
1.  <span data-ttu-id="74d4b-110">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-110">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="google-chrome-on-windows-xp-sp2-or-later"></a><span data-ttu-id="74d4b-111">Windows XP SP2 以降の Google Chrome</span><span class="sxs-lookup"><span data-stu-id="74d4b-111">Google Chrome on Windows XP SP2 or later</span></span>


<span data-ttu-id="74d4b-112">異なるバージョンの Windows に関する ADMX ファイルと最新の ADMX ファイルの管理方法を記載した Windows サポート記事については、[Microsoft サポート](https://support.microsoft.com/ja-JP/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="74d4b-112">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="74d4b-113">また、最新の Google ポリシー ファイルについては [Google Chrome エンタープライズ ヘルプ](https://support.google.com/chrome/a/answer/187202)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74d4b-113">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="74d4b-p101">このセクションに示されている設定が GPMC 内に見つからない場合、適切な ADMX をダウンロードし、[中央ストア](https://docs.microsoft.com/ja-JP/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)にコピーします。コントローラーの中央ストアは 1 つのフォルダーで、以下の名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-p101">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="74d4b-116">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="74d4b-116">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="74d4b-p102">コントローラーが処理するドメインごとに異なるフォルダーが必要です。以下のコマンドを使用すると、コマンド プロンプトから ADMX ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="74d4b-p102">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="74d4b-119">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="74d4b-119">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="74d4b-120">*[ユーザーの構成] と [コンピューターの構成]* の両方の **[管理用テンプレート]** セクションに [Google Chrome] フォルダーと [Google Chrome - 既定の設定] フォルダー (ユーザーによる上書き可能) が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-120">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
   - <span data-ttu-id="74d4b-121">最初のセクションの設定は固定されているため、ローカル管理者は設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="74d4b-121">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
   - <span data-ttu-id="74d4b-p103">ポリシーの後半のセクションの設定は、ユーザーがブラウザーの設定で変更できます。ユーザーが既定の設定を上書き可能かどうかを決定する必要があります。次の手順で、組織のポリシーとニーズに対応するフォルダーの設定を変更します。以下の手順では、既定で [Google Chrome - 既定の設定] を使用します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-p103">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>

1. <span data-ttu-id="74d4b-126">**&lt;[コンピューターの構成] または [ユーザーの構成]&gt;、[管理用テンプレート]、[Google Chrome - 既定の設定]、[ホーム ページ]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-126">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span> 
1. <span data-ttu-id="74d4b-127">**[Use New Tab Page as homepage (新しいタブ ページをホーム ページとして使用する)]** をダブルクリックして、**[Enabled (有効)]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-127">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span> 
1. <span data-ttu-id="74d4b-128">**&lt;[コンピューターの構成] または [ユーザーの構成]&gt;、[管理用テンプレート]、[Google Chrome - 既定の設定]、[新しいタブ ページ]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-128">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span> 
1. <span data-ttu-id="74d4b-129">**[Configure the New Tab Page URL (新しいタブ ページを URL として構成する)]** をダブルクリックして、**[Enabled (有効)]** に設定し、「`https://www.bing.com/business?form=BFBSPR`」と入力します</span><span class="sxs-lookup"><span data-stu-id="74d4b-129">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span> 
1. <span data-ttu-id="74d4b-130">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-130">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

## <a name="internet-explorer-50-or-later"></a><span data-ttu-id="74d4b-131">Internet Explorer 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="74d4b-131">Internet Explorer 5.0 or later</span></span>
<span data-ttu-id="74d4b-132">ユーザーは、このポリシーを設定後にホーム ページを変更できます。</span><span class="sxs-lookup"><span data-stu-id="74d4b-132">Users can still change the homepage after this policy is set.</span></span> 

1. <span data-ttu-id="74d4b-133">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="74d4b-133">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="74d4b-134">**[ユーザーの構成]、[基本設定]、[コントロール パネルの設定]、[インターネットの設定]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-134">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="74d4b-135">**[インターネットの設定]** を右クリックして、**[Internet Explorer 10]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-135">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="74d4b-136">Internet Explorer 11 には Internet Explorer 10 と同じ設定が適用されるため、Internet Explorer 11 に適用するオプションは Internet Explorer 10 で選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="74d4b-136">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="74d4b-p104">赤い下線が引かれた設定はターゲット マシンで構成されていていないことを意味し、緑色の下線が引かれた設定はターゲット マシンで構成されていることを意味します。下線を変更するには、次のファンクション キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-p104">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="74d4b-139">F5 キー: 現在のタブのすべての設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="74d4b-139">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="74d4b-140">F6 キー: 現在選択されている設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="74d4b-140">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="74d4b-141">F7 キー: 現在選択されている設定を無効にする</span><span class="sxs-lookup"><span data-stu-id="74d4b-141">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="74d4b-142">F8 キー: 現在のタブのすべての設定を無効にする</span><span class="sxs-lookup"><span data-stu-id="74d4b-142">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="74d4b-p105">**F8** キーを押して、構成を行う前にすべての設定を無効にします。画面は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="74d4b-p105">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Internet Explorer 10 プロパティのダイアログ](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="74d4b-146">ホーム ページの設定で **F6** キーを押して、「`https://www.bing.com/business?form=BFBSPR`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-146">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="74d4b-147">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="74d4b-147">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>