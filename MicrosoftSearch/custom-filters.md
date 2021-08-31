---
title: フィルターの管理
ms.author: v-revathib
author: revathi-b
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: SERP で使用するフィルターを管理する
ms.openlocfilehash: da8c93f4faef7d52862db7464f61fd8e2cbd9fdf
ms.sourcegitcommit: b69da84c97ea14fd4706d24522a1e324b6798f91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2021
ms.locfileid: "58674778"
---
# <a name="manage-filters"></a>フィルターの管理

フィルターを使用すると、ユーザーはクエリの結果を絞り込み、絞り込み結果を表示できます。 ユーザーが使用できるフィルターは、ユーザーエクスペリエンスでMicrosoft Searchできます。

検索ページでは、2 種類のフィルターを使用できます。

- 箱から出たフィルター
- ユーザー設定フィルタ

> [!NOTE]
> カスタム フィルターは、現在、ターゲット リリースの管理者とエンド ユーザーのプレビュー中です。 プレビューの詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。

## <a name="out-of-the-box-filters"></a>箱から出たフィルター

既定では、[すべて]、[ファイル]、[画像]、および [ニュース] などの検索バーティカルで、既定でフィルターを使用できます。 'All' および 'File' バーティカルでは、FileType プロパティの "ファイルの種類" フィルターと LastModifiedTime プロパティの "最後に変更された" フィルターを確認できます。 これらのフィルターは、SharePoint ホーム、Office.com、SharePoint サイト、および Work vertical で使用Bing。

## <a name="custom-filters"></a>ユーザー設定フィルタ

フィルターは、組織レベルとサイト レベルのカスタム検索バーティカルに追加できます。 絞り込み可能な管理プロパティは、垂直管理ウィザードでフィルターを構成するために使用されます。  次に、接続プロパティに基づいて垂直方向の内部にカスタム フィルターを作成できます。 たとえば、垂直方向の内部に ServiceNow 接続の発行済み On フィルターを作成できます。

組織スコープ内の垂直に対して構成されたフィルターは、組織スコープで使用できます。 フィルターは、サイトのスコープでも構成できます。  

## <a name="create-organization-level-filters"></a>組織レベルのフィルターを作成する

1.  [[Microsoft 365 管理センター]](https://admin.microsoft.com/)の [バーティカル] [**に移動します。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. フィルターを作成する垂直方向を選択し、[編集] を **クリックします**。  
3. 垂直ウィザードの [フィルター] ステップに移動します。
4. [ **フィルターの追加] を** クリックして、絞り込み可能な管理プロパティのフィルターを構成します。
5. フィルターを追加した後、垂直方向を確認して保存できます。

## <a name="create-sharepoint-site-level-filters"></a>サイト SharePointフィルターを作成する

1. 管理 [SharePointで、[](https://sharepoint.com/)管理センター] に移動設定。
2. [サイト コレクション] セクションをMicrosoft Searchし、[このサイト コレクションの **Microsoft Search構成する] を選択します**。
3. ナビゲーション ウィンドウで、[カスタム エクスペリエンス] に移動し、[垂直]  **を選択します**。
4. フィルターを作成する垂直方向を選択し、[編集] を **クリックします**。
5. 垂直ウィザードの [フィルター] ステップに移動します。
6. [ **フィルターの追加] を** クリックして、絞り込み可能な管理プロパティのフィルターを構成します。
7. フィルターを追加した後、垂直方向を確認して保存できます。

## <a name="filter-across-multiple-properties"></a>複数のプロパティをフィルター処理する

バーティカルは、1 つ以上のコンテンツ ソースで作成できます。 複数のコンテンツ ソースで垂直方向が構成されている場合、絞り込み条件のプロパティ リストには、各絞り込み可能なプロパティが属するコンテンツ ソースが表示されます。 共通の管理プロパティは、名前 (またはエイリアス) とデータ型に基づいて結合されます。 フィルターは、これらの一般的なプロパティに対して構成することもできます。 これは、異なる接続間でソース プロパティをエイリアスする共通のエイリアスにフィルターを作成することで行われます。 たとえば、次のようにエイリアスを作成することで、ServiceNow と Jira 接続全体で作成者フィルターを作成できます。

 | Connection | プロパティ | エイリアス |
 | --- | --- | --- |
 | 今すぐサービス | Owner | Author |
 | Jira | Publisher | Author |

## <a name="important-details"></a>重要な詳細

- フィルターは、カスタム垂直にのみ追加できます。 新しいフィルターは、すべて、ファイル、ユーザー、サイト、ニュースなどのボックスの垂直方向に追加できません。
- フィルターは、Text プロパティと DateTime プロパティで構成できます。
- フィルターの数は合計 50 に制限されます。
- ボックスフィルターの順序を調整できません。
- フィルターは、コンテンツのOneDriveされません。 コンテンツの検索結果に対応するフィルター OneDriveフィルターには表示されません。
- カスタム フィルター値は、One Drive コンテンツではなく、SharePointコンテンツのオプションを表示します。たとえば、'Author' および SharePoint コンテンツのカスタム フィルターを作成すると、作成者である 'Amy' の結果だけが含まれるので、OneDrive コンテンツには 'John' という作成者からの結果だけが含まれる場合、Author カスタム フィルターには 'Amy' が唯一のオプションとして表示されます。
- コンテンツに対して表示SharePointフィルター値は、使用するとOneDriveコンテンツに適用されます。
