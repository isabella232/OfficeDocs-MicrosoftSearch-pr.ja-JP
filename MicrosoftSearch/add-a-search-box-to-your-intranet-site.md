---
title: イントラネット サイトに検索ボックス追加する
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
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
description: 関連する検索候補や作業結果にすばやくアクセスするために、イントラネット サイトやページに Microsoft Search の検索ボックスを追加します。
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798227"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="8dfb5-103">イントラネット サイトに検索ボックス追加する</span><span class="sxs-lookup"><span data-stu-id="8dfb5-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="8dfb5-104">ユーザーが組織からの結果に簡単にアクセスできるようにするには、Bing 検索ボックスで、Microsoft Search を任意のイントラネットサイトまたはページに追加します。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="8dfb5-105">次にいくつかの利点を示します。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-105">These are some of the benefits:</span></span>

- <span data-ttu-id="8dfb5-106">SharePoint またはイントラネットポータルの検索ボックスには、検索を開始するための、なじみのある信頼できるエントリポイントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="8dfb5-107">Google Chrome および Microsoft Edge を含む、すべての主要な web ブラウザーをサポートします。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="8dfb5-108">組織からの検索候補のみが表示され、web 提案は含まれません。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="8dfb5-109">ユーザーが Bing の作業結果ページで Microsoft Search を実行して、広告と web の結果を除外します。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="8dfb5-110">検索ボックスの外観と動作を制御する</span><span class="sxs-lookup"><span data-stu-id="8dfb5-110">You control the appearance and behavior of the search box</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="8dfb5-111">イントラネット ページに検索ボックス追加する</span><span class="sxs-lookup"><span data-stu-id="8dfb5-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="8dfb5-112">検索ボックスのコンテナーと、それを動作させるスクリプトの 2 つの要素をページに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="8dfb5-113">従来の SharePoint サイトで、スクリプト エディターの Web パーツを追加し、これにスクリプトをドロップします。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="8dfb5-114">モバイルの検索ボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="8dfb5-114">Enable the search box for mobile</span></span>

<span data-ttu-id="8dfb5-115">モバイル ユーザーがイントラネット サイトやページを利用できるようにするには、設定オブジェクトに isMobile: true を追加します。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="8dfb5-116">既定で検索ボックスにフォーカスを置く</span><span class="sxs-lookup"><span data-stu-id="8dfb5-116">Put focus on the search box by default</span></span>

<span data-ttu-id="8dfb5-117">ユーザーの検索スピードを速めるために、設定オブジェクトに focus: true を追加して、ページやサイトが読み込まれたときにカーソルが検索ボックスに配置されるようにします。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="8dfb5-118">検索ボックスの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="8dfb5-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="8dfb5-119">さまざまな構成オプションを利用して、イントラネットのスタイルに合った検索ボックスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="8dfb5-120">オプションを組み合わせて、ニーズに合わせます。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-120">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="8dfb5-121">iFrame を使用して検索ボックスを埋め込む</span><span class="sxs-lookup"><span data-stu-id="8dfb5-121">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="8dfb5-122">スクリプトの埋め込みがサイトでできない場合は、iFrame を使用して検索ボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-122">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="8dfb5-123">検索ボックスの外観はカスタマイズできません。</span><span class="sxs-lookup"><span data-stu-id="8dfb5-123">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
