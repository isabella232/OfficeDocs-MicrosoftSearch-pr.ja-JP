---
title: Microsoft Search ページをカスタマイズする
ms.author: jeffkizn
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
description: 検索カテゴリを追加し、検索結果をカスタマイズする
ms.openlocfilehash: 0bcb8d8588edf44d4291802d1d9c73b75fd6bf327b19f9a9b1ef0555baca38ad
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533067"
---
# <a name="customize-the-search-results-page"></a>検索結果ページをカスタマイズする

検索カテゴリと結果タイプを作成して、ユーザーが Microsoft [SharePoint](https://sharepoint.com/)、[Microsoft Office](https://office.com)、および [Bing](https://bing.com) の Microsoft Search で検索したときに表示される検索結果をカスタマイズできます。 バーティカルを使用すると、ユーザーは表示を許可されている情報を簡単に見つけることができます。 たとえば、マーケティング部門のユーザー向けに、サードパーティ ソフトウェアからのマーケティング分析データの検索カテゴリを作成できます。 結果の種類を定義し、このデータのレイアウトをカスタマイズすることもできます。  

次のレベルで、バーティカルと結果タイプを作成できます。

- **組織レベル** – 組織レベルで業種を追加することで、ユーザーが [SharePoint](https://sharepoint.com/) スタートページ、[Office](https://office.com)、または [Bing](https://bing.com) から検索すると、検索結果ページに表示されるようになります。
- **サイトレベル** – たとえば、カスタマーサービスの従業員が部門の SharePoint サイトから直接、*重大度 1* のインシデントを検索できるようにすることができます。

## <a name="search-verticals-explained"></a>検索バーティカルの説明

Microsoft Search 結果ページの上部には、タブが表示される行があります。 これらは検索バーティカルです。 検索バーティカルには、特定のタイプまたは特定のコンテンツの結果のみが表示されます。 例として、**ファイル** または **ニュース** があります。 既定では、Microsoft Search には、[**すべて**]、[**人物**]、[**ファイル**]、[**サイト**]、および [**ニュース**] のカテゴリが表示されます。  

組織に関連する検索カテゴリを追加できます。 これらの結果は、[SharePoint](https://sharepoint.com/)、[Office](https://Office.com)、[Bing](https://bing.com) の Microsoft Search 結果ページに表示されます。 たとえば、各グループが必要とする情報のタイプに基づいて、マーケティング関連のコンテンツ用のバーティカルと販売用のバーティカルを作成できます。 バーティカルを追加して、コネクタを介してインデックス付けされたコンテンツからの結果のみを表示できます。  

### <a name="multiple-connections-in-a-vertical"></a>垂直の複数の接続

複数のコネクタ ソースからの検索結果を垂直方向の検索で表示できます。 これにより、検索結果ページを設計する柔軟性が向上します。 垂直セットアップの既存の管理エクスペリエンスでは、"コンテンツ ソース" ステップで複数の接続を選択できます。
可能な限り多くのセマンティック ラベルを正確に任命すると、このエクスペリエンスが強化されます。 スキーマの定義と取り込み時にセマンティック ラベルを追加できます。

[セ](configure-connector.md#step-5-assign-property-labels) マンティック ラベルを作成および管理する方法に関する追加情報を次に示します。

> [!NOTE]
> 垂直の複数の接続が現在プレビュー中です。 プレビューの詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。

### <a name="things-you-should-know"></a>知っている必要があります。

1. 接続は、1 つの垂直の下でのみコンテンツ ソースとして追加できます。 複数の垂直で接続を再利用できません。
2. 複数の接続ソースが追加されている検索バーティカルのクエリを設定する必要がある場合は、一般的なソース プロパティを使用してこのようなクエリを作成する必要があります。

## <a name="things-to-consider"></a>考慮事項

開始する前に、コネクタにインデックスが付けられていることを確認してください。 ファイルサイズによって、これには最大48時間かかる場合があります。

[SharePoint](https://sharepoint.com/) に存在するコンテンツのバーティカルを作成することはできません。

バーティカルを追加するには、次の3つの基本的な手順があります。

1. バーティカルを作成します。 このステップでは、検索するコンテンツのバーティカルの名前、コンテンツソース、および範囲を定義します。
2. このバーティカルの結果がどのようになるかを定義します。  
3. バーティカル リストページからバーティカル (表示する) を有効にします。

## <a name="step-1-create-the-search-vertical"></a>手順 1: 検索バーティカルを作成する

ウィザードを開始すると、業種の名前、コンテンツソース、および検索するコンテンツの範囲を定義する手順がガイドされます。 バーティカルは無効な状態で作成されます。 後ほど有効にします。

限定された[キーワードクエリ言語 (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) のセットを使用して、範囲を狭めることができます。 このページには、利用可能なプロパティが一覧表示されます。 KQL を作成するには、ブール演算子と一緒にフリーテキスト キーワードとプロパティ制限を使用することをお勧めします。
KQL では、プロファイル クエリ [変数を使用](#profile-query-variables) して垂直方向の結果を微調整することもできます。

### <a name="create-a-vertical-at-the-organization-level"></a>組織レベルで業種を作成する

[SharePoint](https://sharepoint.com/) ホーム、[Office](https://office.com)、または[Bing](https://bing.com)で Microsoft Search にカテゴリを作成するには、次の手順を実行します。 

1. [バーティ [Microsoft 365 管理センター](https://admin.microsoft.com)に [**移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)。
2. [追加 **] を** 選択して開始します。  

### <a name="create-a-vertical-at-the-site-level"></a>サイトレベルでカテゴリを作成する

1. バーティカルにする [SharePoint](https://sharepoint.com/) サイトで、**[設定]** に移動します。
2. [**サイト情報**]、[**すべてのサイト設定を表示**] の順に選択します。
3. **[Microsoft Search]** セクションを探し、**[このサイトコレクションの Microsoft 検索の構成]** を選択します。
4. ナビゲーション ウィンドウで、[カスタム エクスペリエンス] **に移動** し、[垂直] タブ **を選択** します。
5. 垂直を追加するには、[追加] を **選択します**。
  または、バーティカルを編集するには、リストから業種を選択します。

バーティカルは無効な状態で作成されることに注意してください。 ユーザーに表示する前に、これらを有効にする必要があります。

## <a name="step-2-create-the-result-types"></a>ステップ 2: 検索結果の種類を作成する

検索結果の種類を使用してレイアウトをデザインすることにより、検索結果がバーティカルにどのように表示されるかを定義できます。 結果のレイアウトを使用すると、重要な情報を検索結果に直接表示できるため、ユーザーはユーザーは各結果を選択して、探しているものが見つかったかどうかを確認する必要がありません。

### <a name="default-search-result-layout"></a>既定の検索結果レイアウト

コネクタの構成時にラベルとコンテンツ プロパティがソースプロパティに正しくマップされている場合、Connector コンテンツの既定の検索結果レイアウトが表示されます。 ラベル タイトル **は、** 最も重要なラベルです。 既定の **検索結果レイアウトを** 使用するには、このラベルにプロパティが割り当てられている必要があります。

### <a name="create-your-own-result-type"></a>独自の結果の種類を作成する

独自の検索結果レイアウトを作成し、結果の種類を作成して既定の検索結果レイアウトを上書 **きすることができます**。 検索結果の種類とは、検索結果のタイプの違いに応じて表示方法を変えるルールのことです。 このルールは、次のような構成になっています。

- 検索結果のコンテンツソースなど、各検索結果を比較するための **1 つ以上の条件**。  
- 条件を満たす検索結果に使用する **結果レイアウト**。 結果のレイアウトは、条件を満たすすべての結果が検索結果ページに表示および動作する方法を制御します。

**既定の検索結果レイアウトを表示するために適切なマッピングが行われない場合は、垂直方向に表示する結果の種類を少なくとも 1 つ作成する必要があります。** 業種ごとに複数の結果タイプを作成できます。これにより、さまざまなタイプの結果にさまざまなレイアウトを使用できます。 たとえば、*重大度 1* のインシデントをカスタマイズして、*重大度 3* のインシデントと比較してより目立つ色と大きなフォントを使用できます。

ウィザードを開始すると、結果タイプの名前、コンテンツソース、および条件を定義する手順がガイドされます。 リストビューから結果タイプの優先度を定義できます。
  
### <a name="create-a-result-type-at-the-organization-level"></a>Create a result type at the organization level

1. [Microsoft 365 管理センター](https://admin.microsoft.com)で、[[結果の種類]**に移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)。
2. 結果の種類を **追加するには、[追加**] を **選択します**。 結果タイプを編集するには、関連するリストで結果タイプを選択します。

### <a name="create-a-results-type-at-the-site-level"></a>サイトレベルで結果タイプを作成する

1. 結果タイプを作成する [SharePoint](https://sharepoint.com/) サイトで、**[設定]** に移動します。
2. [**サイト情報**]、[**すべてのサイト設定を表示**] の順に選択します。
3. [Microsoft Search] セクションを探し、**[このサイトコレクションのMicrosoft Searchの構成]** を選択します。
4. ナビゲーション ウィンドウで、[カスタム エクスペリエンス] に移動 **し、[** 結果の種類 **] タブを選択** します。
5. 結果の種類を追加するには、[追加] を **選択します**。  または、結果タイプを編集するには、リストから結果タイプを選択します。

## <a name="step-3-view-the-vertical-after-its-enabled"></a>手順 3: 垂直を有効にした後に表示する

垂直を有効にした後、表示するには数時間かかります。 有効にした後で待ちたくない場合は、[SharePoint](https://sharepoint.com/) と [Office](https://office.com) の URL に **cacheClear=true** を追加して、カテゴリをすぐに表示できます。 たとえば [Bing、&](https://bing.com)**を**[作業] 垂直 URL に追加して、垂直をすぐに表示します。

> [!NOTE]
> モバイル Web ブラウザーから表示された場合、追加された[SharePointとOffice](https://sharepoint.com/)[に表示](https://office.com)されません。

## <a name="profile-query-variables"></a>プロファイル クエリ変数

クエリ変数は、垂直のクエリへの入力として動的データを提供するために、垂直の KQL クエリ セクションで使用されます。 プロファイル クエリ変数を使用して、サインインしているユーザーに対して検索結果をコンテキストに合った状態にできます。 プロファイル クエリ変数は、サインインしているユーザーのプロファイルから値をフェッチ [します](/graph/api/resources/profile?view=graph-rest-beta)。

たとえば、サインインしているユーザーが割り当てられたサポート チケットを検索できる垂直の "チケット" を作成する場合は、管理ページの垂直方向の作成中に[クエリ] セクションで次のクエリを指定できます。  

**AssignedTo:{Profile.accounts.userPrincipalName}**

これにより、検索結果を絞り込み、割り当て先が検索を実行しているユーザーであるアイテムのみを表示します。

[プロファイル リソースは](/graph/api/resources/profile?view=graph-rest-beta) 、プロパティをコレクションとして公開します。 たとえば、電子メール アドレスに関連する情報は、電子メールのコレクション、職位のコレクションとしての作業位置などによって公開されます。 ソースの種類として AAD を持つユーザー プロファイルで使用可能なすべてのプロパティは、クエリ変数として公開されます。

以下に示すように、電子メール コレクションで使用できる電子メール アドレスが 3 つ含まれます。

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- クエリ **MyProperty: {Profile.emails.address}** は MyProperty: "Megan.Bowen@contoso.com" に解決されます。  

- address 属性のすべての値を解決するには、複数値の拡張構文を使用する必要があります。 クエリ **{|MyProperty:{Profile.emails.address}}** は ((MyProperty:"Megan.Bowen@contoso.com") OR (MyProperty: "meganb@hotmail.com") OR (MyProperty:"meganb@outlook.com")) に解決されます。  

"|" 演算子は、複数値変数の解決に使用する必要があります。 プロファイルの展開に関するその他の例については、以下の表を参照してください。

| #         | 構文 |  戻り値  |
| --------- | ------ | --- |
| 1    | MyProperty:{Profile.emails.address}  |   "Megan.Bowen@contoso.com"  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} 電子メールはオブジェクトなので、これは解決できません。|
| 3    | {?MyProperty:{Profile.emails}}  |  メールはオブジェクトなので、これは解決しない。 "? 演算子は、解決しないクエリ変数を無視します。 この変数は、クエリ スタックの下にさらに渡されると削除されます。   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") OR (MyProperty:"non-official") OR (MyProperty:"personal"))    |

> [!NOTE]
>
> - プロファイル クエリ変数は、コネクタをコンテンツ ソースとして使用するカスタム [バー](connectors-overview.md) ティカルでのみサポートされます。
> - プロファイル クエリ変数は、垂直セットアップ プロセスの "Query" [セクションで定義されます](customize-search-page.md#step-1-create-the-search-vertical)。
> - プロファイル クエリ変数は現在プレビュー中です。 プレビューの詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。

## <a name="troubleshooting"></a>トラブルシューティング

発生する可能性のある一般的な問題とそれらを修正するためのアクションのリストを次に示します。

|Error  |アクション  |
|---------|---------|
| バーティカルに「問題が発生しました」というエラーメッセージが表示されます。 | セットアップを完了するには、バーティカル タイプと結果タイプの両方が必要です。 両方を、同じコンテンツソースに対して作成したことを確認してください。 |
| 結果のレイアウトを作成しましたが、表示されません。 | これらの設定は通常キャッシュされるため、数分かかります。 数分待ってから、もう一度やり直してください。        |
| バーティカル ページまたは結果タイプのページにコンテンツ ソースが表示されません。 | コネクタとインデックス付きデータが構成されていることを確認してください。   |

## <a name="next-steps"></a>次のステップ

[結果のレイアウトをカスタマイズする](customize-results-layout.md)
