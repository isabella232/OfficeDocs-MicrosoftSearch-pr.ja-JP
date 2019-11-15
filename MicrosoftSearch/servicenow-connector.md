---
title: Microsoft Search 用の ServiceNow コネクタ
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の ServiceNow コネクタをセットアップする
ms.openlocfilehash: 78b2831e9a52b6bf0204b5a6b2aba147b529b3f5
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626956"
---
# <a name="servicenow-connector"></a>ServiceNow コネクタ

ServiceNow コネクタを使用すると、組織内のすべてのユーザーに表示されるナレッジベースの記事にインデックスを作成できます。 ServiceNow からコネクタとインデックスコンテンツを構成した後は、エンドユーザーは任意の Microsoft 検索クライアントからこれらの記事を検索できます。  

この記事は、Microsoft 365 管理者、または ServiceNow コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

## <a name="connect-to-a-data-source"></a>データソースへの接続
ServiceNow データに接続するには、組織の**servicenow インスタンスの URL**、このアカウントの資格情報、および OAuth 認証用のクライアント ID とクライアントシークレットが必要です。  

組織の**ServiceNow インスタンスの URL**は、通常 **、&lt;https://> service-now.com**のようになります。 この URL に加えて、ServiceNow への接続を設定するためのアカウントと、更新スケジュールに基づいて、Microsoft Search が ServiceNow から定期的に記事を更新できるようにする必要があります。

ServiceNow からコンテンツを認証および同期するには、次の2つのサポートされている方法のいずれかを選択します。 
1. 基本認証 
2. OAuth (推奨)

> [!Note]
> 認証に OAuth を使用するには、servicenow 管理者が ServiceNow インスタンスにエンドポイントをプロビジョニングする必要があります。これにより、Microsoft Search アプリがインスタンスにアクセスできるようになります。 詳細については、「クライアントが ServiceNow ドキュメントの[インスタンスにアクセスするためのエンドポイントを作成する](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html)」を参照してください。

次の表に、エンドポイント作成フォームに記入する方法についてのガイダンスを示します。

**Field** | **説明** | **推奨値**
--- | --- | ---
名前 | この一意の値は、OAuth アクセスを必要とするアプリケーションを識別します。 | Microsoft Search
クライアント ID | 読み取り専用で、自動生成されたアプリケーションの一意の ID。 このインスタンスは、アクセストークンを要求するときにクライアント ID を使用します。 | 該当なし
クライアントシークレット | この共有シークレット文字列を使用すると、ServiceNow インスタンスと Microsoft Search は相互に通信を承認します。 | これをパスワードとして扱うことにより、セキュリティのベストプラクティスに従います。
リダイレクト URL | 承認サーバーのリダイレクト先となる必要なコールバック URL。 | [OAuth callback](https://gcs.office.com/v1.0/admin/oauth/callback)を参照してください。
ロゴの URL | アプリケーションロゴのイメージを含む URL。 | 該当なし
Active | アプリケーションレジストリをアクティブにするには、チェックボックスをオンにします。 | Active に設定
トークンの寿命を更新する | 更新トークンが有効になる秒数。 既定では、更新トークンの有効期限は100日 (864万秒) です。 | 31536000 (1 年)
アクセストークンの寿命 | アクセストークンの有効期間 (秒数)。 | 43200 (12 時間)

## <a name="set-a-sync-filter"></a>同期フィルターを設定する 
同期フィルターを使用すると、記事を同期するための条件を指定できます。 **SQL Select**ステートメントの**where**句のようになります。 たとえば、公開されていてアクティブな記事のみにインデックスを作成することを選択できます。 [SyncNow の構成] ページには、同期フィルターをキャプチャして設定する方法が記載されています。

## <a name="manage-the-search-schema"></a>検索スキーマを管理する
接続が成功した後、検索スキーママッピングを構成します。 **クエリ**可能、**検索**可能、および取得可能なプロパティを選択でき**ます。**

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する
ServiceNow コネクタは、**すべてのユーザー**に表示される検索アクセス許可のみをサポートします。 インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。
 
## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する 
ServiceNow コネクタは、フルクロールと増分クロールの両方の更新スケジュールをサポートします。 両方を設定することをお勧めします。

フルクロールスケジュールは、Microsoft 検索インデックスと同期フィルターから移動したすべての記事に対して以前に同期された削除済み記事を検索します。 最初に ServiceNow に接続すると、フルクロールが実行され、すべてのナレッジベースの記事が同期されます。 新しいアイテムを同期し、更新を行うには、増分クロールをスケジュールする必要があります。

推奨される既定値は、フルクロールの場合は1日、増分クロールの場合は4時間です。
