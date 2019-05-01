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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="cf9a8-103">SharePoint の昇格した結果および上位のクエリのインポート</span><span class="sxs-lookup"><span data-stu-id="cf9a8-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="cf9a8-104">SharePoint で作成したユーザーのクエリとおすすめコンテンツを活用するために、Microsoft Search には、この情報を提案されたブックマークとしてインポートするためのツールが2つ含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="cf9a8-105">SharePoint で昇格した結果のクエリルールをインポートする</span><span class="sxs-lookup"><span data-stu-id="cf9a8-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="cf9a8-106">推奨されるブックマークとして、これらのルール (以前のおすすめコンテンツ) をインポートします。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-106">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="cf9a8-107">それらをユーザーが使用できるようにするには、それらを公開します。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-107">To make them available to your users, publish them.</span></span> <span data-ttu-id="cf9a8-108">公開時間は、選択したブックマークの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-108">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="cf9a8-109">PowerShell を使用してトップの SharePoint クエリをインポートする</span><span class="sxs-lookup"><span data-stu-id="cf9a8-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="cf9a8-110">SharePoint から上位のクエリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-110">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="cf9a8-111">PowerShell スクリプトでは、SharePoint 管理者の資格情報の入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-111">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="cf9a8-112">上位の検索結果を取得するには、上位の各クエリに対して SharePoint 検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="cf9a8-113">管理ポータルに推奨されるブックマークを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="cf9a8-114">SharePoint の上位のクエリは、ブックマークを作成するのに適しています。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-114">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="cf9a8-115">PowerShell スクリプトを使用して、提案されたブックマークとしてインポートします。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-115">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="cf9a8-116">このスクリプトは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-116">This script will:</span></span>
    
<span data-ttu-id="cf9a8-117">要件、例、および使用可能なパラメーターの詳細については、スクリプトをダウンロードし、README ファイルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-117">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="cf9a8-118">PowerShell スクリプトを実行した後、管理者または編集者は、提案されているブックマークを確認して、公開する前に必要な編集を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf9a8-118">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

