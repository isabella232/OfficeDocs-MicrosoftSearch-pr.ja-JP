---
title: Microsoft Search のエンタープライズ Web サイト Graph コネクタ
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の Enterprise Web サイト Graph コネクタをセットアップする
ms.openlocfilehash: bf706399ec55fafbe96ce53622ce8502c81c2190
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084886"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a>エンタープライズ Web サイト Graph コネクタ

Enterprise Websites Graph コネクタを使用すると、組織は内部向け Web サイトの記事やコンテンツに **インデックスを作成できます**。 コネクタを構成し、Web サイトからコンテンツを同期すると、エンド ユーザーは任意の Microsoft Search クライアントからそのコンテンツを検索できます。

> [!NOTE]
> Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、一般的な Graph コネクタのセットアップ プロセスについて説明します。

この記事は、ServiceNow Graph コネクタを構成、実行、および監視するユーザーを対象にしています。 一般的なセットアップ プロセスを補完し、ServiceNow Graph コネクタにのみ適用する手順を示します。 この記事には、トラブルシューティングと [制限事項に関する](#troubleshooting) 情報も [含まれています](#limitations)。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

データ ソースに接続するには、Web サイトのルート URL を入力し、クロール ソースを選択し、使用する認証の種類 (なし、基本認証、 [または Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/)を使用した OAuth 2.0) を選択する必要があります。 この情報を入力したら、[テスト接続] を選択して設定を確認します。

### <a name="url"></a>URL

URL フィールドを使用して、クロールする Web サイトのルートを指定します。 エンタープライズ Web サイト コネクタは、この URL を開始点として使用し、この URL からのすべてのリンクをクロールに従います。

### <a name="crawl-mode-cloud-or-on-premises-preview"></a>クロール モード: クラウドまたはオンプレミス (プレビュー)

クロール モードでは、クラウドまたはオンプレミスのどちらかで、インデックスを作成する Web サイトの種類を決定します。 クラウド Web サイトの場合は、クロール **モードとして [クラウド** ] を選択します。

また、このコネクタは、オンプレミスの Web サイトのクロールもサポートしています。 このモードはプレビュー中です。 オンプレミスのデータにアクセスするには、最初に Graph コネクタ エージェントをインストールして構成する必要があります。 詳細については [、「Graph コネクタ エージェント」を参照してください](https://docs.microsoft.com/microsoftsearch/on-prem-agent)。

オンプレミス Web サイトの場合は、クロール モードとして [エージェント]を選択し、[オンプレミス エージェント] フィールドで、前にインストールして構成した Graph コネクタ エージェントを選択します。  

> [!div class="mx-imgBorder"]
> ![エンタープライズ Web コネクタの [接続設定] ウィンドウのスクリーンショット](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)

### <a name="authentication"></a>認証

基本認証には、ユーザー名とパスワードが必要です。 Microsoft 365 管理センターを使用して [、このボット アカウントを作成します](https://admin.microsoft.com)。

Azure ADを使用した OAuth 2.0 には、 [リソース](https://docs.microsoft.com/azure/active-directory/) ID、クライアント ID、およびクライアント シークレットが必要です。 OAuth 2.0 はクラウド モードでのみ動作します。

詳細については [、「OAuth 2.0](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)コード付与フローを使用して Azure Active Directory Web アプリケーションへのアクセスを承認する」を参照してください。 次の値を使用して登録します。

**名前:** Microsoft Search <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

リソース、client_id、および client_secret の値を取得するには、「認証コードを使用して、リダイレクト URL の Web ページでアクセス トークンを要求する」に移動します。

詳細については、「クイック スタート: Microsoft ID プラットフォームにアプリケーションを [登録する」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a>手順 3a: 除外する URL を追加する (オプションのクロール制限)

ページがクロールされるのを防ぐには、robots.txt ファイルで禁止する方法と除外一覧に追加する方法の 2 つがあります。

### <a name="support-for-robotstxt"></a>サービスのrobots.txt

コネクタは、ルート サイト用の robots.txt ファイルが存在するかどうかを確認し、存在する場合は、そのファイル内で見つかったルート案内に従って従います。 コネクタでサイト上の特定のページまたはディレクトリをクロールしない場合は、robots.txt ファイルの "Disallow" 宣言でこれらのページまたはディレクトリを呼び出します。

### <a name="add-urls-to-exclude"></a>除外する URL を追加する

必要に応じて、除外一覧を作成して、そのコンテンツが機密性の高い場合やクロールする価値がない場合に、一部の URL をクロール対象から除外できます。 除外一覧を作成するには、ルート URL を参照します。 構成プロセス中に、除外された URL をリストに追加できます。

## <a name="step-4-assign-property-labels"></a>手順 4: プロパティ ラベルを割り当てる

オプションのメニューから選択すると、ソース プロパティを各ラベルに割り当てできます。 この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果の精度が向上します。

## <a name="step-5-manage-schema"></a>手順 5: スキーマを管理する

[スキーマ **の管理**] 画面では、プロパティに関連付けられているスキーマ属性(クエリ、**検索**、**取得**、絞り込み **オプション)** を変更し、オプションのエイリアスを追加して **、Content** プロパティを選択できます。

## <a name="step-6-manage-search-permissions"></a>手順 6: 検索権限を管理する

エンタープライズ Web サイト コネクタは、すべてのユーザーに表示される検索アクセス許可のみをサポート **します**。 インデックス付きデータは検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="step-7-set-the-refresh-schedule"></a>手順 7: 更新スケジュールを設定する

エンタープライズ Web サイト コネクタは、完全な更新のみをサポートします。 つまり、コネクタは更新の間に Web サイトのすべてのコンテンツを再スキャンします。 コネクタがコンテンツをクロールするのに十分な時間を取得するには、大規模な更新スケジュール間隔を設定することをお勧めします。 1 週間から 2 週間の間にスケジュールされた更新をお勧めします。

## <a name="step-8-review-connection"></a>手順 8: 接続を確認する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>トラブルシューティング

Web サイトのコンテンツを読み取る際に、クロールでソース エラーが発生する場合があります。これは、以下の詳細なエラー コードで表されます。 エラーの種類に関する詳細を取得するには、接続を **選択した後** 、エラーの詳細ページに移動します。 エラー コード **を選択すると** 、より詳細なエラーが表示されます。 詳細については、「 [コネクタの管理」](https://docs.microsoft.com/microsoftsearch/manage-connector) も参照してください。

 詳細なエラー コード | エラー メッセージ
 --- | ---
 6001 | インデックス作成を試みたサイトに到達できません
 6005 | インデックス作成を試みようとしているソース ページは、構成に基robots.txtされています。
 6008 | DNS を解決できません
 6009 | クライアント側のすべてのエラー (HTTP 404、408 を除く) の詳細については、HTTP 4xx エラー コードを参照してください。
 6013 | インデックスを作成しようとしたソース ページが見つかりませんでした。 (HTTP 404 エラー)
 6018 | ソース ページが応答していないので、要求がタイム アウトしました。(HTTP 408 エラー)
 6021 | インデックスを作成しようとしたソース ページには、ページ上にテキスト コンテンツはありません。
 6023 | インデックスを作成しようとしたソース ページがサポートされていません (HTML ページではありません)
 6024 | インデックス作成を試みようとしているソース ページに、サポートされていないコンテンツがあります。

* ネットワークの問題が原因でデータ ソースに到達できない場合、またはデータ ソース自体が削除、移動、または名前変更された場合に、エラー 6001 から 6013 が発生します。 指定されたデータ ソースの詳細がまだ有効な場合に確認します。
* エラー 6021 から 6024 は、データ ソースにページにテキスト以外のコンテンツが含まれている場合、またはページが HTML ではない場合に発生します。 データ ソースを確認し、除外一覧にこのページを追加するか、エラーを無視します。

## <a name="limitations"></a>制限事項

エンタープライズ Web サイト コネクタは、動的 Web ページ上のデータの検索 **をサポートしています**。 これらの Web ページの例は [、Confluence](https://www.atlassian.com/software/confluence) や [Unily](https://www.unily.com/) のようなコンテンツ管理システム、または Web サイトコンテンツを格納するデータベースに含まれています。