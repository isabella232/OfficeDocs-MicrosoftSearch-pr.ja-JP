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
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="b656b-103">SharePoint の昇格した結果および上位のクエリのインポート</span><span class="sxs-lookup"><span data-stu-id="b656b-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b656b-104">この記事は、Bing 管理ポータルの Microsoft Search に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b656b-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="b656b-105">ポータルを Microsoft 365 管理センターに移動しており、後で削除されます。</span><span class="sxs-lookup"><span data-stu-id="b656b-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="b656b-106">Microsoft 365 管理センターを使用して作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b656b-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="b656b-107">[Microsoft Search の概要](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="b656b-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="b656b-108">SharePoint で作成したユーザーのクエリと「おすすめコンテンツ」を活用するために、Microsoft Search には、この情報をおすすめのブックマークとしてインポートする 2 つのツールが組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="b656b-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="b656b-109">SharePoint の昇格した結果のクエリ ルールをインポートする</span><span class="sxs-lookup"><span data-stu-id="b656b-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="b656b-110">こうしたルール (以前は「おすすめコンテンツ」と呼ばれていました) を、おすすめのブックマークとしてインポートします。</span><span class="sxs-lookup"><span data-stu-id="b656b-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="b656b-111">これらをユーザーが利用できるようにするには、公開します。</span><span class="sxs-lookup"><span data-stu-id="b656b-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="b656b-112">公開にかかる時間は、選択したブックマークの数に基づいて変化します。</span><span class="sxs-lookup"><span data-stu-id="b656b-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="b656b-113">PowerShell を使用して、SharePoint の上位のクエリをインポートする</span><span class="sxs-lookup"><span data-stu-id="b656b-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="b656b-114">上位のクエリを SharePoint からダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="b656b-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="b656b-115">PowerShell スクリプトでは、SharePoint 管理者の資格情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b656b-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="b656b-116">上位の検索結果を得るには、上位の各クエリの SharePoint 検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="b656b-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="b656b-117">管理ポータルに、おすすめのブックマークを追加します。</span><span class="sxs-lookup"><span data-stu-id="b656b-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="b656b-118">SharePoint の上位のクエリが、ブックマークの適した候補になります。</span><span class="sxs-lookup"><span data-stu-id="b656b-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="b656b-119">おすすめのブックマークとしてインポートするには、PowerShell スクリプトを使用します。</span><span class="sxs-lookup"><span data-stu-id="b656b-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="b656b-120">このスクリプトを使用すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="b656b-120">This script will:</span></span>
    
<span data-ttu-id="b656b-121">要件、例、使用可能なパラメーターについては、スクリプトをダウンロードし、README ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="b656b-121">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="b656b-122">この PowerShell スクリプトの実行後に、管理者または共同編集者は、おすすめのブックマークを確認して、公開する前に必要な編集を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="b656b-122">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

