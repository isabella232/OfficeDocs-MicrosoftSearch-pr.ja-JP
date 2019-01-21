---
title: セットの既定のホーム ページ
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Bing を Microsoft の検索を使用して、会社の既定のホーム ページとして設定する方法について説明します。
ms.openlocfilehash: 9190e607f5e17a0b898ab131886de12cb300a74c
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378997"
---
# <a name="set-default-homepage"></a>セットの既定のホーム ページ

既定のブラウザー、既定の検索エンジン、および既定のホーム ページを構成するがように、Microsoft 検索機能、複数の使用法をお勧めを見つけてより滑らかなエクスペリエンスを提供します。
  
組織の既定のホーム ページを設定するのには以下の手順を実行します。
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-50-or-later"></a>5.0 またはそれ以降の Internet Explorer

1. グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。
    
2. **Configuration\Preferences\Control パネル]、[internet のユーザーの設定**に移動します。
    
3. **インターネットの設定**を右クリックし、 **Internet Explorer 10**を選択します。
    
    > [!NOTE]
    > Internet Explorer 11 に同じ設定を適用すると、11 の Internet Explorer の設定を適用するのには、Internet Explorer 10 のオプションを選択する必要があります。 
  
4. 赤い下線が表示されている設定は、ターゲット マシン上で緑色で下線付きで表示する設定が構成されている間、ターゲット ・ マシン上で構成されていません。下線を変更するには、以下のファンクション キーを使用します。
    
    F5 - 現在のタブ上のすべての設定を有効にします。
    
    F6 キーを押して、現在選択されている設定を有効にする-
    
    F7: 現在選択されている設定を無効にします。
    
    F8 キーの現在のタブ上のすべての設定を無効にします。
    
5. 何かを構成する前にすべての設定を無効にするのには、 **f8 キー**を押します。画面は、次のようになります。 
    
    ![インターネット エクスプ ローラーの 10 のプロパティ] ダイアログ ボックス](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. ホーム ページの設定に、 **f6 キー**を押すし、入力してください。`https://www.bing.com/business?form=BFBSPR`
    
7. 適切なドメインにリンクすることによって、結果の GPO を適用します。
    
> [!NOTE]
> ユーザーがこのポリシーの設定後、ホーム ページを変更できます。 
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1511-or-later"></a>1511 またはそれ以降のバージョンである Windows 10

1. グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。
    
2. **管理用テンプレート \windows コンポーネント Components\Microsoft の端**に移動します。
    
1. **構成の開始ページ**をダブルクリックし、 **[有効**] に設定し、入力`https://www.bing.com/business`
    
3. 適切なドメインにリンクすることによって、結果の GPO を適用します。
    
> [!CAUTION]
> ユーザーはこのポリシーを設定した後検索プロバイダーを変更することはできません。 
  
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 またはそれ以降

ADMX ファイルと異なるバージョンの Windows 用の最新の ADMX ファイルの管理に Windows のサポートの記事は、[マイクロソフトのサポートを](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra)ご覧ください。

最新 Google ポリシー ファイル、 [Google Chrome のエンタープライズのヘルプ](https://support.google.com/chrome/a/answer/187202)で確認する必要もあります。
  
GPMC 内でこのセクションで説明する設定が見つからない場合は、適切な ADMX をダウンロードして、[中央ストア](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29)にコピーします。コント ローラー上の中央のストアは、次の命名規則を含むフォルダーです。
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
各ドメイン コント ローラー ハンドルに別のフォルダーが表示されます。コマンド ・ プロンプトから ADMX ファイルをコピーするのには、次のコマンドを使用できます。
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。
    
2. 両方の*ユーザーまたはコンピューターの構成*の**管理用テンプレート**] セクションで次のフォルダーが表示されるかどうかを確認: Google Chrome と Google Chrome を既定の設定 (ユーザーは無視できます)。
    
   - 最初のセクションの設定が固定されており、ローカルの管理者は、それらを変更するのにはできません。
    
   - 後者のポリシーのセクションの設定は、ブラウザーの設定でユーザーが変更できます。かどうか、ユーザーは、既定の設定をオーバーライドできますを決定する必要があります。次の手順で、組織のポリシーとニーズに対応するフォルダーの設定で変更します。次の手順は、Google のクロムの既定値として既定の設定を使用します。
    
3. 移動**&lt;コンピューターとユーザーの構成&gt;\Administrative Templates\Google クロムのデフォルトの Settings\Home ページ**。
    
4. **ホーム ページに新しいタブ ページを使用して**をダブルクリックし、 **[有効**] に設定します。
    
5. 移動**&lt;コンピューターとユーザーの構成&gt;\Administrative Templates\Google クロム ・ Settings\New] タブの既定のページ**。
    
6. **構成新しいタブ ページの URL**] をダブルクリックし、 **[有効**] に設定し、入力`https://www.bing.com/business?form=BFBSPR`
    
7. 適切なドメインにリンクすることによって、結果の GPO を適用します。
    
ユーザーはこのポリシーを設定した後、ホーム ページを変更することになります。