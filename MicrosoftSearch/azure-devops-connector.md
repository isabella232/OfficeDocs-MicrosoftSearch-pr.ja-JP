---
title: Azure DevOps GraphコネクタMicrosoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: ユーザー用のAzure DevOps GraphコネクタをMicrosoft Search
ms.openlocfilehash: fcf381a92ef397f900b300ca667fa80067a6672a
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701392"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph コネクタ (プレビュー)

このAzure DevOps Graphコネクタを使用すると、組織は、そのサービスのインスタンス内の作業項目Azure DevOpsできます。 コネクタとインデックス コンテンツを構成した後、エンド Azure DevOpsは、コネクタ内のそれらのアイテムをMicrosoft Search。

> [!NOTE]
> 一般的な [**コネクタのセットアップGraph**](configure-connector.md) Graphについては、「Graphコネクタのセットアップ」をご覧ください。

この記事は、コネクタの構成、実行、および監視を行うAzure DevOps Graphです。 これは、一般的なセットアップ プロセスを補足し、コネクタに対してのみ適用される手順Azure DevOps Graphします。

>[!IMPORTANT]
>このAzure DevOpsは、クラウド サービスAzure DevOpsサポートします。 Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015、および TFS 2013 は、このコネクタではサポートされていません。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Graphコネクタを追加Microsoft 365 管理センター

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

クライアント インスタンスにAzure DevOpsするには、OAuth 認証Azure DevOps組織名、その[](/azure/devops/organizations/accounts/create-organization)アプリ ID、およびクライアント シークレットが必要です。

### <a name="register-an-app"></a>アプリを登録します

アプリをアプリに登録Azure DevOps、Microsoft Searchインスタンスにアクセスできます。 詳細については、「アプリの登録Azure DevOpsドキュメント」[を参照してください](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)。

次の表に、アプリ登録フォームに入力する方法に関するガイダンスを示します。

必須フィールド | 説明 | 推奨値
--- | --- | ---
| Company Name         | 会社の名前。 | 適切な値を使用する   |
| アプリケーション名     | 承認するアプリケーションを識別する一意の値。    | Microsoft Search     |
| アプリケーション Web サイト  | コネクタのセットアップ中にアプリケーション インスタンスへのアクセスを要求Azure DevOpsの URL。 (必須)。  | https://<span>gcs.office.</span>com/
| 承認コールバック URL        | 承認サーバーがリダイレクトする必要なコールバック URL。 | https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback|
| 承認済みスコープ | アプリケーションのアクセス範囲 | 次のスコープを選択します。ID (読み取り)、ワーク アイテム (読み取り)、変数グループ (読み取り)、Project とチーム (読み取り)、Graph (読み取り)、Analytics (読み取り)|

>[!IMPORTANT]
>アプリに対して選択する承認済みスコープは、上記の範囲と完全に一致する必要があります。 リスト内のいずれかの承認済みスコープを省略するか、別のスコープを追加すると、承認は失敗します。

上記の詳細にアプリを登録すると、コネクタの構成に使用されるアプリ **ID** と **クライアント** シークレットが取得されます。

>[!NOTE]
>アプリに登録されているアプリへのアクセスを取り消Azure DevOps、ユーザー インスタンスの右側にある [ユーザー設定] にAzure DevOpsします。 [プロファイル] を選択し、サイド ウィンドウの [セキュリティ] セクションで [承認] を選択します。 承認された OAuth アプリにカーソルを合わせると、アプリの詳細の隅にある [失効] ボタンが表示されます。

### <a name="connection-settings"></a>接続設定

アプリを Microsoft Search登録Azure DevOps、接続設定の手順を完了できます。 組織名、アプリ ID、およびクライアント シークレットを入力します。

![接続アプリケーション 設定。](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>データの構成: プロジェクトとフィールドの選択

組織全体または特定のプロジェクトのインデックスを作成する接続を選択できます。

組織全体のインデックスを作成する場合、組織内のすべてのプロジェクト内のアイテムにインデックスが作成されます。 新しいプロジェクトとアイテムは、作成後の次回のクロール中にインデックスが作成されます。

個々のプロジェクトを選択すると、それらのプロジェクトの作業項目だけがインデックス化されます。

![データを構成します。](media/ADO_Configure_data.png)

次に、接続でこれらのフィールドのデータにインデックスを付け、プレビューするフィールドを選択してから、次に進みます。

![プロパティを選択します。](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する

[Azure DevOps コネクタは、[このデータ ソースにアクセスできるユーザーのみ] または [すべてのユーザー] に表示される検索アクセス  **許可を****サポートします**。 [このデータソースにアクセスできるユーザーのみ] を選択すると、Azure DevOps の [組織]、Project、またはエリア パス レベルのユーザーまたはグループへのアクセス許可に基づいてアクセス権を持つユーザーの検索結果にインデックス付きデータが表示されます。 [すべてのユーザー] **を選択** すると、すべてのユーザーの検索結果にインデックス付きデータが表示されます。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

このAzure DevOpsは、フル クロールと増分クロールの両方の更新スケジュールをサポートします。
推奨されるスケジュールは、増分クロールの場合は 1 時間、フル クロールの場合は 1 日です。

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。

>[!TIP]
>**既定の結果の種類**
>* コネクタAzure DevOps発行すると、[結果の種類](./customize-search-page.md#step-2-create-result-types)が自動的に登録されます。 結果の種類は、手順 3 で選択したフィールドに基づいて動的に生成された結果レイアウトを使用します。 [](./customize-results-layout.md) 
>* 結果の種類を管理するには、次のページの [**[結果**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)の種類] に [Microsoft 365 管理センター。](https://admin.microsoft.com) 既定の結果の種類には"Default" という名前が `ConnectionId` 付けられます。 たとえば、接続 ID がである場合、結果レイアウトの名前は `AzureDevOps` "AzureDevOpsDefault" になります。
>* また、必要に応じて、独自の結果の種類を作成できます。

<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="troubleshooting"></a>トラブルシューティング
次に示すのは、コネクタの構成中に発生する一般的なエラーとその考えられる理由です。

| 構成手順 | エラー メッセージ | 考えられる理由 |
| ------------ | ------------ | ------------ |
|  | `The account associated with the connector doesn't have permission to access the item.` | 登録されたアプリには、必要な OAuth スコープはありません。 (注 - 2021 年 8 月 31 日に新しい OAuth スコープ要件 'Analytics:read' が導入されました)  |

<!---## Limitations-->
<!---Insert limitations for this data source-->