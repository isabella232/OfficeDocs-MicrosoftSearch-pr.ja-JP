---
title: Microsoft が開発したコネクタを Microsoft Search 用に構成する
ms.author: mounika.narayanan
author: monaray
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft が開発したコネクタを Microsoft Search 用に構成する
ms.openlocfilehash: 3c54f04c1ac6cc42eef2e27a2b40b6ce92357630
ms.sourcegitcommit: 46303c60e905c89c133278fa41e87055f81a8637
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44535311"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="set-up-your-microsoft-built-connector-for-microsoft-search"></a>Microsoft が開発したコネクタを Microsoft Search 用にセットアップする

この記事では、Microsoft によって作成されたコネクタを構成する手順について説明します。 この記事では、Microsoft 365[管理センター](https://admin.microsoft.com)での接続のセットアップフローについて説明します。 特定の Microsoft が作成したコネクタをセットアップする方法の詳細については、次の記事を参照してください。

* [Azure Data Lake Storage Gen2](azure-data-lake-connector.md)
* [大企業の Web サイト](enterprise-web-connector.md)
* [ファイル共有](file-share-connector.md)
* [MediaWiki](mediawiki-connector.md)
* [Microsoft SQL Server](MSSQL-connector.md)
* [ServiceNow](servicenow-connector.md)

## <a name="set-up"></a>セットアップ

Microsoft によって作成されたコネクタのいずれかを構成するには、[管理センター](https://admin.microsoft.com)に移動します。

1. [Microsoft 365](https://www.microsoft.com/microsoft-365)テストテナントの資格情報を使用して、アカウントにサインインします。
2. [**設定**]  >  **Microsoft 検索**  >  **コネクタ**に移動します。
3. [**コネクタの追加**] を選択します。
4. 使用可能なコネクタのリストから、選択したコネクタを選択します。

![使用可能なデータソースは次のとおりです。 ADLS Gen2 コネクタ、エンタープライズ web サイト、ServiceNow、ファイル共有、Microsoft SQL server、および MediaWiki。](media/addconnector_final.png)

### <a name="name-the-connector"></a>コネクタに名前を指定する

接続を作成するには、最初に次の属性を指定します。

1. 接続の名前
2. 接続 ID
3. 説明 (省略可能)

接続 ID は、コネクタの暗黙的なプロパティを作成します。 このファイルには、英数字のみが含まれ、最大32文字の文字が含まれている必要があります。

### <a name="connect-to-a-data-source"></a>データソースへの接続

データ接続プロセスは、コネクタの種類によって異なります。 オンプレミスのデータソースへの接続の詳細については、「[オンプレミスのデータゲートウェイをインストール](https://aka.ms/configuregateway)する」を参照してください。

### <a name="select-source-properties"></a>ソースのプロパティの選択

サードパーティのデータソースによって設定されたデータフィールドは、ソースプロパティとして Microsoft Search にインデックスが付けられます。 これらのプロパティを変更するには、[**コネクタ**] ページの右側にあるサイドバーで [**プロパティの編集**] を選択します。 **最大64のソースプロパティ**を選択できます。

### <a name="manage-the-search-schema"></a>検索スキーマを管理する

管理者は、検索スキーマの属性を設定して、各ソースプロパティの検索機能を制御できます。 検索スキーマは、検索結果ページに表示される結果と、エンドユーザーが表示およびアクセスできる情報を決定するのに役に立ちます。

検索スキーマの属性には、検索可能、**クエリ**可能 **、および取得**可能**なものが**あります。 次の表に、Microsoft Graph コネクタがサポートしている各属性とその機能について説明します。

**検索スキーマの属性** | **Function** | **例**
--- | --- | ---
サーチ | プロパティのテキストコンテンツを検索可能にします。 プロパティの内容は、フルテキストインデックスに含まれています。 | プロパティが**title**の場合、**エンタープライズ**のクエリは、テキストまたはタイトルに " **enterprise** " が含まれている回答を返します。
クエリ可能 | クエリによって特定のプロパティの一致が検索されます。 プロパティ名は、プログラムまたは逐語的にクエリで指定できます。 |  **Title**プロパティがクエリ可能な場合は、クエリ**タイトル: Enterprise**がサポートされています。
だっ | 検索結果の種類には取得可能なプロパティのみを使用し、検索結果に表示することができます。 |

ファイル共有コネクタを除くすべてのコネクタについては、カスタムの種類を手動で設定する必要があります。 各フィールドの検索機能をアクティブにするには、プロパティのリストにマップされた検索スキーマが必要です。 接続ウィザードは、選択したソースプロパティのセットに基づいて検索スキーマを自動的に選択します。 このスキーマを変更するには、[検索スキーマ] ページで各プロパティと属性のチェックボックスをオンにします。

![コネクタのスキーマは、クエリ、検索、および取得機能を追加または削除することでカスタマイズできます。](media/manageschema.png)

これらの制限と推奨事項は、検索スキーマ設定に適用されます。

* カスタム型のインデックスを作成するコネクタの場合は、取得可能なメインコンテンツを含むフィールドを**マークし****ない**ことをお勧めします。 検索結果が検索属性を使用して表示される場合、パフォーマンスの著しい問題が発生します。 この例は、 [ServiceNow](https://www.servicenow.com)ナレッジベースの記事の**テキスト**コンテンツフィールドです。
* 検索結果には、取得可能としてマークされたプロパティのみが表示され、モダンの検索結果の種類 (MRTs) を作成するために使用できます。
* 検索可能としてマークできるのは、文字列のプロパティだけです。

> [!Note]
> 接続を作成した後、スキーマを変更する**ことはできません**。 そのためには、接続を削除して、新しい接続を作成する必要があります。

### <a name="manage-search-permissions"></a>検索アクセス許可を管理する

アクセス制御リスト (Acl) は、組織内のどのユーザーがデータの各アイテムにアクセスできるかを決定します。 ファイル共有コネクタは、 [Azure Active Directory (AZURE AD)](https://docs.microsoft.com/azure/active-directory/)にマップできる acl のみをサポートしています。 他のすべてのコネクタは、すべてのユーザーに表示される検索アクセス許可をサポートします。

### <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する

更新スケジュールは、Microsoft Graph と Microsoft Search のインデックスとデータを同期する頻度を決定します。 フルクロールまたは増分クロールの2つの方法で更新をスケジュールすることができます。

**フルクロール**では、検索エンジンは、以前のクロールに関係なく、コンテンツソース内のすべてのアイテムを処理してインデックスを付けます。 フルクロールは、次のような場合に最適です。

* データの削除を検出する必要があります。
* 増分クロールで、エラーのためにコンテンツをクロールできませんでした。
* Microsoft Search のソフトウェア更新プログラムが必要です。 更新プログラムによって検索スキーマが変更されます。
* Acl が変更されました。
* クロールルールが変更されました。

**増分クロール**では、検索エンジンは、最後に成功したクロール以降に作成または変更されたアイテムのみを処理してインデックスを作成できます。 そのため、コンテンツソース内のすべてのデータが再インデックス化されるわけではありません。 増分クロールは、コンテンツ、メタデータ、アクセス許可、その他の更新プログラムを検出するのに最適です。

増分クロールは、変更されていないアイテムは処理されないので、フルクロールよりもはるかに高速です。 コンテンツソースと検索インデックスとの間で正確なデータ同期を維持するには、両方のクロールを定期的に実行する必要があります。

各コネクタには、データが変更される頻度と変更の種類に基づいて、更新スケジュールの最適なセットがあります。

![増分クロールとフルクロール間隔の設定は、増分は15分で、フルクロールは1週間で表示されます。](media/refreshschedule.png)

### <a name="review-connector-settings"></a>コネクタの設定を確認する

コネクタを構成した後は、[管理センター](https://admin.microsoft.com)から設定を確認できるページに移動します。 接続を確認する前に、構成プロセスに戻って設定を編集することができます。 詳細については、「[コネクタの管理](manage-connector.md)」を参照してください。

## <a name="next-steps-customize-the-search-results-page"></a>次の手順: 検索結果ページをカスタマイズする

Microsoft 検索ユーザーインターフェイス (UI) を使用すると、エンドユーザーは[microsoft 365](https://www.microsoft.com/microsoft-365)プロダクティビティアプリと microsoft の広範なエコシステムからコンテンツを検索できます。 縦方向検索は、ユーザーが[Bing](https://Bing.com)で[SharePoint](https://sharepoint.com/)、 [Microsoft Office](https://Office.com)、および microsoft search の検索結果を表示するときに表示されるタブを示します。 検索結果を絞り込んで検索結果の特定の種類だけが表示されるように、検索対象をカスタマイズすることができます。 これらの業種は、検索結果ページの上部にタブとして表示されます。 モダン検索結果の種類 (MRT) は、結果の表示方法を指定する UI です。

エンドユーザーが新しい接続から検索結果を表示できるように、独自の業種と結果の種類を作成する必要があります。 この手順を行わないと、接続からのデータが検索結果ページに表示されません。

業種および MRTs の作成方法の詳細については、「[検索結果ページのカスタマイズ](customize-search-page.md)」を参照してください。

## <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

[管理センター](https://admin.microsoft.com)の [**コネクタ**] タブで、公開されている接続の一覧に移動します。 更新と削除を行う方法については、「[コネクタの管理](manage-connector.md)」を参照してください。
