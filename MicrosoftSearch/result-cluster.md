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
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773029"
---
# <a name="graph-connectors-result-cluster"></a>グラフ コネクタの結果クラスター

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>Graph コネクタの結果クラスターの概要 (プレビュー)  

Graph コネクタの結果クラスターを使用すると、企業は既定のビューでサード パーティのデータ ソースのコンテンツ、SharePoint、Office.com、Bing の Microsoft Search の [すべて] タブを検索できます。

結果クラスターは、ユーザーがすべてのサード パーティコンテンツを 1 か所で検出するのに役立ちます。 結果クラスターに表示される結果は、バーティカル検索の構成に基づいてグループ化されます。

## <a name="how-connector-results-are-selected-and-displayed"></a>コネクタの結果を選択して表示する方法

結果クラスターで提供されるコネクタの結果は、コネクタ コンテンツを含む個々のバーティカル検索から得られます。 各バーティカル検索では、候補の結果クラスターとなる関連する結果のセットが提供されます。 関連する結果は、各アイテムの "title" プロパティと "content" プロパティに基づいて選択されます。 スキーマでは、コンテンツ プロパティは *isContent=true として* マークされます。

バーティカル検索からコンテンツを確実に検出するには、アイテムに意味のあるタイトルを提供することをお勧めします。 これは、結果クラスター候補の判定と、結果クラスターにコンテンツが表示される可能性にプラスの影響を与える。 たとえば、ユーザーがコンテンツの検索に ID を使用しない限り、プロパティ "title" の値として ID を使用しないようにします。

結果クラスターが表示される頻度は、構成するバーティカル検索の数やコンテンツの種類などの要因によって異なります。 結果クラスターを操作または無視することで、ユーザーは時間の間にトリガーを調整するヒントを暗黙的に提供します。

結果クラスターに表示されるコネクタ アイテムの検索結果エクスペリエンスでは、ユーザーが定義 [した結果の種類](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) を使用します。 結果の種類が構成されていない場合は、 [システムによって生成されたレイアウトが](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) 使用されます。 

検索結果のタイトルとして "title" プロパティを使用し、検索の説明として "content" プロパティを使用することをお勧めします。 これにより、クラスター内で結果クラスターと最も関連性の高い結果を正確にトリガーして、ユーザーに最適なエクスペリエンスを提供できます。 

## <a name="enable-result-clusters"></a>結果クラスターを有効にする
  
結果クラスター エクスペリエンスは既定で無効になっています。  

組織レベルでエクスペリエンスを有効にする手順は次のとおりです。

1. Microsoft [365 管理センターで、[](https://admin.microsoft.com)バーティカル] に [**移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)。
2. [すべて] **バーティ** カルを選択し、[ **コネクタの結果を表示する] を有効にする**。 


SharePoint サイト レベルでエクスペリエンスを有効にする手順は次のとおりです。

1. 結果クラスターエクスペリエンスを使用する SharePoint サイトで、[設定] に移動 **します**。
2. [サイト情報 **] に移動** > **します。すべてのサイト設定を表示します**。
3. [Microsoft Search] セクションに移動し、[このサイト コレクション **の Microsoft Search の構成] を選択します**。
4. ナビゲーション ウィンドウで、カスタム エクスペリエンスに移動 **し、[** バーティカル] **を選択します**。
5. [すべて] **バーティ** カルを選択し、[ **コネクタの結果を表示する] を有効にする**。

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>有効にした後、結果クラスターのエクスペリエンスを表示する

結果クラスター エクスペリエンスを有効にした後、表示するには数分かかる場合があります。 エクスペリエンスをすぐに必要にする場合は、sharePoint の URL に *cacheClear=true* を追加して、次のOffice。
