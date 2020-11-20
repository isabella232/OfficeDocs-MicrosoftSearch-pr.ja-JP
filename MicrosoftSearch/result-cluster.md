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
ms.openlocfilehash: eac4180a247fe17b4e86b57a69f2b7bdb79e56bb
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367746"
---
# <a name="graph-connectors-result-cluster"></a>グラフコネクタの結果クラスター

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a>グラフコネクタの結果クラスターの概要 (プレビュー)  

 グラフコネクタ結果クラスターを使用すると、エンタープライズは SharePoint および Office.com の既定のビュー ([すべて] タブ) でサードパーティのデータソースからコンテンツを検索できます。

結果クラスターは、1つの場所でサードパーティのコンテンツ (1 つのコネクタに関連付けられた previoulsy と縦向き) を検索するのに役立ちます。 結果クラスターに表示される結果は、テナント管理者が検索垂直方向に構成する方法に基づいてグループ化されます。  

## <a name="how-connector-results-are-selected-and-displayed"></a>コネクタの結果が選択され、表示される方法

結果クラスターで提供されるコネクタの結果は、コネクタコンテンツを含む個々の検索業界から派生します。 各検索垂直は、結果クラスター候補となる関連結果のセットを提供します。 関連する結果は、各アイテムの "title" プロパティ、結果スニペット、およびコンテンツコンポーネントに基づいて選択されます。

検索業界のコンテンツを確実に検出するには、アイテムに対してわかりやすいタイトルを提供することをお勧めします。 これは、結果クラスター候補の調停と、結果クラスターにコンテンツが表示される可能性に影響します。 たとえば、ユーザーがコンテンツを検索するために Id を使用していない場合は、プロパティ "title" の値として Id を使用しないようにします。

結果クラスターの表示頻度は、構成した検索単位数やコンテンツの種類などの要因によって異なります。 結果クラスターの結果を選択または無視することで、結果クラスターのトリガーを時間の経過と共に調整するヒントを暗黙的に提供します。

結果クラスターに表示されるコネクタアイテムの検索結果の処理は、システムによって生成されたものであり、カスタムの結果レイアウトは使用されません。 結果クラスターに結果を表示する場合は、接続登録時に "title" プロパティとアイテムの内容を宣言する必要があります。

## <a name="enable-result-clusters"></a>結果クラスターを有効にする
  
結果のクラスターの機能は既定で無効になっています。  
次の手順に従って、組織レベルでの操作を有効にします。

Microsoft 365 管理センター

1. [Microsoft 365 管理センター](https://admin.microsoft.com/)で、[**設定**  >  **検索 & インテリジェンス** のカスタマイズ] に移動  >  **Customization**  >  **Verticals** します。  
2. [ **すべて** 縦] を選択し、[ **コネクタの結果を表示** ] セクションに移動します。 サイトレベルで快適な表示を有効にします。

Sharepoint

1. 検索結果のクラスター環境を使用する SharePoint サイトで、[ **設定**] に移動します。
2. [**サイト情報**] の [ > **すべてのサイト設定**] を表示します。
3. [Microsoft Search] セクションに移動し、[ **このサイトコレクションの Microsoft 検索を構成** する] を選択します。
4. ナビゲーションウィンドウで、[ **ユーザー設定の操作**] に移動して、[ **垂直**] を選択します。
5. [ **すべて** の垂直] を選択してから、[ **コネクタの結果を表示** する] を有効にします。

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a>有効になった後の結果のクラスターの状態を表示する

結果のクラスター環境を有効にした後は、表示するまでに数分かかる場合があります。 すぐに使用できるようにする場合は、 *cacheClear = true* を SharePoint および OFFICE の URL に追加できます。
