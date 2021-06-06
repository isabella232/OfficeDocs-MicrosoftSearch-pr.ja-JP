---
title: Microsoft Search Graph ServiceNow Graphコネクタ
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
description: Microsoft Search の ServiceNow Graphコネクタをセットアップする
ms.openlocfilehash: 31b581af2c51a5c26b161e778b242e396afe91fd
ms.sourcegitcommit: 6cffa2d29448be9a22514e7b4c3009c522af0860
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52774082"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph コネクタ

ServiceNow Graph コネクタを使用すると、組織内のユーザー条件のアクセス許可に従って、ユーザーに表示されるナレッジ ベースの記事にインデックスを作成できます。 ServiceNow からコネクタとインデックス コンテンツを構成した後、ユーザーは任意の Microsoft Search クライアントから記事を検索できます。

> [!NOTE]
> 一般的な [**コネクタのセットアップGraph**](configure-connector.md) Graphについては、「Graphコネクタのセットアップ」をご覧ください。

この記事は、ServiceNow コネクタを構成、実行、および監視するGraphです。 これは、一般的なセットアップ プロセスを補足し、ServiceNow コネクタに対してのみ適用される手順Graphします。 この記事には、トラブルシューティングと [制限事項に関](#troubleshooting) する情報 [も含まれています](#limitations)。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: 管理センター GraphコネクタをMicrosoft 365する

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>手順 3: 接続設定

ServiceNow データに接続するには、このアカウントの組織の **ServiceNow** インスタンス URL 資格情報、クライアント ID、OAuth 認証用のクライアント シークレットを使用します。  

組織の **ServiceNow** インスタンス URL は、通常、組織 **https://>.service-now.com のように &lt; 表示されます**。 この URL と共に、ServiceNow への接続をセットアップし、更新スケジュールに基づいて Microsoft Search が ServiceNow から記事を更新できるようにアカウントが必要です。 アカウントには、少なくともナレッジ ロール <em>が必要</em> です。 [ServiceNow アカウントの役割を割り当てる方法について学習します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。

>[!NOTE]
>Microsoft 検索結果のナレッジ 記事のアクセス許可を受け入れ、ユーザー ID とグループ ID をクロールする場合、アカウントは ServiceNow で次の表レコードを読み取るアクセス権を持つ必要があります。
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Microsoft Search への接続に使用するアカウントの役割を作成して割り当てできます。 テーブルへの読み取りアクセス権は、その役割に割り当てることができます。 テーブル レコードへの読み取りアクセスを設定する方法については、「テーブル レコードの [セキュリティ保護」を参照してください](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)。

ServiceNow からコンテンツを認証および同期するには、次の 3 つの **サポートされている方法** のいずれかを選択します。

1. 基本認証
1. ServiceNow OAuth (推奨)
1. Azure AD OpenID Connect

### <a name="basic-authentication"></a>基本認証

インスタンスに対する認証を行うナレッジ ロールを持つ ServiceNow **アカウントのユーザー** 名とパスワードを入力します。

### <a name="servicenow-oauth"></a>ServiceNow OAuth

認証に ServiceNow OAuth を使用するには、ServiceNow インスタンスにエンドポイントをプロビジョニングします。 Microsoft Search アプリは、このアプリを使用してインスタンスにアクセスします。 詳細については、ServiceNow のドキュメントの「クライアントがインスタンスにアクセス [する](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) エンドポイントを作成する」を参照してください。

次の表に、エンドポイント作成フォームに入力する方法のガイダンスを示します。

フィールド | 説明 | 推奨値 
--- | --- | ---
名前 | OAuth アクセスが必要なアプリケーションを識別する一意の値。 | Microsoft Search
クライアント ID | アプリケーションの読み取り専用で自動生成された一意の ID。 インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。 | 該当なし
クライアント シークレット | この共有シークレット文字列を使用すると、ServiceNow インスタンスと Microsoft Search は互いに通信を承認します。 | シークレットをパスワードとして扱って、セキュリティのベスト プラクティスに従います。
リダイレクト URL | 承認サーバーがリダイレクトする必要なコールバック URL。 | https://gcs.office.com/v1.0/admin/oauth/callback
ロゴ URL | アプリケーション ロゴのイメージを含む URL。 | 該当なし
有効 | チェック ボックスをオンにして、アプリケーション レジストリをアクティブにします。 | アクティブに設定する
トークンのライフスパンの更新 | 更新トークンが有効な秒の数。 既定では、更新トークンの有効期限は 100 日 (8,640,000 秒) です。 | 31,536,000 (1 年)
アクセス トークンのライフスパン | アクセス トークンが有効な秒の数。 | 43,200 (12 時間)

インスタンスに接続するクライアント ID とクライアント シークレットを入力します。 接続後、ServiceNow アカウント資格情報を使用してクロールするアクセス許可を認証します。 アカウントには、少なくともナレッジ ロール **が必要** です。

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

認証に Azure AD OpenID Connectするには、以下の手順に従います。

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>手順 3.a: 新しいアプリケーションを新しいアプリケーションに登録Azure Active Directory

アプリケーションに新しいアプリケーションを登録する方法については、「Azure Active Directoryを登録する[」を参照してください](/azure/active-directory/develop/quickstart-register-app#register-an-application)。 [単一テナントの組織ディレクトリ] を選択します。 リダイレクト URI は不要です。 登録後、アプリケーション (クライアント) ID とディレクトリ (テナント) ID をメモします。

## <a name="step-3b-create-a-client-secret"></a>手順 3.b: クライアント シークレットを作成する

クライアント シークレットの作成の詳細については、「クライアント シークレットの作成 [」を参照してください](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret)。 クライアント シークレットをメモします。

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>手順 3.c: サービス プリンシパル オブジェクト識別子の取得

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
クライアントの秘密情報 | アプリケーションの秘密キー (手順 3.b から)。 パスワードのように扱います。
サービス プリンシパル ID | サービスとして実行されているアプリケーションの ID。 (手順 3.c から)

## <a name="step-3d-register-servicenow-application"></a>手順 3.d: ServiceNow アプリケーションの登録

ServiceNow インスタンスには、次の構成が必要です。

1. 新しい OAuth OIDC エンティティを登録します。 詳細については [、「Create an OAuth OIDC provider」を参照してください](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

2. 次の表に、OIDC プロバイダー登録フォームに入力する方法のガイダンスを示します。

   フィールド | 説明 | 推奨値
   --- | --- | ---
   名前 | OAuth OIDC エンティティを識別する一意の名前。 | Azure AD
   クライアント ID | サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント ID。 インスタンスは、アクセス トークンを要求するときにクライアント ID を使用します。 | 手順 3.a のアプリケーション (クライアント) ID
   クライアントの秘密情報 | サードパーティの OAuth OIDC サーバーに登録されているアプリケーションのクライアント シークレット。 | 手順 3.b のクライアント シークレット

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

## <a name="step-3e-create-a-servicenow-account"></a>手順 3.e: ServiceNow アカウントを作成する

手順を参照して ServiceNow アカウントを作成し [、ServiceNow でユーザーを作成します](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html)。

次の表は、ServiceNow ユーザー アカウントの登録に記入する方法に関するガイダンスを示しています。

フィールド | 推奨値
--- | ---
ユーザー ID | 手順 3.c のサービス プリンシパル ID
Web サービス アクセスのみ | Checked

その他の値はすべて既定のままにできます。

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>手順 3.f: ServiceNow アカウントのナレッジ ロールを有効にする

ServiceNow プリンシパル ID をユーザー ID として作成した ServiceNow アカウントにアクセスし、ナレッジ ロールを割り当てる。 ServiceNow アカウントに役割を割り当てる手順については、ユーザーに役割を割り当 [てる方法をご覧ください](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)。

手順 3.a のクライアント ID としてアプリケーション ID を使用し、手順 3.b のクライアント シークレットを使用して、Azure AD OpenID を使用して ServiceNow インスタンスConnect。

## <a name="step-4-select-properties-and-filter-data"></a>手順 4: プロパティを選択し、データをフィルター処理する

この手順では、ServiceNow データ ソースから使用可能なプロパティを追加または削除できます。 Microsoft 365では、いくつかのプロパティが既に選択されています。

ServiceNow クエリ文字列を使用すると、記事を同期する条件を指定できます。 これは、Select ステートメント **の Where** **句SQLです**。 たとえば、発行済みおよびアクティブな記事のみをインデックス化できます。 独自のクエリ文字列を作成する方法については、「フィルターを使用してエンコードされたクエリ文字列を [生成する」を参照してください](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)。

[プレビュー結果] ボタンを使用して、選択したプロパティとクエリ フィルターのサンプル値を確認します。

## <a name="step-5-manage-search-permissions"></a>手順 5: 検索アクセス許可を管理する

ServiceNow コネクタは、[すべてのユーザー]または [このデータ ソースにアクセスできるユーザーのみ] に表示 **される検索アクセス許可をサポートしています**。 インデックス付きデータは検索結果に表示され、それぞれアクセス権を持つ組織内のユーザーに表示されます。 ServiceNow Connector は、高度なスクリプトを使用せずに既定のユーザー条件のアクセス許可をサポートします。 コネクタが高度なスクリプトを使用してユーザー条件を見つけると、そのユーザー条件を使用しているすべてのデータが検索結果に表示されません。

[このデータソースへのアクセス権を持つユーザーのみ] を選択する場合は、ServiceNow インスタンスに Azure Active Directory (AAD) プロビジョニングされたユーザーまたは非 AAD ユーザーが含まれるかどうかをさらに選択する必要があります。

>[!NOTE]
>[このデータ ソースにアクセスできるユーザーのみ] を選択した場合、ServiceNow コネクタ **はプレビュー中です**。

>[!NOTE]
>ID ソースの種類として [AAD] を選択した場合は、ServiceNow の電子メール対象プロパティに UPN ソース プロパティを割り当ててみてください。 マッピングを確認または変更するには、「Azure Active Directory での SaaS アプリケーションのユーザー プロビジョニング属性マッピング[のカスタマイズ」を参照Azure Active Directory。](/azure/active-directory/app-provisioning/customize-application-attributes)

ServiceNow インスタンスから ACL を取り込み、ID の種類に対して "非 AAD" を選択した場合は [、「Map your Azure AD Identitys」](map-non-aad.md) を参照してください。

### <a name="managing-search-permissions-in-microsoft-search"></a>Microsoft Search での検索アクセス許可の管理

次のビデオでは、Servicenow コネクタを使用してナレッジ記事のインデックスを作成し、ユーザー条件のアクセス許可を定義し、ServiceNow と Microsoft Search インデックスの間の変更をシームレスに同期する方法を確認できます。

> [!VIDEO https://www.youtube-nocookie.com/embed/TVSkJpk1RiE]

## <a name="step-6-assign-property-labels"></a>手順 6: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>手順 7: スキーマの管理

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>手順 8: 更新設定を選択する

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>ID の場合は、スケジュールされたフル クロールだけが適用されます。

## <a name="step-9-review-connection"></a>手順 9: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>トラブルシューティング

接続を発行し、結果ページをカスタマイズした後、管理センターの [ **コネクタ** ] タブで状態を [確認できます](https://admin.microsoft.com)。 更新と削除を行う方法については、「コネクタの管理 [」を参照してください](manage-connector.md)。

## <a name="limitations"></a>制限事項

ServiceNow Graphコネクタには、最新のリリースで次の制限があります。

- 組織内のすべてのユーザーが利用できるナレッジ 記事のインデックス作成は、一般的に利用できる機能です。
- *[検索のアクセス許可の管理] ステップ* でこのデータ ソース機能にアクセスできるユーザーだけがプレビューに表示され、ユーザー条件 [のアクセス許可のみを](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) 処理します。 その他の種類のアクセス許可は検索結果に適用されません。
- 高度なスクリプトを含むユーザー条件は、現在のプレビュー バージョンではサポートされていません。 アクセス制限を持つナレッジ記事は、すべてのユーザーのアクセスを拒否してインデックスが作成され、サポートされるまで検索結果に表示されません。