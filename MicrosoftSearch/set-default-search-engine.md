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
description: Microsoft Search を使用して会社の既定の検索エンジンとして Bing を設定する方法について取り上げます。
ms.openlocfilehash: a0798da94f4433bb754c71b9e0d00e09ba5a543b
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508781"
---
# <a name="set-default-search-engine"></a><span data-ttu-id="14153-103">既定の検索エンジンの設定</span><span class="sxs-lookup"><span data-stu-id="14153-103">Set default search engine</span></span>

<span data-ttu-id="14153-104">既定のブラウザー、検索エンジン、ホームページを構成すると、ユーザーが Microsoft Search 機能を把握したり、使用を促進したり、円滑なエクスペリエンスを提供したりするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="14153-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="14153-105">組織の既定の検索エンジンを設定するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="14153-105">To set the default search engine for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="14153-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="14153-106">Internet Explorer</span></span>

### <a name="internet-explorer-11"></a><span data-ttu-id="14153-107">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="14153-107">Internet Explorer 11</span></span>

<span data-ttu-id="14153-108">ユーザーは、このポリシーを設定後に検索プロバイダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="14153-108">Users will be able to change the search provider after this policy is set.</span></span>
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="14153-109">1. GPO を設定するのに使用するローカル マシンを構成します</span><span class="sxs-lookup"><span data-stu-id="14153-109">1. Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="14153-110">以下のテキストを reg(\*.reg) ファイルに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="14153-110">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="14153-111">Windows レジストリ エディター バージョン 5.00</span><span class="sxs-lookup"><span data-stu-id="14153-111">Windows Registry Editor Version 5.00</span></span>
  
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
  
<span data-ttu-id="14153-p101">作成されたファイルをダブルクリックし、そのファイルをインポートするための手順を実行します。インポートが成功すると、以下のダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14153-p101">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![レジストリ エディターのインポート成功メッセージ](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="14153-115">2. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います</span><span class="sxs-lookup"><span data-stu-id="14153-115">2. Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="14153-116">**[ユーザーの構成]、[ポリシー]、[基本設定]、[Windows の設定]** と移動します。</span><span class="sxs-lookup"><span data-stu-id="14153-116">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="14153-p102">**[レジストリ]\[新規]** で右クリックし、**[レジストリ ウィザード]** を選択します。[レジストリ ブラウザー] ウィンドウで、**[ローカル コンピューター]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14153-p102">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="14153-119">**HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes** と移動します。</span><span class="sxs-lookup"><span data-stu-id="14153-119">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="14153-120">このキーで、[DefaultScope] が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14153-120">From this key, make sure to select DefaultScope.</span></span>
    
    ![[DefaultScope] が選択されている [レジストリ ブラウザー]](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="14153-p103">Bing における Microsoft Search の GUID が含まれるすべてのサブキーと、対象キーのすべての値 (ユーザー プロファイルのパス以外) を選択状態にします。下方向にスクロールして、他の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="14153-p103">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![他の値が選択されている [レジストリ ブラウザー]](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="14153-125">[終了] をクリックして、この構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="14153-125">Click Finish to complete this configuration.</span></span>
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="14153-126">3. User Preferences を設定して、DefaultScope 検索が実行される場合にユーザーが取得する可能性がある警告をなくします</span><span class="sxs-lookup"><span data-stu-id="14153-126">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="14153-127">この警告は仕様で、プログラムの設定変更が行われようとしていることをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="14153-127">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="14153-128">同じ GPO で **[レジストリ]\[新規]** を右クリックし、**[レジストリ ウィザード]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="14153-128">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="14153-129">**HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences** と移動します。</span><span class="sxs-lookup"><span data-stu-id="14153-129">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="14153-130">**User Preference** キーを選択します。</span><span class="sxs-lookup"><span data-stu-id="14153-130">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="14153-131">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14153-131">Click **Finish**.</span></span>
    
5. <span data-ttu-id="14153-p104">新しく作成されたオブジェクトをクリックします。右側のウィンドウで User Preferences オブジェクトをダブルクリックし、**[アクション]** を **[削除および保存]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="14153-p104">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
    
<span data-ttu-id="14153-134">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="14153-134">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
  
## <a name="microsoft-edge"></a><span data-ttu-id="14153-135">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="14153-135">Microsoft Edge</span></span>

### <a name="windows-10-version-1703-or-later"></a><span data-ttu-id="14153-136">Windows 10 バージョン 1703 以降</span><span class="sxs-lookup"><span data-stu-id="14153-136">Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="14153-137">ユーザーは、このポリシーを設定後に検索プロバイダーを変更できます。</span><span class="sxs-lookup"><span data-stu-id="14153-137">Users will be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="14153-138">各種バージョンの Windows の最新 ADMX ファイルについては、「[Windows でグループ ポリシー管理テンプレート用に中央ストアを作成および管理する方法](https://support.microsoft.com/ja-JP/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14153-138">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/ja-JP/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="14153-p105">このセクションに記述されている設定が GPMC 内に見つからない場合、適切な ADMX をダウンロードし、中央ストアにコピーします。詳しくは、「[ADMX ファイルを使用してドメイン ベースの GPO を編集する](https://docs.microsoft.com/ja-JP/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)」をご覧ください。コントローラーの中央ストアは 1 つのフォルダーで、以下の名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="14153-p105">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/ja-JP/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="14153-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="14153-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="14153-p106">コントローラーが処理するドメインごとに異なるフォルダーが必要です。以下のコマンドを使用すると、コマンド プロンプトから ADMX ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="14153-p106">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="14153-145">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="14153-145">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="14153-146">**&lt;[コンピューター/ユーザーの構成]&gt;、[管理用テンプレート]、[Windows コンポーネント]、[Microsoft Edge]** と移動します。</span><span class="sxs-lookup"><span data-stu-id="14153-146">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="14153-147">**[既定の検索エンジンの設定]** をダブルクリックし、**[有効]** に設定して `https://www.bing.com/sa/osd/bfb.xml` と入力します</span><span class="sxs-lookup"><span data-stu-id="14153-147">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="14153-148">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="14153-148">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
## <a name="google-chrome"></a><span data-ttu-id="14153-149">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="14153-149">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="14153-150">Windows XP SP2 以降</span><span class="sxs-lookup"><span data-stu-id="14153-150">Windows XP SP2 or later</span></span>

<span data-ttu-id="14153-151">ユーザーは、このポリシーを設定後に検索プロバイダーを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="14153-151">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="14153-p107">Chrome には独自の一連のグループ ポリシー設定が備わっていて、[Google Chrome Enterprise ヘルプ](https://support.google.com/chrome/a/answer/187202)から ADMX ファイル形式でダウンロードできます。Windows Vista/Server 2008 以降のオペレーティング システムを使用してドメインの GPO を管理している場合、このパッケージで提供される ADMX ファイルは Windows XP SP2 以降の Chrome 設定に対して有効です。</span><span class="sxs-lookup"><span data-stu-id="14153-p107">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="14153-p108">テンプレート ファイルを、ドメイン コントローラー上の ADMX ファイルの中央ストアにコピーします。詳しくは、「[ADMX ファイルを使用してドメイン ベースの GPO を編集する](https://docs.microsoft.com/ja-JP/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)」をご覧ください。コントローラーの中央ストアは 1 つのフォルダーで、以下の名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="14153-p108">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/ja-JP/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="14153-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="14153-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="14153-p109">コントローラーが処理するドメインごとに異なるフォルダーが必要です。以下のコマンドを使用すると、コマンド プロンプトから ADMX ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="14153-p109">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="14153-160">グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。</span><span class="sxs-lookup"><span data-stu-id="14153-160">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="14153-161">[ユーザーの構成]/[コンピューターの構成] の両方の [管理用テンプレート] セクションに [Google Chrome] フォルダーと [Google Chrome - 既定の設定] フォルダーが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="14153-161">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="14153-162">最初のセクションの設定は固定されているため、ローカル管理者はブラウザーで設定を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="14153-162">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="14153-163">ポリシーの後半のセクションの設定は、ブラウザー設定でユーザーが変更できます。</span><span class="sxs-lookup"><span data-stu-id="14153-163">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="14153-164">[**\<コンピューター/ユーザー\> の構成]、[管理用テンプレート]、[Google Chrome]、[既定の検索プロバイダー (Default search provider)]** と移動します</span><span class="sxs-lookup"><span data-stu-id="14153-164">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="14153-165">**[既定の検索プロバイダーを有効にする (Enable the default search provider)]** をダブルクリックし、**[有効]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="14153-165">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="14153-166">**[既定の検索プロバイダー (Default search provider)] アイコン**をダブルクリックし、**[有効]** に設定して、`https://www.bing.com/sa/simg/bb.ico` と入力します</span><span class="sxs-lookup"><span data-stu-id="14153-166">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="14153-167">**[既定の検索プロバイザー インスタンス URL (Default search provider instant URL)]** をダブルクリックし、`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR` と入力します</span><span class="sxs-lookup"><span data-stu-id="14153-167">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="14153-168">**[既定の検索プロバイダー名 (Default search provider name)]** をダブルクリックし、[有効] に設定して、「Microsoft Search in Bing」と入力します</span><span class="sxs-lookup"><span data-stu-id="14153-168">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="14153-169">**[既定の検索プロバイダー検索 URL (Default search provider search URL)]** をダブルクリックし、**[有効]** に設定して、`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR` と入力します</span><span class="sxs-lookup"><span data-stu-id="14153-169">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="14153-170">**[既定の検索プロバイダー サジェスト URL (Default search provider suggest URL)]** をダブルクリックし、**[有効]** に設定して、`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA` と入力します</span><span class="sxs-lookup"><span data-stu-id="14153-170">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="14153-171">作成された GPO を適切なドメインにリンクさせて適用します。</span><span class="sxs-lookup"><span data-stu-id="14153-171">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="14153-p110">既定の検索エンジンを設定すると、ブラウザーのアドレス バーに Microsoft Search 検索サジェスト機能が追加されます。現在、この機能がサポートしているのはブックマークのみです。アドレス バーに入力すると、パブリックの Web サジェストの上に 2 つのブックマーク サジェストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="14153-p110">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>