---
title: カスタムフィルターを管理する
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: カスタムフィルターを管理する
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927384"
---
# <a name="create-custom-filters"></a>カスタムフィルターを作成する

ユーザーが[Bing](https://bing.com)で microsoft [SharePoint](https://sharepoint.com/)、Microsoft [Office](https://office.com)、microsoft search を検索するときに表示される検索機能をカスタマイズするためのフィルターを作成できます。 フィルターを使用すると、ユーザーは検索クエリの結果セットをすばやく絞り込むことができます。

カスタムフィルターは、接続プロパティに基づいて垂直方向の内部に作成できます。 たとえば、カスタム縦にある ServiceNow 接続に対し **て発行済み** フィルターを作成できます。

## <a name="things-to-consider"></a>考慮事項

1. 接続コンテンツソースにカスタムフィルターを作成する場合は、次の追加機能が提供されます。
- コネクタソースのプロパティへのエイリアスに対してフィルターを作成することもできます。
- 縦方向に複数の接続がある場合は、これらの接続全体で共通フィルターを作成できます。 これを行うには、共通のエイリアスに対してフィルターを作成します。このエイリアスは、ソースプロパティをそれぞれ異なる接続間でエイリアスします。 たとえば、次のようにエイリアスを作成することによって、ServiceNow & の Jira 接続に対して作成 **者** フィルターを作成できます。

| 接続 | プロパティ | エイリアス |
| --- | --- | --- |
| サービスの開始 | 所有者 | 設定元 |
| Jira | Publisher | 設定元 |

2. フィルターは垂直方向の範囲内に存在します。 いえ  
- 組織レベルにある垂直方向にフィルターを作成した場合、フィルターは組織レベルでのみ表示されます。
- サイトレベルにある垂直方向にフィルターを作成すると、そのフィルターはサイトレベルでのみ表示されます。

## <a name="steps-to-create-custom-filter"></a>カスタムフィルターを作成する手順

### <a name="create-filter-in-organizational-level-vertical"></a>組織レベルの垂直方向のフィルターを作成します。

Microsoft search でフィルターを作成するには、次の手順を実行します。

1. Microsoft 365 管理センターで、[ [業種](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) ] ページに移動します。
2. フィルターを作成する垂直線を作成または編集する
3. ウィザードの [フィルター] ステップに移動します。
4. [フィルターの追加] をクリックして、フィルターを追加した後に作業を開始すると、垂直方向の内容を確認して保存することができます。

## <a name="known-limitations"></a>既知の制限

1. 現時点では、フィルターの作成は文字列 & Date 型の管理プロパティに対してのみ行うことができます。
2. 階層フィルターを作成できない

## <a name="resources"></a>リソース

[検索結果ページをカスタマイズする](customize-search-page.md)