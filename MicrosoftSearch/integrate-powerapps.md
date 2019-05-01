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
description: Microsoft Search のブックマーク検索結果にブラウザーベースのアプリを含める
ms.openlocfilehash: d8d9d099848e719c86e0f3cadee330263566d243
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508827"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="76f03-103">PowerApps の統合</span><span class="sxs-lookup"><span data-stu-id="76f03-103">Integrate PowerApps</span></span>

<span data-ttu-id="76f03-104">休暇の入力や、既存の PowerApps をブックマークに統合することによる経費の報告など、ユーザーがタスクを完了できるようにします。</span><span class="sxs-lookup"><span data-stu-id="76f03-104">Help your users complete tasks, such as entering vacation time or reporting expenses by integrating existing PowerApps into your bookmarks.</span></span> <span data-ttu-id="76f03-105">統合 PowerApps はブックマークの結果内に表示されます。別のサイトに移動したり、別のツールを開いたりする必要がなくなり、時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="76f03-105">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="76f03-106">PowerApps とは</span><span class="sxs-lookup"><span data-stu-id="76f03-106">What are PowerApps?</span></span>

<span data-ttu-id="76f03-107">PowerApps は、ブラウザーまたは携帯電話やタブレットで実行されるビジネスアプリを、コーディング操作を必要とせずに作成できるサービスです。</span><span class="sxs-lookup"><span data-stu-id="76f03-107">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="76f03-108">詳細については、次の項目を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76f03-108">Learn more:</span></span>
  
- [<span data-ttu-id="76f03-109">ガイド付き学習</span><span class="sxs-lookup"><span data-stu-id="76f03-109">Guided Learning</span></span>](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="76f03-110">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="76f03-110">Documentation</span></span>](https://docs.microsoft.com/en-us/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="76f03-111">ブックマークに powerapp を追加する</span><span class="sxs-lookup"><span data-stu-id="76f03-111">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="76f03-112">PowerApps は任意のブラウザーおよび任意のデバイスで使用できます。追加するには、1分以内にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76f03-112">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="76f03-113">統合する[powerapp のアプリ ID を検索](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)する</span><span class="sxs-lookup"><span data-stu-id="76f03-113">[Find the App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate</span></span> 
    
2. <span data-ttu-id="76f03-114">Microsoft searchadmin ポータルで、[**ブックマーク**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="76f03-114">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="76f03-115">powerapp を追加するブックマークを追加するか、既存のブックマークを検索します。</span><span class="sxs-lookup"><span data-stu-id="76f03-115">Add a bookmark or find an existing bookmark that you want to add a PowerApp to</span></span>
    
4. <span data-ttu-id="76f03-116">[ブックマークの設定] で、[ **power app**] をクリックし、[ **power app の追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76f03-116">In the bookmark settings, click **Power App**, and then click **Add a Power App**</span></span>
    
5. <span data-ttu-id="76f03-117">アプリ ID を入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="76f03-117">Enter or paste the App ID</span></span>
    
    <span data-ttu-id="76f03-118">高さと幅は自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="76f03-118">The height and width are automatically added.</span></span> <span data-ttu-id="76f03-119">ブックマークは縦方向と横方向の両方をサポートできますが、現在サイズを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="76f03-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="76f03-120">ブックマークのプレビューは、powerapp がブックマークの結果にどのように表示されるかを示しています。</span><span class="sxs-lookup"><span data-stu-id="76f03-120">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="76f03-121">プレビューの powerapp は、テストと使用が容易になるように完全に機能します。</span><span class="sxs-lookup"><span data-stu-id="76f03-121">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="76f03-122">[**発行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="76f03-122">Click **Publish**</span></span>
    
<span data-ttu-id="76f03-123">承認された Microsoft 検索ユーザーが、任意のブックマークのキーワードまたは予約済みキーワードを使用して Bing で検索すると、powerapp がブックマークの結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="76f03-123">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

