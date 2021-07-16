---
title: イントラネット サイトに検索ボックス追加する
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
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: イントラネット サイトまたはページに検索ボックスを追加することで、関連する検索候補を取得し、Microsoft Search検索結果を迅速に検索できます。
ms.openlocfilehash: 7d9ca4be8d3be27a7549ffb940d6dc55b3763baf
ms.sourcegitcommit: 38a0f09596c2bca0e12bf4cada7b4c64fd4c48e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53449063"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="239a1-103">イントラネット サイトに検索ボックス追加する</span><span class="sxs-lookup"><span data-stu-id="239a1-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="239a1-104">ユーザーが組織の結果に簡単にアクセスできるよう、イントラネット サイトまたはMicrosoft SearchページにBingを追加します。</span><span class="sxs-lookup"><span data-stu-id="239a1-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="239a1-105">これらの利点の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="239a1-105">These are some of the benefits:</span></span>

- <span data-ttu-id="239a1-106">ユーザーまたはイントラネット ポータルのSharePointボックスは、検索を開始する使い慣れた信頼できるエントリ ポイントを提供します。</span><span class="sxs-lookup"><span data-stu-id="239a1-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="239a1-107">Google Chrome やアプリを含むすべての主要な Web ブラウザーをサポートMicrosoft Edge</span><span class="sxs-lookup"><span data-stu-id="239a1-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="239a1-108">組織からの検索候補だけが表示され、Web 候補は含まれません</span><span class="sxs-lookup"><span data-stu-id="239a1-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="239a1-109">広告と Web 結果をMicrosoft SearchするBing検索結果ページのユーザーを特定のユーザーに移動します。</span><span class="sxs-lookup"><span data-stu-id="239a1-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="239a1-110">既定の垂直または作成したカスタム垂直にユーザーを配置する機能など、検索ボックスの外観と動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="239a1-110">You control the appearance and behavior of the search box, including the ability to land users on a default vertical or a custom vertical you've created</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="239a1-111">イントラネット ページに検索ボックス追加する</span><span class="sxs-lookup"><span data-stu-id="239a1-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="239a1-112">検索ボックスのコンテナーと、それを動作させるスクリプトの 2 つの要素をページに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="239a1-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="239a1-113">従来の SharePoint サイトで、スクリプト エディターの Web パーツを追加し、これにスクリプトをドロップします。</span><span class="sxs-lookup"><span data-stu-id="239a1-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="239a1-114">モバイルの検索ボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="239a1-114">Enable the search box for mobile</span></span>

<span data-ttu-id="239a1-115">モバイル ユーザーがイントラネット サイトやページを利用できるようにするには、設定オブジェクトに isMobile: true を追加します。</span><span class="sxs-lookup"><span data-stu-id="239a1-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="239a1-116">既定で検索ボックスにフォーカスを置く</span><span class="sxs-lookup"><span data-stu-id="239a1-116">Put focus on the search box by default</span></span>

<span data-ttu-id="239a1-117">ユーザーの検索スピードを速めるために、設定オブジェクトに focus: true を追加して、ページやサイトが読み込まれたときにカーソルが検索ボックスに配置されるようにします。</span><span class="sxs-lookup"><span data-stu-id="239a1-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="239a1-118">検索ボックスの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="239a1-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="239a1-119">さまざまな構成オプションを利用して、イントラネットのスタイルに合った検索ボックスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="239a1-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="239a1-120">オプションを組み合わせて、ニーズに合わせます。</span><span class="sxs-lookup"><span data-stu-id="239a1-120">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: false
        iconColor: "#067FA6",                   // default: #067FA6
        title: "Search box",                    // default: "Search box"
        vertical: "Person-people",              // default: not specified, search box directs to the All vertical on the WORK results page
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="direct-users-to-a-default-or-custom-vertical"></a><span data-ttu-id="239a1-121">ユーザーを既定またはカスタムの垂直に移動する</span><span class="sxs-lookup"><span data-stu-id="239a1-121">Direct users to a default or custom vertical</span></span>

<span data-ttu-id="239a1-122">社内アプリやイントラネット サイトと作業結果との簡単な統合を実現するには、ユーザーが検索候補をクリックするときに設定する既定またはカスタムの垂直を指定して、検索ボックスをカスタマイズすることもできます。</span><span class="sxs-lookup"><span data-stu-id="239a1-122">To provide easy integration between your line-of-business apps or intranet sites and your work results, you can also customize the search box by specifying a default or custom vertical that users should land on when they click a search suggestion.</span></span>

<span data-ttu-id="239a1-123">bfbSearchBoxConfig の垂直オプションを使用して、必要な垂直方向を定義します。</span><span class="sxs-lookup"><span data-stu-id="239a1-123">Use the vertical option in bfbSearchBoxConfig to define the vertical you want.</span></span> <span data-ttu-id="239a1-124">たとえば、ユーザーが常にサイトの垂直方向に移動する場合は、既定の垂直方向の 1 つを使用して、値 "Site-sites" を使用します。</span><span class="sxs-lookup"><span data-stu-id="239a1-124">For example, if you want users to always land on the Sites vertical, one of the default verticals, use the value "Site-sites".</span></span>

:::image type="content" alt-text="[サイトの垂直方向の結果と URL] をMicrosoft SearchページBing画面の作業結果ページのスクリーンショット。" source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

<span data-ttu-id="239a1-126">カスタムバーティカルの場合は、URL の末尾にあるハッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="239a1-126">For custom verticals, use the hash at the end of the URL.</span></span> <span data-ttu-id="239a1-127">これらの値は、Bing の作業ページから検索し、垂直ラベルをクリックし、番号記号 (#)の後に値をコピーすることで確認できます。</span><span class="sxs-lookup"><span data-stu-id="239a1-127">You can find these values by searching from the work page on Bing, clicking a vertical label, and copying the value after the number sign (#).</span></span>

:::image type="content" alt-text="カスタムプレゼンテーションの垂直方向の結果と URL をMicrosoft SearchのBingの作業結果ページのスクリーンショット。" source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="239a1-129">iFrame を使用して検索ボックスを埋め込む</span><span class="sxs-lookup"><span data-stu-id="239a1-129">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="239a1-130">スクリプトの埋め込みがサイトでできない場合は、iFrame を使用して検索ボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="239a1-130">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="239a1-131">検索ボックスをカスタマイズできない。</span><span class="sxs-lookup"><span data-stu-id="239a1-131">You won't be able to customize the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a><span data-ttu-id="239a1-132">InPrivate モードと条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="239a1-132">InPrivate mode and Conditional Access</span></span>

<span data-ttu-id="239a1-133">ページまたはサイトが InPrivate ウィンドウで開いている場合、埋め込み検索ボックスは無効になります。</span><span class="sxs-lookup"><span data-stu-id="239a1-133">An embedded search box will be disabled if the page or site is opened in an InPrivate window.</span></span> <span data-ttu-id="239a1-134">また、Azure AD 条件付きアクセスのサポートが Microsoft Edge の場合、Bing.com は InPrivate モードを使用する場合、AAD サインインをサポートしません。</span><span class="sxs-lookup"><span data-stu-id="239a1-134">Also, with Azure AD Conditional Access support in Microsoft Edge, Bing.com doesn't support AAD sign in when using InPrivate mode.</span></span> <span data-ttu-id="239a1-135">エッジの条件付きアクセスの詳細については、「条件付きアクセス」[および「Microsoft Edgeアクセス」を参照してください](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)。</span><span class="sxs-lookup"><span data-stu-id="239a1-135">For more information about Conditional Access in Edge, see [Microsoft Edge and Conditional Access](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge).</span></span> 
