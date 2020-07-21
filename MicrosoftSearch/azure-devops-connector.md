---
title: Microsoft Search 用 Azure DevOps connector
ms.author: shgrover
author: shakungrover05
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の Azure DevOps connector をセットアップする
ms.openlocfilehash: e2698d7d4a50c15bf765aa4eeada20fbc7328772
ms.sourcegitcommit: 7eda9b621def0659d7e7bc8b989f8adc929cce93
ms.translationtype: Auto
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2020
ms.locfileid: "44861105"
---
# <a name="azure-devops-connector"></a>Azure DevOps コネクタ

Azure DevOps コネクタを使用すると、組織は Azure DevOps service のインスタンスで作業項目のインデックスを作成できます。 Azure DevOps からコネクタとインデックスコンテンツを構成すると、エンドユーザーは Microsoft Search でそれらのアイテムを検索できるようになります。

この記事は、Microsoft 365 管理者または Azure DevOps コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

>[!IMPORTANT]
>Azure DevOps connector では、Azure DevOps cloud service のみがサポートされています。 Azure DevOps Server 2019、TFS 2018、tfs 2017、tfs 2015、tfs 2013 は、このコネクタではサポートされていません。

## <a name="connect-to-a-data-source"></a>データソースへの接続

Azure DevOps インスタンスに接続するには、Azure DevOps[組織](https://docs.microsoft.com/azure/devops/organizations/accounts/create-organization)名、そのアプリ ID、および OAuth 認証のクライアントシークレットが必要です。

### <a name="register-an-app"></a>アプリを登録します

Microsoft Search アプリがインスタンスにアクセスできるようにするには、Azure DevOps でアプリを登録する必要があります。 詳細については、「Azure DevOps のドキュメント」の「[アプリを登録](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/oauth?view=azure-devops#register-your-app)する方法」を参照してください。

次の表に、アプリ登録フォームに記入する方法についてのガイダンスを示します。

 **必須フィールド** | **説明**      | **推奨値**
--- | --- | ---
| Company Name         | これは会社の名前です。 | 適切な値を使用する   |
| アプリケーション名     | この一意の値は、承認しているアプリケーションを識別します。    | Microsoft Search     |
| アプリケーション web サイト  | この必須フィールドは、コネクタのセットアップ時に Azure DevOps インスタンスへのアクセスを要求するアプリケーションの URL です。  | <https://gcs.office.com/>                |
| 認証コールバック URL        | 承認サーバーのリダイレクト先となる必要なコールバック URL。 | <https://gcs.office.com/v1.0/admin/oauth/callback>|
| 承認されたスコープ | これは、アプリケーションへのアクセスの範囲です。 | 次のスコープを選択します。 Identity (read)、作業項目 (読み取り)、変数グループ (読み取り)、プロジェクトおよびチーム (読み取り)|

上記の詳細を使用してアプリを登録する場合は、コネクタの構成に使用する**アプリ ID**と**クライアントシークレット**を取得します。

>[!NOTE]
>Azure DevOps に登録されているすべてのアプリへのアクセスを取り消すには、Azure DevOps インスタンスの右上にある [ユーザーの設定] に移動します。 [プロファイル] をクリックし、作業ウィンドウの [セキュリティ] セクションで [承認] をクリックします。 承認済み OAuth アプリの上にカーソルを移動すると、アプリの詳細の隅にある [取り消し] ボタンが表示されます。

### <a name="connection-settings"></a>接続設定

Microsoft Search アプリを Azure DevOps に登録した後、接続設定の手順を完了できます。 組織名、アプリ ID、およびクライアントシークレットを入力します。

![接続アプリケーションの設定](media/ADO_Connection_settings_2.png)

## <a name="select-projects-and-fields"></a>プロジェクトとフィールドの選択

接続には、組織全体または特定のプロジェクトのいずれかにインデックスを作成するかどうかを選択できます。

組織全体のインデックスを作成することを選択すると、組織内のすべてのプロジェクトの項目にインデックスが付けられます。 新しいプロジェクトとアイテムは、作成後に次のクロール中にインデックス処理されます。 個別のプロジェクトを選択した場合は、それらのプロジェクトの作業項目のみがインデックス作成されます。

![データを構成する](media/ADO_Configure_data.png)

次に、接続するフィールドを選択して、次に進む前にこれらのフィールドにデータをプレビューします。

![プロパティの選択](media/ADO_choose_properties.png)

## <a name="manage-the-search-schema"></a>検索スキーマを管理する

検索スキーママッピングを構成します。  **クエリ**可能にするかどうかを**選択し、** 検索可能で **検索**可能なプロパティを選択できます。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する

現時点では、Azure DevOps コネクタは、**すべてのユーザーに表示される**検索アクセス許可のみをサポートしています。 インデックスが作成されたデータは、すべてのユーザーの検索結果に表示されます。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する

Azure DevOps コネクタは、フルクロールと増分クロールの両方の更新スケジュールをサポートしています。 フルクロールで、以前に Microsoft 検索インデックスと同期された削除済みの作業項目が検索されます。 フルクロールを実行して、すべての作業項目を同期します。 新しい作業項目と更新を既存の作業項目に同期するには、増分クロールをスケジュールする必要があります。

推奨されるスケジュールは、増分クロールの場合は1時間、フルクロールの場合は1日です。
