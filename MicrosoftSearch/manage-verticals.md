---
title: 検索バーティカルの管理
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX
description: 検索結果ページで検索バーティカルを管理する
ms.openlocfilehash: 89887b6ce5391d2473692504efa3c0eb35407b48
ms.sourcegitcommit: 967a02ee932f8a6cee70cfd78bb0c8b1b78d07c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127790"
---
# <a name="manage-search-verticals"></a>検索バーティカルの管理

検索バーティカルは、特定の種類または選択したソースの結果を表示する検索結果ページのタブです。 たとえば、[ファイル] 垂直には、ファイルとして分類された結果が表示され、ドキュメントを探しているユーザーが簡単に検索できます。 組織または個々の部署のニーズMicrosoft Search合わせて、バーティカル をカスタマイズできます。

次の 2 つのレベルで垂直を管理できます。

- **組織レベル**– ユーザーが SharePoint スタート ページ、Microsoft Office、および Microsoft Search から [](https://sharepoint.com/)検索すると、組織レベルの垂直 [](https://office.com)が検索結果ページに [表示](https://bing.com)Bing
- **サイト レベル**– ユーザーがサイトで検索すると、サイト レベルの垂直方向が検索結果ページSharePointされます。 たとえば、顧客サービスの従業員が部署のサイトから重大度 1 インシデントを直接検索SharePointがあります。

## <a name="understanding-search-verticals"></a>検索バーティカルについて

Microsoft Searchには、箱から出る垂直とカスタム垂直の 2 種類があります。 [すべて]、[ファイル]、および [ユーザー] のような垂直方向のボックスから、最も一般的に使用される検索結果に簡単にアクセスできます。

追加の構成オプションはカスタム垂直に提供され、ユーザーに最適なエクスペリエンスを作成するために使用できます。

組織に関連する検索カテゴリを追加できます。 たとえば、各部門で必要な情報の種類に基づいて、マーケティング関連のコンテンツ用の垂直コンテンツと、販売用の別のコンテンツを作成できます。 バーティカルを追加して[、Graph](connectors-overview.md)コネクタによってインデックス付けされたコンテンツの結果を表示できますが、SharePoint に存在するコンテンツの垂直を作成SharePoint。

## <a name="create-search-verticals"></a>検索バーティカルを作成する

垂直方向の管理エクスペリエンスはウィザードによって実行され、検索するコンテンツの垂直方向の名前、コンテンツ ソース、および範囲を定義する手順について説明します。 限られたセットのキーワード クエリ [言語 (KQL)](#keyword-query-language-kql) を使用して、特定のコンテンツ ソースの垂直検索の範囲を定義できます。

次に、カスタムバーティカルをホーム、Microsoft Search、SharePoint、または [](https://sharepoint.com/) [Officeに作成](https://office.com/) [Bing。](https://bing.com/)  

### <a name="manage-organization-level-verticals"></a>組織レベルの縦書きを管理する

1. [カスタマイズ [] Microsoft 365 管理センター[](https://admin.microsoft.com)カスタマイズ] セクションの [**[バー**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)ティカル] ページ **に移動** します。
1. [追加 **] を** クリックして、新しい垂直を作成します。
1. 構成手順を進め、垂直方向を確認して保存できます。  

### <a name="manage-site-level-verticals"></a>サイト レベルの縦書きを管理する

1. 垂直をSharePointするサイトで、ギアをクリックして設定パネルを開きます。
1. [サイト **情報] を** 選択し、[すべてのサイト設定 **を表示する] を選択します**。  
1. [検索設定] セクションをMicrosoft Searchし、[検索設定の構成 **] を選択します**。
1. ナビゲーション ウィンドウで、[カスタム エクスペリエンス] に移動し、[垂直] **を選択します**。
1. [追加 **] を** クリックして、新しい垂直を作成します。
1. 構成を設定した後、垂直方向を確認して保存できます。  

## <a name="view-the-vertical-in-search-results"></a>検索結果で垂直方向を表示する

検索[バーティカル ページ](manage-result-types.md)でコネクタGraph表示するには、検索結果レイアウトが必要です。 適切な結果レイアウトが存在する場合は、垂直検索を有効にできます。 垂直を有効にした後、表示するには数時間の遅延があります。 キャッシュの URL に cacheClear=true を追加しSharePoint、Officeを表示できます。 このBing、作業&URL に features=uncachedVerticals を追加して、垂直をすぐに表示します。

> [!NOTE]
> モバイル Web ブラウザーから表示された場合、追加[SharePointおよびOffice](https://sharepoint.com/)[バーティ](https://office.com)カルは表示されません。

## <a name="advanced-configuration-options"></a>高度な構成オプション

### <a name="multiple-connections-in-a-vertical"></a>垂直の複数の接続

垂直検索では、複数のコネクタ ソースからの結果を表示できます。 このオプションを使用すると、検索結果ページを柔軟に設計できます。 垂直方向のセットアップ プロセスを使用すると、管理者は "コンテンツ ソース" ステップで複数の接続を選択できます。

可能な限り多くのセマンティック ラベル *を正確* に指定すると、このエクスペリエンスが強化されます。 スキーマ定義とインジェストの時点でセマンティック ラベルを追加します。 [セマンティック ラベルを作成および管理する方法の詳細を参照してください](configure-connector.md#step-6-assign-property-labels)。
[セ](configure-connector.md#step-6-assign-property-labels) マンティック ラベルを作成および管理する方法に関する追加情報を次に示します。

> [!NOTE]
> - 垂直機能の複数の接続は現在プレビュー中です。 詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。
> - 接続は、単一の垂直のコンテンツ ソースとして追加できます。 複数の垂直線で接続を使用することはできません。

複数の接続ソースが追加されている検索バーティカルのクエリを設定するには、共通のソース プロパティを使用してクエリを作成します。

### <a name="keyword-query-language-kql"></a>キーワード クエリ言語 (KQL)

クエリを垂直に追加して、キーワード クエリ言語 [(KQL) (](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) 制限付きサポート) を使用して、検索バーティカルに表示される結果を絞り込みできます。 このページには、使用可能なプロパティの一覧が表示されます。 KQL を作成するには、ブール演算子と一緒にフリーテキスト キーワードとプロパティ制限を使用することをお勧めします。 XRANK、近接演算子、単語のような動的ランク付け演算子はサポートされていません。

クエリの例を次に示します。

|シナリオ         | Query   |  
| --------- | ------ |
|アーカイブ サイトからの結果の除外           |NOT (path:http//contoso.sharepoint.com/archive OR path:http//contoso.sharepoint.com/CompanyArchive)|
| ファイルの種類プロパティに基づく結果の除外 | NOT(FileType:htm)|  

#### <a name="profile-query-variables"></a>プロファイル クエリ変数

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
> - プロファイル クエリ変数機能は現在プレビュー中です。 プレビューの詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。

## <a name="troubleshooting"></a>トラブルシューティング

発生する可能性のある一般的な問題と、それらを修正するためのアクションの一覧を次に示します。

|問題  |アクション  |
|---------|---------|
| バーティカルに「問題が発生しました」というエラーメッセージが表示されます。 | セットアップを完了するには、バーティカル タイプと結果タイプの両方が必要です。 両方がコンテンツ ソース用に設定されている必要があります。 |
| 垂直ページにコンテンツ ソースが表示されます。 | コネクタとインデックス付きデータが構成されていることを確認してください。   |
