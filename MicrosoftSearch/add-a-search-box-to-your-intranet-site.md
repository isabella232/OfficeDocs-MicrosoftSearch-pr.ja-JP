---
title: イントラネット サイトに検索ボックス追加
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
description: 関連検索候補を取得し、イントラネット サイトやページに Microsoft Search の検索ボックスを追加することによってより高速な作業の結果を検索します。
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612419"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>イントラネット サイトに検索ボックス追加

高速のアクセスに関連する検索の提案や作業の結果では、イントラネット サイトやページに Microsoft Search の検索ボックスを追加します。
  
## <a name="add-a-search-box-to-an-intranet-page"></a>イントラネット ページに検索ボックスを追加します。

2 つの要素をページに追加する必要があります: 検索ボックスと、それを補強するスクリプトのコンテナーです。
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

クラシック、SharePoint サイトにスクリプト エディター Web パーツの追加し、スクリプトを削除します。
  
## <a name="enable-the-search-box-for-mobile"></a>モバイルの検索] ボックスを有効にします。

イントラネット サイトまたはモバイル ユーザーが利用できるページは、isMobile を追加します。 true の場合、設定オブジェクト。
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>既定では、検索ボックスにフォーカスを移す

ページまたはサイトの負荷は、フォーカスを追加することによって検索ボックスにカーソルを置くより迅速に検索するユーザーを支援する: オブジェクトの設定を true に設定します。
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a>IFrame を使用して、検索ボックスを埋め込むには

スクリプトを埋め込み、サイトのオプションがない場合は場合、は、検索ボックスを追加するのには iFrame を使用します。
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
