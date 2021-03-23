---
title: Power Apps の統合
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Microsoft Search のブックマーク結果にブラウザー ベースのアプリを含める
ms.openlocfilehash: 52fa78c54ab6db74ef1e3679d3d32151a3f5ac10
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031703"
---
# <a name="integrate-power-apps-in-microsoft-search-bookmarks"></a><span data-ttu-id="f6584-103">Microsoft Search ブックマークに Power Apps を統合する</span><span class="sxs-lookup"><span data-stu-id="f6584-103">Integrate Power Apps in Microsoft Search bookmarks</span></span>
   
<span data-ttu-id="f6584-104">既存の [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) を Microsoft Search ブックマークに統合することで、ユーザーが休暇時間の入力や経費の報告など、タスクを完了するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f6584-104">Help your users complete tasks, like entering vacation time or reporting expenses, by integrating existing [Microsoft Power Apps](https://products.office.com/business/microsoft-powerapps) into your Microsoft Search bookmarks.</span></span> <span data-ttu-id="f6584-105">統合された Power Apps はブックマークの結果内に表示され、別のサイトに移動したり、別のツールを開く必要がなくなります。時間と労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="f6584-105">Integrated Power Apps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-power-apps"></a><span data-ttu-id="f6584-106">Power Apps とは</span><span class="sxs-lookup"><span data-stu-id="f6584-106">What are Power Apps?</span></span>

<span data-ttu-id="f6584-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) は、コーディングエクスペリエンスが不要なブラウザーまたは携帯電話やタブレットで実行されるビジネス アプリを構築できるサービスです。</span><span class="sxs-lookup"><span data-stu-id="f6584-107">[Power Apps](https://products.office.com/business/microsoft-powerapps) is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="f6584-108">詳細情報:</span><span class="sxs-lookup"><span data-stu-id="f6584-108">Learn more:</span></span>
  
- [<span data-ttu-id="f6584-109">ガイド付き学習</span><span class="sxs-lookup"><span data-stu-id="f6584-109">Guided Learning</span></span>](/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="f6584-110">ドキュメント</span><span class="sxs-lookup"><span data-stu-id="f6584-110">Documentation</span></span>](/powerapps/)
    
## <a name="add-a-power-app-to-a-bookmark"></a><span data-ttu-id="f6584-111">ブックマークに Power App を追加する</span><span class="sxs-lookup"><span data-stu-id="f6584-111">Add a Power App to a bookmark</span></span>

<span data-ttu-id="f6584-112">[Power Apps( work in any browser and any device and take less less https://products.office.com/business/microsoft-powerapps) 1 minute to add.</span><span class="sxs-lookup"><span data-stu-id="f6584-112">[Power Apps(https://products.office.com/business/microsoft-powerapps) work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="f6584-113">[統合する Power アプリのアプリ ID](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) を見つける。</span><span class="sxs-lookup"><span data-stu-id="f6584-113">[Find the App ID for the Power App](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate.</span></span>
    
2. <span data-ttu-id="f6584-114">Microsoft 365 [管理センターで、[](https://admin.microsoft.com)ブックマーク] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f6584-114">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Bookmarks**.</span></span>
    
3. <span data-ttu-id="f6584-115">ブックマークを追加するか、Power App を追加する既存のブックマークを検索します。</span><span class="sxs-lookup"><span data-stu-id="f6584-115">Add a bookmark or find an existing bookmark that you want to add a Power App to.</span></span>
    
4. <span data-ttu-id="f6584-116">ブックマークの設定で **、[Power App] を選択** し、[Power App の **追加] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f6584-116">In the bookmark settings, select **Power App**, and then select **Add a Power App**.</span></span>
    
5. <span data-ttu-id="f6584-117">App ID を入力するか貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="f6584-117">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="f6584-118">高さと幅が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="f6584-118">The height and width are automatically added.</span></span> <span data-ttu-id="f6584-119">ブックマークでは、縦向きと横向きの両方の向きはサポートされていますが、現在、サイズを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="f6584-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="f6584-120">ブックマーク プレビューは、Power App がブックマークの結果に表示される方法を示します。</span><span class="sxs-lookup"><span data-stu-id="f6584-120">The bookmark preview shows how the Power App will appear in the bookmark result.</span></span>
    
    <span data-ttu-id="f6584-121">プレビューの Power App は完全に機能し、テストと使用が容易になります。</span><span class="sxs-lookup"><span data-stu-id="f6584-121">The Power App in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="f6584-122">[**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f6584-122">Select **Publish**.</span></span>
    
<span data-ttu-id="f6584-123">承認された Microsoft Search ユーザーが [Bing](https://Bing.com) でブックマークのキーワードまたは予約済みキーワードを検索すると、ブックマークの結果に Power App が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f6584-123">When an authorized Microsoft Search user searches on [Bing](https://Bing.com) for any of the bookmark's keywords or reserved keywords, the Power App will appear in the bookmark result.</span></span>