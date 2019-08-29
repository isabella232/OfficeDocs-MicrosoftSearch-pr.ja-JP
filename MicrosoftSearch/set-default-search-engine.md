---
title: 既定の検索エンジンの設定
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
ROBOTS: NOINDEX
description: Microsoft Search を使用して会社の既定の検索エンジンとして Bing を設定する方法について取り上げます。
ms.openlocfilehash: cc03e3aa280ea621702ce99c2cc8eb530b310251
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639840"
---
# <a name="make-bing-the-default-search-engine"></a>Bing を既定の検索エンジンにする
  
この記事では、Bing を Microsoft Edge、Google Chrome、Internet Explorer の規定の検索エンジンとして設定する方法について説明します。 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a>Windows 10 バージョン 1703 以降の Microsoft Edge

Bing を規定の検索エンジンとして設定しても、Microsoft Edge では、ユーザーが設定を変更して別の検索エンジンを使用することができます。
  
各種バージョンの Windows の最新 ADMX ファイルについては、「[Windows でグループ ポリシー管理テンプレート用に中央ストアを作成および管理する方法](https://support.microsoft.com/ja-JP/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)」を参照してください。
  
このセクションに記述されている設定が GPMC 内に見つからない場合、適切な ADMX をダウンロードし、中央ストアにコピーします。詳しくは、「[ADMX ファイルを使用してドメイン ベースの GPO を編集する](https://docs.microsoft.com/ja-JP/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)」をご覧ください。コントローラーの中央ストアは 1 つのフォルダーで、以下の名前付け規則を使用します。
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
コントローラーが処理するドメインごとに異なるフォルダーが必要です。以下のコマンドを使用すると、コマンド プロンプトから ADMX ファイルをコピーできます。
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。
    
2. **&lt;[コンピューター/ユーザーの構成]&gt;、[管理用テンプレート]、[Windows コンポーネント]、[Microsoft Edge]** と移動します。
    
1. **[既定の検索エンジンの設定]** をダブルクリックし、**[有効]** に設定して `https://www.bing.com/sa/osd/bfb.xml` と入力します
    
3. 作成された GPO を適切なドメインにリンクさせて適用します。


## <a name="google-chrome-on-windows-xp-sp2-or-later"></a>Windows XP SP2 以降の Google Chrome

ユーザーは、このポリシーを設定後に既定の検索エンジンを変更することはできません。
  
Chrome には独自の一連のグループ ポリシー設定が備わっていて、[Google Chrome Enterprise ヘルプ](https://support.google.com/chrome/a/answer/187202)から ADMX ファイル形式でダウンロードできます。Windows Vista/Server 2008 以降のオペレーティング システムを使用してドメインの GPO を管理している場合、このパッケージで提供される ADMX ファイルは Windows XP SP2 以降の Chrome 設定に対して有効です。
  
テンプレート ファイルを、ドメイン コントローラー上の ADMX ファイルの中央ストアにコピーします。詳しくは、「[ADMX ファイルを使用してドメイン ベースの GPO を編集する](https://docs.microsoft.com/ja-JP/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)」をご覧ください。コントローラーの中央ストアは 1 つのフォルダーで、以下の名前付け規則を使用します。
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
コントローラーが処理するドメインごとに異なるフォルダーが必要です。以下のコマンドを使用すると、コマンド プロンプトから ADMX ファイルをコピーできます。
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。
    
2. [ユーザーの構成]/[コンピューターの構成] の両方の [管理用テンプレート] セクションに [Google Chrome] フォルダーと [Google Chrome - 既定の設定] フォルダーが表示されていることを確認します。
    
  - 最初のセクションの設定は固定されているため、ローカル管理者はブラウザーで設定を変更することはできません。
    
  - ポリシーの後半のセクションの設定は、ブラウザー設定でユーザーが変更できます。
    
3. [**\<コンピューター/ユーザー\> の構成]、[管理用テンプレート]、[Google Chrome]、[既定の検索プロバイダー (Default search provider)]** と移動します
    
4. **[既定の検索プロバイダーを有効にする (Enable the default search provider)]** をダブルクリックし、**[有効]** に設定します。
    
5. **[既定の検索プロバイダー (Default search provider)] アイコン**をダブルクリックし、**[有効]** に設定して、`https://www.bing.com/sa/simg/bb.ico` と入力します
    
6. **[既定の検索プロバイザー インスタンス URL (Default search provider instant URL)]** をダブルクリックし、`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR` と入力します
    
7. **[既定の検索プロバイダー名 (Default search provider name)]** をダブルクリックし、[有効] に設定して、「Microsoft Search in Bing」と入力します
    
8. **[既定の検索プロバイダー検索 URL (Default search provider search URL)]** をダブルクリックし、**[有効]** に設定して、`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR` と入力します
    
9. **[既定の検索プロバイダー サジェスト URL (Default search provider suggest URL)]** をダブルクリックし、**[有効]** に設定して、`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA` と入力します
    
10. 作成された GPO を適切なドメインにリンクさせて適用します。
    
既定の検索エンジンを設定すると、ブラウザーのアドレス バーに Microsoft Search 検索サジェスト機能が追加されます。現在、この機能がサポートしているのはブックマークのみです。アドレス バーに入力すると、パブリックの Web サジェストの上に 2 つのブックマーク サジェストが表示されます。

## <a name="internet-explorer-11-or-later"></a>Internet Explorer 11 以降

ユーザーは、このポリシーを設定後に検索プロバイダーを変更できます。
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>手順 1. GPO を設定するために使用するローカル コンピューターを構成する

以下のテキストを reg(\*.reg) ファイルに貼り付けます。
  
Windows レジストリ エディター バージョン 5.00
  
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
  
作成されたファイルをダブルクリックし、そのファイルをインポートするための手順を実行します。インポートが成功すると、以下のダイアログが表示されます。
  
![レジストリ エディターのインポート成功メッセージ](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>手順 2. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行う

1. **[ユーザーの構成]、[ポリシー]、[基本設定]、[Windows の設定]** と移動します。
    
2. **[レジストリ]\[新規]** で右クリックし、**[レジストリ ウィザード]** を選択します。[レジストリ ブラウザー] ウィンドウで、**[ローカル コンピューター]** を選択し、**[次へ]** をクリックします。
    
3. **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes** と移動します。
    
4. このキーで、[DefaultScope] が選択されていることを確認します。
    
    ![[DefaultScope] が選択されている [レジストリ ブラウザー]](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Bing における Microsoft Search の GUID が含まれるすべてのサブキーと、対象キーのすべての値 (ユーザー プロファイルのパス以外) を選択状態にします。下方向にスクロールして、他の項目を選択します。
    
    ![他の値が選択されている [レジストリ ブラウザー]](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. [終了] をクリックして、この構成を完了します。
    
### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>手順 3.  ユーザー設定を設定し、DefaultScope 検索が適用された場合にユーザーに表示されることがある警告が表示されないようにする

この警告は仕様で、プログラムの設定変更が行われようとしていることをユーザーに通知します。
  
1. 同じ GPO で **[レジストリ]\[新規]** を右クリックし、**[レジストリ ウィザード]** を選択します。
    
2. **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences** と移動します。
    
3. **User Preference** キーを選択します。
    
4. [**完了**] をクリックします。
    
5. 新しく作成されたオブジェクトをクリックします。右側のウィンドウで User Preferences オブジェクトをダブルクリックし、**[アクション]** を **[削除および保存]** に変更します。
1. 作成された GPO を適切なドメインにリンクさせて適用します。