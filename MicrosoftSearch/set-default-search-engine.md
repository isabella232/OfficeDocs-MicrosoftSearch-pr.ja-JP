---
title: 既定の検索エンジンの設定
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Microsoft Search を使用して、会社の既定の検索エンジン Bing に設定する方法について説明します。
ms.openlocfilehash: a0798da94f4433bb754c71b9e0d00e09ba5a543b
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612531"
---
# <a name="set-default-search-engine"></a><span data-ttu-id="970f7-103">既定の検索エンジンの設定</span><span class="sxs-lookup"><span data-stu-id="970f7-103">Set default search engine</span></span>

<span data-ttu-id="970f7-104">既定のブラウザー、既定の検索エンジン、および既定のホーム ページを構成するがように、Microsoft 検索機能、複数の使用法をお勧めを見つけてより滑らかなエクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="970f7-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="970f7-105">組織の既定の検索エンジンを設定するのには以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="970f7-105">To set the default search engine for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="970f7-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="970f7-106">Internet Explorer</span></span>

### <a name="internet-explorer-11"></a><span data-ttu-id="970f7-107">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="970f7-107">Internet Explorer 11</span></span>

<span data-ttu-id="970f7-108">ユーザーはこのポリシーを設定した後検索プロバイダーを変更することになります。</span><span class="sxs-lookup"><span data-stu-id="970f7-108">Users will be able to change the search provider after this policy is set.</span></span>
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="970f7-109">1. GPO の設定を使用するローカル コンピューターを構成します。</span><span class="sxs-lookup"><span data-stu-id="970f7-109">1. Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="970f7-110">レジストリに次のテキストを貼り付ける (\*.reg) ファイルです。</span><span class="sxs-lookup"><span data-stu-id="970f7-110">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="970f7-111">Windows Registry Editor Version 5.00</span><span class="sxs-lookup"><span data-stu-id="970f7-111">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"SuggestionsURL_JSON"="https://business.ing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA"
"ShowSearchSuggestions"=dword:00000001
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="970f7-p101">作成されたファイルをダブルクリックし、ファイルをインポートする手順を実行します。次のダイアログ ボックスでインポートを成功させるが得られます。</span><span class="sxs-lookup"><span data-stu-id="970f7-p101">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![レジストリ エディターのインポートが成功したメッセージ](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="970f7-115">2. グループ ポリシー管理コンソール (gpmc.msc) を開くし、既存のポリシーを編集または新規に作成するのに切り替える</span><span class="sxs-lookup"><span data-stu-id="970f7-115">2. Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="970f7-116">**ユーザー Configuration\Policies\Preferences\Windows の設定**に移動します。</span><span class="sxs-lookup"><span data-stu-id="970f7-116">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="970f7-p102">**Registry\New**を右クリックし、[**レジストリ ウィザード**] を選択します。レジストリのブラウザーのウィンドウからは、**ローカル コンピューター**を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="970f7-p102">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="970f7-119">**します Explorer\SearchScopes**に移動します。</span><span class="sxs-lookup"><span data-stu-id="970f7-119">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="970f7-120">このキーから、DefaultScope を選択してください。</span><span class="sxs-lookup"><span data-stu-id="970f7-120">From this key, make sure to select DefaultScope.</span></span>
    
    ![レジストリのブラウザーで選択されている DefaultScope](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="970f7-p103">Bing とすべての値を除くすべてのパスをユーザー プロファイルのキーの下で、Microsoft Search の GUID を含むすべてのサブキーを確認します。その他の項目を選択するのには下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="970f7-p103">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![レジストリのブラウザーで選択されている値を追加](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="970f7-125">この構成を完了するには、[完了] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="970f7-125">Click Finish to complete this configuration.</span></span>
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="970f7-126">3. DefaultScope 検索が適用されるユーザーを得る可能性があります警告を解決するユーザーの基本設定を設定します。</span><span class="sxs-lookup"><span data-stu-id="970f7-126">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="970f7-127">この警告は仕様であり、プログラムの設定を変更しようとしてのユーザーに警告します。</span><span class="sxs-lookup"><span data-stu-id="970f7-127">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="970f7-128">同じ GPO 内では、 **Registry\New**を右クリックし、**レジストリ ウィザード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="970f7-128">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="970f7-129">**します Explorer\User の環境設定**に移動します。</span><span class="sxs-lookup"><span data-stu-id="970f7-129">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="970f7-130">**ユーザー設定**キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="970f7-130">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="970f7-131">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="970f7-131">Click **Finish**.</span></span>
    
5. <span data-ttu-id="970f7-p104">新しく作成されたオブジェクトをクリックします。右側のペインで、ユーザー設定オブジェクトをダブルクリックします。**を削除**し、保存**操作**を変更します。</span><span class="sxs-lookup"><span data-stu-id="970f7-p104">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
    
<span data-ttu-id="970f7-134">適切なドメインにリンクすることによって、結果の GPO を適用します。</span><span class="sxs-lookup"><span data-stu-id="970f7-134">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
  
## <a name="microsoft-edge"></a><span data-ttu-id="970f7-135">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="970f7-135">Microsoft Edge</span></span>

### <a name="windows-10-version-1703-or-later"></a><span data-ttu-id="970f7-136">Windows 10、1703 またはそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="970f7-136">Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="970f7-137">ユーザーはこのポリシーを設定した後検索プロバイダーを変更することになります。</span><span class="sxs-lookup"><span data-stu-id="970f7-137">Users will be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="970f7-138">さまざまなバージョンの Windows 用の最新の ADMX ファイルを[作成し、Windows のグループ ポリシーの管理用テンプレートの中央のストアを管理する方法](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="970f7-138">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="970f7-p105">GPMC 内でこのセクションで説明されている設定が見つからない場合は、適切な ADMX をダウンロードして、中央ストアにコピーします。詳細については、 [ADMX ファイルを使用して Gpo](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)を参照してください。コント ローラー上の中央のストアは、次の命名規則を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="970f7-p105">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="970f7-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="970f7-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="970f7-p106">各ドメイン コント ローラーを処理する別のフォルダーが表示されます。コマンド ・ プロンプトから ADMX ファイルをコピーするのには、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="970f7-p106">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="970f7-145">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーを編集または新規に作成するのに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="970f7-145">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="970f7-146">移動**&lt;コンピューターとユーザーの構成&gt;\Administrative Templates\Windows Components\Microsoft エッジ**。</span><span class="sxs-lookup"><span data-stu-id="970f7-146">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="970f7-147">**既定の検索エンジンの設定**をダブルクリックして、 **[有効**] に設定を入力してください。`https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="970f7-147">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="970f7-148">適切なドメインにリンクすることによって、結果の GPO を適用します。</span><span class="sxs-lookup"><span data-stu-id="970f7-148">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
## <a name="google-chrome"></a><span data-ttu-id="970f7-149">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="970f7-149">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="970f7-150">Windows XP SP2 またはそれ以降</span><span class="sxs-lookup"><span data-stu-id="970f7-150">Windows XP SP2 or later</span></span>

<span data-ttu-id="970f7-151">ユーザーはこのポリシーを設定した後検索プロバイダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="970f7-151">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="970f7-p107">クロムは、 [Google Chrome のエンタープライズのヘルプ](https://support.google.com/chrome/a/answer/187202)から ADMX ファイルの形式でダウンロードできるグループ ポリシー設定の独自のセットが付属しています。オペレーティング システム Windows Vista の場合/2008 またはそれ以降のサーバーがドメインの GPO を管理するために使用されると、クロムの設定で Windows XP SP2 またはそれ以降の処理、ADMX ファイルがこのパッケージで提供されています。</span><span class="sxs-lookup"><span data-stu-id="970f7-p107">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="970f7-p108">テンプレート ファイルをドメイン コント ローラーの ADMX ファイルの中央ストアにコピーします。詳細については、 [ADMX ファイルを使用して Gpo](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)を参照してください。コント ローラー上の中央のストアは、次の命名規則を含むフォルダーです。</span><span class="sxs-lookup"><span data-stu-id="970f7-p108">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="970f7-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="970f7-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="970f7-p109">各ドメイン コント ローラーを処理する別のフォルダーが表示されます。コマンド ・ プロンプトから ADMX ファイルをコピーするのには、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="970f7-p109">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="970f7-160">グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="970f7-160">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="970f7-161">両方のユーザーまたはコンピューターの構成の管理用テンプレート] セクションで次のフォルダーが表示されるかどうかを確認: Google Chrome と Google Chrome を既定の設定です。</span><span class="sxs-lookup"><span data-stu-id="970f7-161">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="970f7-162">最初のセクションの設定が固定されており、ローカルの管理者は、ブラウザーでは変更できません。</span><span class="sxs-lookup"><span data-stu-id="970f7-162">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="970f7-163">後者のポリシーのセクションの設定は、ブラウザーの設定でユーザーが変更できます。</span><span class="sxs-lookup"><span data-stu-id="970f7-163">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="970f7-164">**に移動\<コンピューター/ユーザー\> Templates\Google Chrome\Default の構成管理用テンプレートの検索プロバイダー**</span><span class="sxs-lookup"><span data-stu-id="970f7-164">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="970f7-165">、**既定の検索プロバイダーを有効にする**] をダブルクリックし、それが**有効**に設定します。</span><span class="sxs-lookup"><span data-stu-id="970f7-165">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="970f7-166">**既定の検索プロバイダーのアイコン**をダブルクリックして、 **[有効**] に設定し、入力`https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="970f7-166">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="970f7-167">**インスタントの検索プロバイダーの URL を既定値**をダブルクリックし、入力`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="970f7-167">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="970f7-168">**既定の検索プロバイダーの名前**をダブルクリックして、それが有効に設定および 'Microsoft は Bing の検索' を入力してください。</span><span class="sxs-lookup"><span data-stu-id="970f7-168">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="970f7-169">**既定の検索プロバイダーの検索の URL**をダブルクリックして、 **[有効**] に設定を入力してください。`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="970f7-169">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="970f7-170">**既定の検索プロバイダーの URL を提案する**をダブルクリックし、 **[有効**] に設定し、入力`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span><span class="sxs-lookup"><span data-stu-id="970f7-170">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="970f7-171">適切なドメインにリンクすることによって、結果の GPO を適用します。</span><span class="sxs-lookup"><span data-stu-id="970f7-171">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="970f7-p110">既定の検索エンジンを設定すると、ブラウザーのアドレス バーに Microsoft Search の検索候補機能が追加されます。現在、これだけのブックマークをサポートします。アドレス バーに入力するときは、パブリック web 提案上トップの 2 つのブックマーク候補が表示されます。</span><span class="sxs-lookup"><span data-stu-id="970f7-p110">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>