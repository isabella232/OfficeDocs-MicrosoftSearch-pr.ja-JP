---
title: '[オンライン] および [SharePoint] のクラシック ページMicrosoft Search'
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
description: 従来Microsoft SearchページでのSharePointの使用
ms.openlocfilehash: 5b9c40da63ccf3b28cf2d61282763d3d4f62f867
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375843"
---
# <a name="classic-pages-and-microsoft-search"></a>従来のページとMicrosoft Search

SharePoint以前に作成されたサイトでは、従来の検索ボックスと従来の検索結果エクスペリエンスが使用されます。 従来のページを既定で展開し、Microsoft Search を使用する最新の検索エクスペリエンスの使用を開始します。これは、関連性の高いパーソナライズされた結果を提供します。

従来Microsoft Searchを含むすべてのサイトに対して使用をお勧めしますが、クラシック サイトでカスタム マスター ページを使用している場合や、従来の検索結果エクスペリエンスをカスタマイズした場合は、これらのカスタマイズを自動的に検出し、Microsoft Search に切り替える必要があります。

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>従来のサイトに自動的に切り替Microsoft Search

従来のサイトでは、次Microsoft Searchに当てはまる場合は、そのサイトの使用が開始されます。

* サイトはチーム サイト テンプレート (STS#0 や STS#1 など) に基づいて作成されます。
* サイトに発行機能が有効になっていません。
* サイトはカスタム マスター ページ (oslo.master または seattle.master とは異なるマスター ページ) を使用しない。
* 既定の結果ソースにサイト、サイト コレクション、またはテナントの昇格された結果を追加する以外に、アクティブなクエリ ルールはありません。
* 既定の結果ソースには、サイトまたはサイト コレクションのカスタム結果の種類はありません。
* 以下で説明する *SearchBoxInNavBar* 設定を使用して、サイトまたはサイト コレクションがスイッチからオプトアウトされません。

サイト内のクラシック Microsoft Searchに切り替えると、スイート ナビゲーション バーに検索ボックスが表示され、従来の検索ボックスがページから削除されます。 次に、ユーザーが用語を検索すると、最新の検索エクスペリエンスを使用して検索結果が表示Microsoft Search。

## <a name="staying-with-the-classic-search-experience"></a>従来の検索エクスペリエンスを利用する

サイトが上記の条件を満たしているが、Microsoft Search エクスペリエンスに切り替えたくない場合は、サイトまたはサイト コレクションの所有者として、次のコマンドを使用してオプトアウトできます。

このコマンドは、スイッチが発生する前、または発生した後にいつでも使用できます。そのため、以前の検索エクスペリエンスに簡単に戻って操作できます。

以下のコマンドを実行するには、PnP PowerShell 拡張機能を使用SharePoint PowerShell を使用します。 ここから始める方法について、インストールして詳しい情報を参照 [してください](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。 次のコマンドを使用して、サイトまたはサイト コレクションにサインインします。

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

## <a name="opting-into-microsoft-search"></a>オプトイン Microsoft Search

上記の条件を満たしていないサイト、または従来のサイト コレクション内の特定のサイトの場合は、手動で Microsoft Search エクスペリエンスを有効にできます。

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
> チーム サイトMicrosoft Search発行サイト ("STS"、"CMSPUBLISHING"、"BLANKINTERNET" および "GROUP" を含むテンプレート ID) に対してのみ手動で有効にできます。