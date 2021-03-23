---
title: Microsoft Graph Connectors の概要
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
description: Microsoft Search 用 Microsoft Graph コネクタの概要
ms.openlocfilehash: 2d49471c703b765f6e99324f39dbe730f6dea814
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031658"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph コネクタの概要

[Microsoft Search は](./overview-microsoft-search.md) 、 [すべての Microsoft 365](https://www.microsoft.com/microsoft-365) データにインデックスを作成して、ユーザーを検索可能にしています。 Microsoft Graph コネクタを使用すると、組織はサード パーティのデータにインデックスを付け、Microsoft 検索結果に表示できます。 この機能は、Microsoft 365 生産性向上アプリと広範な Microsoft エコシステムで検索可能なコンテンツ ソースの種類を拡張します。 サード パーティのデータは、オンプレミスまたはパブリック クラウドまたはプライベート クラウドでホストできます。

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

この記事は、Microsoft 365 管理者が次の質問に答えるリソースを見つけるのに役立ちます。

* [Microsoft Search に接続できるデータ ソース](#what-data-sources-can-be-connected-to-microsoft-search)
* [接続を管理する方法](#how-do-i-manage-my-connections)
* [Graph コネクタのライセンス要件と使用条件は何ですか?](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [プレビュー機能とは](#what-are-the-preview-features)
* [検索結果をカスタマイズおよび構成する方法](#how-do-i-customize-and-configure-search-results)
* [カスタム アプリケーションからコネクタ データを検索する方法](#how-do-i-search-my-connector-data-from-a-custom-application)
* [検索結果をカスタマイズする方法](#how-do-i-customize-search-results)
* [コネクタの制限事項](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> Microsoft Graph コネクタと Microsoft Search API が一般提供されています。 最初のロールアウトは、ターゲットリリース用に構成された顧客に対して行います。 テナントで Graph コネクタを使用する場合は、ユーザーと管理者がターゲット リリースをオプトイン [する必要があります](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)。

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Microsoft Search に接続できるデータ ソース

Microsoft は 9 つのグラフ コネクタを提供し、エコシステム パートナーは 100 を超える Graph コネクタを作成しました。 独自の Graph コネクタを作成することもできます。

### <a name="graph-connectors-by-microsoft"></a>Microsoft 提供の Graph コネクタ

Microsoft によって作成された Graph コネクタを使用して、次のデータ ソースに接続できます。

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL および Microsoft SQL Server](MSSQL-connector.md)
* [大企業の Web サイト](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [ファイル共有](fileshare-connector.md)
* [Oracle SQL (プレビュー)](OracleSQL-connector.md)
* [Salesforce (プレビュー)](salesforce-connector.md)
* [ServiceNow](servicenow-connector.md)

Graph [コネクタ ギャラリーには、](connectors-gallery.md) これらの各 Graph コネクタの簡単な説明が含まれている。 これらのデータ ソースの 1 つをテナントに接続する準備が整っている場合は、[](configure-connector.md)データ ソースに適用される [Microsoft によるセットアップ コネクタ] セクションのセットアップの概要と他の記事を必ずお読みください。

### <a name="graph-connectors-by-our-partners"></a>パートナーによるグラフ コネクタ

[Microsoft Graph コネクタ ギャラリーには](connectors-gallery.md)、パートナーによって作成された各 Graph コネクタの簡単な説明と、各パートナーの Web サイトへのリンクが含まれています。 詳細については、各パートナーに直接お問い合わせください。

### <a name="build-your-own-graph-connector"></a>独自の Graph コネクタを作成する

必要に応じて、独自の Graph コネクタを作成できます。 Graph コネクタの構築の詳細については、「Microsoft Graph の Microsoft Search API の概要 [」を参照してください](/graph/search-concept-overview)。

## <a name="how-do-i-manage-my-connections"></a>接続を管理する方法

接続は[、Microsoft 365](https://admin.microsoft.com/)[管理センターの](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)[コネクタ] タブから管理できます。 接続の管理の詳細については、「接続の管理 [」を参照してください](manage-connector.md)。

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>Graph コネクタのライセンス要件と使用条件は何ですか?

有効な Microsoft 365 または Office 365 ライセンスと、組織内のユーザーが検索結果でコネクタからのデータを表示するのに十分な Graph Connectors クォータが必要です。

詳細については、「ライセンス要件 [と価格設定」および](licensing.md) 「 [使用条件」を参照してください](terms-of-use.md)。

## <a name="what-are-the-preview-features"></a>プレビュー機能とは

Microsoft Graph コネクタと Microsoft Search API は一般に利用可能ですが、プレビュー中のいくつかの機能があります。

プレビューのコネクタと機能のセットは次のとおりです。

* [Azure DevOps コネクタ](azure-devops-connector.md)
* [Salesforce コネクタ](salesforce-connector.md)
* [ソース ACL を使用](servicenow-connector.md) する検索アクセス許可を持つ ServiceNow コネクタ
* [結果のクラスターを管理する](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a>検索結果をカスタマイズおよび構成する方法

検索結果をカスタマイズおよび構成するには、さまざまな方法があります。 詳細については、次の記事を参照してください。

* [業界および結果の種類を管理する](customize-search-page.md)
* [検索結果のレイアウトを管理する](customize-results-layout.md)
* [結果のクラスターを管理する](result-cluster.md)
* [カスタム フィルターを管理する](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>カスタム アプリケーションからコネクタ データを検索する方法

カスタム データのインデックスが作成された後、開発者は、この [データを照会できます](/graph/search-concept-custom-types)。 任意のアプリケーションでデータを表示できます。 詳細については、「Microsoft Graph の [Microsoft Search API の概要」を参照してください](/graph/search-concept-overview)。

## <a name="how-do-i-customize-search-results"></a>検索結果をカスタマイズする方法

次の手順は、この記事で推奨される検索結果をカスタマイズする方法をカスタマイズし、検索結果[を構成する方法です。](#how-do-i-customize-and-configure-search-results) 検索結果のカスタマイズの詳細については、「[検索結果のカスタマイズ] ページ [」を参照してください](./configure-connector.md#next-steps-customize-the-search-results-page)。

## <a name="what-are-the-connector-limitations"></a>コネクタの制限事項は何ですか?

* Microsoft で **構築された** コネクタを発行すると、接続が作成されるのに数分かかる場合があります。 その間、接続の状態は保留中として表示されます。

* [Microsoft 365 管理センター](https://admin.microsoft.com)では、接続が公開された後の検索 **スキーマ** の編集はサポートされていません。 検索スキーマを編集するには、接続を削除してから、新しい接続を作成します。

* 取り込みスループットは、1 秒あたり約 4 つのアイテムで調整されます。

* スキーマの更新はサポートされていません。 接続セットアップを作成した後、スキーマを更新する方法はありません。 接続の削除と再作成のみ可能です。

* 接続の制限があります。 各テナントは、最大 10 の接続を作成できます。

* 接続の編集サポートは利用できません。 接続が作成されると、その接続を編集または変更することはできません。 詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。