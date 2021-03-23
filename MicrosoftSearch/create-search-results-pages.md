---
title: SharePoint Online でカスタム検索結果ページを作成する
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: SharePoint Online サイトの独自の検索結果ページを作成する
ms.openlocfilehash: b5abb25f15795389dd8b6d5683ac336af7422e0a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031640"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a><span data-ttu-id="0f17b-103">SharePoint Online でカスタム検索結果ページを作成する</span><span class="sxs-lookup"><span data-stu-id="0f17b-103">Create a custom search results page in SharePoint Online</span></span>

<span data-ttu-id="0f17b-104">SharePoint で検索エクスペリエンスをカスタマイズする 1 つの方法は、サイトのカスタム検索結果ページを作成することです。</span><span class="sxs-lookup"><span data-stu-id="0f17b-104">One way to customize the search experience in SharePoint is to create a custom search results page for a site.</span></span> <span data-ttu-id="0f17b-105">これにより、Microsoft 検索結果ページの既定ではなく、作成したページを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-105">This allows you to use a page that you created, rather than the default in Microsoft Search results page.</span></span> <span data-ttu-id="0f17b-106">これにより、検索結果エクスペリエンスがユーザーに対してどのように表示されるのか、より柔軟に対応できます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-106">This gives you more flexibility on how the search results experience looks for your users.</span></span>

>[!NOTE]
> <span data-ttu-id="0f17b-107">既定で使用可能な既定の Microsoft 検索結果ページに変更を加える場合は、「検索結果のカスタマイズ」 [ページをご覧ください](customize-search-page.md)。</span><span class="sxs-lookup"><span data-stu-id="0f17b-107">To make changes to the default Microsoft Search results page that is available by default, please see [Customize the search results page](customize-search-page.md).</span></span>

<span data-ttu-id="0f17b-108">カスタム結果ページを使用すると、組織のニーズをサポートする検索結果のレイアウトとデザインを制御するために使用できる新しいページを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-108">With a custom results page you can create a new page that can be used to control the layout and design of search results to support your organization's needs.</span></span> <span data-ttu-id="0f17b-109">SharePoint Patterns and Practices コミュニティの任意の組み込み Web パーツ、オープンソース検索 Web パーツ、および SharePoint Framework を使用して開発したカスタム Web パーツを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-109">You can use any built-in web parts, open-source search web parts from SharePoint Patterns and Practices community, as well as any custom web parts that you may have developed using SharePoint Framework.</span></span>

## <a name="configure-a-results-page"></a><span data-ttu-id="0f17b-110">結果ページの構成</span><span class="sxs-lookup"><span data-stu-id="0f17b-110">Configure a results page</span></span>

<span data-ttu-id="0f17b-111">SharePoint Online でカスタム結果ページを構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0f17b-111">To configure a custom results page in SharePoint Online follow the steps below:</span></span>

1. <span data-ttu-id="0f17b-112">カスタム結果ページを構成するサイトを参照し、[サイトの設定] >[検索設定] > **移動します**。</span><span class="sxs-lookup"><span data-stu-id="0f17b-112">Browse to the site where you would like to configure a custom results page and go to **Site Settings > Site Collection Settings > Search Settings**.</span></span>

2. <span data-ttu-id="0f17b-113">[検索設定] で、[親と同じ結果ページ設定を使用する]から選択を解除し、[カスタム結果ページにクエリを送信する] を選択し、[結果] ページの URL に値 **を指定します**。</span><span class="sxs-lookup"><span data-stu-id="0f17b-113">In Search Settings, clear selection from **Use the same results page settings as my parent**, choose **Send queries to a custom results page**, and provide a value for **Results page URL:**.</span></span> <span data-ttu-id="0f17b-114">次に、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="0f17b-114">Then, save your changes.</span></span> <span data-ttu-id="0f17b-115">ここで使用する URL は、カスタム結果ページとして使用するために作成したページ用である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f17b-115">The URL you use here should be for the page that you created to use as your custom results page.</span></span>

>[!NOTE]
> <span data-ttu-id="0f17b-116">カスタム結果ページは、サイトと同じドメイン上にある必要がありますが、同じサイト コレクション内に存在する必要はない。</span><span class="sxs-lookup"><span data-stu-id="0f17b-116">The custom results page needs to be on the same domain as your site, but it does not have to be in the same site collection.</span></span>  

<span data-ttu-id="0f17b-117">または、[サイトの設定] ページを使用する代わりに [、Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) コマンドを使用して値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-117">Alternatively, you can use the [Set-PnPSearchSettings SharePoint PnP PowerShell command](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) to set the value instead of using the Site Settings page.</span></span>

<span data-ttu-id="0f17b-118">設定が完了すると、ページの上部のナビゲーション バーに表示される Microsoft Search ボックスを使用して検索すると、カスタム検索結果ページが表示され、サイト ページまたはサイトのホーム ページから検索を入力するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-118">Once set, the custom search results page is displayed when you search using the Microsoft Search box that appears in the navigation bar on top of the page and is used when you enter search from site pages or the home page of the site.</span></span> <span data-ttu-id="0f17b-119">リスト、ライブラリ、またはサイト コンテンツ ページ内で検索する場合は使用されません。</span><span class="sxs-lookup"><span data-stu-id="0f17b-119">It is not used when you are searching within a list, library, or the site contents page.</span></span> <span data-ttu-id="0f17b-120">リンクを使用して、リストとライブラリの検索結果から検索を展開して、カスタム結果ページに移動できます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-120">You may use the link to expand your search from search results in lists and libraries to get to the custom results page.</span></span>

## <a name="change-the-layout-of-your-custom-results-page"></a><span data-ttu-id="0f17b-121">カスタム結果ページのレイアウトを変更する</span><span class="sxs-lookup"><span data-stu-id="0f17b-121">Change the layout of your custom results page</span></span>

<span data-ttu-id="0f17b-122">**HeaderlessSearchResults** という名前のページ レイアウトを使用すると、検索結果ページを検索結果エクスペリエンスの近くに表示できます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-122">A page layout named **HeaderlessSearchResults** can be used to make the search results page appear closer to our out of box search results experience.</span></span> <span data-ttu-id="0f17b-123">この新しいレイアウトは、カスタム検索結果ページに設定されているページでのみアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-123">This new layout can only be active for the pages that are set to be the custom search results page.</span></span>

<span data-ttu-id="0f17b-124">ページ レイアウトを設定するには、-LayoutType HeaderlessSearchResults で [Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) コマンドを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-124">To set the page layout, you can use the [Set-PnPClientSidePageSharePoint PnP PowerShell command](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) with -LayoutType HeaderlessSearchResults.</span></span>

## <a name="use-sharepoint-framework-query-extensions"></a><span data-ttu-id="0f17b-125">SharePoint Framework クエリ拡張機能の使用</span><span class="sxs-lookup"><span data-stu-id="0f17b-125">Use SharePoint Framework Query extensions</span></span>

<span data-ttu-id="0f17b-126">カスタム検索結果ページでは [、SharePoint Framework クエリ](/sharepoint/dev/spfx/building-search-extensions) 拡張機能を使用して、検索エンジンに送信される前にクエリを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f17b-126">Custom search results pages can also make use of the [SharePoint Framework Query Extension](/sharepoint/dev/spfx/building-search-extensions) to modify the query before it gets sent to the search engine.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0f17b-127">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="0f17b-127">Additional resources</span></span>

<span data-ttu-id="0f17b-128">カスタム結果ページの詳細については [、「Ignite 2019 Search Customization and Development session」を参照してください](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)。</span><span class="sxs-lookup"><span data-stu-id="0f17b-128">To learn more about custom results page, check out our [Ignite 2019 Search Customization and Development session](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).</span></span>

<span data-ttu-id="0f17b-129">オープン ソース プロジェクトの場合は、Microsoft Search API の使用を開始し、カスタマイズと拡張性のサンプルを追加するには [、GitHub の Microsoft Search を参照してください](https://github.com/microsoft-search)。</span><span class="sxs-lookup"><span data-stu-id="0f17b-129">For open source projects, getting started with our Microsoft Search APIs, and more customization and extensibility samples, visit [Microsoft Search on GitHub](https://github.com/microsoft-search).</span></span>