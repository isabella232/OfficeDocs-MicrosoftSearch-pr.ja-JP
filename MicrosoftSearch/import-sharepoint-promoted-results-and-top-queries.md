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
ROBOTS: NOINDEX
description: SharePoint からの検索クエリを使用して、Microsoft Search の作業結果を作成します
ms.openlocfilehash: 1538c57a7b4138b36fe62e3076feb58d746b2b3e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591604"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>SharePoint の昇格した結果および上位のクエリのインポート

> [!IMPORTANT]
> この記事は、Bing 管理ポータルの Microsoft Search に適用されます。 ポータルを Microsoft 365 管理センターに移動しており、後で削除されます。 Microsoft 365 管理センターを使用して作業を開始することをお勧めします。 [Microsoft Search の概要](overview-microsoft-search.md)。
    
SharePoint で作成したユーザーのクエリと「おすすめコンテンツ」を活用するために、Microsoft Search には、この情報をおすすめのブックマークとしてインポートする 2 つのツールが組み込まれています。 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>SharePoint の昇格した結果のクエリ ルールをインポートする

こうしたルール (以前は「おすすめコンテンツ」と呼ばれていました) を、おすすめのブックマークとしてインポートします。 これらをユーザーが利用できるようにするには、公開します。 公開にかかる時間は、選択したブックマークの数に基づいて変化します。
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>PowerShell を使用して、SharePoint の上位のクエリをインポートする

- 上位のクエリを SharePoint からダウンロードします。 PowerShell スクリプトでは、SharePoint 管理者の資格情報を求めるメッセージが表示されます。
    
- 上位の検索結果を得るには、上位の各クエリの SharePoint 検索を実行します。
    
- 管理ポータルに、おすすめのブックマークを追加します。
    
- SharePoint の上位のクエリが、ブックマークの適した候補になります。 おすすめのブックマークとしてインポートするには、PowerShell スクリプトを使用します。 このスクリプトを使用すると、次のようになります。
    
要件、例、使用可能なパラメーターについては、スクリプトをダウンロードし、README ファイルを確認します。 この PowerShell スクリプトの実行後に、管理者または共同編集者は、おすすめのブックマークを確認して、公開する前に必要な編集を加える必要があります。

  

