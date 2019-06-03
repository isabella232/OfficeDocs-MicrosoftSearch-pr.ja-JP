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
ROBOTS: NOINDEX
description: Microsoft Search を使用して、会社の既定のブラウザーを構成する方法について説明します。
ms.openlocfilehash: daff7f66bd38bdd56179e44c36092a2c4fd42b42
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591163"
---
# <a name="set-default-browser"></a>既定のブラウザーを設定する

> [!IMPORTANT]
> この記事は、Bing 管理ポータルの Microsoft Search に適用されます。 ポータルを Microsoft 365 管理センターに移動しており、後で削除されます。 Microsoft 365 管理センターを使用して作業を開始することをお勧めします。 [Microsoft Search の概要](overview-microsoft-search.md)。
    
既定のブラウザー、検索エンジン、ホームページを構成すると、ユーザーが Microsoft Search 機能を把握したり、使用を促進したり、円滑なエクスペリエンスを提供したりするのに役立ちます。
  
組織の既定のブラウザーを設定するには、以下の手順を実行します。
  
## <a name="windows-8-and-above"></a>Windows 8 以上

Internet Explorer または Microsoft Edge を既定のブラウザーとして設定するには、以下のいずれかのステップを実行します。
  
### <a name="create-default-associations-file"></a>既定の関連付けファイルの作成

1. 管理者 PowerShell コンソールを開きます。
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
これらの手順では、ドメイン コントローラーの SYSVOL フォルダーに既定の関連付けファイルを作成します。
  
### <a name="add-or-edit-the-default-associations-file"></a>既定の関連付けファイルの追加または編集

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. 以下のエントリ (.htm、.html、http、https) を編集し、必要ない場合はその他のエントリを削除します。
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。
    
1. **[コンピューターの構成]、[管理用テンプレート]、[Windows コンポーネント]、[エクスプローラー]** と移動します。
    
2. **[既定の関連付け構成ファイルを設定する]** をダブルクリックして、**[有効]** に設定して、AppAssoc.xml へのパス (たとえば %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) を入力します。
    
4. 作成された GPO を適切なドメインにリンクさせて適用します。
    
ユーザーは、このポリシーの設定後にブラウザーを変更することができます。
  
## <a name="windows-7"></a>Windows 7

1. GPO を設定するのに使用するローカル マシンを構成します。
    
1. **[コントロール パネル]、[プログラム]、[既定のプログラム]、[既定のプログラムを設定する]** を開き、Internet Explorer を既定として設定します。 
    
2. グループ ポリシー管理コンソール (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。
    
1. **[\<コンピューター/ユーザー\> の構成]、[ポリシー]、[基本設定]、[Windows の設定]** と移動します。
    
2. **[レジストリ]、[新規]** を右クリックし、**[レジストリ ウィザード]** を選択します。
    
3. [レジストリ ブラウザー] ウィンドウで、**[ローカル コンピューター]** を選択し、**[次へ]** をクリックします。
    
4. **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** に移動し、ProgId の値を選択します。次のような値になっていることを確認します。 
    
    ![[文字列の編集] で ProgID 値を選択する](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** に移動し、ProgId の値を選択します。次のような値になっていることを確認します。 
    
    ![[文字列の編集] で HTTPS の ProgID を選択する](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. 作成された GPO を適切なドメインにリンクさせて適用します。
    
ユーザーは、このポリシーの設定後にブラウザーを変更することができます。