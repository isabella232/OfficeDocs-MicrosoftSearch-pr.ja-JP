---
title: Microsoft Search 用 Azure DevOps Graph コネクタ
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
description: Microsoft Search 用の Azure DevOps Graph コネクタをセットアップする
ms.openlocfilehash: 3d922a5384de8bf0ef3c6dfd80bd67ad9170eb66
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084940"
---
<!---Previous ms.author: shgrover --->

# <a name="azure-devops-graph-connector-preview"></a>Azure DevOps Graph コネクタ (プレビュー)

Azure DevOps Graph コネクタを使用すると、組織は Azure DevOps サービスのインスタンスで作業項目のインデックスを作成できます。 Azure DevOps からコネクタとインデックス コンテンツを構成すると、エンド ユーザーは Microsoft Search でそれらのアイテムを検索できます。

> [!NOTE]
> Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、Graph コネクタの一般的なセットアップ プロセスを理解してください。

この記事は、ServiceNow Graph コネクタを構成、実行、および監視するユーザーを対象にしています。 一般的なセットアップ プロセスを補完し、ServiceNow Graph コネクタにのみ適用する手順を示します。

>[!IMPORTANT]
>Azure DevOps コネクタは、Azure DevOps クラウド サービスのみをサポートします。 Azure DevOps Server 2019、TFS 2018、TFS 2017、TFS 2015、および TFS 2013 は、このコネクタではサポートされていません。

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

Azure DevOps インスタンスに接続するには、Azure [DevOps](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization) 組織名、アプリ ID、OAuth 認証用のクライアント シークレットが必要です。

### <a name="register-an-app"></a>アプリを登録します

Microsoft Search アプリがインスタンスにアクセスできるよう、Azure DevOps にアプリを登録します。 詳しくは、アプリの登録方法に関する Azure DevOps の [ドキュメントをご覧ください](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app&preserve-view=true)。

次の表に、アプリ登録フォームに入力する方法のガイダンスを示します。

必須フィールド | 説明 | 推奨値
--- | --- | ---
| Company Name         | 会社の名前。 | 適切な値を使用する   |
| アプリケーション名     | 承認するアプリケーションを識別する一意の値。    | Microsoft Search     |
| アプリケーション Web サイト  | コネクタのセットアップ中に Azure DevOps インスタンスへのアクセスを要求するアプリケーションの URL。 (必須)。  | https://<span>gcs.office.</span>com/
| 認証コールバック URL        | 認証サーバーがリダイレクトする必須のコールバック URL。 | https://<span>gcs.office.</span>com/v1.0/admin/oauth/callback|
| 承認されたスコープ | アプリケーションのアクセスのスコープ | Id (読み取り)、作業項目 (読み取り)、変数グループ (読み取り)、プロジェクトとチーム (読み取り)、グラフ (読み取り) の範囲を選択します。|

上記の詳細を使用してアプリを登録すると、コネクタの構成に使用されるアプリ **ID** とクライアント シークレットが表示されます。

>[!NOTE]
>Azure DevOps に登録されているアプリへのアクセスを取り消す場合は、Azure DevOps インスタンスの右側にあるユーザー設定に移動します。 [プロファイル] を選択し、作業ウィンドウの [セキュリティ] セクションで [承認] を選択します。 承認された OAuth アプリの上にマウス ポインターを移動すると、アプリの詳細の隅に [取り消し] ボタンが表示されます。

### <a name="connection-settings"></a>接続設定

Microsoft Search アプリを Azure DevOps に登録した後、接続設定の手順を完了できます。 組織名、アプリ ID、クライアント シークレットを入力します。

![接続アプリケーションの設定](media/ADO_Connection_settings_2.png)

### <a name="configure-data-select-projects-and-fields"></a>データの構成: プロジェクトとフィールドの選択

接続を選択して、組織全体または特定のプロジェクトのインデックスを作成できます。

組織全体のインデックスを作成する場合は、組織内のすべてのプロジェクト内のアイテムにインデックスが作成されます。 新しいプロジェクトとアイテムは、作成後の次回のクロール時にインデックスが作成されます。

個々のプロジェクトを選択すると、それらのプロジェクトの作業項目だけがインデックス付けされます。

![データを構成する](media/ADO_Configure_data.png)

次に、接続でこれらのフィールドのデータのインデックスを作成およびプレビューするフィールドを選択してから、次に進みます。

![プロパティを選択する](media/ADO_choose_properties.png)

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索権限を管理する

Azure DevOps コネクタは、このデータ ソースにアクセスできるユーザーまたはすべてのユーザーにのみ表示される検索アクセス  **許可を** サポート **しています**。 [このデータソースにアクセスできるユーザーのみ] を選択すると、Azure DevOps の組織、プロジェクト、またはエリア パス レベルのユーザーまたはグループへのアクセス許可に基づいて、そのユーザーにアクセスできるユーザーの検索結果にインデックス付きデータが表示されます。 [すべてのユーザー] **を** 選択すると、すべてのユーザーの検索結果にインデックス付きデータが表示されます。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

Azure DevOps コネクタは、フル クロールと増分クロールの両方の更新スケジュールをサポートしています。
増分クロールの場合は 1 時間、フル クロールの場合は 1 日をお勧めします。

## <a name="step-8-review-connection"></a>手順 8: 接続を確認する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
