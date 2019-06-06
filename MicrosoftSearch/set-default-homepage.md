---
title: 既定のホーム ページの設定
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
ROBOTS: NOINDEX
description: Microsoft Search を使用して、会社の既定のホーム ページとして Bing を設定する方法について説明します。
ms.openlocfilehash: 457202ba8dbebf59c5ef6a4630aea98304b9acdb
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727998"
---
# <a name="set-default-homepage"></a><span data-ttu-id="c6bc8-103">既定のホーム ページの設定</span><span class="sxs-lookup"><span data-stu-id="c6bc8-103">Set default homepage</span></span>

<span data-ttu-id="c6bc8-104">既定のブラウザー、検索エンジン、ホーム ページを構成すると、ユーザーが Microsoft Search 機能を把握したり、使用を促進したり、円滑なエクスペリエンスを提供したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="c6bc8-105">組織の既定のホーム ページを設定するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="c6bc8-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="c6bc8-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="c6bc8-107">Internet Explorer 5.0 以降</span><span class="sxs-lookup"><span data-stu-id="c6bc8-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="c6bc8-108">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="c6bc8-109">**[ユーザーの構成]、[基本設定]、[コントロール パネルの設定]、[インターネットの設定]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="c6bc8-110">**[インターネットの設定]** を右クリックして、**[Internet Explorer 10]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c6bc8-111">Internet Explorer 11 には Internet Explorer 10 と同じ設定が適用されるため、Internet Explorer 11 に適用するオプションは Internet Explorer 10 で選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="c6bc8-p101">赤い下線が引かれた設定はターゲット マシンで構成されていていないことを意味し、緑色の下線が引かれた設定はターゲット マシンで構成されていることを意味します。下線を変更するには、次のファンクション キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="c6bc8-114">F5 キー: 現在のタブのすべての設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="c6bc8-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="c6bc8-115">F6 キー: 現在選択されている設定を有効にする</span><span class="sxs-lookup"><span data-stu-id="c6bc8-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="c6bc8-116">F7 キー: 現在選択されている設定を無効にする</span><span class="sxs-lookup"><span data-stu-id="c6bc8-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="c6bc8-117">F8 キー: 現在のタブのすべての設定を無効にする</span><span class="sxs-lookup"><span data-stu-id="c6bc8-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="c6bc8-p102">**F8** キーを押して、構成を行う前にすべての設定を無効にします。画面は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Internet Explorer 10 プロパティのダイアログ](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="c6bc8-121">ホーム ページの設定で **F6** キーを押して、「`https://www.bing.com/business?form=BFBSPR`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="c6bc8-122">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c6bc8-123">ユーザーは、このポリシーを設定後にホーム ページを変更できます。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="c6bc8-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c6bc8-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="c6bc8-125">Windows 10 バージョン 1511 以降</span><span class="sxs-lookup"><span data-stu-id="c6bc8-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="c6bc8-126">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="c6bc8-127">**[管理用テンプレート]、[Windows コンポーネント]、[Microsoft Edge]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="c6bc8-128">**[スタート ページを構成する]** をダブルクリックして **[Enabled (有効)]** に設定し、「`https://www.bing.com/business`」と入力します</span><span class="sxs-lookup"><span data-stu-id="c6bc8-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="c6bc8-129">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="c6bc8-130">ユーザーは、このポリシーを設定後に検索プロバイダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="c6bc8-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="c6bc8-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="c6bc8-132">Windows XP SP2 以降</span><span class="sxs-lookup"><span data-stu-id="c6bc8-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="c6bc8-133">異なるバージョンの Windows に関する ADMX ファイルと最新の ADMX ファイルの管理方法を記載した Windows サポート記事については、[Microsoft サポート](https://support.microsoft.com/ja-JP/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="c6bc8-134">また、最新の Google ポリシー ファイルについては [Google Chrome エンタープライズ ヘルプ](https://support.google.com/chrome/a/answer/187202)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="c6bc8-p103">このセクションに示されている設定が GPMC 内に見つからない場合、適切な ADMX をダウンロードし、[中央ストア](https://docs.microsoft.com/ja-JP/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)にコピーします。コントローラーの中央ストアは 1 つのフォルダーで、以下の名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="c6bc8-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="c6bc8-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="c6bc8-p104">コントローラーが処理するドメインごとに異なるフォルダーが必要です。以下のコマンドを使用すると、コマンド プロンプトから ADMX ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="c6bc8-140">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="c6bc8-141">*[ユーザーの構成] と [コンピューターの構成]* の両方の **[管理用テンプレート]** セクションに [Google Chrome] フォルダーと [Google Chrome - 既定の設定] フォルダー (ユーザーによる上書き可能) が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="c6bc8-142">最初のセクションの設定は固定されているため、ローカル管理者は設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="c6bc8-p105">ポリシーの後半のセクションの設定は、ユーザーがブラウザーの設定で変更できます。ユーザーが既定の設定を上書き可能かどうかを決定する必要があります。次の手順で、組織のポリシーとニーズに対応するフォルダーの設定を変更します。以下の手順では、既定で [Google Chrome - 既定の設定] を使用します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="c6bc8-147">**&lt;[コンピューターの構成] または [ユーザーの構成]&gt;、[管理用テンプレート]、[Google Chrome - 既定の設定]、[ホーム ページ]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="c6bc8-148">**[Use New Tab Page as homepage (新しいタブ ページをホーム ページとして使用する)]** をダブルクリックして、**[Enabled (有効)]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="c6bc8-149">**&lt;[コンピューターの構成] または [ユーザーの構成]&gt;、[管理用テンプレート]、[Google Chrome - 既定の設定]、[新しいタブ ページ]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="c6bc8-150">**[Configure the New Tab Page URL (新しいタブ ページを URL として構成する)]** をダブルクリックして、**[Enabled (有効)]** に設定し、「`https://www.bing.com/business?form=BFBSPR`」と入力します</span><span class="sxs-lookup"><span data-stu-id="c6bc8-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="c6bc8-151">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="c6bc8-152">ユーザーは、このポリシーを設定後にホーム ページを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c6bc8-152">Users will be able to change the home page after this policy is set.</span></span>