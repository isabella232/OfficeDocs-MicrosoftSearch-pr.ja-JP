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
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="01327-103">SharePoint サイトの検索ボックス設定</span><span class="sxs-lookup"><span data-stu-id="01327-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="01327-104">SharePoint サイトで Microsoft Search をカスタマイズする方法の 1 つは、ニーズに最適な SharePoint サイトのスイート ナビゲーション バーの検索ボックスの動作を調整する方法です。</span><span class="sxs-lookup"><span data-stu-id="01327-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="01327-105">その他のカスタマイズ オプションについては [、「Microsoft Search](customize-search-page.md)の結果ページを変更してカスタムのバーティカル、検索結果の種類とレイアウトを追加する」、および「カスタム検索結果ページを作成する」を [参照してください](create-search-results-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="01327-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="01327-106">現時点では、スイート ナビゲーション バーの検索ボックスは、すべてのユーザーが利用できるとは言え、これらのオプションは現在も設定できます。これらのオプションは、利用可能になったときに有効になります。</span><span class="sxs-lookup"><span data-stu-id="01327-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="01327-107">以下のタスクでは、PowerShell と SharePoint PnP PowerShell 拡張機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="01327-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="01327-108">ここでは、インストールを行い、開始する方法について詳しい情報を参照 [できます](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps)。</span><span class="sxs-lookup"><span data-stu-id="01327-108">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="01327-109">次のコマンドを使用して、サイトまたはサイト コレクションにサインインします。</span><span class="sxs-lookup"><span data-stu-id="01327-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="01327-110">検索範囲の変更</span><span class="sxs-lookup"><span data-stu-id="01327-110">Changing the scope of search</span></span>

<span data-ttu-id="01327-111">SharePoint Online で新しいサイトを作成し、検索ボックスに入力すると、Microsoft Search の結果ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01327-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="01327-112">このページには、既定で現在のサイトからの結果が表示され、検索範囲を現在のサイトが関連付けられているハブ (存在する場合) または組織全体に展開できます。</span><span class="sxs-lookup"><span data-stu-id="01327-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="01327-113">既定では、検索ボックスが使用する範囲はサイトの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="01327-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="01327-114">通常のサイトは、現在のサイトを検索します。</span><span class="sxs-lookup"><span data-stu-id="01327-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="01327-115">ハブ サイトは、ハブ内のすべてのサイトを検索します。</span><span class="sxs-lookup"><span data-stu-id="01327-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="01327-116">ホーム サイトは、すべてのコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="01327-116">Home sites search over all content.</span></span>

<span data-ttu-id="01327-117">場合によっては、これらの既定値を変更して、追加のクリックを必要とせずに、常に組織全体を検索したり、サイトが関連付けられているハブ全体を検索したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="01327-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="01327-118">サイト所有者は、次のコマンドを使用してこれらの既定値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="01327-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="01327-119">このコマンドを実行すると、既定で現在のサイトからの結果が以前に表示されたサイトには、組織全体からの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="01327-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="01327-120">既定の設定に戻る場合は、値 "DefaultScope" を指定してコマンドを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="01327-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="01327-121">ハブ全体を検索するには、SearchScope 値として "Hub" を使用します。</span><span class="sxs-lookup"><span data-stu-id="01327-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="01327-122">この設定は、個々のサイト レベルで適用されます。</span><span class="sxs-lookup"><span data-stu-id="01327-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="01327-123">サイト コレクションに相当する設定はありません。</span><span class="sxs-lookup"><span data-stu-id="01327-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="01327-124">検索ボックスを表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="01327-124">Show or hide the search box</span></span>

<span data-ttu-id="01327-125">ユーザーが検索を実行したり、カスタム検索ボックスの実装を使用したりするには、スイート ナビゲーション バーの検索ボックスを非表示にできます。</span><span class="sxs-lookup"><span data-stu-id="01327-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="01327-126">特定のサイトに対してこの設定を変更するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="01327-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="01327-127">または、サイト コレクション内のすべてのサイトに設定する場合は、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01327-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="01327-128">これらのコマンドを実行すると、ページの上部のナビゲーション バーに検索ボックスが表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="01327-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="01327-129">検索ボックスの表示に戻る場合は、"SearchBoxInNavBar" パラメーターに指定した値を使用してコマンドを再度実行し、"Inherit" に設定します。</span><span class="sxs-lookup"><span data-stu-id="01327-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="01327-130">次の点を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01327-130">There are several points to consider:</span></span>

* <span data-ttu-id="01327-131">この設定は、スイート ナビゲーション バーの検索ボックスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="01327-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="01327-132">ページ内の検索ボックスや、従来のページの検索ボックスには適用されません。</span><span class="sxs-lookup"><span data-stu-id="01327-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="01327-133">ナビゲーション バーの検索ボックスを無効にしたら、サイトで検索機能を使用する場合は、カスタム Web パーツまたは SharePoint Framework 拡張機能を使用して検索ボックスを自分で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01327-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="01327-134">このソリューションでは、サイトのリストとライブラリから検索ボックスも削除されます。</span><span class="sxs-lookup"><span data-stu-id="01327-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="01327-135">カスタム検索ソリューションでは、サイト全体の検索に加えて、SharePoint リストとライブラリのコンテキスト検索を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01327-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="01327-136">ドメインのルート サイトに設定を適用すると、SharePoint のスタート ページにも検索ボックスが表示されません。</span><span class="sxs-lookup"><span data-stu-id="01327-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="01327-137">検索ボックスに表示されるヒントを変更する</span><span class="sxs-lookup"><span data-stu-id="01327-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="01327-138">特定のサイトまたはサイト コレクションの検索ボックスに表示されるヒントを変更できます。</span><span class="sxs-lookup"><span data-stu-id="01327-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="01327-139">これは、入力を開始する前に検索ボックスに表示されるテキストです。</span><span class="sxs-lookup"><span data-stu-id="01327-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="01327-140">これは、カスタムの結果ページを構成した場合や、他の方法で検索の動作を変更した場合に、検索で期待される動作についてユーザーをガイドするのに役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="01327-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="01327-141">この変更を行うには、テナント管理者として、サイトでカスタム スクリプトの実行を許可する必要があります。これは既定では許可されません。</span><span class="sxs-lookup"><span data-stu-id="01327-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="01327-142">詳細については https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script 、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01327-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="01327-143">カスタム スクリプトの実行を許可し、変更を行い、必要に応じてサイトのスクリプトを禁止に戻します。</span><span class="sxs-lookup"><span data-stu-id="01327-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="01327-144">特定のサイトのこの設定を変更するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="01327-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="01327-145">または、サイト コレクション内のすべてのサイトに設定する場合は、次のコマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="01327-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="01327-146">既定のプレースホルダー テキストに戻る場合は、値を空白 ("") に設定します。</span><span class="sxs-lookup"><span data-stu-id="01327-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>
