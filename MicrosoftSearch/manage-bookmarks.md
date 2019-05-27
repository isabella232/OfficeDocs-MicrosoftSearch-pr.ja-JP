---
title: ブックマークの管理
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: 更新の必要があるブックマークと、Microsoft Search のブックマーク結果を一括編集する方法を調べます
ms.openlocfilehash: d5cebbfd5779bc8a6aa25cdbcdedb6e9b18f242e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968485"
---
# <a name="manage-bookmarks"></a>ブックマークの管理

> [!IMPORTANT]
> Bing の Microsoft Search の設定は、Microsoft 365 管理センターで利用できるようになりました。 まず、管理センターで[検索管理者を割り当てる](https://docs.microsoft.com/ja-JP/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)ことから作業を開始します。
    
時間の経過と共に、ブックマークの状態やコンテンツを更新して、関連性の高い状態を維持することが必要になる場合があります。 
  
## <a name="filter-bookmarks"></a>ブックマークをフィルタリングする

[ブックマーク] ページの右上隅のフィルタリング オプションを使用して、日付や変更したユーザー別にブックマークを検索します。 たとえば、日付スライダーを 30 日間に設定して管理者または編集者を選択し、その時期にその管理者または編集者によって作成されたブックマークの一覧を表示します。
  
## <a name="change-bookmark-content-or-settings"></a>ブックマークのコンテンツまたは設定を変更する

1. Microsoft Search 管理ポータルに移動する
    
2. [ナビゲーション] ウィンドウで [**ブックマーク**] をクリックします。
    
3. ブックマークを見つけるには、ブックマークの状態を検索したり、フィルタリングしたり、クリックしたりして、結果を絞り込みます。
    
4. ブックマークを更新または変更するには、タイトルをクリックします。
    
5. コンテンツや設定を変更または更新し、どのように表示されるかをプレビューします。 
    
6. [**保存**] をクリックします。
    
## <a name="bulk-export-and-edit-bookmarks"></a>ブックマークを一括でエクスポートおよび編集する

これらのフィールドのデータは編集しないでください。
  
- ID
    
- 最終更新日時
    
- 最終更新者
    
ID は各ブックマークの一意の識別子なので、編集しないでください。 [最終更新日時] および [最終更新者] フィールドはブックマークの並べ替えと検索のみに使用します。
  
1. ブックマークのサブセットをエクスポートする場合は、フィルタリングします。
    
2. [ブックマーク] ページの右上隅にある [**エクスポート**] をクリックします。
    
3. .csv ファイルを保存するか開きます。
    
4. これらのフィールドのいずれかを編集します。
   - タイトル
    
   - URL
    
   - キーワード
    
   - 状態
    
   - 説明
    
   - 予約済みキーワード
    
   - 開始日
    
   - 終了日
    
   - 国/地域
    
   - グループ
    
   - デバイス&amp;OS
    
   - 対象のバリエーション
    
5. .csv ファイルを保存します

    この .csv ファイルは、CSV UTF-8 ファイルとして保存する必要があります。その他のファイルの種類やエンコーディングでは、インポート エラーが発生する可能性があります
    
6. [ブックマーク] ページの右上隅にある **[インポート]** をクリックします。
    
7. [ブックマークのインポート] ウィンドウで、**[参照]** をクリックして、編集済みの .csv ファイルを選択します。 
    
8. **[インポート]** をクリックします