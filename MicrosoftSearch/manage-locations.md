---
title: 場所の管理
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 11/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: 時間の経過と共に、場所の情報の状態やコンテンツを更新して、関連性の高い状態を維持することが必要になる場合があります。
ms.openlocfilehash: 0e23cf3d3d3d05fe86cdc3e09ce808e54242d670
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968432"
---
# <a name="manage-locations"></a>場所の管理

> [!IMPORTANT]
> Bing の Microsoft Search の設定は、Microsoft 365 管理センターで利用できるようになりました。 まず、管理センターで[検索管理者を割り当てる](https://docs.microsoft.com/ja-JP/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)ことから作業を開始します。
    
時間の経過と共に、場所の情報の状態やコンテンツを更新して、関連性の高い状態を維持することが必要になる場合があります。 
  
## <a name="filter-locations"></a>場所のフィルタリング

場所ページの右上隅のフィルター オプションを使用して、日付や変更したユーザー別に場所を検索します。 たとえば、日付スライダーを 30 日間に設定して管理者または編集者を選択し、その時期にその管理者または編集者によって作成された場所所の情報の一覧を表示します。
  
## <a name="change-location-content"></a>場所の内容の変更

1. Microsoft Search 管理ポータルに移動します
    
2. ナビゲーション ウィンドウで、**[場所]** をクリックします
    
3. 場所を検索するには、場所の情報の状態を検索、フィルタリング、またはクリックして、結果を絞り込みます。
    
4. 場所の情報を変更または更新するには、場所の名前をクリックします
    
5. 内容を変更または更新して、どのように表示されるかをプレビューします。 
    
6. **[保存]** をクリックします
    
## <a name="bulk-export-and-edit-locations"></a>場所の一括エクスポートおよび編集

次のフィールドのデータは編集しないでください。
  
- ID
    
- 最終更新日時
    
- 最終更新者
    
ID は各場所の一意の識別子なので、編集しないでください。 [最終更新日時] および [最終更新者] フィールドは場所の並べ替えと検索にのみ使用してください。
  
1. 場所のサブセットをエクスポートする場合は、フィルタリングします
    
2. [場所] ページの右上にある **[エクスポート]** をクリックします
    
3. .csv ファイルを保存するか開きます
    
4. 次のフィールドのいずれかを編集します。
    
   - 名前
    
   - 住所行 1
    
   - 住所行 2
    
   - 市区町村
    
   - 都道府県
    
   - 郵便番号
    
   - 国
    
   - 完全な住所
    
   - 緯度
    
   - 経度
    
   - キーワード
    
   - 予約済みキーワード
    
   - 状態
    
5. .csv ファイルを保存します

    この .csv ファイルは、CSV UTF-8 ファイルとして保存する必要があります。その他のファイルの種類やエンコーディングでは、インポート エラーが発生する可能性があります
    
6. [場所] ページの右上にある **[インポート]** をクリックします
    
7. [場所のインポート] ウィンドウで、**[参照]** をクリックして、編集済みの .csv ファイルを選択します 
    
8. **[インポート]** をクリックします

  

