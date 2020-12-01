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
description: コネクタの結果のクラスター環境の詳細
ms.openlocfilehash: fa6ac2dc720ed43e40454b952526734accd45ea4
ms.sourcegitcommit: a328b9764abf5cd0c1c0a8c7def0c6e334da9a1d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477115"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="238f0-103">グラフコネクタの結果クラスター</span><span class="sxs-lookup"><span data-stu-id="238f0-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="238f0-104">グラフコネクタの結果クラスターの概要 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="238f0-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="238f0-105">グラフコネクタ結果クラスターを使用すると、エンタープライズは SharePoint および Office.com の既定のビュー ([すべて] タブ) でサードパーティのデータソースからコンテンツを検索できます。</span><span class="sxs-lookup"><span data-stu-id="238f0-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view (the All tab) in SharePoint and Office.com.</span></span>

<span data-ttu-id="238f0-106">結果クラスターは、1つの場所でサードパーティのコンテンツ (1 つのコネクタに関連付けられた previoulsy と縦向き) を検索するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="238f0-106">Result clusters help users discover all third party content (previoulsy tied to a single connector and vertical) in one place.</span></span> <span data-ttu-id="238f0-107">結果クラスターに表示される結果は、テナント管理者が検索垂直方向に構成する方法に基づいてグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="238f0-107">The results shown in a result cluster are grouped together based on how the tenant administrator configures them in a search vertical.</span></span>  

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="238f0-108">コネクタの結果が選択され、表示される方法</span><span class="sxs-lookup"><span data-stu-id="238f0-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="238f0-109">結果クラスターで提供されるコネクタの結果は、コネクタコンテンツを含む個々の検索業界から派生します。</span><span class="sxs-lookup"><span data-stu-id="238f0-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="238f0-110">各検索垂直は、結果クラスター候補となる関連結果のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="238f0-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="238f0-111">関連する結果は、各アイテムの "title" プロパティ、結果スニペット、およびコンテンツコンポーネントに基づいて選択されます。</span><span class="sxs-lookup"><span data-stu-id="238f0-111">Relevant results are chosen based on the "title" property, result snippet, and content component of each item.</span></span>

<span data-ttu-id="238f0-112">検索業界のコンテンツを確実に検出するには、アイテムに対してわかりやすいタイトルを提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="238f0-112">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="238f0-113">これは、結果クラスター候補の調停と、結果クラスターにコンテンツが表示される可能性に影響します。</span><span class="sxs-lookup"><span data-stu-id="238f0-113">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="238f0-114">たとえば、ユーザーがコンテンツを検索するために Id を使用していない場合は、プロパティ "title" の値として Id を使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="238f0-114">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="238f0-115">結果クラスターの表示頻度は、構成した検索単位数やコンテンツの種類などの要因によって異なります。</span><span class="sxs-lookup"><span data-stu-id="238f0-115">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="238f0-116">結果クラスターの結果を選択または無視することで、結果クラスターのトリガーを時間の経過と共に調整するヒントを暗黙的に提供します。</span><span class="sxs-lookup"><span data-stu-id="238f0-116">By either selecting or ignoring result cluster results, you will implicitly provide hints that will adjust the triggering of result clusters over time.</span></span>

<span data-ttu-id="238f0-117">結果クラスターに表示されるコネクタアイテムの検索結果の処理は、システムによって生成されたものであり、カスタムの結果レイアウトは使用されません。</span><span class="sxs-lookup"><span data-stu-id="238f0-117">The search result experience for connector items shown in your result cluster is system generated and does not use custom result layouts.</span></span> <span data-ttu-id="238f0-118">結果クラスターに結果を表示する場合は、接続登録時に "title" プロパティとアイテムの内容を宣言する必要があります。</span><span class="sxs-lookup"><span data-stu-id="238f0-118">You must declare the "title" property and item content during connection registration if you want results to appear in your result cluster.</span></span>

## <a name="enable-result-clusters"></a><span data-ttu-id="238f0-119">結果クラスターを有効にする</span><span class="sxs-lookup"><span data-stu-id="238f0-119">Enable result clusters</span></span>
  
<span data-ttu-id="238f0-120">結果のクラスターの機能は既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="238f0-120">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="238f0-121">次の手順に従って、組織レベルでの操作を有効にします。</span><span class="sxs-lookup"><span data-stu-id="238f0-121">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="238f0-122">[Microsoft 365 管理センター](https://admin.microsoft.com/)で、[**設定**  >  **検索 & インテリジェンス** のカスタマイズ] に移動  >  **Customization**  >  **Verticals** します。</span><span class="sxs-lookup"><span data-stu-id="238f0-122">In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to **Settings** > **Search & intelligence** > **Customization** > **Verticals**.</span></span>  
2. <span data-ttu-id="238f0-123">[ **すべて** の垂直] を選択してから、[ **コネクタの結果を表示** する] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="238f0-123">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="238f0-124">サイトレベルでの操作を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="238f0-124">Follow these steps to turn on the experience at the site level:</span></span>

1. <span data-ttu-id="238f0-125">検索結果のクラスター環境を使用する SharePoint サイトで、[ **設定**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="238f0-125">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="238f0-126">[**サイト情報**] の [ > **すべてのサイト設定**] を表示します。</span><span class="sxs-lookup"><span data-stu-id="238f0-126">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="238f0-127">[Microsoft Search] セクションに移動し、[ **このサイトコレクションの Microsoft 検索を構成** する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="238f0-127">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="238f0-128">ナビゲーションウィンドウで、[ **ユーザー設定の操作**] に移動して、[ **垂直**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="238f0-128">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="238f0-129">[ **すべて** の垂直] を選択してから、[ **コネクタの結果を表示** する] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="238f0-129">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="238f0-130">有効になった後の結果のクラスターの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="238f0-130">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="238f0-131">結果のクラスター環境を有効にした後は、表示するまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="238f0-131">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="238f0-132">すぐに使用できるようにする場合は、 *cacheClear = true* を SharePoint および OFFICE の URL に追加できます。</span><span class="sxs-lookup"><span data-stu-id="238f0-132">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
