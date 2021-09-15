---
title: イントラネット サイトに検索ボックス追加する
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: イントラネット サイトまたはページに検索ボックスを追加することで、関連する検索候補を取得し、Microsoft Search検索結果を迅速に検索できます。
ms.openlocfilehash: d9f730eee98291d64e1f860c67be3eb7aa52a4a8
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375859"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>イントラネット サイトに検索ボックス追加する

ユーザーが組織の結果に簡単にアクセスできるよう、イントラネット サイトまたはMicrosoft SearchページにBingを追加します。 これらの利点の一部を次に示します。

- ユーザーまたはイントラネット ポータルのSharePointボックスは、検索を開始する使い慣れた信頼できるエントリ ポイントを提供します。
- Google Chrome やアプリを含むすべての主要な Web ブラウザーをサポートMicrosoft Edge
- 組織からの検索候補だけが表示され、Web 候補は含まれません
- 広告と Web 結果をMicrosoft SearchするBing検索結果ページのユーザーを特定のユーザーに移動します。
- 既定の垂直または作成したカスタム垂直にユーザーを配置する機能など、検索ボックスの外観と動作を制御します。
  
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

## <a name="direct-users-to-a-default-or-custom-vertical"></a>ユーザーを既定またはカスタムの垂直に移動する

社内アプリやイントラネット サイトと作業結果との簡単な統合を実現するには、ユーザーが検索候補をクリックするときに設定する既定またはカスタムの垂直を指定して、検索ボックスをカスタマイズすることもできます。

bfbSearchBoxConfig の垂直オプションを使用して、必要な垂直方向を定義します。 たとえば、ユーザーが常にサイトの垂直方向に移動する場合は、既定の垂直方向の 1 つを使用して、値 "Site-sites" を使用します。

:::image type="content" alt-text="[サイトの垂直方向の結果と URL] をMicrosoft SearchページBing画面の作業結果ページのスクリーンショット。" source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

カスタムバーティカルの場合は、URL の末尾にあるハッシュを使用します。 これらの値は、Bing の作業ページから検索し、垂直ラベルをクリックし、番号記号 (#)の後に値をコピーすることで確認できます。

:::image type="content" alt-text="カスタムプレゼンテーションの垂直方向の結果と URL をMicrosoft SearchのBingの作業結果ページのスクリーンショット。" source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a>iFrame を使用して検索ボックスを埋め込む

スクリプトの埋め込みがサイトでできない場合は、iFrame を使用して検索ボックスを追加します。 検索ボックスをカスタマイズできない。
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a>InPrivate モードと条件付きアクセス

ページまたはサイトが InPrivate ウィンドウで開いている場合、埋め込み検索ボックスは無効になります。 また、Azure AD 条件付きアクセスのサポートが Microsoft Edge の場合、Bing.com は InPrivate モードを使用する場合、AAD サインインをサポートしません。 エッジの条件付きアクセスの詳細については、「条件付きアクセス」[および「Microsoft Edgeアクセス」を参照してください](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)。 
