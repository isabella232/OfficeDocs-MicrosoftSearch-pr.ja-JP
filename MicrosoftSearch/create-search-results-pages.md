---
title: SharePoint Online でカスタム検索結果ページを作成する
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: SharePoint Online サイト用の独自の検索結果ページを作成する
ms.openlocfilehash: 9b168dccaa6126148c877b5841b91c63f7bdc2ac
ms.sourcegitcommit: 5fb46a04e86fb49477f8ce7ab3caa1b503215b8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503241"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a><span data-ttu-id="644eb-103">SharePoint Online でカスタム検索結果ページを作成する</span><span class="sxs-lookup"><span data-stu-id="644eb-103">Create a custom search results page in SharePoint Online</span></span>

<span data-ttu-id="644eb-104">SharePoint での検索の動作をカスタマイズする方法の1つは、サイトのカスタム検索結果ページを作成することです。</span><span class="sxs-lookup"><span data-stu-id="644eb-104">One way to customize the search experience in SharePoint is to create a custom search results page for a site.</span></span> <span data-ttu-id="644eb-105">これにより、Microsoft の検索結果ページの既定値ではなく、作成したページを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="644eb-105">This allows you to use a page that you created, rather than the default in Microsoft Search results page.</span></span> <span data-ttu-id="644eb-106">これにより、検索結果がユーザーに対してどのように表示されるかをより柔軟にすることができます。</span><span class="sxs-lookup"><span data-stu-id="644eb-106">This gives you more flexibility on how the search results experience looks for your users.</span></span>

>[!NOTE]
> <span data-ttu-id="644eb-107">既定で利用できる既定の Microsoft 検索結果ページに変更を加えるには、「[検索結果ページをカスタマイズ](customize-search-page.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="644eb-107">To make changes to the default Microsoft Search results page that is available by default, please see [Customize the search results page](customize-search-page.md).</span></span>

<span data-ttu-id="644eb-108">カスタム結果ページを使用すると、組織のニーズをサポートするための検索結果のレイアウトと設計を制御するために使用できる新しいページを作成できます。</span><span class="sxs-lookup"><span data-stu-id="644eb-108">With a custom results page you can create a new page that can be used to control the layout and design of search results to support your organization's needs.</span></span> <span data-ttu-id="644eb-109">Sharepoint のパターンとプラクティスコミュニティから、任意の組み込み web パーツ、オープンソース検索 web パーツを使用することができます。また、SharePoint Framework を使用して開発したカスタム web パーツを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="644eb-109">You can use any built-in web parts, open-source search web parts from SharePoint Patterns and Practices community, as well as any custom web parts that you may have developed using SharePoint Framework.</span></span>

## <a name="configure-a-results-page"></a><span data-ttu-id="644eb-110">結果ページを構成する</span><span class="sxs-lookup"><span data-stu-id="644eb-110">Configure a results page</span></span>

<span data-ttu-id="644eb-111">SharePoint Online でカスタムの結果ページを構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="644eb-111">To configure a custom results page in SharePoint Online follow the steps below:</span></span>

1. <span data-ttu-id="644eb-112">カスタムの結果ページを構成するサイトを参照し、[サイトの設定] **> サイトコレクションの設定 > 検索**の設定] に移動します。</span><span class="sxs-lookup"><span data-stu-id="644eb-112">Browse to the site where you would like to configure a custom results page and go to **Site Settings > Site Collection Settings > Search Settings**.</span></span>

2. <span data-ttu-id="644eb-113">[検索の設定] で、 **[親と同じ結果ページの設定を使用**する] をオフにし、[**カスタムの結果ページにクエリを送信**] を選択して、 **結果ページの URL**の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="644eb-113">In Search Settings, clear selection from **Use the same results page settings as my parent**, choose **Send queries to a custom results page**, and provide a value for **Results page URL:**.</span></span><span data-ttu-id="644eb-114">次に、変更内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="644eb-114"> Then, save your changes.</span></span> <span data-ttu-id="644eb-115">ここで使用する URL は、カスタムの結果ページとして使用するために作成したページに対して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="644eb-115">The URL you use here should be for the page that you created to use as your custom results page.</span></span>

>[!NOTE]
> <span data-ttu-id="644eb-116">カスタムの結果ページは、サイトと同じドメインにある必要がありますが、同じサイトコレクションに存在する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="644eb-116">The custom results page needs to be on the same domain as your site, but it does not have to be in the same site collection.</span></span>  

<span data-ttu-id="644eb-117">または、 [PnPSearchSettings SharePoint PnP PowerShell コマンド](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps)を使用して、[サイトの設定] ページを使用する代わりに値を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="644eb-117">Alternatively, you can use the [Set-PnPSearchSettings SharePoint PnP PowerShell command](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) to set the value instead of using the Site Settings page.</span></span>

<span data-ttu-id="644eb-118">設定すると、ページの上部にあるナビゲーションバーに表示される Microsoft 検索ボックスを使用して検索すると、カスタム検索結果ページが表示され、サイトページまたはサイトのホームページから検索を入力したときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="644eb-118">Once set, the custom search results page is displayed when you search using the Microsoft Search box that appears in the navigation bar on top of the page and is used when you enter search from site pages or the home page of the site.</span></span> <span data-ttu-id="644eb-119">リスト、ライブラリ、または [サイトコンテンツ] ページ内で検索する場合は、使用されません。</span><span class="sxs-lookup"><span data-stu-id="644eb-119">It is not used when you are searching within a list, library, or the site contents page.</span></span> <span data-ttu-id="644eb-120">このリンクを使用すると、リストとライブラリの検索結果から検索を拡張して、カスタムの結果ページにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="644eb-120">You may use the link to expand your search from search results in lists and libraries to get to the custom results page.</span></span>

## <a name="change-the-layout-of-your-custom-results-page"></a><span data-ttu-id="644eb-121">カスタム結果ページのレイアウトを変更する</span><span class="sxs-lookup"><span data-stu-id="644eb-121">Change the layout of your custom results page</span></span>

<span data-ttu-id="644eb-122">[ **Header狭く Searchresults** ] という名前のページレイアウトを使用して、検索結果ページを、不在時の検索結果ページに近い状態で表示することができます。</span><span class="sxs-lookup"><span data-stu-id="644eb-122">A page layout named **HeaderlessSearchResults** can be used to make the search results page appear closer to our out of box search results experience.</span></span><span data-ttu-id="644eb-123">この新しいレイアウトは、カスタム検索結果ページになるように設定されたページに対してのみアクティブにできます。</span><span class="sxs-lookup"><span data-stu-id="644eb-123"> This new layout can only be active for the pages that are set to be the custom search results page.</span></span>

<span data-ttu-id="644eb-124">ページレイアウトを設定するには、 [PnPClientSidePageSharePoint PnP PowerShell コマンド](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps)を-Layouttype HeaderlessSearchResults で使用できます。</span><span class="sxs-lookup"><span data-stu-id="644eb-124">To set the page layout, you can use the [Set-PnPClientSidePageSharePoint PnP PowerShell command](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) with -LayoutType HeaderlessSearchResults.</span></span>

## <a name="use-sharepoint-framework-query-extensions"></a><span data-ttu-id="644eb-125">SharePoint Framework のクエリ拡張機能を使用する</span><span class="sxs-lookup"><span data-stu-id="644eb-125">Use SharePoint Framework Query extensions</span></span>

<span data-ttu-id="644eb-126">カスタム検索結果ページでは、 [SharePoint Framework クエリ拡張機能](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions)を使用してクエリを変更してから、検索エンジンに送信することもできます。</span><span class="sxs-lookup"><span data-stu-id="644eb-126">Custom search results pages can also make use of the [SharePoint Framework Query Extension](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions) to modify the query before it gets sent to the search engine.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="644eb-127">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="644eb-127">Additional resources</span></span>

<span data-ttu-id="644eb-128">カスタム結果ページの詳細については、「 [Ignite 2019 Search Customization And Development session](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="644eb-128">To learn more about custom results page, check out our [Ignite 2019 Search Customization and Development session](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).</span></span>

<span data-ttu-id="644eb-129">オープンソースプロジェクト、Microsoft Search Api の概要、およびカスタマイズと拡張機能のサンプルについては、 [GitHub の Microsoft search](https://github.com/microsoft-search)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="644eb-129">For open source projects, getting started with our Microsoft Search APIs, and more customization and extensibility samples, visit [Microsoft Search on GitHub](https://github.com/microsoft-search).</span></span>
