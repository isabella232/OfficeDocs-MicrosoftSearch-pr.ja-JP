---
title: PowerApps の統合
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
ROBOTS: NOINDEX
description: Microsoft Search のブックマーク検索結果にブラウザーベースのアプリを含める
ms.openlocfilehash: 36389a8b53390c7dd18cf98285b0faa6df73c8b4
ms.sourcegitcommit: 3da22a2e09830672ebf199e05a32fa89b75c083b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288930"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="4c4fe-103">PowerApps の統合</span><span class="sxs-lookup"><span data-stu-id="4c4fe-103">Integrate PowerApps</span></span>
   
<span data-ttu-id="4c4fe-104">休暇の入力や、既存の PowerApps をブックマークに統合することによる経費の報告など、ユーザーがタスクを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-104">Help your users complete tasks, such as entering vacation time or reporting expenses by integrating existing PowerApps into your bookmarks.</span></span> <span data-ttu-id="4c4fe-105">統合 PowerApps はブックマークの結果内に表示されます。別のサイトに移動したり、別のツールを開いたりする必要がなくなり、時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-105">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="4c4fe-106">PowerApps とはどういったものですか? </span><span class="sxs-lookup"><span data-stu-id="4c4fe-106">What are PowerApps?</span></span>

<span data-ttu-id="4c4fe-107">PowerApps は、コーディング経験がなくても、ブラウザーまたは携帯電話やタブレットで実行するビジネス アプリケーションを作成できるサービスです。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-107">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="4c4fe-108">詳細については、次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-108">Learn more:</span></span>
  
- <span data-ttu-id="4c4fe-109">
  [ガイド付き学習](https://docs.microsoft.com/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="4c4fe-109">[Guided Learning](https://docs.microsoft.com/learn/browse/?products=powerapps)</span></span>
    
- [<span data-ttu-id="4c4fe-110">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="4c4fe-110">Documentation</span></span>](https://docs.microsoft.com/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="4c4fe-111">ブックマークに PowerApp を追加する</span><span class="sxs-lookup"><span data-stu-id="4c4fe-111">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="4c4fe-112">PowerApps は、どのブラウザーやデバイスでも動作し、追加するのに 1 分かかりません。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-112">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="4c4fe-113">統合する[PowerApp のアプリ ID を検索](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)します。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-113">[Find the App ID for the PowerApp](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="4c4fe-114">Microsoft 検索管理ポータルで、[**ブックマーク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-114">In the Microsoft Search Admin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="4c4fe-115">PowerApp を追加するブックマークを追加するか、既存のブックマークを検索します。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-115">Add a bookmark or find an existing bookmark that you want to add a PowerApp to</span></span>
    
4. <span data-ttu-id="4c4fe-116">[ブックマークの設定] で、[ **Power app**] をクリックし、[ **Power app の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-116">In the bookmark settings, click **Power App**, and then click **Add a Power App**</span></span>
    
5. <span data-ttu-id="4c4fe-117">アプリ ID を入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-117">Enter or paste the App ID</span></span>
    
    <span data-ttu-id="4c4fe-118">高さと幅は自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-118">The height and width are automatically added.</span></span> <span data-ttu-id="4c4fe-119">ブックマークでは、縦向きと横向きの両方の向きはサポートされていますが、現在、サイズを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="4c4fe-120">ブックマークのプレビューは、PowerApp がブックマークの結果にどのように表示されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-120">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="4c4fe-121">プレビューの PowerApp は、テストと使用が容易になるように完全に機能します。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-121">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="4c4fe-122">[**発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-122">Click **Publish**</span></span>
    
<span data-ttu-id="4c4fe-123">承認された Microsoft 検索ユーザーが、任意のブックマークのキーワードまたは予約済みキーワードを使用して Bing で検索すると、PowerApp がブックマークの結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c4fe-123">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>
