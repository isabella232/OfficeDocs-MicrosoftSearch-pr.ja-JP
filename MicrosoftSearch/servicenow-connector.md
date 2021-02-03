---
title: Microsoft Search の ServiceNow Graph コネクタ
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
description: Microsoft Search の ServiceNow Graph コネクタをセットアップする
ms.openlocfilehash: d1fdfb5f1aec5091fd526152de2bdc86932cfdb9
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084895"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph コネクタ

ServiceNow Graph コネクタを使用すると、組織内のユーザー条件のアクセス許可に従って、ユーザーに表示されるナレッジ ベースの記事のインデックスを作成できます。 ServiceNow からコネクタとインデックス コンテンツを構成すると、ユーザーは任意の Microsoft Search クライアントから記事を検索できます。

> [!NOTE]
> Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、Graph コネクタの一般的なセットアップ プロセスを理解してください。

この記事は、ServiceNow Graph コネクタを構成、実行、および監視するユーザーを対象にしています。 一般的なセットアップ プロセスを補完し、ServiceNow Graph コネクタにのみ適用される手順を示します。 この記事には、トラブルシューティングと [制限事項に関する](#troubleshooting) 情報も [含まれています](#limitations)。
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>手順 3: 接続設定

ServiceNow データに接続するには、このアカウントの組織の **ServiceNow** インスタンス URL 資格情報、クライアント ID、および OAuth 認証用のクライアント シークレットを使用します。  

組織の **ServiceNow** インスタンスの URL は、通常、組織https://ドメイン **&lt;>.service-now.com。** この URL と共に、ServiceNow への接続を設定し、Microsoft Search が更新スケジュールに基づいて ServiceNow から記事を更新できるように、アカウントが必要です。 アカウントには、少なくともナレッジ ロールが <em>必要</em> です。 [ServiceNow アカウントにロールを割り当てる方法について学習します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。

>[!NOTE]
>Microsoft Search の結果でナレッジ記事のアクセス許可を受け入れ、ユーザーおよびグループ ID をクロールする場合、アカウントは ServiceNow の次の表のレコードを読み取るアクセス権を持っている必要があります。
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Microsoft Search への接続に使用するアカウントの役割を作成して割り当てできます。 テーブルへの読み取りアクセス権は、そのロールに割り当てることができます。 テーブル レコードへの読み取りアクセスを設定する方法については、「テーブル レコードの [セキュリティ保護」を参照してください](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)。

ServiceNow からコンテンツを認証して同期するには、次の 3 つのサポート **される** 方法のいずれかを選択します。

1. 基本認証
1. ServiceNow OAuth (推奨)
1. Azure AD OpenID Connect

### <a name="basic-authentication"></a>基本認証

インスタンスに対する認証を行うナレッジロールを持つ ServiceNow アカウントのユーザー名とパスワードを入力します。

### <a name="servicenow-oauth"></a>ServiceNow OAuth

認証に ServiceNow OAuth を使用するには、ServiceNow インスタンスにエンドポイントを準備します。 Microsoft Search アプリは、このアプリを使用してインスタンスにアクセスします。 詳細については、ServiceNow ドキュメント [の「クライアントがインスタンスにアクセス](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) するエンドポイントを作成する」を参照してください。

次の表に、エンドポイント作成フォームに入力する方法のガイダンスを示します。

Field | 説明 | 推奨値 
--- | --- | ---
名前 | OAuth アクセスが必要なアプリケーションを識別する一意の値。 | Microsoft Search
クライアント ID | アプリケーションの読み取り専用で自動生成された一意の ID。 インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。 | 該当なし
クライアント シークレット | この共有シークレット文字列を使用すると、ServiceNow インスタンスと Microsoft Search は互いに通信を承認します。 | シークレットをパスワードとして扱って、セキュリティのベスト プラクティスに従います。
リダイレクト URL | 認証サーバーがリダイレクトする必須のコールバック URL。 | https://gcs.office.com/v1.0/admin/oauth/callback
ロゴ URL | アプリケーション ロゴのイメージを含む URL。 | 該当なし
Active | チェック ボックスをオンにして、アプリケーション レジストリをアクティブにします。 | アクティブに設定
更新トークンの有効期限 | 更新トークンが有効な時間 (秒)。 既定では、更新トークンの有効期限は 100 日 (8,640,000 秒) です。 | 31,536,000 (1 年間)
アクセス トークンの有効期限 | アクセス トークンが有効な時間 (秒)。 | 43,200 (12 時間)

インスタンスに接続するクライアント ID とクライアント シークレットを入力します。 接続後、ServiceNow アカウント資格情報を使用してクロールのアクセス許可を認証します。 アカウントには、少なくともナレッジ ロールが **必要** です。

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

認証に Azure AD OpenID Connect を使用するには、次の手順を実行します。

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>手順 3.a: Azure Active Directory に新しいアプリケーションを登録する

Azure Active Directory に新しいアプリケーションを登録する方法については、「アプリケーションの登録 [」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application)。 単一テナントの組織ディレクトリを選択します。 リダイレクト URI は必要ない。 登録後、アプリケーション (クライアント) ID とディレクトリ (テナント) ID をメモします。

## <a name="step-3b-create-a-client-secret"></a>手順 3.b: クライアント シークレットを作成する

クライアント シークレットの作成については、「クライアント シークレットの作成 [」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。 クライアント シークレットをメモします。

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>手順 3.c: サービス プリンシパル オブジェクト識別子を取得する

手順に従ってサービス プリンシパル オブジェクト識別子を取得する

1. PowerShell を実行します。

2. 次のコマンドを使用して Azure PowerShell をインストールします。

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Azure に接続します。

   ```powershell
   Connect-AzAccount
   ```

4. サービス プリンシパル オブジェクト識別子を取得します。

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   "Application-ID" を手順 3.a. で登録したアプリケーションのアプリケーション (クライアント) ID (引用符なし) に置き換えてください。 PowerShell 出力からの ID オブジェクトの値をメモします。 サービス プリンシパル ID です。

これで、Azure portal から必要なすべての情報が取得しました。 情報の簡単な概要を次の表に示します。

プロパティ | 説明 
--- | ---
ディレクトリ ID (テナント ID) | 手順 3.a. からの Azure Active Directory テナントの一意の ID。
アプリケーション ID (クライアント ID) | 手順 3.a. で登録したアプリケーションの一意の ID。
クライアントの秘密情報 | アプリケーションの秘密キー (手順 3.b)。 パスワードのように扱います。
サービス プリンシパル ID | サービスとして実行されているアプリケーションの ID。 (手順 3.c から)

## <a name="step-3d-register-servicenow-application"></a>手順 3.d: ServiceNow アプリケーションを登録する

ServiceNow インスタンスには、次の構成が必要です。

1. 新しい OAuth OIDC エンティティを登録します。 詳細については [、「OAuth OIDC プロバイダーの作成」を参照してください](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

2. 次の表に、OIDC プロバイダー登録フォームに入力する方法のガイダンスを示します。

   Field | 説明 | 推奨値
   --- | --- | ---
   名前 | OAuth OIDC エンティティを識別する一意の名前。 | Azure AD
   クライアント ID | サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント ID。 インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。 | 手順 3.a のアプリケーション (クライアント) ID
   クライアントの秘密情報 | サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント シークレット。 | 手順 3.b のクライアント シークレット

   その他の値はすべて既定に設定できます。

3. OIDC プロバイダー登録フォームで、新しい OIDC プロバイダー構成を追加する必要があります。 *OAuth OIDC* プロバイダー構成フィールドに対する検索アイコンを選択して、OIDC 構成のレコードを開きます。 [新規]を選択します。

4. 次の表に、OIDC プロバイダー構成フォームに入力する方法のガイダンスを示します。

   Field | 推奨値
   --- | ---
   OIDC プロバイダー |  Azure AD
   OIDC メタデータ URL | URL は https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration の形式である必要があります。 <br/>手順 3.a の "tenantID" をディレクトリ (テナント) ID に置き換える。
   OIDC 構成キャッシュの寿命 |  120
   アプリケーション | グローバル
   ユーザークレーム | sub
   ユーザー フィールド | ユーザー ID
   JTI 要求の検証を有効にする | 無効

5. [OAuth OIDC エンティティ の送信と更新] フォームを選択します。

## <a name="step-3e-create-a-servicenow-account"></a>手順 3.e: ServiceNow アカウントを作成する

手順を参照して ServiceNow アカウントを作成し、ServiceNow [でユーザーを作成します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。

次の表に、ServiceNow ユーザー アカウントの登録に入力する方法のガイダンスを示します。

Field | 推奨値
--- | ---
ユーザー ID | 手順 3.c のサービス プリンシパル ID
Web サービス アクセスのみ | Checked

その他の値はすべて既定のままにすることができます。

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>手順 3.f: ServiceNow アカウントのナレッジ ロールを有効にする

ServiceNow プリンシパル ID をユーザー ID として作成した ServiceNow アカウントにアクセスし、ナレッジ ロールを割り当てる。 ServiceNow アカウントにロールを割り当てる手順については、ユーザーにロールを割り当てる [方法をご覧ください](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。

手順 3.a のクライアント ID としてアプリケーション ID を使用し、手順 3.b のクライアント シークレットを使用して、Azure AD OpenID Connect を使用して ServiceNow インスタンスに認証します。

## <a name="step-4-select-properties-and-filter-data"></a>手順 4: プロパティを選択し、データをフィルター処理する

この手順では、ServiceNow データ ソースに対して使用可能なプロパティを追加または削除できます。 Microsoft 365 では、既定でいくつかのプロパティが既に選択されています。

ServiceNow クエリ文字列を使用すると、記事を同期する条件を指定できます。 これは、Select ステートメントの **Where** **句SQL似たもの** です。 たとえば、発行済みでアクティブな記事のインデックスのみを作成できます。 独自のクエリ文字列の作成については、「フィルターを使用してエンコードされたクエリ文字列を生成する [」を参照してください](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。

[結果のプレビュー] ボタンを使用して、選択したプロパティとクエリ フィルターのサンプル値を確認します。

## <a name="step-5-manage-search-permissions"></a>手順 5: 検索権限を管理する

ServiceNow コネクタは、[すべてのユーザー]または [このデータ ソースにアクセスできるユーザーのみ] に表示される検索 **アクセス許可をサポートします**。 インデックス付きデータは検索結果に表示され、それぞれアクセス権を持つ組織内のユーザーに表示されます。 ServiceNow Connector は、高度なスクリプトのない既定のユーザー条件のアクセス許可をサポートしています。 コネクタが高度なスクリプトを使用してユーザー条件を見つけると、そのユーザー条件を使用しているすべてのデータが検索結果に表示されません。

[このデータソースにアクセスできるユーザーのみ] を選択した場合は、ServiceNow インスタンスに Azure Active Directory (AAD) がプロビジョニングされたユーザーと AAD 以外のユーザーの 2 人を含むかどうかをさらに選択する必要があります。

>[!NOTE]
>The ServiceNow connector is in **preview** if you choose **Only people with access to this data source**.

>[!NOTE]
>ID ソースの種類として AAD を選択する場合は、ServiceNow の電子メールターゲット プロパティに UPN ソース プロパティを割り当て中です。 マッピングを確認または変更するには、「Azure Active Directory での SaaS アプリケーションのユーザー プロビジョニング属性マッピング [のカスタマイズ」を参照してください](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)。

ServiceNow インスタンスから ACL を取り込み、ID の種類として [非 AAD] を選択した場合は、「ID のマッピング方法については [、Azure 以外の AD](map-non-aad.md) ID をマップする」を参照してください。

## <a name="step-6-assign-property-labels"></a>手順 6: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>手順 7: スキーマを管理する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>手順 8: 更新設定を選択する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>ID の場合は、スケジュールされたフル クロールだけが適用されます。

## <a name="step-9-review-connection"></a>手順 9: 接続を確認する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>トラブルシューティング

接続を発行し、結果ページをカスタマイズした後、管理センターの [コネクタ]タブで状態を[確認できます](https://admin.microsoft.com)。 更新と削除を行う方法については、「コネクタの管理」 [を参照してください](manage-connector.md)。

## <a name="limitations"></a>制限事項

ServiceNow Graph コネクタの最新リリースには、次の制限があります。

- 組織内のすべてのユーザーが使用できるナレッジ項目のインデックス作成は、一般に利用可能な機能です。
- *[検索のアクセス許可の* 管理] ステップでこのデータ ソース機能にアクセスできるユーザーだけがプレビュー段階であり、ユーザー条件のアクセス許可 [のみを](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 処理します。 その他の種類のアクセス許可は、検索結果には適用されません。
- 高度なスクリプトを使用したユーザーの条件は、現在のプレビュー バージョンではサポートされていません。 アクセス制限を持つナレッジ項目には、すべてのユーザーのアクセスを拒否するインデックスが付けされ、サポートされるまでは検索結果に表示されません。
