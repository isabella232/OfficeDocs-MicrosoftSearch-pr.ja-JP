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
# <a name="make-microsoft-edge-the-default-browser"></a>Microsoft Edge を既定のブラウザーにする
  
Microsoft Search のエクスペリエンスを最善にするためには、Microsoft Edge を既定のブラウザーにします。 これにより、組織のユーザーの既定のブラウザーとして Microsoft Edge の設定のみを行えます。それでも個々のユーザーは、別のブラウザーを選択できます。
  
  
## <a name="windows-8-and-later"></a>Windows 8 以降

以下の手順では、Windows 8 以降を実行しているコンピューター向けに、既定のブラウザーとして Microsoft Edge または Internet Explorer を設定する方法について説明します。 ユーザーは、このポリシーの設定後にブラウザーを変更することができます。
  
### <a name="step-1-create-the-default-associations-file"></a>手順 1: 既定の関連付けファイルの作成
ドメイン コントローラーの SYSVOL フォルダーに既定の関連付けファイルを作成します。

1. 管理者 PowerShell コンソールを開きます。
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a>手順 2. 既定の関連付けファイルの追加または編集

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. 以下のエントリ (.htm、.html、http、https) を編集し、必要ない場合はその他のエントリを削除します。
  - **Microsoft Edge**
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a>手順 3.  グループ ポリシーを編集する

1. **グループ ポリシー管理コンソール** (gpmc.msc) を開き、既存のポリシーの編集または新しいポリシーの作成を行います。
1. **[コンピューターの構成]、[管理用テンプレート]、[Windows コンポーネント]、[エクスプローラー]** と移動します。
1. **[既定の関連付け構成ファイルを設定する]** をダブルクリックし、**[有効]** に設定して、AppAssoc.xml へのパス (例: %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) を入力します。設定を行った GPO を適切なドメインにリンクして適用します。

  
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
    
