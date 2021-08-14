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
ms.openlocfilehash: 256cf9748aa3050aacf48c3562f6f84b4ba2e460
ms.sourcegitcommit: 5151bcd8fd929ef37239b7c229e2fa33b1e0e0b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235925"
---
# <a name="manage-custom-filters"></a>カスタム フィルターを管理する

フィルターを使用して、ユーザー エクスペリエンスMicrosoft Searchできます。 フィルターを使用すると、ユーザーは検索クエリから一連の結果をすばやく絞り込みます。

カスタム フィルターは、接続プロパティに基づいて垂直方向の内部に作成できます。 たとえば、垂直方向の内部に **ServiceNow** 接続の発行済み On フィルターを作成できます。

> [!NOTE]
> カスタム フィルターは、現在、ターゲット リリースの管理者とエンド ユーザーのプレビュー中です。 プレビューの詳細については [、「Connectors preview features」を参照してください](connectors-overview.md#what-are-the-preview-features)。

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

    | Connection | プロパティ | Alias |
    | --- | --- | --- |
    | 今すぐサービス | 所有者 | Author |
    | Jira | Publisher | Author |

1. フィルターは垂直のスコープ内に存在します。

    - 組織レベルの垂直方向にフィルターが作成された場合、フィルターは組織レベルでのみ表示されます。
    - サイト レベルの垂直方向にフィルターを作成した場合、フィルターはサイト レベルでのみ表示されます。

## <a name="known-limitations"></a>既知の制限事項

1. 現在、フィルターは、日付型管理プロパティ&に対してのみ作成できます。
1. 階層フィルターは作成できません。

## <a name="resources"></a>リソース

[業界および結果の種類を管理する](customize-search-page.md)
