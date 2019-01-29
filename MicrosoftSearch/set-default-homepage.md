---
title: 既定のホームページの設定
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
description: Bing を Microsoft の検索を使用して、会社の既定のホーム ページとして設定する方法について説明します。
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612491"
---
# <a name="set-default-homepage"></a><span data-ttu-id="73471-103">既定のホームページの設定</span><span class="sxs-lookup"><span data-stu-id="73471-103">Set default homepage</span></span>

<span data-ttu-id="73471-104">既定のブラウザー、既定の検索エンジン、および既定のホーム ページを構成するがように、Microsoft 検索機能、複数の使用法をお勧めを見つけてより滑らかなエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="73471-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="73471-105">組織の既定のホーム ページを設定するのには以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="73471-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="73471-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="73471-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="73471-107">5.0 またはそれ以降の Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="73471-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="73471-108">グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="73471-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="73471-109">**Configuration\Preferences\Control パネル]、[internet のユーザーの設定**に移動します。</span><span class="sxs-lookup"><span data-stu-id="73471-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="73471-110">**インターネットの設定**を右クリックし、 **Internet Explorer 10**を選択します。</span><span class="sxs-lookup"><span data-stu-id="73471-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="73471-111">Internet Explorer 11 に同じ設定を適用すると、11 の Internet Explorer の設定を適用するのには、Internet Explorer 10 のオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73471-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="73471-p101">赤い下線が表示されている設定は、ターゲット マシン上で緑色で下線付きで表示する設定が構成されている間、ターゲット ・ マシン上で構成されていません。下線を変更するには、以下のファンクション キーを使用します。</span><span class="sxs-lookup"><span data-stu-id="73471-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="73471-114">F5 - 現在のタブ上のすべての設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="73471-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="73471-115">F6 キーを押して、現在選択されている設定を有効にする-</span><span class="sxs-lookup"><span data-stu-id="73471-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="73471-116">F7: 現在選択されている設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="73471-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="73471-117">F8 キーの現在のタブ上のすべての設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="73471-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="73471-p102">何かを構成する前にすべての設定を無効にするのには、 **f8 キー**を押します。画面は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="73471-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![インターネット エクスプ ローラーの 10 のプロパティ] ダイアログ ボックス](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="73471-121">ホーム ページの設定に、 **f6 キー**を押すし、入力してください。`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="73471-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="73471-122">適切なドメインにリンクすることによって、結果の GPO を適用します。</span><span class="sxs-lookup"><span data-stu-id="73471-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="73471-123">ユーザーがこのポリシーの設定後、ホーム ページを変更できます。</span><span class="sxs-lookup"><span data-stu-id="73471-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="73471-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="73471-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="73471-125">1511 またはそれ以降のバージョンである Windows 10</span><span class="sxs-lookup"><span data-stu-id="73471-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="73471-126">グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="73471-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="73471-127">**管理用テンプレート \windows コンポーネント Components\Microsoft の端**に移動します。</span><span class="sxs-lookup"><span data-stu-id="73471-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="73471-128">**構成の開始ページ**をダブルクリックし、 **[有効**] に設定し、入力`https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="73471-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="73471-129">適切なドメインにリンクすることによって、結果の GPO を適用します。</span><span class="sxs-lookup"><span data-stu-id="73471-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="73471-130">ユーザーはこのポリシーを設定した後検索プロバイダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="73471-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="73471-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="73471-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="73471-132">Windows XP SP2 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="73471-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="73471-133">ADMX ファイルと異なるバージョンの Windows 用の最新の ADMX ファイルの管理に Windows のサポートの記事は、[マイクロソフトのサポートを](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)ご覧ください。</span><span class="sxs-lookup"><span data-stu-id="73471-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="73471-134">最新 Google ポリシー ファイル、 [Google Chrome のエンタープライズのヘルプ](https://support.google.com/chrome/a/answer/187202)で確認する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="73471-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="73471-p103">GPMC 内でこのセクションで説明する設定が見つからない場合は、適切な ADMX をダウンロードして、[中央ストア](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)にコピーします。コント ローラー上の中央のストアは、次の命名規則を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="73471-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="73471-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="73471-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="73471-p104">各ドメイン コント ローラー ハンドルに別のフォルダーが表示されます。コマンド ・ プロンプトから ADMX ファイルをコピーするのには、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="73471-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="73471-140">グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="73471-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="73471-141">両方の*ユーザーまたはコンピューターの構成*の**管理用テンプレート**] セクションで次のフォルダーが表示されるかどうかを確認: Google Chrome と Google Chrome を既定の設定 (ユーザーは無視できます)。</span><span class="sxs-lookup"><span data-stu-id="73471-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="73471-142">最初のセクションの設定が固定されており、ローカルの管理者は、それらを変更するのにはできません。</span><span class="sxs-lookup"><span data-stu-id="73471-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="73471-p105">後者のポリシーのセクションの設定は、ブラウザーの設定でユーザーが変更できます。かどうか、ユーザーは、既定の設定をオーバーライドできますを決定する必要があります。次の手順で、組織のポリシーとニーズに対応するフォルダーの設定で変更します。次の手順は、Google のクロムの既定値として既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="73471-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="73471-147">移動**&lt;コンピューターとユーザーの構成&gt;\Administrative Templates\Google クロムのデフォルトの Settings\Home ページ**。</span><span class="sxs-lookup"><span data-stu-id="73471-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="73471-148">**ホーム ページに新しいタブ ページを使用して**をダブルクリックし、 **[有効**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="73471-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="73471-149">移動**&lt;コンピューターとユーザーの構成&gt;\Administrative Templates\Google クロム ・ Settings\New] タブの既定のページ**。</span><span class="sxs-lookup"><span data-stu-id="73471-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="73471-150">**構成新しいタブ ページの URL**] をダブルクリックし、 **[有効**] に設定し、入力`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="73471-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="73471-151">適切なドメインにリンクすることによって、結果の GPO を適用します。</span><span class="sxs-lookup"><span data-stu-id="73471-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="73471-152">ユーザーはこのポリシーを設定した後、ホーム ページを変更することになります。</span><span class="sxs-lookup"><span data-stu-id="73471-152">Users will be able to change the home page after this policy is set.</span></span>