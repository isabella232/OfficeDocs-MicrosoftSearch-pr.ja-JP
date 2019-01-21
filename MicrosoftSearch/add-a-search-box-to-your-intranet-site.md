---
title: イントラネット サイトに検索ボックスを追加します。
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
description: 関連検索候補を取得し、イントラネット サイトやページに Microsoft Search の検索ボックスを追加することによってより高速な作業の結果を検索します。
ms.openlocfilehash: a27b4d79e8795cdd2749c12119709f97710061e7
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379098"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="93e49-103">イントラネット サイトに検索ボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="93e49-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="93e49-104">高速のアクセスに関連する検索の提案や作業の結果では、イントラネット サイトやページに Microsoft Search の検索ボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="93e49-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="93e49-105">イントラネット ページに検索ボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="93e49-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="93e49-106">2 つの要素をページに追加する必要があります: 検索ボックスと、それを補強するスクリプトのコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="93e49-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="93e49-107">クラシック、SharePoint サイトにスクリプト エディター Web パーツの追加し、スクリプトを削除します。</span><span class="sxs-lookup"><span data-stu-id="93e49-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="93e49-108">モバイルの検索] ボックスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="93e49-108">Enable the search box for mobile</span></span>

<span data-ttu-id="93e49-109">イントラネット サイトまたはモバイル ユーザーが利用できるページは、isMobile を追加します。 true の場合、設定オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="93e49-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="93e49-110">既定では、検索ボックスにフォーカスを移す</span><span class="sxs-lookup"><span data-stu-id="93e49-110">Put focus on the search box by default</span></span>

<span data-ttu-id="93e49-111">ページまたはサイトの負荷は、フォーカスを追加することによって検索ボックスにカーソルを置くより迅速に検索するユーザーを支援する: オブジェクトの設定を true に設定します。</span><span class="sxs-lookup"><span data-stu-id="93e49-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="93e49-112">IFrame を使用して、検索ボックスを埋め込むには</span><span class="sxs-lookup"><span data-stu-id="93e49-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="93e49-113">スクリプトを埋め込み、サイトのオプションがない場合は場合、は、検索ボックスを追加するのには iFrame を使用します。</span><span class="sxs-lookup"><span data-stu-id="93e49-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
