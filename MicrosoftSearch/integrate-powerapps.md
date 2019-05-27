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
description: Microsoft Search のブックマーク結果にブラウザー ベースのアプリを組み込みます
ms.openlocfilehash: 96b409274e3fa06cef7dcc6f1c43360a3e6b9d34
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968383"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="31e56-103">PowerApps の統合</span><span class="sxs-lookup"><span data-stu-id="31e56-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="31e56-104">Bing の Microsoft Search の設定は、Microsoft 365 管理センターで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="31e56-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="31e56-105">まず、管理センターで[検索管理者を割り当てる](https://docs.microsoft.com/ja-JP/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor)ことから作業を開始します。</span><span class="sxs-lookup"><span data-stu-id="31e56-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="31e56-106">既存の PowerApps をブックマークに統合することで、休暇期間の入力や経費の報告などのユーザーのタスク実行を支援します。</span><span class="sxs-lookup"><span data-stu-id="31e56-106">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="31e56-107">統合された PowerApps はブックマークの結果内に表示されるため、別のサイトへの移動や別のツールを開く必要がなくなり、時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="31e56-107">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="31e56-108">PowerApps とはどういったものですか? </span><span class="sxs-lookup"><span data-stu-id="31e56-108">What are PowerApps?</span></span>

<span data-ttu-id="31e56-109">PowerApps は、コーディング経験がなくても、ブラウザーまたは携帯電話やタブレットで実行するビジネス アプリケーションを作成できるサービスです。</span><span class="sxs-lookup"><span data-stu-id="31e56-109">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="31e56-110">詳細情報:</span><span class="sxs-lookup"><span data-stu-id="31e56-110">Learn more:</span></span>
  
- <span data-ttu-id="31e56-111">
  [ガイド付き学習](https://docs.microsoft.com/ja-JP/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="31e56-111">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="31e56-112">
  [ドキュメント](https://docs.microsoft.com/ja-JP/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="31e56-112">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="31e56-113">ブックマークに PowerApp を追加する</span><span class="sxs-lookup"><span data-stu-id="31e56-113">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="31e56-114">PowerApps は、どのブラウザーやデバイスでも動作し、追加するのに 1 分もかかりません。</span><span class="sxs-lookup"><span data-stu-id="31e56-114">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="31e56-115">統合する [PowerApp の App ID を検索します](https://docs.microsoft.com/ja-JP/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)</span><span class="sxs-lookup"><span data-stu-id="31e56-115">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="31e56-116">Microsoft Search 管理ポータルで、**[ブックマーク]** に移動します</span><span class="sxs-lookup"><span data-stu-id="31e56-116">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="31e56-117">ブックマークを追加するか、PowerApp を追加する既存のブックマークを検索します。</span><span class="sxs-lookup"><span data-stu-id="31e56-117">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="31e56-118">[ブックマークの設定] で、**[Power App]** をクリックして、**[Power App の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31e56-118">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="31e56-119">App ID を入力するか貼り付けます</span><span class="sxs-lookup"><span data-stu-id="31e56-119">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="31e56-120">高さと幅が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="31e56-120">The height and width are automatically adjusted.</span></span> <span data-ttu-id="31e56-121">ブックマークでは、縦向きと横向きの両方の向きはサポートされていますが、現時点では、サイズの変更はできません。</span><span class="sxs-lookup"><span data-stu-id="31e56-121">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="31e56-122">ブックマーク プレビューには、PowerApp がブックマーク結果にどのように表示されるかが示されます。</span><span class="sxs-lookup"><span data-stu-id="31e56-122">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="31e56-123">プレビューの PowerApp は、テストおよび使用を簡単にするための完全な機能が備わっています。</span><span class="sxs-lookup"><span data-stu-id="31e56-123">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="31e56-124">**[公開]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="31e56-124">Click **Publish**.</span></span>
    
<span data-ttu-id="31e56-125">承認された Microsoft Search ユーザーがブックマークのキーワードまたは予約キーワードを検索すると、ブックマーク結果に PowerApp が表示されます。</span><span class="sxs-lookup"><span data-stu-id="31e56-125">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

