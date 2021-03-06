---
title: Microsoft Search の Salesforce Graph コネクタ
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
description: Microsoft Search の Salesforce Graph コネクタをセットアップする
ms.openlocfilehash: 86140a4650593e08188f171be54f1753b73ecf7a
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508825"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a>Salesforce Graph コネクタ (プレビュー)

Salesforce Graph コネクタを使用すると、組織は Salesforce インスタンスの連絡先、商談、見込み客、およびアカウント オブジェクトのインデックスを作成できます。 Salesforce からコネクタとインデックス コンテンツを構成した後、エンド ユーザーは任意の Microsoft Search クライアントからそれらのアイテムを検索できます。

> [!NOTE]
> Graph コネクタ [**のセットアップの一**](configure-connector.md) 般的な手順については、Graph コネクタのセットアップに関する記事をご覧ください。

この記事は、Salesforce Graph コネクタを構成、実行、および監視するユーザー向けです。 これは、一般的なセットアップ プロセスを補足し、Salesforce Graph コネクタにのみ適用される手順を示します。 この記事には、制限に関する [情報も含まれています](#limitations)。

>[!IMPORTANT]
>Salesforce Graph コネクタは現在、Summer '19 以降をサポートしています。

## <a name="before-you-get-started"></a>使用を開始する前に

Salesforce インスタンスに接続するには、OAuth 認証用の Salesforce インスタンス URL、クライアント ID、およびクライアント シークレットが必要です。 次の手順では、自分または Salesforce 管理者が Salesforce アカウントからこの情報を取得する方法について説明します。

- Salesforce インスタンスにログインし、[セットアップ] に移動します。

- [アプリ] ->に移動します。

- [新 **しい接続アプリ] を選択します**。

- 次のように API セクションを完了します。

    - [Oauth 設定を有効 **にする] のチェック ボックスをオンにします**。

    - コールバック URL を次のように指定します。 [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - これらの必須の OAuth スコープを選択します。

        - データへのアクセスと管理 (api)

        - いつでも代理で要求を実行する (refresh_token、offline_access)

    - [Web サーバー フローにシークレット **を要求する] チェック ボックスをオンにします**。

    - アプリを保存します。
    
      > [!div class="mx-imgBorder"]
      > ![管理者が上記のすべての必須構成を入力した後の Salesforce インスタンスの API セクション。](media/salesforce-connector/sf1.png)

- コンシューマー キーとコンシューマー シークレットをコピーします。 この情報は、Microsoft 365 管理ポータルでグラフ コネクタの接続設定を構成するときに、クライアント ID とクライアント シークレットとして使用されます。

  > [!div class="mx-imgBorder"]
  > ![管理者が必要なすべての構成を送信した後、Salesforce インスタンスの API セクションによって返される結果。 コンシューマー キーは左側の列の上部に、コンシューマー シークレットは右列の上部に表示されます。](media/salesforce-connector/clientsecret.png)
  
- Salesforce インスタンスを閉じる前に、次の手順に従って更新トークンの有効期限が切れなかってください。
    - [アプリ] -> マネージャーに移動します。
    - 作成したアプリを見つけて、右側のドロップダウンを選択します。 [管理] **の選択**
    - ポリシー **の編集を選択する**
    - 更新トークン ポリシーの場合、[更新トークン **は失効するまで有効です] を選択します。**

  > [!div class="mx-imgBorder"]
  > !["Refresh token is valid is valid until revoked" という名前の Refresh Token Policy を選択します。](media/salesforce-connector/oauthpolicies.png)

[これで、M365 管理センターを](https://admin.microsoft.com/)使用して、Graph コネクタのセットアップ プロセスの残りの部分を完了できます。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターに Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

インスタンス URL の場合は、https://[domain].my.salesforce.com を使用します。ドメインは組織の Salesforce ドメインになります。

Salesforce インスタンスから取得したクライアント ID とクライアント シークレットを入力し、[サインイン] を選択します。

これらの設定で初めてサインインしようとすると、管理者のユーザー名とパスワードを使用して Salesforce にログインするためのポップアップが表示されます。 次のスクリーンショットは、ポップアップを示しています。 資格情報を入力し、[ログイン] を選択します。

  ![ユーザー名とパスワードを求めるログイン ポップアップ。](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >ポップアップが表示されない場合は、ブラウザーでブロックされている可能性があります。ポップアップとリダイレクトを許可する必要があります。

下のスクリーンショットに示すように、「接続が成功しました」という緑色のバナーを検索して、接続が成功したと確認します。

  > [!div class="mx-imgBorder"]
  > ![成功したログインのスクリーンショット。 「接続が成功しました」という緑色のバナーが、Salesforce インスタンス URL のフィールドの下に表示されます。](media/salesforce-connector/sf5.png)

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する

このデータ ソースから検索結果を表示するユーザーを選択する必要があります。 特定の Azure Active Directory (Azure AD) または Azure 以外のユーザー AD検索結果の表示のみを許可する場合は、ID をマップしてください。

## <a name="step-4a-select-permissions"></a>手順 4a: アクセス許可の選択

Salesforce インスタンスからアクセス制御リスト (ACL) を取り込むか、組織内のすべてのユーザーにこのデータ ソースからの検索結果を表示できます。 ACL には、Azure Active Directory (AAD) ID (Azure AD から Salesforce にフェデレーションされているユーザー)、Azure AD 以外の ID (Azure AD で対応する ID を持つネイティブ Salesforce ユーザー)、または両方が含まれます。

>[!NOTE]
>Ping ID や secureAuth などのサードパーティ ID プロバイダーを使用する場合は、ID の種類として "非 AAD" を選択する必要があります。

> [!div class="mx-imgBorder"]
> ![管理者が完了した [アクセス許可] 画面を選択します。管理者は[このデータ ソースにアクセスできるユーザーのみ] オプションを選択し、ID の種類のドロップダウン メニューから [AAD] も選択しています。](media/salesforce-connector/sf6.png)

Salesforce インスタンスから ACL を取り込み、ID の種類として [非 AAD] を選択した場合は、「Id のマッピング方法については [、「Map your Azure AD Identitys」](map-non-aad.md) を参照してください。

## <a name="step-4b-map-aad-identities"></a>手順 4b: AAD ID のマップ

Salesforce インスタンスから ACL を取り込み、ID の種類として [AAD] を選択した場合は、「Id のマッピング方法については [、「Map your Azure AD Identitys」](map-aad.md) を参照してください。 Azure AD SSO を設定する方法については、このチュートリアルを参照 [してください](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

各ラベルにソース プロパティを割り当てるには、オプションのメニューから選択します。 この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果が向上します。 既定では、"Title"、"URL"、"CreatedBy"、"LastModifiedBy" のような一部のラベルには、ソース プロパティが既に割り当て済みです。

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

インデックスを作成するソース プロパティを選択して、検索結果に表示できます。 既定では、接続ウィザードは、一連のソース プロパティに基づいて検索スキーマを選択します。 検索スキーマ ページの各プロパティと属性のチェック ボックスをオンにすると、変更できます。 検索スキーマ属性には、検索、クエリ、取得、絞り込みがあります。
絞り込みでは、後で検索エクスペリエンスでカスタム絞り込み条件またはフィルターとして使用できるプロパティを定義できます。  

> [!div class="mx-imgBorder"]
> ![各ソース プロパティのスキーマを選択します。 オプションは、クエリ、検索、取得、絞り込みです。](media/salesforce-connector/sf9.png)

## <a name="step-7-set-the-refresh-schedule"></a>手順 7: 更新スケジュールを設定する

Salesforce コネクタは現在、フル クロールの更新スケジュールのみをサポートしています。

>[!IMPORTANT]
>フル クロールでは、削除されたオブジェクトと、以前に Microsoft Search インデックスに同期されたユーザーが検索されます。

推奨されるスケジュールは、フル クロールの場合は 1 週間です。

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>制限事項

- Graph コネクタは現在、Salesforce の個人グループを使用した Apex ベースの地域ベースの共有と共有をサポートしています。
- Graph コネクタが使用する Salesforce API には既知のバグがあります。現在、リードのプライベート組織全体の既定値は適用されません。  
- フィールドにプロファイルのフィールド レベルセキュリティ (FLS) が設定されている場合、グラフ コネクタは、その Salesforce 組織のプロファイルに対してそのフィールドを取り込む必要があります。その結果、ユーザーはそれらのフィールドの値を検索したり、結果に表示したりしなかることができます。  
- [スキーマの管理] 画面で、これらの一般的な標準プロパティ名が 1 回表示され、オプションは **クエリ**、**検索**、取得、絞り込み、すべてまたはなしに適用されます。
    - 名前
    - Url
    - 説明
    - FAX
    - Phone
    - MobilePhone
    - メール
    - 型
    - タイトル
    - AccountId
    - AccountName
    - AccountUrl
    - AccountOwner
    - AccountOwnerUrl
    - 所有者
    - OwnerUrl
    - CreatedBy
    - CreatedByUrl
    - LastModifiedBy
    - LastModifiedByUrl
    - LastModifiedDate
    - ObjectName
