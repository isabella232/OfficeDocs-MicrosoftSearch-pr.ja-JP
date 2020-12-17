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
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="690a4-103">クラシック ページと Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="690a4-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="690a4-104">モダン サイトより前に作成された SharePoint サイトでは、クラシック検索ボックスと従来の検索結果エクスペリエンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="690a4-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="690a4-105">Microsoft Search を使用するモダン検索エクスペリエンスの使用を開始するために、従来のページを既定で使用する機能を展開します。この機能は、関連性の高いカスタマイズされた結果を提供します。</span><span class="sxs-lookup"><span data-stu-id="690a4-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="690a4-106">クラシックサイトを含むすべてのサイトには Microsoft Search の使用をお勧めしますが、クラシック サイトでカスタム マスター ページを使用している場合や、クラシック検索結果のエクスペリエンスをカスタマイズした場合は、これらのカスタマイズが自動検出され、Microsoft Search に切り替えは行いません。</span><span class="sxs-lookup"><span data-stu-id="690a4-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="690a4-107">Microsoft Search に自動的に切り替える従来のサイト</span><span class="sxs-lookup"><span data-stu-id="690a4-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="690a4-108">以下のすべてが当てはまる場合、クラシック サイトは Microsoft Search の使用を開始します。</span><span class="sxs-lookup"><span data-stu-id="690a4-108">Classic sites will start using Microsoft Search if all of the following are true.</span></span>

* <span data-ttu-id="690a4-109">サイトはチーム サイト テンプレート (STS#0 や STS#1 など) に基づいて作成されます。</span><span class="sxs-lookup"><span data-stu-id="690a4-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="690a4-110">サイトで発行機能が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="690a4-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="690a4-111">サイトはカスタム マスター ページ (oslo.master または seattle.master とは異なるマスター ページ) を使用しない。</span><span class="sxs-lookup"><span data-stu-id="690a4-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="690a4-112">既定の検索元のサイト、サイト コレクション、またはテナントに昇格した結果を追加するクエリ ルール以外にアクティブなクエリ ルールはありません。</span><span class="sxs-lookup"><span data-stu-id="690a4-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="690a4-113">既定の結果ソースには、サイトまたはサイト コレクションに対するカスタムの結果の種類はありません。</span><span class="sxs-lookup"><span data-stu-id="690a4-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="690a4-114">その一部であるサイトまたはサイト コレクションは、以下で説明する SearchBoxInNavBar 設定を使用して切り替えからオプトアウトしていない。</span><span class="sxs-lookup"><span data-stu-id="690a4-114">The site or the site collection it is part of has not opted out of the switch using the SearchBoxInNavBar setting described below.</span></span>

<span data-ttu-id="690a4-115">Microsoft Search に切り替えると、サイト内の従来のページがスイート ナビゲーション バーに検索ボックスの表示を開始し、従来の検索ボックスをページから削除します。</span><span class="sxs-lookup"><span data-stu-id="690a4-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="690a4-116">次に、ユーザーが用語を検索すると、Microsoft Search のモダン検索エクスペリエンスを使用して結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="690a4-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="690a4-117">クラシック検索エクスペリエンスの使用</span><span class="sxs-lookup"><span data-stu-id="690a4-117">Staying with the classic search experience</span></span>

<span data-ttu-id="690a4-118">サイトが上記の条件を満たしているが、Microsoft Search エクスペリエンスに切り替えたくない場合は、サイトまたはサイト コレクションの所有者として、次のコマンドを使用してオプトアウトできます。</span><span class="sxs-lookup"><span data-stu-id="690a4-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="690a4-119">このコマンドは、切り替えの発生前または実行後にいつでも使用できます。そのため、以前の検索エクスペリエンスに簡単に戻って操作できます。</span><span class="sxs-lookup"><span data-stu-id="690a4-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="690a4-120">以下のコマンドを実行するには、PowerShell と SharePoint PnP PowerShell 拡張機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="690a4-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="690a4-121">ここでは、インストールを行い、開始する方法について詳しい情報を参照 [できます](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="690a4-121">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="690a4-122">次のコマンドを使用して、サイトまたはサイト コレクションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="690a4-122">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

<span data-ttu-id="690a4-123">サイトのクラシック検索エクスペリエンスを使用するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="690a4-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="690a4-124">または、サイト コレクション内のすべてのサイトに設定する場合は、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="690a4-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="690a4-125">Microsoft Search へのオプトイン</span><span class="sxs-lookup"><span data-stu-id="690a4-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="690a4-126">上記の条件を満たしていないサイト、またはクラシックを使用することを選択したサイト コレクション内の特定のサイトに対して、Microsoft Search エクスペリエンスを手動で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="690a4-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="690a4-127">特定のサイトに対してこの設定を変更するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="690a4-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="690a4-128">サイト コレクション内のすべてのサイトに設定する場合は、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="690a4-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="690a4-129">チーム サイトまたは発行サイト ("STS"、"CMSPUBLISHING"、"BLANKINTERNET"、および "GROUP" を含むテンプレート ID) に対してだけ Microsoft Search を手動で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="690a4-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>
