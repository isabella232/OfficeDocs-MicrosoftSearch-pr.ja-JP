---
title: イントラネット サイトに検索ボックス追加する
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: 関連する検索候補や作業結果にすばやくアクセスするために、イントラネット サイトやページに Microsoft Search の検索ボックスを追加します。
ms.openlocfilehash: 867282393c7a4bffa63363a3455e4f1543c7f8a1
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590695"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="6dd6a-103">イントラネット サイトに検索ボックスを追加する</span><span class="sxs-lookup"><span data-stu-id="6dd6a-103">Add a search box to your intranet site</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6dd6a-104">この記事は、Bing 管理ポータルの Microsoft Search に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="6dd6a-105">ポータルを Microsoft 365 管理センター に移動しており、後で削除されます。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="6dd6a-106">Microsoft 365 管理センターを使用して作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="6dd6a-107">[Microsoft Search の概要](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-107">Overview of Microsoft Search</span></span>

<span data-ttu-id="6dd6a-108">関連する検索候補や作業結果にすばやくアクセスするために、任意のイントラネット サイトやページに Microsoft Search の検索ボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-108">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="6dd6a-109">イントラネット ページに検索ボックス追加する</span><span class="sxs-lookup"><span data-stu-id="6dd6a-109">Add a search box to an intranet page</span></span>

<span data-ttu-id="6dd6a-110">検索ボックスのコンテナーと、それを動作させるスクリプトの 2 つの要素をページに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-110">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="6dd6a-111">従来の SharePoint サイトで、スクリプト エディターの Web パーツを追加し、これにスクリプトをドロップします。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-111">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="6dd6a-112">モバイルの検索ボックスを有効にする</span><span class="sxs-lookup"><span data-stu-id="6dd6a-112">Enable the search box for mobile</span></span>

<span data-ttu-id="6dd6a-113">モバイル ユーザーがイントラネット サイトやページを利用できるようにするには、設定オブジェクトに isMobile: true を追加します。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-113">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="6dd6a-114">既定で検索ボックスにフォーカスを置く</span><span class="sxs-lookup"><span data-stu-id="6dd6a-114">Put focus on the search box by default</span></span>

<span data-ttu-id="6dd6a-115">ユーザーの検索スピードを速めるために、設定オブジェクトに focus: true を追加して、ページやサイトが読み込まれたときにカーソルが検索ボックスに配置されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-115">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="6dd6a-116">検索ボックスの外観をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="6dd6a-116">Customize the appearance of the search box</span></span> 

<span data-ttu-id="6dd6a-117">さまざまな構成オプションを利用して、イントラネットのスタイルに合った検索ボックスにすることができます。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-117">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="6dd6a-118">オプションを組み合わせて、ニーズに合わせます。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-118">Mix and match options to suit your needs.</span></span>

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
                                                // when absent, ghost text will be "Search work and the web"
                                                // when specified, text will be "Search the web and [Contoso]"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="6dd6a-119">iFrame を使用して検索ボックスを埋め込む</span><span class="sxs-lookup"><span data-stu-id="6dd6a-119">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="6dd6a-120">スクリプトの埋め込みがサイトでできない場合は、iFrame を使用して検索ボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-120">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="6dd6a-121">検索ボックスの外観はカスタマイズできません。</span><span class="sxs-lookup"><span data-stu-id="6dd6a-121">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```