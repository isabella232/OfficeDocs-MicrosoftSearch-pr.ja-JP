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
description: SharePoint からの検索クエリを使用して、Microsoft Search の作業結果を作成します
ms.openlocfilehash: 6e55e2000792bdb576a18a0efeb353dc3ea13605
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968453"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="720da-103">SharePoint の昇格した結果および上位のクエリのインポート</span><span class="sxs-lookup"><span data-stu-id="720da-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="720da-104">Bing の Microsoft Search の設定は、Microsoft 365 管理センターで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="720da-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="720da-105">まず、管理センターで[検索管理者を割り当てる](https://docs.microsoft.com/ja-JP/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)ことから作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="720da-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="720da-106">SharePoint で作成したユーザーのクエリと「おすすめコンテンツ」を活用するために、Microsoft Search には、この情報をおすすめのブックマークとしてインポートする 2 つのツールが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="720da-106">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="720da-107">SharePoint の昇格した結果のクエリ ルールをインポートする</span><span class="sxs-lookup"><span data-stu-id="720da-107">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="720da-108">こうしたルール (以前は「おすすめコンテンツ」と呼ばれていました) を、おすすめのブックマークとしてインポートします。</span><span class="sxs-lookup"><span data-stu-id="720da-108">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="720da-109">これらをユーザーが利用できるようにするには、公開します。</span><span class="sxs-lookup"><span data-stu-id="720da-109">To make them available to your users, publish them.</span></span> <span data-ttu-id="720da-110">公開にかかる時間は、選択したブックマークの数に基づいて変化します。</span><span class="sxs-lookup"><span data-stu-id="720da-110">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="720da-111">PowerShell を使用して、SharePoint の上位のクエリをインポートする</span><span class="sxs-lookup"><span data-stu-id="720da-111">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="720da-112">上位のクエリを SharePoint からダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="720da-112">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="720da-113">PowerShell スクリプトでは、SharePoint 管理者の資格情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="720da-113">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="720da-114">上位の検索結果を得るには、上位の各クエリの SharePoint 検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="720da-114">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="720da-115">管理ポータルに、おすすめのブックマークを追加します。</span><span class="sxs-lookup"><span data-stu-id="720da-115">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="720da-116">SharePoint の上位のクエリが、ブックマークの適した候補になります。</span><span class="sxs-lookup"><span data-stu-id="720da-116">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="720da-117">おすすめのブックマークとしてインポートするには、PowerShell スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="720da-117">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="720da-118">このスクリプトを使用すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="720da-118">This script will:</span></span>
    
<span data-ttu-id="720da-119">要件、例、使用可能なパラメーターについては、スクリプトをダウンロードし、README ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="720da-119">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="720da-120">この PowerShell スクリプトの実行後に、管理者または共同編集者は、おすすめのブックマークを確認して、公開する前に必要な編集を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="720da-120">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

