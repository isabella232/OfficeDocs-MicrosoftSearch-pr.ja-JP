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
ms.openlocfilehash: 605e63a30ad166c63320c7e89e1b2745e628e15d
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700975"
---
# <a name="classic-pages-and-microsoft-search"></a>クラシック ページと Microsoft Search

モダン サイトより前に作成された SharePoint サイトでは、クラシック検索ボックスと従来の検索結果エクスペリエンスが使用されます。 Microsoft Search を使用するモダン検索エクスペリエンスの使用を開始するために、従来のページを既定で使用する機能を展開します。この機能は、関連性の高いカスタマイズされた結果を提供します。

クラシックサイトを含むすべてのサイトには Microsoft Search の使用をお勧めしますが、クラシック サイトでカスタム マスター ページを使用している場合や、クラシック検索結果のエクスペリエンスをカスタマイズした場合は、これらのカスタマイズが自動検出され、Microsoft Search に切り替えは行いません。

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Microsoft Search に自動的に切り替える従来のサイト

以下のすべてが当てはまる場合、クラシック サイトは Microsoft Search の使用を開始します。

* サイトはチーム サイト テンプレート (STS#0 や STS#1 など) に基づいて作成されます。
* サイトで発行機能が有効になっていません。
* サイトはカスタム マスター ページ (oslo.master または seattle.master とは異なるマスター ページ) を使用しない。
* 既定の検索元のサイト、サイト コレクション、またはテナントに昇格した結果を追加するクエリ ルール以外にアクティブなクエリ ルールはありません。
* 既定の結果ソースには、サイトまたはサイト コレクションに対するカスタムの結果の種類はありません。
* その一部であるサイトまたはサイト コレクションは、以下で説明する SearchBoxInNavBar 設定を使用して切り替えからオプトアウトしていない。

Microsoft Search に切り替えると、サイト内の従来のページがスイート ナビゲーション バーに検索ボックスの表示を開始し、従来の検索ボックスをページから削除します。 次に、ユーザーが用語を検索すると、Microsoft Search のモダン検索エクスペリエンスを使用して結果が表示されます。

## <a name="staying-with-the-classic-search-experience"></a>クラシック検索エクスペリエンスの使用

サイトが上記の条件を満たしているが、Microsoft Search エクスペリエンスに切り替えたくない場合は、サイトまたはサイト コレクションの所有者として、次のコマンドを使用してオプトアウトできます。

このコマンドは、切り替えの発生前または実行後にいつでも使用できます。そのため、以前の検索エクスペリエンスに簡単に戻って操作できます。

以下のコマンドを実行するには、PowerShell と SharePoint PnP PowerShell 拡張機能を使用します。 ここでは、インストールを行い、開始する方法について詳しい情報を参照 [できます](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。 次のコマンドを使用して、サイトまたはサイト コレクションにサインインします。

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

サイトのクラシック検索エクスペリエンスを使用するには、次のコマンドを実行します。

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

または、サイト コレクション内のすべてのサイトに設定する場合は、次のコマンドを使用できます。

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Microsoft Search へのオプトイン

上記の条件を満たしていないサイト、またはクラシックを使用することを選択したサイト コレクション内の特定のサイトに対して、Microsoft Search エクスペリエンスを手動で有効にできます。

特定のサイトに対してこの設定を変更するには、次のコマンドを使用します。

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
> チーム サイトまたは発行サイト ("STS"、"CMSPUBLISHING"、"BLANKINTERNET"、および "GROUP" を含むテンプレート ID) に対してだけ Microsoft Search を手動で有効にできます。
