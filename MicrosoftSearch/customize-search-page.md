---
title: Microsoft Search ページをカスタマイズする
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: 検索カテゴリを追加し、検索結果をカスタマイズする
ms.openlocfilehash: 1ca436a2617e32e285715e4fffd622dc7a571ca1
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973570"
---
# <a name="customize-the-search-results-page"></a>検索結果ページをカスタマイズする

検索バーティカル *と* 結果の種類を作成して、ユーザーが Microsoft [SharePoint、Microsoft Office、](https://sharepoint.com/)および Bing で [](https://office.com)検索するときに表示される検索結果をカスタマイズ [Microsoft Search](https://bing.com)できます。 バーティカルを使用すると、ユーザーは表示を許可されている情報を簡単に見つけることができます。

たとえば、マーケティング部門のユーザー向けに、サードパーティ ソフトウェアからのマーケティング分析データの検索カテゴリを作成できます。 結果の種類を定義し、このデータのレイアウトをカスタマイズすることもできます。

## <a name="about-search-verticals"></a>検索バーティカルについて

検索結果ページの上部にタブMicrosoft Searchがあります。 これらは検索バーティカルです。 垂直方向の検索では、特定の種類または特定のコンテンツ セットからの結果のみを表示します。 例として、**ファイル** または **ニュース** があります。 既定では、Microsoft Search には、[**すべて**]、[**人物**]、[**ファイル**]、[**サイト**]、および [**ニュース**] のカテゴリが表示されます。  

組織に関連する検索カテゴリを追加できます。 これらの結果は、SharePoint、Office、Bing の Microsoft Search 結果ページに表示されます。 たとえば、各部門で必要な情報の種類に基づいて、マーケティング関連のコンテンツ用の垂直コンテンツと、販売用の別のコンテンツを作成できます。 バーティカルを追加して、コネクタを介してインデックス付けされたコンテンツからの結果のみを表示できます。

垂直方向と結果の種類は、次の 2 つのレベルで作成できます。

- **組織レベル**– ユーザーが SharePoint スタート ページ [、Office、](https://sharepoint.com/)または Bing で検索すると、組織レベルで作成した垂直方向が検索結果 [](https://office.com)ページ [に表示されます](https://bing.com)。
- **サイトレベル** – たとえば、カスタマーサービスの従業員が部門の SharePoint サイトから直接、*重大度 1* のインシデントを検索できるようにすることができます。

### <a name="multiple-connections-in-a-vertical"></a>垂直の複数の接続

垂直検索では、複数のコネクタ ソースからの結果を表示できます。 このオプションを使用すると、検索結果ページを柔軟に設計できます。 垂直方向のセットアップ プロセスを使用すると、管理者は "コンテンツ ソース" ステップで複数の接続を選択できます。

可能な限り多くのセマンティック ラベル *を正確* に指定すると、このエクスペリエンスが強化されます。 スキーマ定義とインジェストの時点でセマンティック ラベルを追加します。 [セマンティック ラベルを作成および管理する方法の詳細を参照してください](configure-connector.md#step-6-assign-property-labels)。
[セ](configure-connector.md#step-6-assign-property-labels) マンティック ラベルを作成および管理する方法に関する追加情報を次に示します。

> [!NOTE]
> 垂直機能の複数の接続は現在プレビュー中です。 詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。

接続は、単一の垂直のコンテンツ ソースとして追加できます。 複数の垂直線で接続を使用することはできません。

複数の接続ソースが追加されている検索バーティカルのクエリを設定するには、共通のソース プロパティを使用してクエリを作成します。

### <a name="before-you-create-verticals-and-result-types"></a>垂直方向と結果の種類を作成する前に

計画では、次の要因を考慮します。

- コネクタにインデックスが作成されている必要があります。 ファイルサイズによって、これには最大48時間かかる場合があります。

- SharePoint に存在するコンテンツのバーティカルを作成することはできません。

垂直方向を実装する手順は次のとおりです。

1. バーティカルを作成します。 このステップでは、検索するコンテンツのバーティカルの名前、コンテンツソース、および範囲を定義します。
2. このバーティカルの結果がどのようになるかを定義します。  
3. バーティカル リストページからバーティカル (表示する) を有効にします。

## <a name="step-1-create-the-search-vertical"></a>手順 1: 垂直検索を作成する

ウィザードを開始すると、検索するコンテンツの垂直方向の名前、コンテンツ ソース、および範囲を定義する手順について説明します。

>[!Note]
>バーティカルは無効な状態で作成されます。 それらを有効にして、表示可能にできます。

限定された[キーワードクエリ言語 (KQL)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) のセットを使用して、範囲を狭めることができます。 (使用できるプロパティについては、この記事で後述します)。ブール演算子には、フリーテキスト キーワードとプロパティ制限を使用することをお勧めします。 KQL では、プロファイル [クエリ変数をサポートして](#profile-query-variables) 、垂直方向の結果を微調整することもできます。

### <a name="create-a-vertical-at-the-organization-level"></a>組織レベルで業種を作成する

ホーム、Microsoft Search、SharePoint、Office、Bingに垂直を作成するには、次の手順を実行します。

1. [バーティ [Microsoft 365 管理センター](https://admin.microsoft.com)に [**移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)。
2. [追加 **] を** 選択して開始します。  

### <a name="create-a-vertical-at-the-site-level"></a>サイトレベルでカテゴリを作成する

1. バーティカルにする [SharePoint](https://sharepoint.com/) サイトで、**[設定]** に移動します。
2. [サイト **情報] を** 選択し、[すべてのサイト設定 **を表示する] を選択します**。
3. [サイト コレクション] **Microsoft Search** を見つけて、[このサイト コレクションのMicrosoft Search **を構成する] を選択します**。
4. ナビゲーション ウィンドウで、[カスタム エクスペリエンス] **に移動** し、[垂直] タブ **を選択** します。
5. 垂直を追加するには、[追加] を **選択します**。 または、縦書きを編集するには、リストから選択します。

## <a name="step-2-create-result-types"></a>手順 2: 結果の種類を作成する

結果の種類 *を使用して* 、垂直での結果の表示方法を定義できます。 結果のレイアウトを使用すると、重要な情報を検索結果に直接表示できるため、ユーザーはユーザーは各結果を選択して、探しているものが見つかったかどうかを確認する必要がありません。

### <a name="default-search-result-layout"></a>既定の検索結果レイアウト

コネクタの構成時にラベルとコンテンツ プロパティがソースプロパティに正しくマップされている場合、コネクタ コンテンツの既定の検索結果レイアウトが表示されます。 タイトル *ラベルは* 、最も重要なラベルです。 既定 *の検索結果レイアウト* を使用するには、このラベルにプロパティを割り当てすることをお勧めします。

### <a name="create-your-own-result-type"></a>独自の結果の種類を作成する

独自の検索結果レイアウトを作成し、既定の検索結果レイアウトを上書きするには、結果の種類を *作成します*。 検索結果の種類とは、検索結果のタイプの違いに応じて表示方法を変えるルールのことです。 この構成内容は次のとおりです。

- 検索結果のコンテンツソースなど、各検索結果を比較するための **1 つ以上の条件**。  
- 条件を満たす検索結果に使用する **結果レイアウト**。 結果のレイアウトは、条件を満たす結果が検索結果ページに表示および動作する方法を制御します。

*既定の検索結果レイアウトを表示するために適切なマッピングを実行しない場合は、垂直方向に表示する結果の種類を少なくとも 1 つ作成する必要があります。* 

業種ごとに複数の結果タイプを作成できます。これにより、さまざまなタイプの結果にさまざまなレイアウトを使用できます。 たとえば、重大度 *1* インシデントをカスタマイズして、重大度 *3* インシデントよりも目立つ色と大きなフォントを使用できます。

ウィザードを開始すると、結果タイプの名前、コンテンツソース、および条件を定義する手順がガイドされます。 リストビューから結果タイプの優先度を定義できます。
  
### <a name="create-a-result-type-at-the-organization-level"></a>Create a result type at the organization level

1. [Microsoft 365 管理センター](https://admin.microsoft.com)で、[[結果の種類]**に移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)。
2. 結果の種類を追加するには、[追加] を **選択します**。 結果の種類を編集するには、関連するリストから結果の種類を選択します。

### <a name="create-a-result-type-at-the-site-level"></a>サイト レベルで結果の種類を作成する

1. 結果の [SharePoint](https://sharepoint.com/)するサイトで、次のページに **移動** 設定。
2. [サイト **情報] を** 選択し、[すべてのサイト設定 **を表示する] を選択します**。
3. **[Microsoft Search]** セクションを探し、**[このサイトコレクションの Microsoft 検索の構成]** を選択します。
4. ナビゲーション ウィンドウで、[カスタム エクスペリエンス] **に移動し**、[結果の種類 **] タブを選択** します。
5. 結果の種類を追加するには、[追加] を **選択します**。  または、結果タイプを編集するには、リストから結果タイプを選択します。

## <a name="step-3-view-the-vertical-after-its-enabled"></a>手順 3: 垂直を有効にした後に表示する

垂直を有効にした後、表示するには数時間の遅延があります。 ただし、ページの `cacheClear=true` URL に追加してSharePoint、Officeをすぐに表示できます。 このBingに追加 `&features=uncachedVerticals` して `Work vertical URL` 、垂直をすぐに表示します。

> [!NOTE]
> モバイル Web ブラウザーから表示した場合、SharePoint] および Officeバーティカルは https://sharepoint.com/) 表示されません。 [](https://office.com)

## <a name="profile-query-variables"></a>プロファイル クエリ変数

垂直の KQL クエリ セクションの変数を使用して、垂直のクエリへの入力として動的データを提供します。 プロファイル クエリ変数を使用して、サインインしているユーザーに対して検索結果をコンテキストに合った状態にできます。 プロファイル クエリ変数は、サインインしているユーザーのプロファイルから値をフェッチ [します](/graph/api/resources/profile)。

たとえば、ユーザーが割り当てられたサポート チケットを検索する垂直の "チケット" を作成するには、管理ページの垂直方向の作成中に [クエリ] セクションで次のクエリを指定できます。  

`AssignedTo:{Profile.accounts.userPrincipalName}`

この言語では、検索結果を絞り込み、割り当て先が検索を実行するユーザーであるアイテムのみを表示します。

[プロファイル リソースは](/graph/api/resources/profile) 、プロパティをコレクションとして公開します。 たとえば、電子メール アドレスに関連する情報は、電子メールのコレクション、職位のコレクションとしての作業位置などによって公開されます。 ソースの種類として AAD を持つユーザー プロファイルで使用可能なすべてのプロパティは、クエリ変数として公開されます。


次に示すように、電子メール コレクションで 3 つの電子メール アドレスを使用できるユーザーを検討します。

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

- クエリは `MyProperty: {Profile.emails.address}` *MyProperty: "Megan.Bowen@contoso.com" に解決されます*。  

- address 属性のすべての値を解決するには、複数値の拡張構文を使用します。 クエリは `{|MyProperty:{Profile.emails.address}}` *((MyProperty:"Megan.Bowen@contoso \. com")* または *(MyProperty: "meganb@hotmail \. com")* または  *(MyProperty:"meganb@outlook \. com"))* に解決されます。

"|" 演算子を使用して、複数値の変数を解決します。 プロファイル拡張の例については、次の表を参照してください。

| #         | 構文 |  戻り値  |
| --------- | ------ | --- |
| 1    | MyProperty:{Profile.emails.address}  |   "Megan \. Bowen@contoso.com"  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} 電子メールはオブジェクトなので、これは解決できません。|
| 3    | {?MyProperty:{Profile.emails}}  |  メールはオブジェクトなので *、これは* 解決しない。 "? 演算子は、解決しないクエリ変数を無視します。 この変数は、クエリ スタックの下にさらに渡されると削除されます。   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") または (MyProperty:"non-official") または (MyProperty:"personal"))    |

> [!NOTE]
>
> - プロファイル クエリ変数は、コネクタをコンテンツ ソースとして使用するカスタムバーティ [カルでのみサポート](connectors-overview.md) されます。
> - プロファイル クエリ変数は、垂直セットアップ プロセスの "Query" セクション [で定義されます](customize-search-page.md#step-1-create-the-search-vertical)。
> - プロファイル クエリ変数機能は現在プレビュー中です。 プレビューの詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。

## <a name="troubleshooting"></a>トラブルシューティング

発生する可能性のある一般的な問題と、それらを修正するためのアクションの一覧を次に示します。

|問題  |アクション  |
|---------|---------|
| バーティカルに「問題が発生しました」というエラーメッセージが表示されます。 | セットアップを完了するには、バーティカル タイプと結果タイプの両方が必要です。 両方を同じコンテンツ ソース用に作成してください。 |
| 結果のレイアウトを作成しましたが、表示されません。 | これらの設定がキャッシュされたため、数分の遅延が発生する可能性があります。 数分待って、もう一度やり直してください。        |
| バーティカル ページまたは結果タイプのページにコンテンツ ソースが表示されません。 | コネクタとインデックス付きデータが構成されていることを確認してください。   |

## <a name="next-steps"></a>次のステップ

[結果のレイアウトをカスタマイズする](customize-results-layout.md)
