---
title: SharePoint の昇格した結果および上位のクエリのインポート
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
description: SharePoint からの検索クエリを使用して Microsoft search の作業結果を作成する
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508755"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>SharePoint の昇格した結果および上位のクエリのインポート

SharePoint で作成したユーザーのクエリとおすすめコンテンツを活用するために、Microsoft Search には、この情報を提案されたブックマークとしてインポートするためのツールが2つ含まれています。 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>SharePoint で昇格した結果のクエリルールをインポートする

推奨されるブックマークとして、これらのルール (以前のおすすめコンテンツ) をインポートします。 それらをユーザーが使用できるようにするには、それらを公開します。 公開時間は、選択したブックマークの数によって異なります。
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>PowerShell を使用してトップの SharePoint クエリをインポートする

- SharePoint から上位のクエリをダウンロードします。 PowerShell スクリプトでは、SharePoint 管理者の資格情報の入力を求められます。
    
- 上位の検索結果を取得するには、上位の各クエリに対して SharePoint 検索を実行します。
    
- 管理ポータルに推奨されるブックマークを追加します。
    
- SharePoint の上位のクエリは、ブックマークを作成するのに適しています。 PowerShell スクリプトを使用して、提案されたブックマークとしてインポートします。 このスクリプトは次のようになります。
    
要件、例、および使用可能なパラメーターの詳細については、スクリプトをダウンロードし、README ファイルを参照してください。 PowerShell スクリプトを実行した後、管理者または編集者は、提案されているブックマークを確認して、公開する前に必要な編集を行う必要があります。

  

