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
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790336"
---
# <a name="manage-custom-filters"></a>カスタム フィルターを管理する

フィルターを使用して、Microsoft Search のエクスペリエンスをカスタマイズできます。 フィルターを使用すると、ユーザーは検索クエリから一連の結果をすばやく絞り込みます。

カスタム フィルターは、接続プロパティに基づいて垂直方向の内部に作成できます。 たとえば、垂直方向の内部に **ServiceNow** 接続の Published On フィルターを作成できます。

## <a name="create-a-filter-in-an-organizational-level-vertical"></a>組織レベルのバーティカルでフィルターを作成する

Microsoft Search でフィルターを作成するには、次の手順を実行します。

1. Microsoft 365 管理センターで、[縦] に [移動します](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)。
1. フィルターを作成する垂直方向の作成/編集
1. ウィザードの [フィルター] ステップに移動します。
1. [フィルターの追加] をクリックして開始する
1. フィルターを追加した後、垂直を確認して保存できます。

## <a name="things-to-consider"></a>考慮事項

1. 追加のフィルター機能は、接続コンテンツに存在します。

    - コネクタ ソース プロパティのエイリアスに対するフィルターを作成できます。
    - 垂直に複数の接続がある場合は、これらの接続間で共通のフィルタを作成できます。 これは、異なる接続間でソース プロパティをエイリアスする共通エイリアスにフィルターを作成することで実行できます。 たとえば、次のようにエイリアスを作成することで、ServiceNow 接続と Jira 接続に対して **作成者** フィルターを作成できます。

    | Connection | プロパティ | エイリアス |
    | --- | --- | --- |
    | 今すぐサービス | 所有者 | 設定元 |
    | ジラ | 発行者 | 設定元 |

1. フィルターは、垂直の範囲内に存在します。

    - フィルターが組織レベルの垂直方向に作成された場合、フィルターは組織レベルでのみ表示されます。
    - サイト レベルの垂直方向にフィルターを作成した場合、フィルターはサイト レベルでのみ表示されます。

## <a name="known-limitations"></a>既知の制限

1. 現在、フィルターは、日付型の管理&文字列でのみ作成できます。
1. 階層フィルターは作成できません。

## <a name="resources"></a>リソース

[業界および結果の種類を管理する](customize-search-page.md)
