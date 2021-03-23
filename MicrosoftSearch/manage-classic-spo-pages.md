---
title: SharePoint Online と Microsoft Search のクラシック ページ
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
description: 従来の SharePoint ページでの Microsoft Search の使用
ms.openlocfilehash: 33215c730d34c14f8ce1d55e93730615688f1e2a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031433"
---
# <a name="classic-pages-and-microsoft-search"></a>クラシック ページと Microsoft Search

モダン サイトより前に作成された SharePoint サイトでは、従来の検索ボックスと従来の検索結果エクスペリエンスが使用されます。 Microsoft Search を使用するモダン検索エクスペリエンスの使用を開始するために、従来のページを既定で使用する機能を展開します。これは、関連性の高いパーソナライズされた結果を提供します。

従来のサイトを含むすべてのサイトでは Microsoft Search の使用をお勧めしますが、クラシック サイトでカスタム マスター ページを使用している場合や、従来の検索結果エクスペリエンスをカスタマイズした場合は、これらのカスタマイズを自動的に検出し、Microsoft Search に切り替える必要があります。

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Microsoft Search に自動的に切り替える従来のサイト

以下のすべてが当てはまる場合、従来のサイトでは Microsoft Search の使用が開始されます。

* サイトはチーム サイト テンプレート (STS#0 や STS#1 など) に基づいて作成されます。
* サイトに発行機能が有効になっていません。
* サイトはカスタム マスター ページ (oslo.master または seattle.master とは異なるマスター ページ) を使用しない。
* 既定の結果ソースにサイト、サイト コレクション、またはテナントの昇格された結果を追加する以外に、アクティブなクエリ ルールはありません。
* 既定の結果ソースには、サイトまたはサイト コレクションのカスタム結果の種類はありません。
* 以下で説明する *SearchBoxInNavBar* 設定を使用して、サイトまたはサイト コレクションがスイッチからオプトアウトされません。

Microsoft Search への切り替え後、サイト内のクラシック ページがスイート ナビゲーション バーに検索ボックスを表示し始め、クラシック検索ボックスをページから削除します。 次に、ユーザーが用語を検索すると、Microsoft Search の最新の検索エクスペリエンスを使用して結果が表示されます。

## <a name="staying-with-the-classic-search-experience"></a>従来の検索エクスペリエンスを利用する

サイトが上記の条件を満たしているが、Microsoft Search エクスペリエンスに切り替えたくない場合は、サイトまたはサイト コレクションの所有者として、次のコマンドを使用してオプトアウトできます。

このコマンドは、スイッチが発生する前、または発生した後にいつでも使用できます。そのため、以前の検索エクスペリエンスに簡単に戻って操作できます。

以下のコマンドを実行するには、PowerShell と SharePoint PnP PowerShell 拡張機能を使用します。 ここから始める方法について、インストールして詳しい情報を参照 [してください](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。 次のコマンドを使用して、サイトまたはサイト コレクションにサインインします。

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

サイトの従来の検索エクスペリエンスを利用するには、次のコマンドを実行します。

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

または、サイト コレクション内のすべてのサイトに対して設定する場合は、次のコマンドを使用できます。

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Microsoft Search のオプトイン

上記の条件を満たしていないサイト、または従来のサイト コレクション内の特定のサイトに対して、Microsoft Search エクスペリエンスを手動で有効にできます。

特定のサイトのこの設定を変更するには、次のコマンドを使用します。

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

サイト コレクション内のすべてのサイトに設定する場合は、次のコマンドを使用できます。

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> チーム サイトまたは発行サイト ("STS"、"CMSPUBLISHING"、"BLANKINTERNET" および "GROUP" を含むテンプレート ID) に対してのみ Microsoft Search を手動で有効にできます。