---
title: ServiceNow GraphコネクタMicrosoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: サービスの ServiceNow Graph コネクタをMicrosoft Search
ms.openlocfilehash: 11abe956e624fa23cd19e2dfc2ae9a4af31a0f81407f6e2c5672723c5fdfc8b5
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54534133"
---
<!---Previous ms.author: kam1 --->


# <a name="servicenow-graph-connector"></a>ServiceNow Graph コネクタ

Microsoft Graph コネクタ for ServiceNow を使用すると、組織内のすべてのユーザーに表示される、または組織内のユーザー条件のアクセス許可で制限されているナレッジ ベースの記事にインデックスを作成できます。 ServiceNow からコネクタとインデックス コンテンツを構成した後、エンド ユーザーは任意のクライアントからそれらの記事Microsoft Searchできます。  

この記事は、Microsoft 365管理者または ServiceNow サーバー コネクタを構成、実行、および監視するGraphです。 この記事では、「コネクタ コネクタのセットアップ」に記載されている一般的Graph[補足](configure-connector.md)します。 まだ実行していない場合は、「コネクタのセットアップ」の記事Graph一般的なセットアップ プロセスを理解してください。

セットアップ プロセスの各手順は、トラブルシューティングと制限事項に関する情報を含む ServiceNow Graph コネクタにのみ適用される一般的なセットアップ手順または他の手順に従う必要があるというメモ[](#troubleshooting)と共に[](#limitations)、以下に示します。  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Graphコネクタを追加Microsoft 365 管理センター。
一般的なセットアップ手順に従います。

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付けています。
一般的なセットアップ手順に従います。


## <a name="step-3-connection-settings"></a>手順 3: 接続設定
ServiceNow データに接続するには、組織の ServiceNow インスタンス **URL が必要です**。 通常、組織の ServiceNow インスタンス URL は、組織 **https:// &lt;>.service-now.com のように表示されます**。 

この URL と共に、ServiceNow への接続をセットアップするサービス アカウントと、Microsoft Search が更新スケジュールに基づいてナレッジ記事を定期的に更新できるようにする必要があります。  サービス アカウントでは、さまざまなエンティティを正常にクロールするには、次の **ServiceNow** テーブル レコードへの読み取りアクセスが必要です。

**機能** | **読み取りアクセス必須テーブル** | **Description**
--- | --- | ---
すべてのユーザーが利用できるナレッジ 記事の <em>インデックスを作成する</em> | kb_knowledge | ナレッジ記事をクロールする場合
ユーザー条件のアクセス許可のインデックスとサポート | kb_uc_can_read_mtom | Whoナレッジ ベースを読み取る
| | kb_uc_can_contribute_mtom | Whoこのナレッジ ベースに貢献できる
| | kb_uc_cannot_read_mtom | Whoナレッジ ベースを読み取りできません
| | kb_uc_cannot_contribute_mtom | Whoナレッジ ベースに貢献できない
| | sys_user | ユーザー テーブルの読み取り
| | sys_user_has_role | ユーザーの役割情報の読み取り
| | sys_user_grmember | ユーザーのグループ メンバーシップの読み取り
| | user_criteria | ユーザー条件のアクセス許可の読み取り
| | kb_knowledge_base | ナレッジ ベース情報の読み取り

サービス アカウント **への接続に使用** するサービス アカウントの役割を作成して割り当Microsoft Search。 [ServiceNow アカウントの役割を割り当てる方法について学習します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。 テーブルへの読み取りアクセスは、作成された役割に割り当てることができます。 テーブル レコードへの読み取りアクセスを設定する方法については、「テーブル レコードの [セキュリティ保護」を参照してください](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)。 


>[!NOTE]
> ServiceNow Graph コネクタは、高度なスクリプトを使用せずにナレッジ記事とユーザー条件のアクセス許可をインデックス化できます。 ユーザー条件に高度なスクリプトが含まれている場合、関連するナレッジ記事はすべて検索結果から非表示になります。

ServiceNow からコンテンツを認証および同期するには、次の 3 つの **サポートされている方法** のいずれかを選択します。 
 
- 基本認証 
- ServiceNow OAuth (推奨)
- Azure AD OpenID Connect

## <a name="step-31-basic-authentication"></a>手順 3.1: 基本認証

インスタンスに対する認証を行うナレッジ ロールを持つ ServiceNow **アカウントのユーザー** 名とパスワードを入力します。

## <a name="step-32-servicenow-oauth"></a>手順 3.2: ServiceNow OAuth

認証に ServiceNow OAuth を使用するには、ServiceNow 管理者が ServiceNow インスタンスでエンドポイントをプロビジョニングし、Microsoft Search アプリがアクセスできる必要があります。 詳細については、ServiceNow のドキュメントの「クライアントがインスタンスにアクセス [する](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) エンドポイントを作成する」を参照してください。

次の表に、エンドポイント作成フォームに入力する方法のガイダンスを示します。

フィールド | 説明 | 推奨値 
--- | --- | ---
名前 | OAuth アクセスが必要なアプリケーションを識別する一意の値。 | Microsoft Search
クライアント ID | アプリケーションの読み取り専用で自動生成された一意の ID。 インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。 | 該当なし
クライアント シークレット | この共有シークレット文字列を使用すると、ServiceNow インスタンスと Microsoft Searchの通信を承認できます。 | シークレットをパスワードとして扱って、セキュリティのベスト プラクティスに従います。
リダイレクト URL | 承認サーバーがリダイレクトする必要なコールバック URL。 | https://gcs.office.com/v1.0/admin/oauth/callback
ロゴ URL | アプリケーション ロゴのイメージを含む URL。 | 該当なし
アクティブ | チェック ボックスをオンにして、アプリケーション レジストリをアクティブにします。 | アクティブに設定する
トークンのライフスパンの更新 | 更新トークンが有効な秒の数。 既定では、更新トークンの有効期限は 100 日 (8,640,000 秒) です。 | 31,536,000 (1 年)
アクセス トークンのライフスパン | アクセス トークンが有効な秒の数。 | 43,200 (12 時間)

インスタンスに接続するクライアント ID とクライアント シークレットを入力します。 接続後、ServiceNow アカウント資格情報を使用してクロールするアクセス許可を認証します。 アカウントには、少なくともナレッジ ロール **が必要** です。 より多くの ServiceNow テーブル レコードへの読み取りアクセスを提供し、ユーザー条件のアクセス許可をインデックス化するための接続設定の手順 [3:](#step-3-connection-settings) の先頭にある表を参照してください。

## <a name="step-33-azure-ad-openid-connect"></a>手順 3.3: Azure AD OpenID Connect

認証に Azure AD OpenID Connectするには、以下の手順に従います。

### <a name="step-331-register-a-new-application-in-azure-active-directory"></a>手順 3.3.1: 新しいアプリケーションを新しいアプリケーションに登録Azure Active Directory

アプリケーションに新しいアプリケーションを登録する方法については、「Azure Active Directoryを登録する[」を参照してください](/azure/active-directory/develop/quickstart-register-app#register-an-application)。 [単一テナントの組織ディレクトリ] を選択します。 リダイレクト URI は不要です。 登録後、アプリケーション (クライアント) ID とディレクトリ (テナント) ID をメモします。

### <a name="step-332-create-a-client-secret"></a>手順 3.3.2: クライアント シークレットを作成する

クライアント シークレットの作成の詳細については、「クライアント シークレットの作成 [」を参照してください](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。 クライアント シークレットをメモします。

### <a name="step-333-retrieve-service-principal-object-identifier"></a>手順 3.3.3: サービス プリンシパル オブジェクト識別子の取得

手順に従ってサービス プリンシパル オブジェクト識別子を取得する

1. PowerShell を実行します。

2. 次のAzure PowerShellを使用してインストールします。

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Connect Azure にアクセスします。

   ```powershell
   Connect-AzAccount
   ```

4. サービス プリンシパル オブジェクト識別子を取得します。

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   手順 3.a で登録したアプリケーションの "Application-ID" をアプリケーション (クライアント) ID (引用符なし) に置き換えてください。 PowerShell 出力からの ID オブジェクトの値に注意してください。 サービス プリンシパル ID です。

これで、Azure portal で必要なすべての情報が取得されます。 情報の簡単な概要を次の表に示します。

プロパティ | 説明 
--- | ---
ディレクトリ ID (テナント ID) | 手順 3.a から、Azure Active Directoryテナントの一意の ID。
アプリケーション ID (クライアント ID) | 手順 3.a で登録されているアプリケーションの一意の ID。
クライアント シークレット | アプリケーションの秘密キー (手順 3.b から)。 パスワードのように扱います。
サービス プリンシパル ID | サービスとして実行されているアプリケーションの ID。 (手順 3.c から)

### <a name="step-334-register-servicenow-application"></a>手順 3.3.4: ServiceNow アプリケーションの登録

ServiceNow インスタンスには、次の構成が必要です。

1. 新しい OAuth OIDC エンティティを登録します。 詳細については [、「Create an OAuth OIDC provider」を参照してください](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

2. 次の表に、OIDC プロバイダー登録フォームに入力する方法のガイダンスを示します。

   フィールド | 説明 | 推奨値
   --- | --- | ---
   名前 | OAuth OIDC エンティティを識別する一意の名前。 | Azure AD
   クライアント ID | サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント ID。 インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。 | 手順 3.a のアプリケーション (クライアント) ID
   クライアント シークレット | サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント シークレット。 | 手順 3.b のクライアント シークレット

   その他の値はすべて既定で指定できます。

3. OIDC プロバイダー登録フォームで、新しい OIDC プロバイダー構成を追加する必要があります。 *[OAuth OIDC* プロバイダー構成] フィールドに対して検索アイコンを選択して、OIDC 構成のレコードを開きます。 [新規]を選択します。

4. 次の表に、OIDC プロバイダー構成フォームに入力する方法のガイダンスを示します。

   フィールド | 推奨値
   --- | ---
   OIDC プロバイダー |  Azure AD
   OIDC メタデータ URL | URL は \: 、/.well known/openid-configuration login.microsoftonline.com/<https //login.microsoftonline.com/<tenandId">形式である必要があります。 <br/>手順 3.a から "tenantID" をディレクトリ (テナント) ID に置き換えてください。
   OIDC 構成キャッシュのライフ スパン |  120
   アプリケーション | グローバル
   ユーザークレーム | sub
   ユーザー フィールド | ユーザー ID
   JTI クレーム検証を有効にする | 無効

5. [OAuth OIDC エンティティ] フォームの [送信と更新] を選択します。

### <a name="step-335-create-a-servicenow-account"></a>手順 3.3.5: ServiceNow アカウントを作成する

手順を参照して ServiceNow アカウントを作成し [、ServiceNow でユーザーを作成します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。

次の表は、ServiceNow ユーザー アカウントの登録に記入する方法に関するガイダンスを示しています。

フィールド | 推奨値
--- | ---
ユーザー ID | 手順 3.c のサービス プリンシパル ID
Web サービス アクセスのみ | Checked

その他の値はすべて既定のままにできます。

### <a name="step-336-enable-knowledge-role-for-the-servicenow-account"></a>手順 3.3.6: ServiceNow アカウントのナレッジ ロールを有効にする

ServiceNow プリンシパル ID をユーザー ID として作成した ServiceNow アカウントにアクセスし、ナレッジ ロールを割り当てる。 ServiceNow アカウントに役割を割り当てる手順については、ここで、ユーザーに役割を割 [り当てる方法をご覧ください](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。 より多くの ServiceNow テーブル レコードへの読み取りアクセスを提供し、ユーザー条件のアクセス許可をインデックス化するための接続設定の手順 [3:](#step-3-connection-settings) の先頭にある表を参照してください。

Azure AD OpenID Connect を使用して ServiceNow インスタンスに対して認証するには、管理センター構成ウィザードでクライアント ID として (手順 3.a から)、クライアント シークレット (手順 3.b から) を使用します。

## <a name="step-4-select-properties-and-filter-data"></a>手順 4: プロパティを選択し、データをフィルター処理する

この手順では、ServiceNow データ ソースから使用可能なプロパティを追加または削除できます。 Microsoft 365では、いくつかのプロパティが既に選択されています。

ServiceNow クエリ文字列を使用すると、記事を同期する条件を指定できます。 これは、Select ステートメント **の Where** **句SQLです**。 たとえば、発行済みおよびアクティブな記事のみをインデックス化できます。 独自のクエリ文字列を作成する方法については、「フィルターを使用してエンコードされたクエリ文字列を [生成する」を参照してください](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。

[プレビュー結果] ボタンを使用して、選択したプロパティとクエリ フィルターのサンプル値を確認します。

## <a name="step-5-manage-search-permissions"></a>手順 5: 検索アクセス許可を管理する

ServiceNow コネクタは、[すべてのユーザー]または [このデータ ソースにアクセスできるユーザーのみ] に表示 **される検索アクセス許可をサポートしています**。 インデックス付きデータは検索結果に表示され、組織内のすべてのユーザー、またはユーザー条件のアクセス許可を介してアクセス権を持つユーザーにそれぞれ表示されます。 ナレッジ 記事がユーザー条件で有効になっていない場合は、組織内のすべてのユーザーの検索結果に表示されます。

ServiceNow Graph コネクタは、高度なスクリプトを使用せずに既定のユーザー条件のアクセス許可をサポートします。 コネクタが高度なスクリプトでユーザー条件を検出すると、そのユーザー条件を使用しているすべてのデータが検索結果に表示されません。

>[!NOTE]
>[この **データ ソースにアクセスできるユーザーのみ] を選択するには、** テナントで対象のリリース更新プログラムを有効にします。 ターゲット リリースの設定の詳細については [、「Setup Targeted release options」を参照してください。](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)

[このデータソースへのアクセス権を持つユーザーのみ] を選択する場合は、ServiceNow インスタンスに Azure Active Directory (AAD) プロビジョニングされたユーザーまたは非 AAD ユーザーが含まれるかどうかをさらに選択する必要があります。

>[!NOTE]
>ID ソースの種類として AAD を選択する場合は、ServiceNow のメール対象プロパティに UserPrincipalName (UPN) ソース プロパティを割り当ててみてください。 マッピングを確認または変更するには、「Azure Active Directory での SaaS アプリケーションのユーザー プロビジョニング属性マッピング[のカスタマイズ」を参照Azure Active Directory。](/azure/active-directory/app-provisioning/customize-application-attributes)

ID の種類に対して "非 AAD" を選択した場合は、「Id のマッピング方法については、「Map your [Azure AD Id」](map-non-aad.md) を参照してください。 

検索アクセス許可の管理の詳細については、次のビデオを参照してください。

[![ServiceNow 用 Microsoft Graph コネクタでの検索アクセス許可の管理](https://img.youtube.com/vi/TVSkJpk1RiE/hqdefault.jpg)](https://www.youtube.com/watch?v=TVSkJpk1RiE)

## <a name="step-6-assign-property-labels"></a>手順 6: プロパティ ラベルを割り当てる

一般的なセットアップ手順に従います。

## <a name="step-7-manage-schema"></a>手順 7: スキーマの管理

一般的なセットアップ手順に従います。

## <a name="step-8-choose-refresh-settings"></a>手順 8: 更新設定を選択する

一般的なセットアップ手順に従います。

>[!NOTE]
>ID の場合は、スケジュールされたフル クロールだけが適用されます。

## <a name="step-9-review-connection"></a>手順 9: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。

ServiceNow Graphコネクタには、最新のリリースで次の制限があります。

接続を公開した後、検索結果ページをカスタマイズする必要があります。 検索結果のカスタマイズの詳細については、「検索結果のカスタマイズ [ページ」を参照してください](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。

## <a name="limitations"></a>制限事項
ServiceNow Graphコネクタには、最新のリリースで次の制限があります。
- 組織内のすべてのユーザーが利用できるナレッジ 記事のインデックス作成は、一般的に利用できる機能です。
- *[検索のアクセス許可の管理] 手順* でこのデータ ソース機能にアクセスできるユーザーだけが対象のリリース チャネルに含まれており、ユーザー条件のアクセス許可 [のみを](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 処理します。 その他の種類のアクセス許可は検索結果には適用されません。
- 高度なスクリプトを含むユーザー条件は、現在のバージョンではサポートされていません。 このようなアクセス制限を持つナレッジ記事は、すべてのユーザーのアクセスを拒否するインデックスが作成されます。つまり、サポートするまで、すべてのユーザーに検索結果に表示されません。

## <a name="troubleshooting"></a>トラブルシューティング
接続を発行し、結果ページをカスタマイズした後、管理センターの [ **データ** ソース] タブの状態を [確認できます](https://admin.microsoft.com)。 更新と削除を行う方法については、「コネクタの管理 [」を参照してください](manage-connector.md)。
一般的に見られる問題のトラブルシューティング手順については、以下をご覧ください。
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a>1. シングル アクセスが有効になっている ServiceNow インスタンスSign-Onログインできません

組織で ServiceNow へのシングル Sign-On (SSO) を有効にしている場合、サービス アカウントでのログインに問題が発生する可能性があります。 ServiceNow インスタンス URL に追加することで、<em> `login.do` </em>ユーザー名とパスワードベースのログインを表示できます。 例。 `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a>2. API 要求に対する承認されていない応答または禁止された応答

#### <a name="21-check-table-access-permissions"></a>2.1. テーブル のアクセス許可を確認する
接続状態に禁止または承認されていない応答が表示される場合は、手順 3: 接続設定で説明されているテーブルへのアクセスがサービス アカウントに必要なアクセス権を持つ [必要がある場合を確認します](#step-3-connection-settings)。 テーブル内のすべての列に読み取りアクセス権が設定されているかどうかを確認してください。

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a>2.2. ファイアウォールの背後にある ServiceNow インスタンスを確認する
Graphネットワーク ファイアウォールの背後にある場合、コネクタが ServiceNow インスタンスに到達できない場合があります。 コネクタ サービスへのアクセスを明示的に許可Graph必要があります。 コネクタ サービスのパブリック IP アドレス範囲Graph表に示します。 テナント地域に基づいて、ServiceNow インスタンスネットワークホワイトリストに追加します。

**環境** | **Region** | **Range**
--- | --- | ---
PROD | 北アメリカ | 52.250.92.252/30, 52.224.250.216/30
PROD | ヨーロッパ | 20.54.41.208/30, 51.105.159.88/30 
PROD | アジア太平洋 | 52.139.188.212/30, 20.43.146.44/30 


その他の問題がある場合、またはフィードバックを提供する場合は、お問い [合わせ aka.ms/TalkToGraphConnectors](https://aka.ms/TalkToGraphConnectors)
