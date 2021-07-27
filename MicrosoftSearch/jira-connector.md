---
title: Atlassian Jira GraphコネクタMicrosoft Search
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
description: ユーザー用に Atlassian Jira Graph コネクタをMicrosoft Search
ms.openlocfilehash: 55457adf9c507ba9f551732cdb014b48b5df4d9f
ms.sourcegitcommit: 9cfe9b7f6d4ddf783ee31a6d2a02a73f0c0aef79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2021
ms.locfileid: "53590275"
---
# <a name="atlassian-jira-graph-connector-preview"></a>Atlassian Jira Graph コネクタ (プレビュー)

Atlassian Jira Graphコネクタを使用すると、組織は Jira の問題をインデックス化できます。 Jira サイトからコネクタとインデックス コンテンツを構成した後、エンド ユーザーは、これらのアイテムを Jira サイトでMicrosoft Search。

> [!NOTE]
> 一般的な [**コネクタのセットアップGraph**](configure-connector.md) Graphについては、「Graphコネクタのセットアップ」をご覧ください。

この記事は、Atlassian Jira コネクタを構成、実行、および監視するGraphです。 これは、一般的なセットアップ プロセスを補足し、Atlassian Jira Graphコネクタにのみ適用される手順を示します。

>[!IMPORTANT]
>Atlassian Jira Graphコネクタは、Jira クラウド ホストインスタンスのみをサポートします。 Jira Server と Jira データ センターのバージョンは、このコネクタではサポートされていません。

## <a name="before-you-get-started"></a>使用を開始する前に
組織の M365 テナントの管理者である必要があります。また、組織の Jira サイトの管理者である必要があります。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Graphコネクタを追加Microsoft 365 管理センター
一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け
一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する
Jira サイトに接続するには、Jira サイトの URL を使用します。 Jira クラウド サイトの URL は通常 *、https://<organization_name>.atlassian.net/ のように見えます*。 Jira サイトへの認証には、基本認証または OAuth 2.0 (推奨) のいずれかを選択できます。

### <a name="basic-auth"></a>Basic Auth
基本認証を使用して認証するために、アカウントのユーザー名 (通常は電子メール ID) と API トークンを入力します。API トークンの生成の詳細については、Atlassian アカウントの API トークンを管理する方法に関する [Atlassian のドキュメントを参照してください](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)。

### <a name="oauth-20"></a>OAuth 2.0
アプリを Atlassian Jira に登録して、Microsoft Searchにアクセスできます。 詳細については [、「OAuth 2.0](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)を有効にする方法」の「Atlassian サポート」のドキュメントを参照してください。

次の手順では、アプリを登録する方法に関するガイダンスを提供します。

1. [Atlassian Jira 管理者アカウントを使用](https://developer.atlassian.com/console/myapps/)して、Atlassian Developer コンソールにサインインします。
2. をクリック `Create` して選択する `OAuth 2.0 integration`
3. アプリケーションに適切な名前を指定し、新しいアプリを作成します。
4. 左側の `Permissions` ナビゲーション ウィンドウから移動します。 を `Add` クリックします `Jira platform REST API` 。 追加したら、次のスコープ `Configure` をクリックして追加します。 `View Jira issue data` `Manage Jira global settings` `View user profiles`
5. 左側の `Authorization` ナビゲーション ウィンドウから移動します。 コールバック URL を追加 `https://gcs.office.com/v1.0/admin/oauth/callback` し、変更を保存します。
6. 左側の `Settings` ナビゲーション ウィンドウから移動します。 このページから `Client ID` と `Secret` を取得します。

上記の詳細でアプリを登録すると、クライアント ID と **シークレットが** 取得 **されます**。 これらを使用して接続設定手順を完了します。

### <a name="step-3a-configure-data-select-projects"></a>手順 3a: データの構成: プロジェクトの選択

Jira サイト全体または特定のプロジェクトのみをインデックス化する接続を選択できます。

* Jira サイト全体のインデックスを作成する場合、サイト内のすべてのプロジェクトで Jira の問題がインデックス付けされます。 新しいプロジェクトと問題は、作成後の次回のクロール中にインデックスが作成されます。
* 個々のプロジェクトを選択すると、それらのプロジェクトの Jira の問題だけがインデックス化されます。

さらに、2 つの方法でインデックスが作成される Jira の問題をフィルター処理できます。
* 変更された **問題の期間を指定します**。 これにより、現在のクロールに基づいてローリングベースで選択された期間に作成または変更された Jiraの問題にのみインデックスが作成されます。
* **JQL を指定します**。 これは、指定された Jira クエリ言語 (JQL) に基づいてフィルター処理後に返される Jira の問題にのみインデックスを作成します。 JQL の使用の詳細については、「Jira クエリ言語での高度な検索の使用に関する Atlassian サポート のドキュメント [」を参照してください。](https://support.atlassian.com/jira-service-management-cloud/docs/use-advanced-search-with-jira-query-language-jql/)

> [!TIP]
> JQL フィルターを使用して *、"issueType in (Bug,Improvement)*" を使用して特定の Jira の問題の種類のみをインデックス化できます。

### <a name="step-3b-configure-data-select-properties"></a>手順 3b: データの構成: プロパティの選択

次に進む前に、接続でこれらのフィールドのデータにインデックスを付け、プレビューするフィールドを選択します。 一部のフィールドは既定で既に選択され、削除できません。

Atlassian Jira Graphコネクタは、既定の問題フィールドとカスタム作成された問題フィールドの両方にインデックスを作成できます。

> [!NOTE]
> 選択したカスタム作成フィールドが一部の Jira 発行タイプに存在しない場合、フィールドは NULL (空白) として取 *り* 込されます。

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する

Atlassian Jira Graph コネクタは、[すべてのユーザー] または  ****[このデータ ソースにアクセスできるユーザーのみ] に表示される検索 **アクセス許可をサポートします**。 [すべてのユーザー] **を選択** すると、すべてのユーザーの検索結果にインデックス付きデータが表示されます。 [このデータ **ソースにアクセス** できるユーザーのみ] を選択すると、アクセス権を持つユーザーの検索結果にインデックス付きデータが表示されます。 Atlassian Jira では、セキュリティアクセス許可は、サイト レベルのグループとプロジェクトの役割を含むプロジェクトのアクセス許可スキームを使用して定義されます。 問題レベルのセキュリティは、問題レベルのアクセス許可スキームを使用して定義できます。

[このデータソースへのアクセス権を持つユーザーのみ] を選択する場合は、Jira サイトに Azure Active Directory (AAD) プロビジョニング されたユーザーまたは非 AAD ユーザーが含まれるかどうかをさらに選択する必要があります。

組織に適したオプションを特定するには、次の方法を使用します。

1. **Jira ユーザーのメール** ID が AADのユーザーの UserPrincipalName (UPN) と同じ場合は、AAD オプションを選択します。
2. Jira **ユーザーの電子メール** ID が AAD のユーザーの UserPrincipalName (UPN) と異なる場合は、[非 AAD] オプションを選択します。 

>[!NOTE]
> * ID ソースの種類として AAD を選択した場合、コネクタは Jira から取得したユーザーのメール ID を AAD から UPN プロパティに直接マップします。
> * ID の種類に対して "Non-AAD" を選択した場合は、「Id のマッピングの手順については [、「Map your-Azure AD Id」](map-non-aad.md) を参照してください。 このオプションを使用すると、メール ID から UPN へのマッピング正規表現を指定できます。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

Atlassian Jira Graph コネクタは、フル クロールと増分クロールの両方の更新スケジュールをサポートします。
推奨されるスケジュールは、増分クロールの場合は 1 時間、フル クロールの場合は 1 日です。

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="troubleshooting"></a>トラブルシューティング
その下に、コネクタの構成中に発生する一般的なエラーとその考えられる理由の一覧を示します。

| 構成手順 | エラー メッセージ | 考えられる理由 |
| ------------ | ------------ | ------------ |
| 接続設定 | 要求は形式が正しくないか、無効です。 | Jira サイトの URL が正しくありません |
| 接続設定 | Jira サイトの Jira クラウド サービスにアクセスできません。 | Jira サイトの URL が正しくありません |
| 接続設定 | クライアントには、アクションを実行するアクセス許可はありません。 | Basic auth に対して提供された無効な API トークン |


## <a name="limitations"></a>制限事項
Atlassian Jira コネクタの既知のGraphします。
* Jira Server とデータ センターのバージョンはサポートされていません。