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
description: Microsoft 検索用の Microsoft Graph のコネクタの概要
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367525"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph コネクタの概要

[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) では、ユーザーが検索できるように、 [microsoft 365](https://www.microsoft.com/microsoft-365) のすべてのデータのインデックスが作成されます。 Microsoft Graph コネクタを使用すると、組織はサードパーティのデータにインデックスを作成して、Microsoft の検索結果に表示することができます。 これにより、Microsoft 365 プロダクティビティアプリと Microsoft の広範なエコシステムで検索可能なコンテンツソースの種類が拡張されます。 サードパーティのデータは、オンプレミスまたはパブリッククラウドまたはプライベートクラウドでホストできます。

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

この記事の残りの部分では、Microsoft 365 管理者が、次の質問に回答するために avaiable されているリソースを見つけるのを支援します。

* [Microsoft Search に接続できるデータソース](#what-data-sources-can-be-connected-to-microsoft-search)
* [接続を管理するにはどうすればよいですか?](#how-do-i-manage-my-connections)
* [グラフコネクタのライセンス要件と使用条件について](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [検索結果をカスタマイズして構成するにはどうすればよいですか?](#how-do-i-customize-and-configure-search-results)
* [カスタムアプリケーションからコネクタデータを検索するにはどうすればよいですか?](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> Microsoft Graph のコネクタと Microsoft 検索 Api は、一般公開されるようになりました。 最初のロールアウトは、対象となるリリース用に構成された顧客に対して行われます。 テナントで Graph connector を使用する場合は、ユーザーと管理者が [対象となるリリース](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)にオプトインする必要があります。

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a>Microsoft Search に接続できるデータソース

Microsoft は10個のグラフコネクタを提供しており、エコシステムパートナーは100を超える追加の Graph コネクタを作成しています。 独自の Graph connector を構築することもできます。 

### <a name="graph-connectors-by-microsoft"></a>Microsoft によるグラフコネクタ

Microsoft によって作成された Graph コネクタを使用して、次のデータソースに接続できます。

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

[グラフコネクタギャラリー](connectors-gallery.md)には、これらのグラフコネクタの簡単な説明が含まれています。 これらのデータソースのいずれかをテナントに接続する準備が整っている場合は、「セットアップの [概要](configure-connector.md) 」および「Microsoft が設定したコネクタ」セクションにある、データソースに適用されるその他の記事を必ずお読みください。

### <a name="graph-connectors-by-our-partners"></a>パートナーによるグラフコネクタ

[Microsoft graph のコネクタギャラリー](connectors-gallery.md)には、パートナーによって作成された各グラフコネクタの簡単な説明と、各パートナーの web サイトへのリンクが含まれています。 詳細については、各パートナーに直接お問い合わせください。

### <a name="build-your-own-graph-connector"></a>独自の Graph connector を構築する

独自の Graph connector の構築を計画している場合は、詳細について「 [Microsoft graph の Microsoft SEARCH API の概要](https://docs.microsoft.com/graph/search-concept-overview) 」を参照してください。

## <a name="how-do-i-manage-my-connections"></a>接続を管理するにはどうすればよいですか?

[Microsoft 365 管理センター](https://admin.microsoft.com/)の [[コネクタ] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)から、接続を管理できます。 詳細については [、「接続を管理](manage-connector.md) する」を参照してください。

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a>グラフコネクタのライセンス要件と使用条件について

検索結果のコネクタのデータを表示するには、組織内のユーザーに対して有効な Microsoft 365 または Office 365 のライセンスと十分なグラフコネクタクォータが必要です。

詳細については、「[ライセンス要件と](licensing.md)[使用条件](terms-of-use.md)」を参照してください。

## <a name="how-do-i-customize-and-configure-search-results"></a>検索結果をカスタマイズして構成するにはどうすればよいですか?

検索結果をカスタマイズして構成するには、いくつかの方法があります。 詳細については、次の記事を参照してください。

* [業界および結果の種類を管理する](customize-search-page.md)
* [検索結果のレイアウトを管理する](customize-results-layout.md)
* [検索結果クラスターを管理する](result-cluster.md)
* [カスタムフィルターを管理する](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a>カスタムアプリケーションからコネクタデータを検索するにはどうすればよいですか?

カスタムデータのインデックスを作成すると、開発者は [このデータをクエリ](https://docs.microsoft.com/graph/search-concept-custom-types)できます。 任意のアプリケーションでデータを表示できます。 詳細については、microsoft [Graph の Microsoft SEARCH API の概要](https://docs.microsoft.com/graph/search-concept-overview)を参照してください。
