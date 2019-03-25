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
description: 関連する検索候補や作業結果にすばやくアクセスするために、イントラネット サイトやページに Microsoft Search の検索ボックスを追加します。
ms.openlocfilehash: a66c0cea71cf637209d298f49542864755e92ec9
ms.sourcegitcommit: c18809f57f957de958a87e940dc3904061fe0bd0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2019
ms.locfileid: "30789315"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>イントラネット サイトに検索ボックス追加する

関連する検索候補や作業結果にすばやくアクセスするために、任意のイントラネット サイトやページに Microsoft Search の検索ボックスを追加します。
  
## <a name="add-a-search-box-to-an-intranet-page"></a>イントラネット ページに検索ボックス追加する

検索ボックスのコンテナーと、それを動作させるスクリプトの 2 つの要素をページに追加する必要があります。
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

従来の SharePoint サイトで、スクリプト エディターの Web パーツを追加し、これにスクリプトをドロップします。
  
## <a name="enable-the-search-box-for-mobile"></a>モバイルの検索ボックスを有効にする

モバイル ユーザーがイントラネット サイトやページを利用できるようにするには、設定オブジェクトに isMobile: true を追加します。
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>既定で検索ボックスにフォーカスを置く

ユーザーの検索スピードを速めるために、設定オブジェクトに focus: true を追加して、ページやサイトが読み込まれたときにカーソルが検索ボックスに配置されるようにします。
  
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

## <a name="customize-the-appearance-of-the-search-box"></a>検索ボックスの外観をカスタマイズする 

さまざまな構成オプションを利用して、イントラネットのスタイルに合った検索ボックスにすることができます。 オプションを組み合わせて、ニーズに合わせます。

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

## <a name="use-an-iframe-to-embed-a-search-box"></a>iFrame を使用して検索ボックスを埋め込む

スクリプトの埋め込みがサイトでできない場合は、iFrame を使用して検索ボックスを追加します。 検索ボックスの外観はカスタマイズできません。
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```