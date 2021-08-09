---
title: カスタム フィルターを管理する
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
description: カスタム フィルターを管理する
ms.openlocfilehash: 339c7e96a00860a044a4e1af7382932f8e440e01b8b6d12445c24c1ea9b8cad0
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533130"
---
# <a name="manage-custom-filters"></a>カスタム フィルターを管理する

フィルターを使用して、ユーザー エクスペリエンスMicrosoft Searchできます。 フィルターを使用すると、ユーザーは検索クエリから一連の結果をすばやく絞り込みます。

カスタム フィルターは、接続プロパティに基づいて垂直方向の内部に作成できます。 たとえば、垂直方向の内部に **ServiceNow** 接続の発行済み On フィルターを作成できます。

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>組織レベルの垂直方向にフィルターを作成する

Microsoft 検索でフィルターを作成するには、次の手順を実行します。

1. [バーティMicrosoft 365 管理センター] に[移動します](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)。
1. フィルターを作成する垂直方向を作成/編集する
1. ウィザードの [フィルター] ステップに移動します。
1. [フィルターの追加] をクリックして開始する
1. フィルターを追加した後、垂直方向を確認して保存できます。

## <a name="things-to-consider"></a>考慮事項

1. 追加のフィルター機能は、接続コンテンツに存在します。

    - コネクタソースのプロパティへのエイリアスにフィルターを作成できます
    - 垂直に複数の接続がある場合は、これらの接続間で共通のフィルターを作成できます。 これは、異なる接続間でソース プロパティをエイリアスする共通のエイリアスにフィルターを作成することで実行できます。 たとえば、次のようにエイリアスを作成することで、ServiceNow と Jira 接続全体で作成者フィルターを作成できます。

    | Connection | プロパティ | エイリアス |
    | --- | --- | --- |
    | 今すぐサービス | 所有者 | Author |
    | Jira | 発行者 | Author |

1. フィルターは垂直のスコープ内に存在します。

    - 組織レベルの垂直方向にフィルターが作成された場合、フィルターは組織レベルでのみ表示されます。
    - サイト レベルの垂直方向にフィルターを作成した場合、フィルターはサイト レベルでのみ表示されます。

## <a name="known-limitations"></a>既知の制限事項

1. 現在、フィルターは、日付型管理プロパティ&に対してのみ作成できます。
1. 階層フィルターは作成できません。

## <a name="resources"></a>リソース

[業界および結果の種類を管理する](customize-search-page.md)
