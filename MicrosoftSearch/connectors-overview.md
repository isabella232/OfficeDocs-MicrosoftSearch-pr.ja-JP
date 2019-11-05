---
title: コネクタの概要
ms.author: v-pamcn
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsfot 検索用の Microsoft Graph コネクタの概要
ms.openlocfilehash: c372d4750c6644f0f98054a2531b6431fb8cd334
ms.sourcegitcommit: 90f82efc3671c477536cbe8d8846132910b64600
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37961957"
---
# <a name="overview-of-microsoft-graph-connectors"></a>Microsoft Graph コネクタの概要

Microsoft Search では、ユーザーが検索できるように、Microsoft 365 のすべてのデータのインデックスが作成されます。 Microsoft Graph のコネクタを使用すると、組織はサードパーティのデータにインデックスを作成して、Microsoft の検索結果に表示することができます。 サードパーティのデータは、オンプレミスまたはパブリッククラウドまたはプライベートクラウドでホストできます。 コネクタは、Microsoft 365 プロダクティビティアプリと Microsoft の広範なエコシステムで検索可能なコンテンツソースの種類を拡張します。

> [!IMPORTANT]
> **免責事項**: microsoft Graph のコネクタと Microsoft search api (インデックスと検索) は現在プレビュー段階です。 プレビューの詳細については、「 [Microsoft Graph コネクタプレビュー](connectors-preview.md)」を参照してください。 プレビューに参加するには、最初に[Microsoft Graph Connector preview のサインアップフォーム](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u)を送信する必要があります。

## <a name="architecture"></a>アーキテクチャ
Microsoft Graph プラットフォームの次のアーキテクチャ図は、 [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search)クライアントでのコンテンツインデックスを使用してコネクタコンテンツをユーザーの結果にどのように流し込むかを示しています。 この記事では、Microsoft Graph コネクタデータフロープロセスの主な構成要素について説明します。

![](media/highlevel-connectors_FINAL.png)

API は、データソースごとに1つの接続をインスタンス化します。 その後、API はデータをインデックス処理して格納します。 確立された接続は Microsoft Search とやり取りされるので、ユーザーは検索結果を取得できます。

Microsoft [365 管理センター](https://admin.microsoft.com)では、microsoft によって作成されたすべてのコネクタを構成できます。 管理センターを使用すると、簡単なユーザーインターフェイスでコネクタを簡単に構成できます。

データソースへの**接続**を作成するには、管理者がデータとコンテンツリポジトリ全体への認証されたアクセスを必要とします。 データは、インデックス作成のために graph connector サービスに送られます。

## <a name="available-connectors"></a>利用可能なコネクタ
現在、マイクロソフトが提供しているコネクタが6つあり、エコシステムパートナーから100以上のコネクタを利用できます。

エコシステムパートナーの1つからコネクタをプレビューするには、そのパートナーに直接連絡します。 詳細については、 [Microsoft Graph のコネクタギャラリー](connectors-gallery.md)を参照してください。

[独自のコネクタを作成](https://docs.microsoft.com/graph/search-concept-overview)することもできます。

### <a name="connectors-by-microsoft"></a>Microsoft によるコネクタ
Microsoft Graph コネクタプレビューリリースには、6つの Microsoft が作成したコネクタが含まれています。 [Microsoft 365 管理センター](https://admin.microsoft.com)で設定し、 [microsoft が作成](configure-connector.md)したコネクタをセットアップする方法について説明します。

次のセクションでは、これらの Microsoft が作成したコネクタについて簡単に説明します。 各コネクタのリンクされた記事に詳細情報を表示できます。

- **[Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-introduction)**。 この Microsoft Graph コネクタを使用すると、組織内のユーザーは Azure Blob コンテナーに格納されているファイルとコンテンツを検索できます。 Azure Data Lake Storage Gen2 connector は、指定した Azure Data Lake Storage Gen2 アカウント内の階層が有効なフォルダーにもインデックスを作成します。
詳細については、「 [Azure Data Lake Storage Gen2 connector](azure-data-lake-connector.md)」を参照してください。

- **エンタープライズ web サイト**。 この Microsoft Graph コネクタを使用すると、組織内のユーザーは、SharePoint 以外のエンタープライズ web サイト内のページを検索できます。
詳細については、「[エンタープライズ web サイトコネクタ](enterprise-web-connector.md)」を参照してください。

- [**ファイル共有**]。 この Microsoft Graph コネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有に保存されているファイルを検索できます。
[ファイル共有コネクタ](file-share-connector.md)の詳細について説明します。

- **[Mediawiki](https://www.mediawiki.org/wiki/MediaWiki)**。 この Microsoft Graph コネクタを使用すると、ユーザーは、組織が MediaWiki を使用して作成した wiki サイトで、サポート技術情報の記事を検索できます。
詳細については、「 [Mediawiki コネクタ](mediawiki-connector.md)」を参照してください。

- **[MICROSOFT SQL server](https://www.microsoft.com/sql-server/sql-server-2017)**。 この Microsoft Graph コネクタを使用すると、組織内のユーザーはオンプレミスの SQL server データベースのデータを検索できます。
詳細については、「 [MICROSOFT SQL server connector](MSSQL-connector.md)」を参照してください。

- **[ServiceNow](https://www.servicenow.com)** この Microsoft Graph コネクタを使用すると、組織内のユーザーは ServiceNow インスタンスからサポート技術情報の記事を検索できます。
[ServiceNow コネクタ](servicenow-connector.md)の詳細について説明します。

### <a name="connectors-from-our-partners"></a>パートナーからのコネクタ
エコシステムパートナーからのプレビューには、100を超えるコネクタが用意されています。 エコシステムパートナーの1つからコネクタをプレビューするには、そのパートナーに直接連絡します。
パートナーからのコネクタの詳細については、 [Microsoft Graph のコネクタギャラリー](connectors-gallery.md)を参照してください。

### <a name="build-your-own-connector"></a>独自のコネクタを作成する
カスタムデータ型またはファイルにインデックスを作成するために、開発者は[Microsoft Graph](https://developer.microsoft.com/graph/)でコネクタを作成できます。 コネクタは、[接続を作成](https://docs.microsoft.com/graph/search-index-manage-connections)し、Microsoft 検索インデックスにアイテムをプッシュするアプリケーションです。 詳細については、microsoft [Graph でアプリの Microsoft 検索機能を拡張するための概要](https://docs.microsoft.com/graph/search-concept-overview)を参照してください。

### <a name="search-results-with-your-custom-built-connector"></a>カスタム作成コネクタを使用した検索結果
カスタムデータのインデックスを作成すると、開発者は[このデータをクエリ](https://docs.microsoft.com/graph/search-concept-custom-types)できます。 任意のアプリケーションでデータを表示できます。 詳細については、microsoft [Graph でアプリの Microsoft 検索機能を拡張するための概要](https://docs.microsoft.com/graph/search-concept-overview)を参照してください。

## <a name="license-requirements"></a>ライセンス要件
検索結果のコネクタからのデータを表示するには、ユーザーは次の Microsoft 365 サブスクリプションのいずれかを所有している必要があります。
- <a href="https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans" target="_blank">Microsoft 365 for enterprise E3 または E5</a>
- <a href="https://www.microsoft.com/microsoft-365/academic/compare-office-365-education-plans?activetab=tab:primaryr1" target="_blank">Microsoft 365 エデュケーション A3 または A5</a>
