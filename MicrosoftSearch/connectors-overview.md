---
title: コネクタの概要
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用 Microsoft Graph コネクタの概要
ms.openlocfilehash: 677c91f121185faa6dc96f80c517917f429a3ab0
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847521"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph コネクタの概要

[Microsoft Search は](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) 、 [すべての Microsoft 365 データのインデックスを作成して](https://www.microsoft.com/microsoft-365) 、ユーザーを検索可能にしています。 Microsoft Graph コネクタを使用すると、組織はサード パーティのデータにインデックスを付け、Microsoft Search の結果に表示できます。 これにより、Microsoft 365 生産性アプリと広範な Microsoft エコシステムで検索できるコンテンツ ソースの種類が拡張されます。 サード パーティのデータは、オンプレミスまたはパブリック クラウドまたはプライベート クラウドでホストできます。

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

この記事の残りの部分は、Microsoft 365 管理者が次の質問に回答できるリソースを見つけるのに役立ちます。

* [Microsoft Search に接続できるデータ ソース](#what-data-sources-can-be-connected-to-microsoft-search)
* [接続を管理する方法](#how-do-i-manage-my-connections)
* [Graph コネクタのライセンス要件と使用条件は何ですか?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [検索結果をカスタマイズおよび構成する方法](#how-do-i-customize-and-configure-search-results)
* [カスタム アプリケーションからコネクタ データを検索する方法](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Microsoft Graph コネクタと Microsoft Search API が一般提供されます。 最初のロールアウトは、対象となるリリース用に構成されたユーザーに対して行います。 テナントで Graph コネクタを使用する場合、ユーザーと管理者は対象指定リリースにオプトイン [する必要があります](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)。

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Microsoft Search に接続できるデータ ソース

Microsoft は 10 個の Graph コネクタを提供し、エコシステム パートナーは 100 を超える追加の Graph コネクタを作成しています。 独自の Graph コネクタを作成することもできます。 

### <a name="graph-connectors-by-microsoft"></a>Microsoft 提供の Graph コネクタ

Microsoft によって作成された Graph コネクタを使用して、次のデータ ソースに接続できます。

<!---Need to add a few links below when docs exist--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* Azure SQL
* [大企業の Web サイト](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [ファイル共有](fileshare-connector.md)
* Oracle (プレビュー)
* [Salesforce (プレビュー)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

Graph [コネクタ ギャラリーには、](connectors-gallery.md) これらの Graph コネクタの簡単な説明が含まれている。 これらのデータ ソースの 1 つをテナントに接続する準備ができている場合は、セットアップ[](configure-connector.md)の概要と、データ ソースに適用される Microsoft によるセットアップ コネクタに関するその他の記事を必ずお読みください。

### <a name="graph-connectors-by-our-partners"></a>パートナーによるグラフ コネクタ

[Microsoft Graph コネクタ](connectors-gallery.md)ギャラリーには、パートナーによって作成された各 Graph コネクタの簡単な説明と、各パートナーの Web サイトへのリンクが含まれています。 詳細については、各パートナーに直接お問い合わせください。

### <a name="build-your-own-graph-connector"></a>独自の Graph コネクタを作成する

独自の Graph コネクタを構築する予定の場合は [、Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) の Microsoft Search API の概要を参照してください。

## <a name="how-do-i-manage-my-connections"></a>接続を管理する方法

[接続は、Microsoft 365](https://admin.microsoft.com/)管理センターの [コネクタ] タブから管理できます。 [](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) 詳細 [については、「接続の管理](manage-connector.md) 」を参照してください。

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Graph コネクタのライセンス要件と使用条件は何ですか?

有効な Microsoft 365 または Office 365 ライセンスと、組織内のユーザーがコネクタからのデータを検索結果で表示するのに十分な Graph コネクタ クォータが必要です。

詳細については、「ライセンス要件 [と価格と使用](licensing.md) 条件」 [を参照してください](terms-of-use.md)。

## <a name="how-do-i-customize-and-configure-search-results"></a>検索結果をカスタマイズおよび構成する方法

検索結果をカスタマイズおよび構成するには、さまざまな方法があります。 詳細については、次の記事を参照してください。

* [業界および結果の種類を管理する](customize-search-page.md)
* [検索結果のレイアウトを管理する](customize-results-layout.md)
* [結果のクラスターを管理する](result-cluster.md)
* [カスタム フィルターを管理する](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>カスタム アプリケーションからコネクタ データを検索する方法

カスタム データのインデックスが作成された後、開発者は、この [データに対してクエリを実行できます](https://docs.microsoft.com/graph/search-concept-custom-types)。 データは任意のアプリケーションで表示できます。 詳細については、Microsoft Graph の Microsoft Search API の [概要を参照してください](https://docs.microsoft.com/graph/search-concept-overview)。

## <a name="limitations"></a>制限事項

* Microsoft **が作成** したコネクタを発行すると、接続が作成されるのに数分かかる場合があります。 その間、接続の状態は保留中として表示されます。

* [Microsoft 365 管理](https://admin.microsoft.com)センターでは、接続の公開後 **の検索スキーマ** の編集はサポートされていません。 検索スキーマを編集するには、接続を削除してから新しい接続を作成します。

* 取り込みスループットは、1 秒あたり約 4 アイテムで調整されます。

* スキーマの更新はサポートされていません。 接続セットアップを作成した後、スキーマを更新する方法はありません。 接続を削除して作成し、もう一度作成する必要があります。

* 接続の制限があります。 各テナントは、最大 10 の接続を作成できます。

* 接続の編集サポートは利用できません。 接続が作成されると、その接続を編集または変更することはできません。 詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。
