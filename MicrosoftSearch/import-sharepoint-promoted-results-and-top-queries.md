---
title: SharePoint の昇格した結果および上位のクエリのインポート
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
ROBOTS: NOINDEX
description: SharePoint からの検索クエリを使用して Microsoft Search の作業結果を作成する
ms.openlocfilehash: c69203ce2138a7609e1b52614f8bfccc98bc9616
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626848"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>SharePoint の昇格した結果および上位のクエリのインポート

> [!IMPORTANT]
> この記事は、Bing 管理ポータルの Microsoft Search に適用されます。 ポータルを Microsoft 365 管理センターに移動していますので、後で Bing ポータルの Microsoft Search は削除されます。 Microsoft 365 管理センターを使用して作業を開始することをお勧めします。 [Microsoft Search の概要](overview-microsoft-search.md)。
    
SharePoint で作成したユーザーのクエリとおすすめコンテンツを活用するために、Microsoft Search には、この情報を提案されたブックマークとしてインポートするためのツールが2つ含まれています。 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>SharePoint で昇格した結果のクエリルールをインポートする

推奨されるブックマークとして、これらのルール (以前のおすすめコンテンツ) をインポートします。 それらをユーザーが使用できるようにするには、それらを公開します。 公開時間は、選択したブックマークの数によって異なります。
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>PowerShell を使用してトップの SharePoint クエリをインポートする

- SharePoint から上位のクエリをダウンロードします。 PowerShell スクリプトでは、SharePoint 管理者の資格情報の入力を求められます。
    
- 上位の検索結果を取得するには、上位の各クエリに対して SharePoint 検索を実行します。
    
- 管理ポータルに推奨されるブックマークを追加します。
    
- SharePoint の上位のクエリは、ブックマークを作成するのに適しています。 PowerShell スクリプトを使用して、提案されたブックマークとしてインポートします。 このスクリプトは、次の作業を行います。
    - SharePoint の上位のクエリに基づいて、Microsoft 検索ブックマークの範囲を向上させるために推奨されるブックマークを追加します。 このスクリプトは、SharePoint 管理ポータルからアクセス可能な上位のクエリをダウンロードし、次に Microsoft 検索管理ポータルでレビューするための管理者のために推奨されるブックマークとしてアップロードします。
    - 既定では、スクリプトは、使用可能なすべての月の指定されたテナントに提案されたブックマークを追加します。 このメソッドは、指定された SharePoint 管理者 web サイトから上位のクエリを取得し、提案されたブックマークとして Microsoft Search に追加します。 推奨されるブックマークは、公開する前に管理者ポータルで権限を付与するための管理者/編集者を必要とします。 このスクリプトを実行すると、Microsoft Search 管理ポータルにアクセスするための資格情報を求めるメッセージが表示されます。
    - このスクリプトでは、追加のパラメーターを指定できます。 たとえば、使用可能な各月の top N クエリに対して、指定したテナントに提案されたブックマークを追加することができます。
    - 必要に応じて、指定した年の月に対して、指定したテナントに提案されたブックマークを追加できます。 このコマンドは、指定された期間のクエリを SharePoint 管理者 web サイトから取得し、提案されたブックマークとして Microsoft Search に追加します。
    - その他にも、多くのオプションとコマンドモードがあります。 SharePoint から指定されたフォルダーに上位クエリをダウンロードし、スクリプトをセーフモードで実行し、詳細モードでスクリプトを実行し、デバッグモードにします。
    - [この](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip)スクリプトをダウンロードします。 

要件、例、および使用可能なパラメーターの詳細については、スクリプトをダウンロードし、README ファイルを参照してください。 PowerShell スクリプトを実行した後、管理者または編集者は、提案されているブックマークを確認して、公開する前に必要な編集を行う必要があります。