---
title: カスタムフィルターを管理する
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
description: カスタムフィルターを管理する
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927384"
---
# <a name="create-custom-filters"></a><span data-ttu-id="e4a7f-103">カスタムフィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="e4a7f-103">Create custom Filters</span></span>

<span data-ttu-id="e4a7f-104">ユーザーが[Bing](https://bing.com)で microsoft [SharePoint](https://sharepoint.com/)、Microsoft [Office](https://office.com)、microsoft search を検索するときに表示される検索機能をカスタマイズするためのフィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-104">You can create filters to customize the search experience that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="e4a7f-105">フィルターを使用すると、ユーザーは検索クエリの結果セットをすばやく絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-105">Filters lets users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="e4a7f-106">カスタムフィルターは、接続プロパティに基づいて垂直方向の内部に作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="e4a7f-107">たとえば、カスタム縦にある ServiceNow 接続に対し **て発行済み** フィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-107">For example, you can create a **Published On** filter for ServiceNow connection inside a custom vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="e4a7f-108">考慮事項</span><span class="sxs-lookup"><span data-stu-id="e4a7f-108">Things to consider</span></span>

1. <span data-ttu-id="e4a7f-109">接続コンテンツソースにカスタムフィルターを作成する場合は、次の追加機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-109">For creating custom filter on connection content source, some additional capabilities are provided:</span></span>
- <span data-ttu-id="e4a7f-110">コネクタソースのプロパティへのエイリアスに対してフィルターを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-110">You can also create filter on an alias to connector source properties</span></span>
- <span data-ttu-id="e4a7f-111">縦方向に複数の接続がある場合は、これらの接続全体で共通フィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-111">In case your vertical has multiple connections then you can create a common filter across these connections.</span></span> <span data-ttu-id="e4a7f-112">これを行うには、共通のエイリアスに対してフィルターを作成します。このエイリアスは、ソースプロパティをそれぞれ異なる接続間でエイリアスします。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-112">This can be done by creating the filter on an common alias which aliases source properties across across different connections.</span></span> <span data-ttu-id="e4a7f-113">たとえば、次のようにエイリアスを作成することによって、ServiceNow & の Jira 接続に対して作成 **者** フィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-113">For example you can create an **Author** filter across a ServiceNow & a Jira connection by creating aliases as follows:</span></span>

| <span data-ttu-id="e4a7f-114">接続</span><span class="sxs-lookup"><span data-stu-id="e4a7f-114">Connection</span></span> | <span data-ttu-id="e4a7f-115">プロパティ</span><span class="sxs-lookup"><span data-stu-id="e4a7f-115">Property</span></span> | <span data-ttu-id="e4a7f-116">エイリアス</span><span class="sxs-lookup"><span data-stu-id="e4a7f-116">Alias</span></span> |
| --- | --- | --- |
| <span data-ttu-id="e4a7f-117">サービスの開始</span><span class="sxs-lookup"><span data-stu-id="e4a7f-117">Service Now</span></span> | <span data-ttu-id="e4a7f-118">所有者</span><span class="sxs-lookup"><span data-stu-id="e4a7f-118">Owner</span></span> | <span data-ttu-id="e4a7f-119">設定元</span><span class="sxs-lookup"><span data-stu-id="e4a7f-119">Author</span></span> |
| <span data-ttu-id="e4a7f-120">Jira</span><span class="sxs-lookup"><span data-stu-id="e4a7f-120">Jira</span></span> | <span data-ttu-id="e4a7f-121">Publisher</span><span class="sxs-lookup"><span data-stu-id="e4a7f-121">Publisher</span></span> | <span data-ttu-id="e4a7f-122">設定元</span><span class="sxs-lookup"><span data-stu-id="e4a7f-122">Author</span></span> |

2. <span data-ttu-id="e4a7f-123">フィルターは垂直方向の範囲内に存在します。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-123">Filters exist within the scope of the vertical.</span></span> <span data-ttu-id="e4a7f-124">いえ</span><span class="sxs-lookup"><span data-stu-id="e4a7f-124">Hence,</span></span>  
- <span data-ttu-id="e4a7f-125">組織レベルにある垂直方向にフィルターを作成した場合、フィルターは組織レベルでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-125">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
- <span data-ttu-id="e4a7f-126">サイトレベルにある垂直方向にフィルターを作成すると、そのフィルターはサイトレベルでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-126">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="steps-to-create-custom-filter"></a><span data-ttu-id="e4a7f-127">カスタムフィルターを作成する手順</span><span class="sxs-lookup"><span data-stu-id="e4a7f-127">Steps to Create custom filter</span></span>

### <a name="create-filter-in-organizational-level-vertical"></a><span data-ttu-id="e4a7f-128">組織レベルの垂直方向のフィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-128">Create filter in organizational level vertical:</span></span>

<span data-ttu-id="e4a7f-129">Microsoft search でフィルターを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-129">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="e4a7f-130">Microsoft 365 管理センターで、[ [業種](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-130">In the Microsoft 365 admin center, go to the [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) page.</span></span>
2. <span data-ttu-id="e4a7f-131">フィルターを作成する垂直線を作成または編集する</span><span class="sxs-lookup"><span data-stu-id="e4a7f-131">Create/Edit the vertical in which you want to create the filter</span></span>
3. <span data-ttu-id="e4a7f-132">ウィザードの [フィルター] ステップに移動します。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-132">Navigate to the 'Filters' step in the wizard</span></span>
4. <span data-ttu-id="e4a7f-133">[フィルターの追加] をクリックして、フィルターを追加した後に作業を開始すると、垂直方向の内容を確認して保存することができます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-133">Click on 'Add Filter' and get started After adding filters, you can review and save the vertical.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e4a7f-134">既知の制限</span><span class="sxs-lookup"><span data-stu-id="e4a7f-134">Known Limitations</span></span>

1. <span data-ttu-id="e4a7f-135">現時点では、フィルターの作成は文字列 & Date 型の管理プロパティに対してのみ行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4a7f-135">You can currently create filters only on String & Date type managed properties.</span></span>
2. <span data-ttu-id="e4a7f-136">階層フィルターを作成できない</span><span class="sxs-lookup"><span data-stu-id="e4a7f-136">You cannot create hierarchical filters</span></span>

## <a name="resources"></a><span data-ttu-id="e4a7f-137">リソース</span><span class="sxs-lookup"><span data-stu-id="e4a7f-137">Resources</span></span>

[<span data-ttu-id="e4a7f-138">検索結果ページをカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="e4a7f-138">Customize search result page</span></span>](customize-search-page.md)