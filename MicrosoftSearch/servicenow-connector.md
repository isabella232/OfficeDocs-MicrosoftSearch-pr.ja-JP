---
title: Microsoft Search 用の ServiceNow コネクタ
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の ServiceNow コネクタをセットアップする
ms.openlocfilehash: f7ae05ad00a96a6f05780acfeb8c75911505ee6f
ms.sourcegitcommit: 2ce86461e845c3ea84feb215df17685d2ef705c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48340858"
---
# <a name="servicenow-connector"></a>ServiceNow コネクタ

ServiceNow コネクタを使用すると、組織内のすべてのユーザーに表示されるナレッジベースの記事にインデックスを作成できます。 ServiceNow からコネクタとインデックスコンテンツを構成した後は、エンドユーザーは任意の Microsoft 検索クライアントからこれらの記事を検索できます。  

この記事は、Microsoft 365 管理者、または ServiceNow コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

Microsoft によって作成された microsoft [のコネクタを Microsoft Search 用にセットアップして、](https://docs.microsoft.com/microsoftsearch/configure-connector)microsoft の作成済みコネクタにアクセスする方法について説明します。 ServiceNow connector 固有の構成については、以下の記事で説明します。

## <a name="connection-settings"></a>接続設定
ServiceNow データに接続するには、組織の **servicenow インスタンスの URL**、このアカウントの資格情報、および OAuth 認証用のクライアント ID とクライアントシークレットが必要です。  

組織の **ServiceNow インスタンスの URL** は、通常 ** &lt; 、https://> service-now.com**のようになります。 この URL に加えて、ServiceNow への接続を設定するためのアカウントと、更新スケジュールに基づいて、Microsoft Search が ServiceNow から定期的に記事を更新できるようにする必要があります。 このアカウントには、 <em>ナレッジ</em> の役割が必要です。 [ServiceNow アカウントの役割を割り当てる方法について説明](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)します。

ServiceNow からコンテンツを認証および同期するには、次の3つのサポートされている方法 **のいずれか** を選択します。 
1. 基本認証 
2. ServiceNow OAuth (推奨)
3. Azure AD OpenID Connect

#### <a name="basic-authentication"></a>基本認証
ユーザーのインスタンスに対して認証を行うための、 <em>サポート</em> の役割を持つ ServiceNow アカウントのユーザー名とパスワードを入力します。
#### <a name="servicenow-oauth"></a>ServiceNow OAuth

認証に ServiceNow OAuth を使用するには、Microsoft Search アプリがインスタンスにアクセスできるようにするために、servicenow 管理者が ServiceNow インスタンスでエンドポイントを準備する必要があります。 詳細については、「クライアントが ServiceNow ドキュメントの [インスタンスにアクセスするためのエンドポイントを作成する](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) 」を参照してください。

次の表に、エンドポイント作成フォームに記入する方法についてのガイダンスを示します。

**Field** | **説明** | **推奨値**
--- | --- | ---
名前 | この一意の値は、OAuth アクセスを必要とするアプリケーションを識別します。 | Microsoft Search
クライアント ID | 読み取り専用で、自動生成されたアプリケーションの一意の ID。 このインスタンスは、アクセストークンを要求するときにクライアント ID を使用します。 | 該当なし
クライアントシークレット | この共有シークレット文字列を使用すると、ServiceNow インスタンスと Microsoft Search は相互に通信を承認します。 | これをパスワードとして扱うことにより、セキュリティのベストプラクティスに従います。
リダイレクト URL | 承認サーバーのリダイレクト先となる必要なコールバック URL。 | https://gcs.office.com/v1.0/admin/oauth/callback
ロゴの URL | アプリケーションロゴのイメージを含む URL。 | 該当なし
Active | アプリケーションレジストリをアクティブにするには、チェックボックスをオンにします。 | Active に設定
トークンの寿命を更新する | 更新トークンが有効になる秒数。 既定では、更新トークンの有効期限は100日 (864万秒) です。 | 31536000 (1 年)
アクセストークンの寿命 | アクセストークンの有効期間 (秒数)。 | 43200 (12 時間)

クライアント id とクライアントシークレットを入力して、インスタンスに接続します。 接続した後、ServiceNow アカウントの資格情報を使用して、クロールするためのアクセス許可を認証します。 このアカウントには、 <em>ナレッジ</em> の役割が必要です。 

#### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Azure AD OpenID Connect を認証に使用するには、次の手順を実行します。

###### <a name="step-1-register-a-new-application-in-azure-active-directory"></a>手順 1: Azure Active Directory に新しいアプリケーションを登録する

Azure Active Directory に新しいアプリケーションを登録する方法については、「 [アプリケーションを登録](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application)する」を参照してください。 [単一テナントの組織ディレクトリ] を選択します。 リダイレクト URI は必要ありません。 登録後、アプリケーション (クライアント) ID とディレクトリ (テナント) ID を書き留めます。

###### <a name="step-2-create-a-client-secret"></a>手順 2: クライアントシークレットを作成する

クライアントシークレットを作成する方法については、「 [クライアントシークレットの作成](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)」を参照してください。 クライアントシークレットをメモします。

###### <a name="step-3-retrieve-service-principal-object-identifier"></a>手順 3: サービスプリンシパルオブジェクト識別子を取得する

手順に従ってサービスプリンシパルオブジェクト識別子を取得する

1. PowerShell を実行する
2. 次のコマンドを使用して Azure PowerShell をインストールする
```<language>
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
```
3. Azure への接続
```<language>
    Connect-AzAccount
```
4. サービスプリンシパルオブジェクト識別子を取得する
```<language>
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
```
手順1で登録したアプリケーションの "アプリケーション ID" を (引用符を除く) アプリケーション (クライアント) ID に置き換えます。 PowerShell 出力からの ID オブジェクトの値に注意してください。 これは、サービスプリンシパル ID です。

これで、Azure portal から必要な情報がすべて得られました。 情報の簡単な概要については、以下の表で説明します。

**Property** | **説明**
--- | ---
ディレクトリ ID (テナント ID) | これは、Azure Active Directory テナントを参照する一意の ID です (手順1を参照)。
アプリケーション ID (クライアント ID) | これは、手順1で登録したアプリケーションを参照する一意の ID です。
クライアントの秘密情報 | これは、(手順2から) アプリケーションの秘密キーです。 パスワードと同じように扱います。
サービスプリンシパル ID | サービスとして実行されているアプリケーションの id。 (手順 3)

###### <a name="step-4-register-servicenow-application"></a>手順 4: ServiceNow アプリケーションを登録する

ServiceNow インスタンスでは、次の構成を行う必要があります。

1. 新しい OAuth OIDC エンティティを登録します。 詳細については、「 [Create An OAuth OIDC provider](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)」を参照してください。
2. 次の表では、OIDC プロバイダ登録フォームに記入する方法についてのガイダンスを示します。

**Field** | **説明** | **推奨値**
--- | --- | ---
名前 | OAuth OIDC エンティティを識別する一意の名前。 | Azure AD
クライアント ID | サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント ID。 このインスタンスは、アクセストークンを要求するときにクライアント ID を使用します。 | 手順1のアプリケーション (クライアント) ID
クライアントの秘密情報 | サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアントシークレット。 | 手順2のクライアントシークレット

その他の値はすべて既定値にすることができます。

3. OIDC プロバイダ登録フォームで、新しい OIDC プロバイダ構成を追加する必要があります。 *OAUTH Oidc プロバイダ構成*フィールドに対して [検索] アイコンをクリックして、oidc 構成のレコードを開きます。 [新規作成] をクリックします。
4. 次の表では、OIDC プロバイダ構成フォームに記入する方法についてのガイダンスを示します。

**Field** | **推奨値**
--- | ---
OIDC プロバイダ |  Azure AD
OIDC メタデータの URL | これは https \: //login.microsoftonline.com/"/.well-known/openid-configuration" という形式でなければなりません。 <br/>手順 1 (引用符なし) の "tenantID" をディレクトリ (テナント) ID に置き換えます。
OIDC 構成キャッシュの有効期間 |  120
アプリケーション | グローバル
ユーザー要求 | 形式
ユーザーフィールド | ユーザー ID
JTI クレーム検証を有効にする | 無効

5. [Submit and Update OAuth OIDC Entity] フォームをクリックします。

###### <a name="step-5-create-a-servicenow-account"></a>手順 5: ServiceNow アカウントを作成する

ServiceNow アカウントを作成する手順を参照し、 [servicenow でユーザーを作成](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)します。

次の表に、ServiceNow ユーザーアカウント登録に記入する方法についてのガイダンスを示します。

**Field** | **推奨値**
--- | ---
ユーザー ID | 手順3のサービスプリンシパル ID
Web サービスのアクセスのみ | Checked

その他の値は、すべて既定のままにしておくことができます。

###### <a name="step-6-enable-knowledge-role-for-the-servicenow-account"></a>手順 6: ServiceNow アカウントのナレッジロールを有効にする

ServiceNow プリンシパル ID を使用して作成した ServiceNow アカウントにユーザー ID としてアクセスし、ナレッジの役割を割り当てます。 ServiceNow アカウントに役割を割り当てる手順については、「 [ユーザーに役割を割り当てる](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)」を参照してください。

管理センター構成ウィザードのクライアント ID (手順 1) とクライアントシークレット (手順 2) を使用して、Azure AD OpenID Connect を使用して ServiceNow インスタンスを認証します。

## <a name="filter-data"></a>データをフィルター処理する 
ServiceNow クエリ文字列を使用すると、記事を同期するための条件を指定できます。 **SQL Select**ステートメントの**where**句のようになります。 たとえば、公開されていてアクティブな記事のみにインデックスを作成することを選択できます。 独自のクエリ文字列を作成する方法については、「 [フィルターを使用してエンコードされたクエリ文字列を生成](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)する」を参照してください。

## <a name="manage-the-search-schema"></a>検索スキーマを管理する
接続が成功した後、検索スキーママッピングを構成します。 **クエリ**可能、**検索**可能、および取得可能なプロパティを選択でき**ます。** 検索スキーマの管理の詳細については、「 [Manage the search schema](https://docs.microsoft.com/microsoftsearch/configure-connector#manage-the-search-schema)」を参照してください。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する
ServiceNow コネクタは、 **すべてのユーザー**に表示される検索アクセス許可のみをサポートします。 インデックス付きデータが検索結果に表示され、組織内のすべてのユーザーに表示されます。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する
ServiceNow コネクタは、フルクロールと増分クロールの両方の更新スケジュールをサポートします。 両方を設定することをお勧めします。

フルクロールスケジュールは、Microsoft 検索インデックスと同期フィルターから移動したすべての記事に対して以前に同期された削除済み記事を検索します。 最初に ServiceNow に接続すると、フルクロールが実行され、すべてのナレッジベースの記事が同期されます。 新しいアイテムを同期し、更新を行うには、増分クロールをスケジュールする必要があります。

推奨される既定値は、フルクロールの場合は1日、増分クロールの場合は4時間です。
## <a name="review-and-publish"></a>レビューと発行
コネクタを構成した後、接続を確認して発行することができます。

## <a name="next-steps"></a>次の手順
接続を公開した後、[検索結果] ページをカスタマイズする必要があります。 検索結果のカスタマイズについては、「 [検索結果ページをカスタマイズ](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)する」を参照してください。
