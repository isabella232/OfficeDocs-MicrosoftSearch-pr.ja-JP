---
title: 検索結果のレイアウトをカスタマイズする
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
description: アダプティブカードを使用して、カスタマイズされた検索結果を表示するレイアウトを作成する
ms.openlocfilehash: 5bd42eded291781f5122cfede3759327b5222108
ms.sourcegitcommit: 995ce23d4e47a3456a02dba0ba7c9cd0de64528a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919512"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a>レイアウトを作成して検索結果をカスタマイズする

検索レイアウトデザイナーを使用して、カスタム縦の結果レイアウトを設計できます。 レイアウトの設計を開始するには、レイアウトデザイナーで提供されているテンプレートを選択し、要件に適合している場合はそのテンプレートを使用します。 また、必要に応じてさまざまな方法でテンプレートを編集することもできます。 たとえば、画像の追加、削除、テキストの追加と削除、テキストの変更などを行います。 要件を満たすテンプレートがない場合は、空白のテンプレートを使用してレイアウトの設計を開始することを選択できます。  

レイアウトの準備が整ったら、 [アダプティブカードテンプレート言語](https://docs.microsoft.com/adaptive-cards/templating/language) を使用して、結果の種類を定義するために使用する結果レイアウト JSON を作成します。 レイアウトデザイナーのマッピング手順を使用して、結果のプロパティをレイアウトにマップします。  

## <a name="create-a-layout-on-your-own"></a>独自のレイアウトを作成する

独自にレイアウトを作成するには、 [アダプティブカード](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) とその [スキーマ](https://adaptivecards.io/explorer/)についての知識が必要です。 検索結果のレイアウトでは、アダプティブカードによって提供される要素のサブセットを使用し、レイアウトデザイナーを使用して、サポートされている要素のセットについて調べることができます。  

独自のレイアウトを作成するときに、コネクタのデータを使用してアダプティブカードレイアウトを作成し、レイアウトを確定します。
独自のレイアウトを作成するには、次の2つの主要な手順があります。

- レイアウトを設計します。
- テンプレートからデータを分離します。

### <a name="design-the-layout"></a>レイアウトのデザイン

この例では、ヘッダー、リンク、および説明テキストを含むレイアウトを示します。

![ヘッダー、リンク、および説明を含むレイアウトの例です。](media/Verts-ExampleLayout.png)

レイアウトに関連付けられている JSON ファイルは次のとおりです。

```json
{
    "type": "AdaptiveCard",
    "version": "1.0",
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
                             "$when": "{title != \"\"}",
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

データをレイアウトから分離し、データをバインドすることができます。

データをバインドした後のレイアウト JSON を次に示します。

```json
{

    "type": "AdaptiveCard",
    "version": "1.0",
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
                "text": "[{title}]({titleUrl})",
                "color": "Accent",
                "size": "Medium",
                "spacing": "None",
                "weight": "Bolder"

                 },
                 {
                 "type": "TextBlock",
                 "text": "{link}",
                 "spacing": "None",
                 "color": "Dark",
                 "weight": "Bolder"
                 },
                 {
                 "type": "TextBlock",
                 "text": "{description}",
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

サンプルデータ: **プレビューモード** でデータバインドカードを表示するには、サンプル **データエディター** でサンプルデータを指定します。

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a>レイアウトを結果プロパティにマップする

結果レイアウト JSON を生成するには、レイアウトの各フィールドを result プロパティまたは connector プロパティにマップする必要があります。

![フィールドが選択され、プロパティウィンドウが開いている状態で、[検索レイアウトデザイナー] ページのレイアウトの例を画面キャプチャします。](media/Verts-SearchLayoutDesigner.png)

レイアウト内のフィールドを選択して、マップする必要がある変数を強調表示にします。 1つのフィールドに複数の変数を使用することができます。また、すべてのフィールドを result プロパティにマップする必要があります。

### <a name="show-snippet-on-search-result"></a>検索結果にスニペットを表示する  

コネクタの結果の **コンテンツ** プロパティで生成された動的スニペットは、検索結果に表示できます。 **Resultsnippet** は、各コネクタの結果に対して生成されたスニペットの placeholder プロパティとして機能するシステムプロパティです。 結果のレイアウトにスニペットを表示するには、検索結果のレイアウトで、 **resultsnippet** システムプロパティを適切なフィールド (Description など) にマップする必要があります。 各結果に対して生成されたスニペットも、ユーザーが入力したクエリ用語でスニペット内の一致を強調表示します。

## <a name="things-to-consider"></a>考慮事項

開始する前に、レイアウトが正常に機能するようにするために、いくつかの作業を行う必要があります。

### <a name="do"></a>するべきこと

- ロゴに対して静的なリンクを使用していて、結果のプロパティではない場合は、テンプレートを編集して、レイアウトにロゴのリンクを表示します。
- Result のレイアウトを検証します。結果の JSON で使用される result プロパティのデータが返されない場合があります。 `$when`プロパティにデータが含まれていない場合は、条件を使用して要素を非表示にします。  
- 条件のデータ型と result プロパティが一致していることを確認してください `$when` 。 たとえば、条件のとは比較しません `Number` `Text` `$when` 。  
- 結果のレイアウトを設計するときは、テーマの要件を考慮してください。  
- `Textblock`   要素が動的コンテンツを処理できることを確認します。 `wrap`この目的には、および要素のプロパティを使用でき `maxLines` ます。
- Markdown で使用するときに、日付を適切に書式設定 `{DATE()}` します。  

### <a name="dont"></a>してはいけないこと

- 値をバインドするときは、無効なデータ型を定義しないでください。 データ型の詳細については、「 [Manage The Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema)」を参照してください。
- 結果レイアウト JSON の最大の高さに従って、結果ページ上の結果をトリミングしないようにします。 結果レイアウトの高さの最大値を超えた場合、結果は結果ページにトリミングされます。
- `px`要素のプロパティで値を使用しないでください。
- 結果レイアウトの **Resultsnippet** プロパティで markdown を使用して、検索結果のクエリ一致を強調表示しないようにします。

## <a name="resources"></a>リソース

[検索結果ページをカスタマイズする](customize-search-page.md)

[アダプティブカード](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[アダプティブカードテンプレートの言語](https://docs.microsoft.com/adaptive-cards/templating/language)

[アダプティブカードスキーマ](https://adaptivecards.io/explorer/)