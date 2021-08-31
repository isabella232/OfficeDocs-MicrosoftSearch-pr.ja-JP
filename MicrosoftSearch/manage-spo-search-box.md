---
title: サイト内の検索ボックスSharePointする
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: サイトで検索ボックスのエクスペリエンスをカスタマイズSharePointする方法
ms.openlocfilehash: b5d58dd5a241ccf2ada556c44ec0ea5479ea2e2b
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701978"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>サイトの検索ボックスSharePoint設定

SharePoint サイトで Microsoft Search をカスタマイズできるいくつかの方法の 1 つは、SharePoint サイトのスイート ナビゲーション バーの検索ボックスの動作をニーズに合わせて調整する方法です。

その他のカスタマイズ オプション[](customize-search-page.md)については、「Microsoft Searchページを変更してカスタム垂直、結果の種類とレイアウトを追加する」、および「カスタム検索結果ページを作成する」[を参照してください](create-search-results-pages.md)。

> [!NOTE]
> 現時点では、スイート ナビゲーション バーの検索ボックスは、すべてのユーザーが使用できるとは言え、これらのオプションは現在も設定できます。使用可能になると有効になります。

以下に示すタスクでは、PnP PowerShell 拡張機能を使用SharePoint PowerShell を使用します。 ここから始める方法について、インストールして詳しい情報を参照 [してください](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。 次のコマンドを使用して、サイトまたはサイト コレクションにサインインします。

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>検索範囲の変更

今日のオンラインで新しいサイトSharePoint作成し、検索ボックスに入力すると、[検索結果] ページMicrosoft Searchされます。 このページには、既定で現在のサイトの結果が表示され、検索範囲を、現在のサイトが関連付けられているハブ (存在する場合) または組織全体に展開できます。

既定では、検索ボックスで使用されるスコープは、サイトの種類によって異なります。

* 通常のサイトは、現在のサイトを検索します。
* ハブ サイトは、ハブ内のすべてのサイトを検索します。
* ホーム サイトは、すべてのコンテンツを検索します。

場合によっては、これらの既定値を変更して、組織全体、またはサイトが関連付けられているハブ全体で、追加のクリックを必要とせずに検索する必要があります。

サイトの所有者は、次のコマンドを使用してこれらの既定値を変更できます。

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

このコマンドを実行すると、既定で現在のサイトの結果が以前に表示されたサイトは、組織全体の結果を表示し始める。

既定の設定に戻る場合は、値 "DefaultScope" でコマンドを再度実行します。 ハブ全体を検索するには、SearchScope 値として "Hub" を使用します。

この設定は、個々のサイト レベルで適用されます。 サイト コレクションに対して同等の設定はありません。

## <a name="show-or-hide-the-search-box"></a>検索ボックスを表示または非表示にする

ユーザーが検索を行うのを防ぐ場合や、カスタム検索ボックスの実装を使用する場合は、スイート ナビゲーション バーの検索ボックスを非表示にできます。

特定のサイトのこの設定を変更するには、次のコマンドを使用します。

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

または、サイト コレクション内のすべてのサイトに対して設定する場合は、次のコマンドを使用できます。

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

これらのコマンドを実行すると、ページの上部のナビゲーション バーに検索ボックスが表示されなくなりました。 検索ボックスの表示に戻る場合は、"SearchBoxInNavBar" パラメーターに指定された値を "Inherit" に設定して、コマンドを再度実行します。

次の点を考慮する必要があります。

* この設定は、スイート ナビゲーション バーの検索ボックスにのみ適用されます。 ページ内の検索ボックスや従来のページの検索ボックスには適用されません。

* ナビゲーション バーの検索ボックスを無効にしたら、サイトで検索機能を使用する場合は、カスタム Web パーツまたは SharePoint Framework 拡張機能を使用して検索ボックスを提供する必要があります。

* このソリューションでは、サイトのリストとライブラリから検索ボックスも削除されます。 カスタム検索ソリューションでは、サイト全体の検索に加えて、SharePointライブラリのコンテキスト検索を検討する必要があります。

* この設定をドメインのルート サイトに適用すると、SharePointスタート ページにも検索ボックスが表示されません。

## <a name="changing-the-hint-displayed-in-the-search-box"></a>検索ボックスに表示されるヒントを変更する

特定のサイトまたはサイト コレクションの検索ボックスに表示されるヒントを変更できます。 これは、入力を開始する前に検索ボックスに表示されるテキストです。 これは、カスタム結果ページを構成した場合や、他の方法で検索の動作を変更した場合に、ユーザーが検索から何を期待するかについてユーザーに案内するのに役立ちます。

> [!NOTE]
> この変更を行うには、テナント管理者として、問題のサイトでカスタム スクリプトの実行を許可する必要があります。既定では許可されません。 詳細については https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script 、以下を参照してください。 カスタム スクリプトの実行を許可し、変更を行い、必要に応じてサイトのスクリプトを禁止に戻します。

特定のサイトのこの設定を変更するには、次のコマンドを実行します。

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

または、サイト コレクション内のすべてのサイトに対して設定する場合は、次のコマンドを使用できます。

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

既定のプレースホルダー テキストに戻る場合は、値を空白 ("") に設定します。