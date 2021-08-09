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
description: 検索クエリを使用して、SharePointの作業結果を作成Microsoft Search
ms.openlocfilehash: cfd5fafd0529f537a55e436ef078800a4b9714177e04c63e65e968f16fcf322e
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533826"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a>SharePoint の昇格した結果および上位のクエリのインポート

> [!IMPORTANT]
> この記事は、管理者ポータルMicrosoft SearchのBing適用されます。 ポータルを Microsoft 365 管理センターに移動していますので、後で Bing ポータルの Microsoft Search は削除されます。 Microsoft 365 管理センターを使用して作業を開始することをお勧めします。 [Microsoft Search の概要](overview-microsoft-search.md)。
    
SharePoint で作成したユーザーのクエリとベスト ベットを活用するために、Microsoft Search には、この情報を推奨ブックマークとしてインポートするための 2 つのツールが含まれています。 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a>昇格SharePointクエリ ルールのインポート

推奨ブックマークとして、以前はベスト ベットと呼ばばしいこれらのルールをインポートします。 ユーザーがそれらを使用するには、ユーザーを公開します。 発行時間は、選択したブックマークの数によって異なります。
  
## <a name="import-top-sharepoint-queries-using-powershell"></a>PowerShell をSharePointトップ クエリをインポートする

- トップ クエリをユーザーのページからダウンロードSharePoint。 PowerShell スクリプトを使用すると、管理者の資格情報SharePoint求めるメッセージが表示されます。
    
- 上位のSharePoint検索を実行して、上位の検索結果を取得します。
    
- 推奨ブックマークを管理ポータルに追加します。
    
- 上位のSharePointは、ブックマークの優れた候補です。 PowerShell スクリプトを使用して、推奨ブックマークとしてインポートします。 このスクリプトは、次の作業を実行します。
    - 上位クエリに基づいて候補ブックマークSharePoint追加し、ブックマークのMicrosoft Searchを改善します。 このスクリプトは、SharePoint 管理ポータルからアクセス可能な上位クエリをダウンロードし、管理者が Microsoft Search 管理ポータルで確認するために推奨されるブックマークとしてアップロードします。
    - 既定では、スクリプトは使用可能なすべての月の特定のテナントに推奨ブックマークを追加します。 特定の管理者 Web サイトから上位クエリSharePoint取得し、候補のブックマークMicrosoft Search追加します。 推奨ブックマークには、公開する前に管理ポータルで承認する管理者/編集者が必要です。 このスクリプトを実行すると、管理者ポータルにアクセスするための資格情報を求Microsoft Searchされます。
    - スクリプトを使用すると、追加のパラメーターを指定できます。 たとえば、利用可能な各月に上位 N クエリの候補ブックマークを特定のテナントに追加できます。
    - 必要に応じて、指定した年の数か月間、提案されたブックマークを特定のテナントに追加できます。 このコマンドは、管理者 web サイトから特定の期間SharePointクエリを取得し、Microsoft Searchブックマークとして追加します。
    - また、SharePoint から指定したフォルダーに上位クエリをダウンロードする、セーフ モードでスクリプトを実行する、詳細モードでスクリプトを実行する、デバッグ モードなど、他にも多数のオプションとコマンド モードがあります。
    - スクリプトのダウンロード [は、こちらから行います](https://www.bingforbusiness.com/distribution/SharepointTopQueryBookmarks.zip)。 

要件、例、および使用可能なパラメーターの詳細については、スクリプトをダウンロードして README ファイルを確認してください。 PowerShell スクリプトの実行後、管理者または編集者は推奨ブックマークを確認し、公開する前に必要な編集を行う必要があります。