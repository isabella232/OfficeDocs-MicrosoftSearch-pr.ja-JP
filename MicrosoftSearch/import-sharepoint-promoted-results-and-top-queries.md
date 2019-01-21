---
title: インポートの SharePoint の昇格の結果、上位のクエリ
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
description: Microsoft Search の作業の結果を作成する sharepoint サイトからの検索クエリを使用してください。
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379021"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="07db5-103">インポートの SharePoint の昇格の結果、上位のクエリ</span><span class="sxs-lookup"><span data-stu-id="07db5-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="07db5-104">ユーザーのクエリと SharePoint で作成したおすすめを活用するには、Microsoft Search には、ブックマークの候補としては、この情報をインポートするのには 2 つのツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="07db5-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="07db5-105">インポートの SharePoint は、クエリ規則の結果を昇格</span><span class="sxs-lookup"><span data-stu-id="07db5-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="07db5-p101">しおりの候補としては、おすすめと呼ばれていた、これらのルールをインポートします。利用できるように、ユーザーに、それらを公開します。公開にかかる時間は、選択したブックマークの数に基づいて変化します。</span><span class="sxs-lookup"><span data-stu-id="07db5-p101">Import these rules, previously called Best Bets, as suggested bookmarks. To make them available to your users, publish them. Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="07db5-109">PowerShell を使用して SharePoint の上位のクエリをインポートします。</span><span class="sxs-lookup"><span data-stu-id="07db5-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="07db5-p102">最上位のクエリ、sharepoint サイトからダウンロードしてください。PowerShell スクリプトでは、SharePoint 管理者の資格情報を求められます。</span><span class="sxs-lookup"><span data-stu-id="07db5-p102">Download the top queries from your SharePoint. The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="07db5-112">上位の検索結果を得るための上位のクエリのそれぞれの SharePoint の検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="07db5-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="07db5-113">提案されたブックマークを管理ポータルに追加します。</span><span class="sxs-lookup"><span data-stu-id="07db5-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="07db5-p103">SharePoint の上位のクエリは、ブックマークの最適な候補です。として提案されているブックマークをインポートするのにには、PowerShell スクリプトを使用します。このスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="07db5-p103">Your top SharePoint queries are excellent candidates for bookmarks. Use the PowerShell script to import them as suggested bookmarks. This script will:</span></span>
    
<span data-ttu-id="07db5-p104">要件、例、および使用可能なパラメーターについては、スクリプトをダウンロードし、README ファイルを確認します。PowerShell スクリプトの後の実行、管理者またはエディター候補のブックマークを確認してください投稿する前に、必要な編集を行います。</span><span class="sxs-lookup"><span data-stu-id="07db5-p104">For information about requirements, examples, and available parameters, download the script and review the README file. After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

