---
title: SharePoint サイトでの検索ボックスの管理
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: SharePoint サイトで検索ボックスのエクスペリエンスをカスタマイズする方法
ms.openlocfilehash: 6ebd084aadb38acb5475b7e43d7c4092ffc09eb8
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700966"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>SharePoint サイトの検索ボックス設定

SharePoint サイトで Microsoft Search をカスタマイズする方法の 1 つは、ニーズに最適な SharePoint サイトのスイート ナビゲーション バーの検索ボックスの動作を調整する方法です。

その他のカスタマイズ オプションについては [、「Microsoft Search](customize-search-page.md)の結果ページを変更してカスタムのバーティカル、検索結果の種類とレイアウトを追加する」、および「カスタム検索結果ページを作成する」を [参照してください](create-search-results-pages.md)。

> [!NOTE]
> 現時点では、スイート ナビゲーション バーの検索ボックスは、すべてのユーザーが利用できるとは言え、これらのオプションは現在も設定できます。これらのオプションは、利用可能になったときに有効になります。

以下のタスクでは、PowerShell と SharePoint PnP PowerShell 拡張機能を使用します。 ここでは、インストールを行い、開始する方法について詳しい情報を参照 [できます](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。 次のコマンドを使用して、サイトまたはサイト コレクションにサインインします。

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>検索範囲の変更

SharePoint Online で新しいサイトを作成し、検索ボックスに入力すると、Microsoft Search の結果ページが表示されます。 このページには、既定で現在のサイトからの結果が表示され、検索範囲を現在のサイトが関連付けられているハブ (存在する場合) または組織全体に展開できます。

既定では、検索ボックスが使用する範囲はサイトの種類によって異なります。

* 通常のサイトは、現在のサイトを検索します。
* ハブ サイトは、ハブ内のすべてのサイトを検索します。
* ホーム サイトは、すべてのコンテンツを検索します。

場合によっては、これらの既定値を変更して、追加のクリックを必要とせずに、常に組織全体を検索したり、サイトが関連付けられているハブ全体を検索したりすることもできます。

サイト所有者は、次のコマンドを使用してこれらの既定値を変更できます。

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

このコマンドを実行すると、既定で現在のサイトからの結果が以前に表示されたサイトには、組織全体からの結果が表示されます。

既定の設定に戻る場合は、値 "DefaultScope" を指定してコマンドを再度実行します。 ハブ全体を検索するには、SearchScope 値として "Hub" を使用します。

この設定は、個々のサイト レベルで適用されます。 サイト コレクションに相当する設定はありません。

## <a name="show-or-hide-the-search-box"></a>検索ボックスを表示または非表示にする

ユーザーが検索を実行したり、カスタム検索ボックスの実装を使用したりするには、スイート ナビゲーション バーの検索ボックスを非表示にできます。

特定のサイトに対してこの設定を変更するには、次のコマンドを使用します。

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

または、サイト コレクション内のすべてのサイトに設定する場合は、次のコマンドを使用できます。

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

これらのコマンドを実行すると、ページの上部のナビゲーション バーに検索ボックスが表示されなくなりました。 検索ボックスの表示に戻る場合は、"SearchBoxInNavBar" パラメーターに指定した値を使用してコマンドを再度実行し、"Inherit" に設定します。

次の点を考慮する必要があります。

* この設定は、スイート ナビゲーション バーの検索ボックスにのみ適用されます。 ページ内の検索ボックスや、従来のページの検索ボックスには適用されません。

* ナビゲーション バーの検索ボックスを無効にしたら、サイトで検索機能を使用する場合は、カスタム Web パーツまたは SharePoint Framework 拡張機能を使用して検索ボックスを自分で指定する必要があります。

* このソリューションでは、サイトのリストとライブラリから検索ボックスも削除されます。 カスタム検索ソリューションでは、サイト全体の検索に加えて、SharePoint リストとライブラリのコンテキスト検索を考慮する必要があります。

* ドメインのルート サイトに設定を適用すると、SharePoint のスタート ページにも検索ボックスが表示されません。

## <a name="changing-the-hint-displayed-in-the-search-box"></a>検索ボックスに表示されるヒントを変更する

特定のサイトまたはサイト コレクションの検索ボックスに表示されるヒントを変更できます。 これは、入力を開始する前に検索ボックスに表示されるテキストです。 これは、カスタムの結果ページを構成した場合や、他の方法で検索の動作を変更した場合に、検索で期待される動作についてユーザーをガイドするのに役立つ場合があります。

> [!NOTE]
> この変更を行うには、テナント管理者として、サイトでカスタム スクリプトの実行を許可する必要があります。これは既定では許可されません。 詳細については https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script 、以下を参照してください。 カスタム スクリプトの実行を許可し、変更を行い、必要に応じてサイトのスクリプトを禁止に戻します。

特定のサイトのこの設定を変更するには、次のコマンドを実行します。

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

または、サイト コレクション内のすべてのサイトに設定する場合は、次のコマンドを使用できます。

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

既定のプレースホルダー テキストに戻る場合は、値を空白 ("") に設定します。
