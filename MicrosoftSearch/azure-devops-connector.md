---
title: Microsoft Search 用 Azure DevOps Graph コネクタ
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
description: Microsoft Search 用の Azure DevOps Graph コネクタをセットアップする
ms.openlocfilehash: 9352f619e0a48bc2dac8441107f87f725211ab13
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031316"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph コネクタ (プレビュー)

Azure DevOps Graph コネクタを使用すると、組織は Azure DevOps サービスのインスタンス内の作業項目をインデックス化できます。 Azure DevOps からコネクタとインデックス コンテンツを構成した後、エンド ユーザーは Microsoft Search でそれらのアイテムを検索できます。

> [!NOTE]
> Graph コネクタ [**のセットアップの一**](configure-connector.md) 般的な手順については、Graph コネクタのセットアップに関する記事をご覧ください。

この記事は、Azure DevOps Graph コネクタを構成、実行、監視するユーザー向けです。 一般的なセットアップ プロセスを補足し、Azure DevOps Graph コネクタにのみ適用される手順を示します。

>[!IMPORTANT]
>Azure DevOps コネクタは、Azure DevOps クラウド サービスのみをサポートします。 Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015、TFS 2013 は、このコネクタではサポートされていません。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターに Graph コネクタを追加する

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

Azure DevOps インスタンスに接続するには、OAuth 認証用の Azure [DevOps](/azure/devops/organizations/accounts/create-organization) 組織名、そのアプリ ID、およびクライアント シークレットが必要です。

### <a name="register-an-app"></a>アプリを登録します

Microsoft Search アプリがインスタンスにアクセスできるよう、Azure DevOps にアプリを登録します。 詳細については、アプリの登録方法に関する Azure DevOps [のドキュメントを参照してください](/azure/devops/integrate/get-started/authentication/oauth?preserve-view=true&view=azure-devops#register-your-app)。

次の表に、アプリ登録フォームに入力する方法に関するガイダンスを示します。

必須フィールド | 説明 | 推奨値
--- | --- | ---
| Company Name         | 会社の名前。 | 適切な値を使用する   |
| アプリケーション名     | 承認するアプリケーションを識別する一意の値。    | Microsoft Search     |
| アプリケーション Web サイト  | コネクタのセットアップ中に Azure DevOps インスタンスへのアクセスを要求するアプリケーションの URL。 (必須)。  | https://<span>gcs.office.</span>com/
| 承認コールバック URL        | 承認サーバーがリダイレクトする必要なコールバック URL。 | https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback|
| 承認済みスコープ | アプリケーションのアクセス範囲 | 次のスコープを選択します。ID (読み取り)、作業項目 (読み取り)、変数グループ (読み取り)、Project とチーム (読み取り)、グラフ (読み取り)|

上記の詳細にアプリを登録すると、コネクタの構成に使用されるアプリ **ID** と **クライアント** シークレットが取得されます。

>[!NOTE]
>Azure DevOps に登録されているアプリへのアクセスを取り消す場合は、Azure DevOps インスタンスの右側にある [ユーザー設定] に移動します。 [プロファイル] を選択し、サイド ウィンドウの [セキュリティ] セクションで [承認] を選択します。 承認された OAuth アプリにカーソルを合わせると、アプリの詳細の隅にある [失効] ボタンが表示されます。

### <a name="connection-settings"></a>接続設定

Microsoft Search アプリを Azure DevOps に登録したら、接続設定の手順を完了できます。 組織名、アプリ ID、およびクライアント シークレットを入力します。

![接続アプリケーションの設定](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>データの構成: プロジェクトとフィールドの選択

組織全体または特定のプロジェクトのインデックスを作成する接続を選択できます。

組織全体のインデックスを作成する場合、組織内のすべてのプロジェクト内のアイテムにインデックスが作成されます。 新しいプロジェクトとアイテムは、作成後の次回のクロール中にインデックスが作成されます。

個々のプロジェクトを選択すると、それらのプロジェクトの作業項目だけがインデックス化されます。

![データの構成](media/ADO_Configure_data.png)

次に、接続でこれらのフィールドのデータにインデックスを付け、プレビューするフィールドを選択してから、次に進みます。

![プロパティの選択](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する

Azure DevOps コネクタは、[このデータ ソースにアクセスできるユーザーのみ] または [すべてのユーザー] に表示される検索  **アクセス** 許可を **サポートしています**。 [このデータソースにアクセスできるユーザーのみ] を選択すると、Azure DevOps の組織、プロジェクト、またはエリア パス レベルのユーザーまたはグループへのアクセス許可に基づいて、アクセス権を持つユーザーの検索結果にインデックス付きデータが表示されます。 [すべてのユーザー] **を選択** すると、すべてのユーザーの検索結果にインデックス付きデータが表示されます。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

Azure DevOps コネクタは、フル クロールと増分クロールの両方の更新スケジュールをサポートします。
推奨されるスケジュールは、増分クロールの場合は 1 時間、フル クロールの場合は 1 日です。

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->