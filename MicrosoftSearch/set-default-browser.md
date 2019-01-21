---
title: セットの既定のブラウザー
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
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Microsoft の検索を使用して、会社の既定のブラウザーを構成する方法について説明します。
ms.openlocfilehash: 13a0a878b3288abeb7b07defdab839a158adc2ac
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379038"
---
# <a name="set-default-browser"></a>セットの既定のブラウザー

既定のブラウザー、既定の検索エンジン、および既定のホーム ページを構成するがように、Microsoft 検索機能、複数の使用法をお勧めを見つけてより滑らかなエクスペリエンスを提供します。
  
組織の既定のブラウザーを設定するのには以下の手順を実行します。
  
## <a name="windows-8-and-above"></a>Windows 8 以降

既定のブラウザーとして Internet Explorer または Microsoft のエッジを設定するには、次の手順を実行します。
  
### <a name="create-default-associations-file"></a>デフォルトの関連付けファイルを作成します。

1. 管理の PowerShell コンソールを開きます。
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
次の手順は、ドメイン コント ローラーの SYSVOL フォルダーの既定の関連付けのファイルを作成してください。
  
### <a name="add-or-edit-the-default-associations-file"></a>追加または既定の関連付けのファイルを編集します。

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. (.Htm、.html、http、https) は、次のエントリを編集し、必要ない場合は、他のエントリを削除します。
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。
    
1. **コンピューターの構成 \ 管理用テンプレート Components\File エクスプ ローラー**に移動します。
    
2. **既定の関連付けの構成ファイルの設定**] をダブルクリック、 **[有効**] に設定し、AppAssoc.xml へのパスを入力 (たとえば %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)
    
4. 適切なドメインにリンクすることによって、結果の GPO を適用します。
    
ユーザーはこのポリシーを設定した後にブラウザーを変更することになります。
  
## <a name="windows-7"></a>Windows 7

1. GPO の設定を使用するローカル コンピューターを構成します。
    
1. **コントロール Panel\Programs\Default Programs\Set の既定のプログラム**を開くし、Internet Explorer を既定として設定します。 
    
2. グループ ポリシー管理コンソール (gpmc.msc) を開き、任意の既存のポリシーを編集または新規に作成するのに切り替えます。
    
1. 移動**\<コンピューター/ユーザー\> Configuration\Policies\Preferences\Windows 設定**。
    
2. **Registry\New**を右クリックし、[**レジストリ ウィザード**] を選択します。
    
3. レジストリのブラウザーのウィンドウからは、**ローカル コンピューター**を選択し、[**次へ**] をクリックします。
    
4. **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**に移動し、ProgId の値を選択します。値は次のような外観を確認します。 
    
    ![ProgID の値を選択して [文字列の編集](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https**に移動し、ProgId の値を選択します。行います。 値が、いずれかのようになっていることを確認して下 
    
    ![編集文字列での HTTPS のプログラム Id を選択します](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. 適切なドメインにリンクすることによって、結果の GPO を適用します。
    
ユーザーはこのポリシーを設定した後にブラウザーを変更することになります。