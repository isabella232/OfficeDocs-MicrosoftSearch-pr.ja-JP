---
title: Microsoft Graph コネクタの概要
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
description: Microsoft Graph コネクタのMicrosoft Search
ms.openlocfilehash: 2dec2d17479368bc6d85c0a5bd275461a4114800
ms.sourcegitcommit: 02d4f91210d992da080fd39d5b60f8cf30d8f0b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2021
ms.locfileid: "60238396"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph コネクタの概要

[Microsoft Search](./overview-microsoft-search.md)ユーザーを検索[Microsoft 365、すべての](https://www.microsoft.com/microsoft-365)データにインデックスを作成します。 Microsoft Graphコネクタを使用すると、組織はサードパーティのデータをインデックス化して、結果に表示Microsoft Searchできます。 この機能は、Microsoft 365 の生産性向上アプリと Microsoft の広範なエコシステムで検索可能な、コンテンツ ソースの種類を拡大しています。 サード パーティのデータは、オンプレミスまたはパブリック クラウドまたはプライベート クラウドでホストできます。

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

この記事は、管理者がMicrosoft 365に回答できるリソースを見つけるのに役立ちます。

* [どのデータ ソースをデータ ソースに接続Microsoft Search?](#what-data-sources-can-be-connected-to-microsoft-search)
* [接続を管理する方法](#how-do-i-manage-my-connections)
* [Microsoft Graphコネクタのライセンス要件と使用条件は何ですか?](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [プレビュー機能とは](#what-are-the-preview-features)
* [検索結果をカスタマイズおよび構成する方法](#how-do-i-customize-and-configure-search-results)
* [カスタム アプリケーションからコネクタ データを検索する方法](#how-do-i-search-my-connector-data-from-a-custom-application)
* [検索結果をカスタマイズする方法](#how-do-i-customize-search-results)
* [コネクタの制限事項](#what-are-the-connector-limitations)

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>どのデータ ソースをデータ ソースに接続Microsoft Search?

Microsoft は 9 つのコネクタを提供し、エコシステム パートナーは 100 を超えるコネクタを作成しました。 独自のコネクタを作成できます。

### <a name="microsoft-graph-connectors-by-microsoft"></a>Microsoft Graphコネクタ

Microsoft によって作成されたコネクタを使用して、次のデータ ソースに接続できます。

<!---Add links below when new docs are created--->
* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [Azure DevOps](azure-devops-connector.md)
* [Azure SQL および Microsoft SQL Server](MSSQL-connector.md)
* [Confluence Cloud (プレビュー)](confluence-cloud-connector.md)
* [大企業の Web サイト](enterprise-web-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [ファイル共有](fileshare-connector.md)
* [Oracle SQL](OracleSQL-connector.md)
* [Salesforce](salesforce-connector.md)
* [ServiceNow ナレッジ](servicenow-knowledge-connector.md)
* [ServiceNow カタログ (プレビュー)](servicenow-catalog-connector.md)

[Microsoft Graph コネクタ ギャラリーには](https://www.microsoft.com/microsoft-search/connectors)、これらの各コネクタの簡単な説明が含まれている。 これらのデータ ソースの 1 つをテナントに接続する準備が整っている場合は、[](configure-connector.md)データ ソースに適用される [Microsoft によるセットアップ コネクタ] セクションのセットアップの概要と他の記事を必ずお読みください。

### <a name="microsoft-graph-connectors-by-our-partners"></a>Microsoft Graphパートナーによるコネクタ

[Microsoft Graph コネクタ](https://www.microsoft.com/microsoft-search/connectors)ギャラリーには、パートナーによって作成された各コネクタの簡単な説明と、各パートナーの Web サイトへのリンクが含まれています。 詳細については、各パートナーに直接お問い合わせください。

### <a name="build-your-own-microsoft-graph-connector"></a>独自の Microsoft Graph コネクタを構築する

必要に応じて、独自のコネクタを構築できます。 コネクタの構築の詳細については、「Build [your first custom Microsoft Graph コネクタ」を参照してください](/graph/connecting-external-content-build-quickstart)。

## <a name="how-do-i-manage-my-connections"></a>接続を管理する方法

接続は、[コネクタ] タブ[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)の [コネクタ] タブから[管理Microsoft 365 管理センター。](https://admin.microsoft.com/) 接続の管理の詳細については、「接続の管理 [」を参照してください](manage-connector.md)。

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a>コネクタのライセンス要件と使用条件は何ですか?

組織内のユーザーがMicrosoft 365データOffice 365を表示するには、有効なライセンスまたはライセンスと十分なコネクタ クォータが必要です。

詳細については、「ライセンス要件 [と価格設定」および](licensing.md) 「 [使用条件」を参照してください](terms-of-use.md)。

## <a name="what-are-the-preview-features"></a>プレビュー機能とは

Microsoft Graphおよび Microsoft Search API は一般に使用できるが、プレビュー中のいくつかの機能があります。

プレビューのコネクタと機能のセットは次のとおりです。

* [Azure DevOps コネクタ](azure-devops-connector.md)
* [Confluence クラウド コネクタ](confluence-cloud-connector.md)
* [ServiceNow カタログ コネクタ](servicenow-catalog-connector.md)
* [カスタム フィルターを管理する](custom-filters.md)
* [垂直の複数の接続](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a>検索結果をカスタマイズおよび構成する方法

検索結果をカスタマイズおよび構成するには、さまざまな方法があります。 詳細については、次の記事を参照してください。

* [垂直および結果の](manage-verticals.md) 種類 [を管理する](manage-result-types.md)
* [検索結果のレイアウトを管理する](customize-results-layout.md)
* [結果のクラスターを管理する](result-cluster.md)
* [カスタム フィルターを管理する](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>カスタム アプリケーションからコネクタ データを検索する方法

カスタム データのインデックスが作成された後、開発者は、この [データを照会できます](/graph/search-concept-custom-types)。 任意のアプリケーションでデータを表示できます。 詳細については、「Microsoft Microsoft Search API の概要[」を参照Graph。](/graph/search-concept-overview)

## <a name="how-do-i-customize-search-results"></a>検索結果をカスタマイズする方法

次の手順は、この記事で推奨される検索結果をカスタマイズする方法をカスタマイズし、検索結果[を構成する方法です。](#how-do-i-customize-and-configure-search-results) 検索結果のカスタマイズの詳細については、「[検索結果のカスタマイズ] ページ [」を参照してください](customize-search-page.md)。

## <a name="what-are-the-connector-limitations"></a>コネクタの制限事項は何ですか?

* Microsoft で **構築された** コネクタを発行すると、接続が作成されるのに数分かかる場合があります。 その間、接続の状態は保留中として表示されます。

* 取り込みスループットは、1 秒あたり約 4 つのアイテムで調整されます。

* スキーマの更新はサポートされていません。 接続セットアップを作成した後、スキーマを更新する方法はありません。 接続の削除と再作成のみ可能です。

* 接続の制限があります。 各テナントは、最大 10 の接続を作成できます。

* 接続を作成した後で、接続を編集または変更することはできません。 詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。
