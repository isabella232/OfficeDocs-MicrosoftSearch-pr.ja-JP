---
title: 既定のホーム ページの設定
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Microsoft Search を使用して、会社の既定のホーム ページとして Bing を設定する方法について説明します。
ms.openlocfilehash: 745e4a81e4b53ff88b612cd19295cb89dc041ddc
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701446"
---
# <a name="make-bingcom-the-default-home-page"></a>Bing.com を既定のホーム ページにする

この記事では、Bing.com を Microsoft Edge、Google Chrome、Internet Explorer ブラウザーの規定のホームページとして設定する方法について説明します。 
  
 
## <a name="microsoft-edge-on-windows-10-version-1511-or-later"></a>Windows 10 バージョン 1511 以降の Microsoft Edge

ユーザーは、このポリシーを設定した後に変更することはできません。 

1. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。 
1. **[管理用テンプレート]、[Windows コンポーネント]、[Microsoft Edge]** の順に移動します。    
1. **[スタート ページを構成する]** をダブルクリックして **[Enabled (有効)]** に設定し、「`https://www.bing.com/business`」と入力します
1.  作成された GPO を適切なドメインにリンクさせて適用します。

  
## <a name="google-chrome-on-windows-xp-sp2-or-later"></a>Windows XP SP2 以降の Google Chrome


異なるバージョンの Windows に関する ADMX ファイルと最新の ADMX ファイルの管理方法を記載した Windows サポート記事については、[Microsoft サポート](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)をご確認ください。

また、最新の Google ポリシー ファイルについては [Google Chrome エンタープライズ ヘルプ](https://support.google.com/chrome/a/answer/187202)を参照してください。
  
このセクションに示されている設定が GPMC 内に見つからない場合、適切な ADMX をダウンロードし、[中央ストア](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)にコピーします。コントローラーの中央ストアは 1 つのフォルダーで、以下の名前付け規則を使用します。
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
コントローラーが処理するドメインごとに異なるフォルダーが必要です。以下のコマンドを使用すると、コマンド プロンプトから ADMX ファイルをコピーできます。
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。
1. *[ユーザーの構成] と [コンピューターの構成]* の両方の **[管理用テンプレート]** セクションに [Google Chrome] フォルダーと [Google Chrome - 既定の設定] フォルダー (ユーザーによる上書き可能) が表示されていることを確認します。
   - 最初のセクションの設定は固定されているため、ローカル管理者は設定を変更することはできません。
   - ポリシーの後半のセクションの設定は、ユーザーがブラウザーの設定で変更できます。ユーザーが既定の設定を上書き可能かどうかを決定する必要があります。次の手順で、組織のポリシーとニーズに対応するフォルダーの設定を変更します。以下の手順では、既定で [Google Chrome - 既定の設定] を使用します。

1. **&lt;[コンピューターの構成] または [ユーザーの構成]&gt;、[管理用テンプレート]、[Google Chrome - 既定の設定]、[ホーム ページ]** の順に移動します。 
1. **[Use New Tab Page as homepage (新しいタブ ページをホーム ページとして使用する)]** をダブルクリックして、**[Enabled (有効)]** に設定します。 
1. **&lt;[コンピューターの構成] または [ユーザーの構成]&gt;、[管理用テンプレート]、[Google Chrome - 既定の設定]、[新しいタブ ページ]** の順に移動します。 
1. **[Configure the New Tab Page URL (新しいタブ ページを URL として構成する)]** をダブルクリックして、**[Enabled (有効)]** に設定し、「`https://www.bing.com/business?form=BFBSPR`」と入力します 
1. 作成された GPO を適切なドメインにリンクさせて適用します。

## <a name="internet-explorer-50-or-later"></a>Internet Explorer 5.0 以降
ユーザーは、このポリシーを設定後にホーム ページを変更できます。 

1. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。
    
2. **[ユーザーの構成]、[基本設定]、[コントロール パネルの設定]、[インターネットの設定]** の順に移動します。
    
3. **[インターネットの設定]** を右クリックして、**[Internet Explorer 10]** を選択します。
    
    > [!NOTE]
    > Internet Explorer 11 には Internet Explorer 10 と同じ設定が適用されるため、Internet Explorer 11 に適用するオプションは Internet Explorer 10 で選択する必要があります。 
  
4. 赤い下線が引かれた設定はターゲット マシンで構成されていていないことを意味し、緑色の下線が引かれた設定はターゲット マシンで構成されていることを意味します。下線を変更するには、次のファンクション キーを使用します。
    
    F5 キー: 現在のタブのすべての設定を有効にする
    
    F6 キー: 現在選択されている設定を有効にする
    
    F7 キー: 現在選択されている設定を無効にする
    
    F8 キー: 現在のタブのすべての設定を無効にする
    
5. **F8** キーを押して、構成を行う前にすべての設定を無効にします。画面は次のようになります。 
    
    ![Internet Explorer 10[プロパティ] ダイアログ。](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. ホーム ページの設定で **F6** キーを押して、「`https://www.bing.com/business?form=BFBSPR`」と入力します。
    
7. 作成された GPO を適切なドメインにリンクさせて適用します。