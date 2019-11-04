---
title: Microsoft Search のエンタープライズ Web サイトコネクタ
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search のエンタープライズ web サイトコネクタを設定する
ms.openlocfilehash: 3caca53204bfb2cca4209e048a21173f550e3d39
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949940"
---
# <a name="enterprise-websites-connector"></a>エンタープライズ web サイトコネクタ

エンタープライズ web サイトコネクタを使用すると、組織は**内部に接続している web サイトの**記事とコンテンツにインデックスを作成できます。 コネクタを構成し、web サイトからコンテンツを同期すると、エンドユーザーは任意の Microsoft 検索クライアントからそのコンテンツを検索できるようになります。

この記事は、Microsoft 365 管理者またはエンタープライズ websites コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。  

## <a name="connect-to-a-data-source"></a>データソースへの接続 
データソースに接続するには、ルート URL と認証の形式 (Azure AD を使用する基本認証または OAuth 2.0) が必要です。

### <a name="root-url"></a>ルート URL
ルート URL は、クロールを開始するもので、認証に使用されます。 クロールする web サイトのホームページから URL を取得できます。

### <a name="authentication"></a>認証 
基本認証には、ユーザー名とパスワードが必要です。 [Microsoft 365 管理センター](https://admin.microsoft.com)を使用して、この bot アカウントを作成します。

Azure AD を使用する OAuth 2.0 には、テナント ID、リソース ID、クライアント ID、およびクライアントシークレットが必要です。
詳細については、「 [OAuth 2.0 コード付与フローを使用して Azure Active Directory web アプリケーションへのアクセスを承認する](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)」を参照してください。 次の値を使用して登録します。
* **Name:** Microsoft Search
* **Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`

名前付きテナント、resource、client_id、および client_secret の値を取得するには、「承認コードを使用して、リダイレクト URL の web ページで**アクセストークンを要求**します。

詳細については、「[クイックスタート: アプリケーションを Microsoft identity platform に登録する](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)」を参照してください。

### <a name="reverse-proxy-url"></a>リバースプロキシの URL 
エンタープライズ web サイトコネクタはクラウドベースであるため、オンプレミスのコンテンツにはアクセスしません。 そのアクセスを提供するには、リバースプロキシをインストールします。 リバースプロキシは、オンプレミスの web サイトへの安全で信頼できるアクセスを提供します。 Azure アプリケーションプロキシ (AAP) をお勧めします。

ルート URL と認証のリバースプロキシの要件は、クラウドベースのコンテンツの場合と同じですが、ルート URL と認証はリバースプロキシサーバーによって提供される点が異なります。

[AZURE AD アプリケーションプロキシを使用してリモートでアプリにアクセスする場合のセキュリティに関する考慮事項を](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-security)参照してください。

## <a name="select-the-source-properties"></a>ソースのプロパティを選択する 
ソースのプロパティは、エンタープライズ web サイトのデータ形式に基づいて定義されます。 ただし、コンテンツが機密である場合やクロールに価値がない場合があるため、一部の Url をクロール対象から除外する除外**リスト**を作成できます。 除外リストを作成するには、ルート URL を参照します。 構成プロセス中に、除外された Url をリストに追加するオプションがあります。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する 
アクセス制御リスト (Acl) はサポートされていません。 そのため、組織内のどのユーザーにも表示されている web サイトのみを接続することをお勧めします。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する
エンタープライズ web サイトコネクタは、フルクロールのみをサポートします。 これは、すべてのクロール中にコネクタがすべての web サイトのコンテンツを読み取ることを意味します。 コネクタがコンテンツを読み取るのに十分な時間がかかることを確認するには、更新スケジュールの間隔を長く設定することをお勧めします。 更新スケジュールは3日から2週間にすることをお勧めします。

## <a name="limitations"></a>制限事項 
エンタープライズ web サイトコネクタは、動的 web ページ上のデータの検索をサポートしていません。 これらの web ページの例は、コンテンツ管理システム (Confluence、Unily、web サイトのコンテンツを格納するデータベースなど) に存在します。