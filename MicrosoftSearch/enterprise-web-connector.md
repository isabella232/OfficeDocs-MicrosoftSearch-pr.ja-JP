---
title: Enterprise web サイトGraphコネクタMicrosoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Web サイトのEnterpriseコネクタGraph設定Microsoft Search
ms.openlocfilehash: 2461a447b07dec827c8cf699865c027b01e42608
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973594"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a>Enterprise web サイトGraph コネクタ

コネクタEnterpriseサイトGraphを使用すると、組織は内部向け Web サイトから記事やコンテンツ **をインデックス化できます**。 コネクタを構成し、Web サイトからコンテンツを同期すると、エンド ユーザーは任意のクライアントからそのコンテンツMicrosoft Searchできます。

> [!NOTE]
> コネクタの [**セットアップに関する**](configure-connector.md)Graph一般的なコネクタのセットアップGraph説明します。

この記事は、Web サイト コネクタを構成、実行、監視するユーザー Enterpriseです。 これは、一般的なセットアップ プロセスを補足し、Web サイト コネクタに適用される手順Enterprise示します。 この記事には、トラブルシューティングに関する [情報も含まれています](#troubleshooting)。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Graphコネクタを追加Microsoft 365 管理センター

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

データ ソースに接続するには、Web サイトのルート URL を入力し、クロール ソースを選択し、使用する認証の種類 (None、Basic Authentication、または OAuth 2.0 with [Azure Active Directory (Azure AD)](/azure/active-directory/)を選択します。 この情報を完了したら、[接続のテスト] を選択して設定を確認します。

### <a name="url"></a>URL

URL フィールドを使用して、クロールする Web サイトのルートを指定します。 エンタープライズ Web サイト コネクタは、この URL を開始点として使用し、クロールのためにこの URL からのすべてのリンクに従います。

### <a name="crawl-websites-listed-in-the-sitemap"></a>サイトマップにリストされている Web サイトをクロールする

選択すると、コネクタはサイトマップにリストされている URL のみをクロールします。 選択されていない場合、またはサイト マップが見つからない場合、コネクタはサイトのルート URL で見つかったすべてのリンクを深くクロールします。

### <a name="dynamic-site-configuration"></a>動的サイト構成

Web サイトに動的コンテンツ (たとえば、Confluence や Unily のようなコンテンツ管理システムに含まれる Web ページ) が含まれている場合は、動的クローラーを有効にできます。 有効にするには、[動的サイトの **クロールを有効にする] を選択します**。 クローラは、クロールを開始する前に動的コンテンツのレンダリングを待機します。

> [!div class="mx-imgBorder"]
> ![Web コネクタの [接続設定] ウィンドウEnterpriseスクリーンショット。](media/enterprise-web-connector/connectors-enterpriseweb-connectionsettings-dynamicconfig-small.png)

チェック ボックスに加えて、次の 3 つのオプション フィールドを使用できます。

1. **DOM Ready**: コンテンツが完全にレンダリングされ、クロールが開始されるというシグナルとしてクローラーが使用する DOM 要素を入力します。
1. **追加するヘッダー**: 特定の Web URL を送信するときにクローラーに含める HTTP ヘッダーを指定します。 Web サイトごとに複数のヘッダーを設定できます。 認証トークンの値を含めてお勧めします。
1. **スキップするヘッダー**: 動的クロール要求から除外する必要がある不要なヘッダーを指定します。

> [!NOTE]
> 動的クロールは、エージェント クロール モードでのみサポートされます。

### <a name="crawl-mode-cloud-or-on-premises"></a>クロール モード: クラウドまたはオンプレミス

クロール モードは、インデックスを作成する Web サイトの種類 (クラウドまたはオンプレミス) を決定します。 クラウド Web サイトの場合は、クロール **モードとして [クラウド** ] を選択します。

また、コネクタはオンプレミス Web サイトのクロールをサポートしています。 オンプレミス のデータにアクセスするには、最初にコネクタ エージェントをインストールして構成Graph必要があります。 詳細については、「コネクタ エージェント[Graph」を参照してください](./graph-connector-agent.md)。

オンプレミス Web サイトの場合は、クロール モードとして [エージェント]を選択し、[オンプレミス エージェント] フィールドで、前にインストールして構成した Graph コネクタ エージェントを選択します。  

### <a name="authentication"></a>認証

基本認証には、ユーザー名とパスワードが必要です。 このボット アカウントを作成するには、次[のMicrosoft 365 管理センター。](https://admin.microsoft.com)

Azure サーバーを使用する [OAuth](/azure/active-directory/) 2.0 AD ID、クライアント ID、およびクライアント シークレットが必要です。 OAuth 2.0 はクラウド モードでのみ動作します。

詳細については[、「OAuth 2.0 コード許可](/azure/active-directory/develop/v1-protocols-oauth-code)フローをAzure Active Directory Web アプリケーションへのアクセスを承認する」を参照してください。 次の値を使用して登録します。

**名前: Microsoft Search** <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

リソース、client_id、client_secretの値を取得するには、「承認コードを使用してリダイレクト URL  Web ページでアクセス トークンを要求する」を参照してください。

詳細については、「クイック スタート[: アプリケーションをアプリケーションに](/azure/active-directory/develop/quickstart-register-app)登録する」を参照Microsoft ID プラットフォーム。

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a>手順 3a: 除外する URL を追加する (オプションのクロール制限)

ページがクロールされるのを防ぐ方法は、robots.txt ファイルで禁止するか、除外リストに追加する方法の 2 つがあります。

### <a name="support-for-robotstxt"></a>サービスのrobots.txt

コネクタは、ルート サイトの robots.txt ファイルが存在するかどうかを確認し、存在する場合は、そのファイル内で見つかった方向に従って尊重します。 コネクタでサイト上の特定のページまたはディレクトリをクロールしない場合は、robots.txt ファイルの "Disallow" 宣言でそれらのページまたはディレクトリを呼び出します。

### <a name="add-urls-to-exclude"></a>除外する URL を追加する

必要に応じて除外リストを作成して、コンテンツが機密性の高い場合やクロールする価値がない場合に、一部の URL をクロールから除外できます。 除外リストを作成するには、ルート URL を参照します。 構成プロセス中に、除外された URL をリストに追加できます。

## <a name="step-4-assign-property-labels"></a>手順 4: プロパティ ラベルを割り当てる

各ラベルにソース プロパティを割り当てるには、オプションのメニューから選択します。 この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果の精度が向上します。

## <a name="step-5-manage-schema"></a>手順 5: スキーマの管理

[スキーマの **管理**] 画面で、プロパティに関連付けられたスキーマ属性(オプションはクエリ、**検索**、取得、絞り込 **み)** を変更し、オプションのエイリアスを追加し **、Content** プロパティを選択できます。

## <a name="step-6-manage-search-permissions"></a>手順 6: 検索アクセス許可を管理する

Web Enterpriseコネクタは、Everyone に表示される検索アクセス許可のみを **サポートします**。 インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="step-7-set-the-refresh-schedule"></a>手順 7: 更新スケジュールを設定する

Web Enterpriseコネクタは、完全な更新のみをサポートします。 つまり、更新の度にコネクタが Web サイトのすべてのコンテンツを再スキャンします。 コネクタがコンテンツをクロールするのに十分な時間を取得するには、大規模な更新スケジュール間隔を設定することをお勧めします。 1 ~ 2 週間の間にスケジュールされた更新をお勧めします。

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>トラブルシューティング

Web サイトのコンテンツを読み取る場合、クロールでソース エラーが発生する可能性があります。これは、以下の詳細なエラー コードで表されます。 エラーの種類の詳細については、接続を選択した後でエラー **の詳細** ページに移動します。 エラー コード **を選択して** 、詳細なエラーを表示します。 詳細については、「 [コネクタの管理」](./manage-connector.md) も参照してください。

 詳細なエラー コード | エラー メッセージ
 --- | ---
 6001 | インデックス作成を試みようとしているサイトに到達できない
 6005 | インデックス作成を試みようとしているソース ページは、構成に基robots.txtされています。
 6008 | DNS を解決できません
 6009 | クライアント側のすべてのエラー (HTTP 404、408 を除く) については、HTTP 4xx エラー コードを参照してください。
 6013 | インデックス作成を試みようとしているソース ページが見つかりませんでした。 (HTTP 404 エラー)
 6018 | ソース ページが応答していないと、要求がタイム アウトしました。(HTTP 408 エラー)
 6021 | インデックスを作成するソース ページには、ページにテキスト コンテンツはありません。
 6023 | インデックス作成を試みようとしているソース ページはサポートされていません (HTML ページではありません)
 6024 | インデックス作成を試みようとしているソース ページには、サポートされていないコンテンツがあります。

* エラー 6001~6013 は、ネットワークの問題が原因でデータ ソースに到達できない場合、またはデータ ソース自体が削除、移動、または名前変更された場合に発生します。 提供されたデータ ソースの詳細がまだ有効か確認します。
* エラー 6021-6024 は、データ ソースにページにテキスト以外のコンテンツが含まれている場合、またはページが HTML でない場合に発生します。 データ ソースを確認し、除外リストにこのページを追加するか、エラーを無視します。
