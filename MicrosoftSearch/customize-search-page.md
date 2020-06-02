---
title: Microsoft 検索ページをカスタマイズする
ms.author: jypal6
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 検索垂直を追加して検索結果をカスタマイズする
ms.openlocfilehash: 44b1b9ff211a65313f5c5cf532334335994c486d
ms.sourcegitcommit: 0050e113517a36e3ca26028a04ac5c236caaf524
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2020
ms.locfileid: "44470283"
---
# <a name="customize-the-search-results-page"></a>検索結果ページをカスタマイズする

検索の業種と結果の種類を作成して、 [Bing](https://bing.com)で microsoft [SharePoint](https://sharepoint.com/)、 [microsoft Office](https://office.com)、microsoft search を検索するときにユーザーに表示される検索結果をカスタマイズできます。 各業種では、ユーザーが表示するアクセス許可を持っている情報を簡単に見つけられるようにします。 たとえば、マーケティング部門のユーザーのために、サードパーティ製のソフトウェアからマーケティング分析データの検索を縦に作成できます。 また、検索結果の種類を定義し、このデータのレイアウトをカスタマイズすることもできます。  

次のレベルで、業種と結果の種類を作成できます。

- **組織レベル**–組織レベルで垂直を追加すると、ユーザーが[SharePoint](https://sharepoint.com/)のスタートページ、 [Office](https://office.com)、または[Bing](https://bing.com)で検索したときに、検索結果ページに表示されます。
- **サイトレベル**–たとえば、顧客サービスの従業員が、部門の SharePoint サイトから直接、*重要度 1*のインシデントを検索できるようにすることができます。

## <a name="search-verticals-explained"></a>検索業種の説明

Microsoft 検索結果ページの上部には、タブの行があります。 これらは検索業界です。 検索垂直では、特定の種類の結果または特定のコンテンツのみが表示されます。 例としては、**ファイル**または**ニュース**があります。 Microsoft Search では、既定で、**すべて**の業種、**人**、**ファイル**、**サイト**、および**ニュース**が表示されます。  

組織に関連する検索業種を追加することができます。 これらは、 [SharePoint](https://sharepoint.com/)、 [Office](https://Office.com)、および[Bing](https://bing.com)の Microsoft 検索結果ページに表示されます。 たとえば、各グループに必要な情報の種類に基づいて、マーケティング関連のコンテンツを縦にまとめ、売り上げに対して別のものを作成することができます。 すべての業種を追加して、コネクタ経由でインデックスが作成されたコンテンツからの結果のみを表示することができます。  

>[!NOTE]
> 各業種および結果の種類は、Microsoft Graph のコネクタプレビューの一部として現在プレビュー段階にあります。 プレビューの詳細については、「[コネクタプレビュー](connectors-preview.md)」を参照してください。 プレビューに参加するには、最初に[Microsoft Graph Connector preview のサインアップフォーム](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)を送信する必要があります。

## <a name="things-to-consider"></a>考慮事項

開始する前に、コネクタにインデックスが作成されていることを確認してください。 これには、ファイルサイズに応じて、最大48時間かかることがあります。

[SharePoint](https://sharepoint.com/)または[ファイル共有コネクタ](file-share-connector.md)によってインデックスが作成されたコンテンツに対して、垂直方向を作成することはできません。 [コンテンツにインデックス](configure-connector.md)を作成する方法について説明します。

垂直方向を追加するには、次の3つの基本的な手順を実行します。

1. 垂直方向のを作成します。 この手順では、検索するコンテンツの縦の名前、コンテンツソース、および範囲を定義します。
2. この垂直方向の結果がどのように表示されるかを定義します。  
3. 垂直リストページから、垂直 (表示する) を有効にします。

## <a name="step-1-create-the-search-vertical"></a>手順 1: 検索垂直を作成する

ウィザードを開始したら、検索するコンテンツの縦の名前、コンテンツソース、および範囲を定義する手順に従って操作します。 垂直は無効な状態で作成されます。 後で有効にします。

限定された一連の[キーワードクエリ言語 (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)を使用して、範囲を絞ることができます。 このページには、使用可能なプロパティの一覧が表示されます。 この KQL を作成するブール演算子では、freetext キーワードとプロパティ制限を使用することをお勧めします。

### <a name="create-a-vertical-at-the-organization-level"></a>組織レベルで垂直線を作成する

[SharePoint](https://sharepoint.com/) Home、 [Office](https://office.com)、または[Bing](https://bing.com)で Microsoft Search に垂直にするには、次の手順を実行します。

1. Microsoft 365 [管理センター](https://admin.microsoft.com)で、[microsoft Search の **設定**] に移動   >  **Microsoft Search**   >  **Verticals**します。
1. 開始するには、[ **追加**] を選択します。  

### <a name="create-a-vertical-at-the-site-level"></a>サイトレベルで垂直方向のを作成する

1. 垂直にする[SharePoint](https://sharepoint.com/)サイトで、[**設定**] に移動します。
1. [**サイト情報**] を選択し、[**すべてのサイト設定**] を表示します。
1. [ **Microsoft search** ] セクションを探し、[**このサイトコレクションの Microsoft Search を構成する**] を選択します。
1. ナビゲーションウィンドウで、[ **ユーザー設定の操作**] に移動し、[**垂直**] タブを選択します。
1. 垂直方向を追加するには、[ **追加**] を選択します。
  または、縦方向を編集するには、一覧から選択します。

各業種は無効な状態で作成されることに注意してください。 ユーザーが表示できるようにするには、それらを有効にする必要があります。

## <a name="step-2-create-the-result-types"></a>手順 2: 検索結果の種類を作成する

結果の種類を使用してレイアウトを設計することで、結果を垂直に表示する方法を定義できます。 結果レイアウトでは、重要な情報を検索結果に直接表示することができます。したがって、ユーザーが探しているものが見つかったかどうかを確認するために、各結果を選択する必要はありません。

検索結果の種類とは、検索結果のタイプの違いに応じて表示方法を変えるルールのことです。このルールは、次のような構成になっています。

- 検索結果のコンテンツソースなど、各検索結果を比較する**1 つまたは複数の条件**。  
- 条件に一致する検索結果に使用する**結果レイアウト**。 結果レイアウトは、条件を満たすすべての結果が検索結果ページに表示され、動作する方法を制御します。

**結果を垂直に表示するには、少なくとも1つの結果の種類を作成する必要があります。** 垂直方向に複数の検索結果の種類を作成できます。これにより、さまざまな種類の結果に異なるレイアウトを使用できます。 たとえば、重大度*1*のインシデントをカスタマイズして、*重要度 3*のインシデントに比べて目立つ色とより大きいフォントを設定することができます。

ウィザードを開始した後、検索結果の種類の名前、コンテンツソース、および条件を定義する手順について説明しています。 リストビューから検索結果の種類の優先度を定義できます。
  
### <a name="create-a-result-type-at-the-organization-level"></a>組織レベルで結果の種類を作成する

1. [管理センター](https://admin.microsoft.com)で、[ **Setting**  >  **Microsoft Search**の設定] に移動し、 **[結果の種類**] を選択します。
1. **検索結果の種類**を追加するには、[ **追加**] を選択します。 検索結果の種類を編集するには、関連するリストで結果の種類を選択します。

### <a name="create-a-results-type-at-the-site-level"></a>サイトレベルで結果の種類を作成する

1. 検索結果の種類を作成する[SharePoint](https://sharepoint.com/)サイトで、[**設定**] に移動します。
1. [**サイト情報**] を選択し、[**すべてのサイト設定**] を表示します。
1. [Microsoft Search] セクションを探し、[**このサイトコレクションの Microsoft search を構成する**] を選択します。
1. ナビゲーションウィンドウで、[ **ユーザー設定の操作**] に移動し、[**結果の種類**] タブを選択します。
2. 検索結果の種類を追加するには、[ **追加**] を選択します。  または、結果の種類を編集するには、リストで結果の種類を選択します。

### <a name="view-the-vertical-after-its-enabled"></a>有効になった縦の表示

垂直方向を有効にした後は、表示する前にしばらく時間がかかる場合があります。 有効にした後に待機する必要がない場合は、 **cacheClear = true**を[SharePoint](https://sharepoint.com/)および[Office](https://office.com)の URL に追加して、すぐに垂直状態を表示することができます。

## <a name="troubleshooting"></a>トラブルシューティング

発生する可能性のある一般的な問題と、それらを修正するためのアクションを次に示します。

|Error  |Action  |
|---------|---------|
| 垂直方向に "問題が発生しました" というエラーメッセージが表示されます。 | セットアップを完了するには、垂直と結果の両方の種類が必要です。 同じコンテンツソースに対して両方の作成が完了していることを確認してください。 |
| 結果のレイアウトは表示されませんでしたが、作成しました。 | これらの設定は一般的にキャッシュされるため、数分かかることがあります。 数分待ってから、もう一度実行してください。        |
| [垂直または結果の種類] ページにコンテンツソースが表示されません。 | コネクタとインデックスデータが構成されていることを確認してください。   |

## <a name="next-steps"></a>次の手順

[手順 3: 結果のレイアウトをカスタマイズする](customize-results-layout.md)
