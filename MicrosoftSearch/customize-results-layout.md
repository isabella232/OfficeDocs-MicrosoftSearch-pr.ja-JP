---
title: 検索結果のレイアウトを管理する
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: アダプティブ カードを使用して、カスタマイズした検索結果を表示するレイアウトを作成する
ms.openlocfilehash: 1badb5bb34d746b22de8ddb91cd26c813fe9f67f
ms.sourcegitcommit: 8270e4271b1eeb57b988ea5265e5b6d9d6ef64a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/22/2021
ms.locfileid: "53529364"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a>検索結果をカスタマイズするためのレイアウトを作成する

検索レイアウト デザイナーを使用して、カスタム垂直の結果レイアウトを設計できます。 レイアウト デザイナーで提供されるテンプレートを選択し、要件に合わせて使用することで、レイアウトの設計を開始できます。 または、要件に合わせてさまざまな方法でこれらのテンプレートを編集することもできます。 たとえば、画像の追加と削除、テキストの追加と削除、テキストの変更を行います。 どのテンプレートも要件を満たしない場合は、空白のテンプレートを使用してレイアウトの設計を開始できます。  

レイアウトの準備が整った後、 [アダプティブ](/adaptive-cards/templating/language) カード テンプレート言語を使用して、結果の種類を定義するために使用される結果レイアウト JSON を作成します。 結果プロパティをレイアウトにマップするには、レイアウト デザイナーの Mapping ステップを使用します。  

## <a name="create-a-layout-on-your-own"></a>独自のレイアウトを作成する

レイアウトを独自に作成するには、アダプティブ カードとそのスキーマ [に関する](/adaptive-cards/authoring-cards/getting-started) 知識が必要 [です](https://adaptivecards.io/explorer/)。 検索結果のレイアウトでは、アダプティブ カードによって提供される要素のサブセットが使用され、レイアウト デザイナーを使用して、サポートされている一連の要素について学習できます。  

独自のレイアウトを作成する際に、コネクタのデータを使用してアダプティブ カード レイアウトを作成し、レイアウトを最終決定します。
独自のレイアウトを作成するには、主に 2 つの手順があります。

- レイアウトを設計します。
- テンプレートからデータを分離します。

### <a name="design-the-layout"></a>レイアウトのデザイン

この例では、ヘッダー、リンク、説明テキストを含むレイアウトを表示します。

![ヘッダー、リンク、および説明を含むレイアウトの例。](media/Verts-ExampleLayout.png)

レイアウトに関連付けられている JSON ファイルを次に示します。

```json
{
    "type": "AdaptiveCard",
    "version": "1.3",
    "body": [
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": 8,
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "Contoso Marketing Analysis - Q3 FY18",
                            "color": "Accent",
                            "size": "Medium",
                            "spacing": "None",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "https://contoso.com/hr/link",
                            "spacing": "None",
                            "color": "Dark",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",
                            "wrap": true,
                            "maxLines": 2,
                            "spacing": "Medium"
                        }
                    ],
                    "horizontalAlignment": "Center",
                    "spacing": "None"
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
}
```

### <a name="separate-the-data-from-the-layout"></a>レイアウトからデータを分離する

レイアウトからデータを分離し、データをバインドできます。

データをバインドした後のレイアウト JSON を次に示します。

```json
{
    "type": "AdaptiveCard",
    "version": "1.3",
    "body": [
        {
            "type": "ColumnSet",
            "columns": [
                {
                    "type": "Column",
                    "width": 8,
                    "items": [
                        {
                            "type": "TextBlock",
                            "text": "[${title}](${titleUrl})",
                            "color": "Accent",
                            "size": "Medium",
                            "spacing": "None",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "${link}",
                            "spacing": "None",
                            "color": "Dark",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "${description}",
                            "wrap": true,
                            "maxLines": 2,
                            "spacing": "Medium"
                        }
                    ],
                    "horizontalAlignment": "Center",
                    "spacing": "None"
                }
            ]
        }
    ],
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json"
}
```

サンプル データ: サンプル データ エディターでサンプル データを **指定** して、プレビュー モードのときにデータ バインド カード **を表示します**。

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a>結果プロパティにレイアウトをマップする

結果レイアウト JSON を生成するには、レイアウトの各フィールドを result プロパティまたは connector プロパティにマップする必要があります。

![フィールドが選択され、プロパティ ウィンドウが開いている [検索レイアウト デザイナー] ページのレイアウト例のスクリーン キャプチャ。](media/Verts-SearchLayoutDesigner.png)

レイアウト内のフィールドを選択して、マップする必要がある変数を強調表示します。 1 つのフィールドに複数の変数を使用できます。すべてのフィールドを結果プロパティにマップする必要があります。

### <a name="show-snippet-on-search-result"></a>検索結果にスニペットを表示する  

コネクタの結果の **content** プロパティで生成された動的スニペットを検索結果に表示できます。 **ResultSnippet** は、Connector の結果ごとに生成されるスニペットのプレースホルダー プロパティとして機能する system プロパティです。 結果レイアウトにスニペットを表示するには **、ResultSnippet** システム プロパティを、検索結果レイアウトの Description など、適切なフィールドにマップする必要があります。 各結果で生成されたスニペットは、ユーザーが入力したクエリ用語を含むスニペット内の一致も強調表示します。

## <a name="things-to-consider"></a>考慮事項

開始する前に、いくつかのことを行う必要があります。また、レイアウトが成功するために避ける必要があるものがあります。

### <a name="do"></a>するべきこと

- 結果のプロパティではなく、ロゴに静的リンクを使用している場合は、レイアウトにロゴ リンクを提供するテンプレートを編集します。
- 結果 JSON で使用される結果プロパティに対してデータが返されるシナリオの結果レイアウトを検証します。 プロパティに `$when` データが含まれている場合は、条件を使用して要素を非表示にしてください。  
- 条件と result プロパティのデータ型が `$when` 一致する必要があります。 たとえば、条件と `Number` 比較 `Text` `$when` しない。  
- 結果レイアウトを設計する際のテーマ要件について考えてみろ。  
- 要素が動的コンテンツ `Textblock`   を処理できる必要があります。 この目的のために `wrap` and `maxLines` 要素プロパティを使用できます。
- Markdown で使用する場合は、日付 `{DATE()}` を適切に書式設定します。  

### <a name="dont"></a>してはいけないこと

- 値をバインドするときに無効なデータ型を定義しない。 データ型の詳細については、「検索スキーマの [管理」を参照してください](/sharepoint/search/manage-the-search-schema)。
- 結果レイアウト JSON の最大高さに従って、結果ページで結果をトリミングしないようにします。 結果レイアウトの最大高さを超えると、結果は結果ページでトリミングされます。
- 要素プロパティで `px` 値を使用しない。
- 検索結果のクエリの一致を強調表示するには、 **結果レイアウトの ResultSnippet** プロパティにマークダウンを使用しません。

## <a name="resources"></a>リソース

[検索結果ページのカスタマイズ](customize-search-page.md)

[アダプティブ カード](/adaptive-cards/authoring-cards/getting-started)

[アダプティブ カード テンプレート言語](/adaptive-cards/templating/language)

[アダプティブ カード スキーマ](https://adaptivecards.io/explorer/)
