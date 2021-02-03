---
title: コネクタの結果クラスター
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: コネクタの結果クラスター エクスペリエンスの詳細
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080839"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="0d85e-103">グラフ コネクタの結果クラスター</span><span class="sxs-lookup"><span data-stu-id="0d85e-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="0d85e-104">Graph コネクタの結果クラスターの概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="0d85e-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="0d85e-105">Graph コネクタの結果クラスターを使用すると、企業は既定のビューでサード パーティのデータ ソースのコンテンツを検索できます。[すべて] タブ、SharePoint、Office.com、および Bing の Microsoft Search で検索できます。</span><span class="sxs-lookup"><span data-stu-id="0d85e-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="0d85e-106">結果クラスターは、ユーザーがすべてのサード パーティコンテンツを 1 か所で検出するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0d85e-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="0d85e-107">結果クラスターに表示される結果は、バーティカル検索の構成に基づいてグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="0d85e-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="0d85e-108">コネクタの結果を選択して表示する方法</span><span class="sxs-lookup"><span data-stu-id="0d85e-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="0d85e-109">結果クラスターで提供されるコネクタの結果は、コネクタ コンテンツを含む個々のバーティカル検索から派生します。</span><span class="sxs-lookup"><span data-stu-id="0d85e-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="0d85e-110">各バーティカル検索では、候補の結果クラスターとなる関連する結果のセットが提供されます。</span><span class="sxs-lookup"><span data-stu-id="0d85e-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="0d85e-111">関連する結果は、各アイテムの "title" プロパティと "content" プロパティに基づいて選択されます。</span><span class="sxs-lookup"><span data-stu-id="0d85e-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="0d85e-112">スキーマでは、コンテンツ プロパティは *isContent=true として* マークされます。</span><span class="sxs-lookup"><span data-stu-id="0d85e-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="0d85e-113">バーティカル検索からコンテンツを確実に検出するには、アイテムに意味のあるタイトルを提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d85e-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="0d85e-114">これは、結果クラスター候補の判定と、コンテンツが結果クラスターに表示される可能性にプラスの影響を与える。</span><span class="sxs-lookup"><span data-stu-id="0d85e-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="0d85e-115">たとえば、ユーザーがコンテンツの検索に ID を使用しない限り、プロパティ "title" の値として ID を使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="0d85e-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="0d85e-116">結果クラスターが表示される頻度は、構成するバーティカル検索の数やコンテンツの種類などの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0d85e-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="0d85e-117">結果クラスターを操作または無視することで、ユーザーは時間の間にトリガーを調整するヒントを暗黙的に提供します。</span><span class="sxs-lookup"><span data-stu-id="0d85e-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="0d85e-118">結果クラスターに表示されるコネクタ アイテムの検索結果エクスペリエンスでは、ユーザーが定義 [した結果の種類](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) を使用します。</span><span class="sxs-lookup"><span data-stu-id="0d85e-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="0d85e-119">結果の種類が構成されていない場合は、 [システムによって生成されたレイアウトが](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) 使用されます。</span><span class="sxs-lookup"><span data-stu-id="0d85e-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="0d85e-120">検索結果のタイトルとして "title" プロパティを使用し、検索の説明として "content" プロパティを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0d85e-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="0d85e-121">これにより、クラスター内で結果クラスターと最も関連性の高い結果を正確にトリガーして、ユーザーに最適なエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0d85e-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="0d85e-122">結果クラスターを有効にする</span><span class="sxs-lookup"><span data-stu-id="0d85e-122">Enable result clusters</span></span>
  
<span data-ttu-id="0d85e-123">結果クラスター エクスペリエンスは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0d85e-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="0d85e-124">組織レベルでエクスペリエンスを有効にする手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0d85e-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="0d85e-125">Microsoft [365 管理センターで、[](https://admin.microsoft.com)バーティカル] に [**移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)。</span><span class="sxs-lookup"><span data-stu-id="0d85e-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="0d85e-126">[すべて] **バーティ** カルを選択し、[ **コネクタの結果を表示する] を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="0d85e-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="0d85e-127">SharePoint サイト レベルでエクスペリエンスを有効にする手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0d85e-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="0d85e-128">結果クラスターエクスペリエンスを使用する SharePoint サイトで、[設定] に移動 **します**。</span><span class="sxs-lookup"><span data-stu-id="0d85e-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="0d85e-129">[サイト情報 **] に移動** > **します。すべてのサイト設定を表示します**。</span><span class="sxs-lookup"><span data-stu-id="0d85e-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="0d85e-130">[Microsoft Search] セクションに移動し、[このサイト コレクション **の Microsoft Search の構成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d85e-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="0d85e-131">ナビゲーション ウィンドウで、カスタム エクスペリエンスに移動 **し、[** バーティカル] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="0d85e-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="0d85e-132">[すべて] **バーティ** カルを選択し、[ **コネクタの結果を表示する] を有効にする**。</span><span class="sxs-lookup"><span data-stu-id="0d85e-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="0d85e-133">有効にした後、結果クラスターのエクスペリエンスを表示する</span><span class="sxs-lookup"><span data-stu-id="0d85e-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="0d85e-134">結果クラスター エクスペリエンスを有効にした後、表示するには最大 12 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0d85e-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="0d85e-135">エクスペリエンスをすぐに必要にする場合は、sharePoint の URL に *cacheClear=true* を追加して、次のOffice。</span><span class="sxs-lookup"><span data-stu-id="0d85e-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
