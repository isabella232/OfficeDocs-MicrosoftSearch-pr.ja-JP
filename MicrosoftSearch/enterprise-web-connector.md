---
title: Microsoft Search のエンタープライズ Web サイトコネクタ
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search のエンタープライズ web サイトコネクタを設定する
ms.openlocfilehash: b4d9f837892bcfd795421530e0571fa0509a2761
ms.sourcegitcommit: be0c64845477127d73ee24dc727e4583ced3d0e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48206943"
---
<!-- markdownlint-disable no-inline-html -->
# <a name="enterprise-websites-connector"></a>エンタープライズ web サイトコネクタ

エンタープライズ web サイトコネクタを使用すると、組織は **内部に接続している web サイトの**記事とコンテンツにインデックスを作成できます。 コネクタを構成し、web サイトからコンテンツを同期すると、エンドユーザーは任意の Microsoft 検索クライアントからそのコンテンツを検索できるようになります。

この記事は、 [Microsoft 365](https://www.microsoft.com/microsoft-365) 管理者またはエンタープライズ websites コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。  

## <a name="connect-to-a-data-source"></a>データソースへの接続

データソースに接続するには、 [Azure Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/)を使用して、ルート URL と認証の形式 (None、Basic Authentication、OAuth 2.0) が必要です。

### <a name="authentication"></a>認証

基本認証には、ユーザー名とパスワードが必要です。 [Microsoft 365 管理センター](https://admin.microsoft.com)を使用して、この bot アカウントを作成します。

[AZURE AD](https://docs.microsoft.com/azure/active-directory/)を使用する OAuth 2.0 には、リソース ID、クライアント ID、およびクライアントシークレットが必要です。

詳細については、「 [OAuth 2.0 コード付与フローを使用して Azure Active Directory web アプリケーションへのアクセスを承認する](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)」を参照してください。 次の値を使用して登録します。

**Name:** Microsoft Search <br/>
**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

リソース、client_id、client_secret の値を取得するには、「承認コードを使用して、リダイレクト URL web ページで **アクセストークンを要求** する」に移動します。

詳細については、「 [クイックスタート: アプリケーションを Microsoft identity platform に登録する](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)」を参照してください。

### <a name="root-url"></a>ルート URL

ルート URL は、クロールを開始するもので、認証に使用されます。 クロールする web サイトのホームページから URL を取得できます。

## <a name="select-the-source-properties"></a>ソースのプロパティを選択する

ソースのプロパティは、エンタープライズ web サイトのデータ形式に基づいて定義されます。 ただし、コンテンツに機密がある場合やクロール価値がない場合は、一部の Url をクロール対象から除外する除外 **リスト** を作成できます。 除外リストを作成するには、ルート URL を参照します。 構成プロセス中に、除外された Url をリストに追加するオプションがあります。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する

アクセス制御リスト (Acl) はサポートされていません。 そのため、組織内のすべてのユーザーに表示される web サイトのみを接続することをお勧めします。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する

エンタープライズ web サイトコネクタは、フルクロールのみをサポートします。 これは、すべてのクロール中にコネクタがすべての web サイトのコンテンツを読み取ることを意味します。 コネクタがコンテンツを読み取るのに十分な時間をかけるようにするには、更新のスケジュール間隔を大きくすることをお勧めします。 スケジュールされた更新は、1週間から2週間の間で行うことをお勧めします。

## <a name="troubleshooting"></a>トラブルシューティング

Web サイトのコンテンツを読み取るときに、以下の詳細なエラーコードで示されているソースエラーが発生することがあります。 エラーの種類に関する詳細を確認するには、接続を選択した後、[ **エラーの詳細** ] ページに移動します。 **エラーコード**をクリックして、より詳細なエラーを表示します。 詳細については [、「コネクタの管理](https://docs.microsoft.com/microsoftsearch/manage-connector) 」を参照してください。

 詳細なエラーコード | エラー メッセージ
 --- | ---
 6001 | インデックスを作成しようとしているサイトに到達できない
 6005 | インデックスを作成しようとしているソースページは robots.txt 構成ごとにブロックされています。
 6008 | DNS を解決できない
 6009 | すべてのクライアント側エラー (HTTP 404、408を除く) については、「HTTP 4xx エラーコード」を参照してください。
 6013 | インデックスを作成しようとしているソースページが見つかりませんでした。 (HTTP 404 エラー)
 6018 | ソースページが応答していないため、要求がタイムアウトしました。(HTTP 408 エラー)
 6021 | インデックスを作成しようとしているソースページには、ページ上にテキストコンテンツがありません。
 6023 | インデックスを作成しようとしているソースページはサポートされていません (HTML ページではありません)。
 6024 | インデックスを作成しようとしているソースページに、サポートされていないコンテンツがあります。

* エラー6001-6013 は、ネットワークの問題が原因でデータソースに到達できない場合、またはデータソース自体が削除、移動、または名前変更された場合に発生します。 指定したデータソースの詳細が有効であるかどうかを確認します。
* エラー6021-6024 データソースにページ上にテキスト以外のコンテンツが含まれている場合、またはページが HTML ではない場合にエラーが発生します。 データソースを確認し、このページを除外リストに追加するか、エラーを無視してください。

## <a name="limitations"></a>制限事項

エンタープライズ web サイトコネクタは、 **動的 web ページ**上のデータの検索をサポートしていません。 これらの web ページの例は、コンテンツ管理システム ( [Confluence](https://www.atlassian.com/software/confluence) 、 [Unily](https://www.unily.com/) 、web サイトのコンテンツを格納するデータベースなど) に存在します。
