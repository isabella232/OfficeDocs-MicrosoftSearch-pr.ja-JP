---
title: カスタム フィルターを管理する
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
description: カスタム フィルターを管理する
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790336"
---
# <a name="manage-custom-filters"></a><span data-ttu-id="edaea-103">カスタム フィルターを管理する</span><span class="sxs-lookup"><span data-stu-id="edaea-103">Manage custom filters</span></span>

<span data-ttu-id="edaea-104">フィルターを使用して、Microsoft Search のエクスペリエンスをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="edaea-104">You can use filters to customize the Microsoft Search experience.</span></span> <span data-ttu-id="edaea-105">フィルターを使用すると、ユーザーは検索クエリから一連の結果をすばやく絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="edaea-105">Filters let users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="edaea-106">カスタム フィルターは、接続プロパティに基づいて垂直方向の内部に作成できます。</span><span class="sxs-lookup"><span data-stu-id="edaea-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="edaea-107">たとえば、垂直方向の内部に **ServiceNow** 接続の Published On フィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="edaea-107">For example, you can create a **Published On** filter for ServiceNow connection inside a vertical.</span></span>

## <a name="create-a-filter-in-an-organizational-level-vertical"></a><span data-ttu-id="edaea-108">組織レベルのバーティカルでフィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="edaea-108">Create a filter in an organizational level vertical</span></span>

<span data-ttu-id="edaea-109">Microsoft Search でフィルターを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="edaea-109">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="edaea-110">Microsoft 365 管理センターで、[縦] に [移動します](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)。</span><span class="sxs-lookup"><span data-stu-id="edaea-110">In the Microsoft 365 admin center, go to [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="edaea-111">フィルターを作成する垂直方向の作成/編集</span><span class="sxs-lookup"><span data-stu-id="edaea-111">Create/Edit the vertical in which you want to create the filter</span></span>
1. <span data-ttu-id="edaea-112">ウィザードの [フィルター] ステップに移動します。</span><span class="sxs-lookup"><span data-stu-id="edaea-112">Navigate to the 'Filters' step in the wizard</span></span>
1. <span data-ttu-id="edaea-113">[フィルターの追加] をクリックして開始する</span><span class="sxs-lookup"><span data-stu-id="edaea-113">Click on 'Add Filter' and get started</span></span>
1. <span data-ttu-id="edaea-114">フィルターを追加した後、垂直を確認して保存できます。</span><span class="sxs-lookup"><span data-stu-id="edaea-114">After adding filters, you can review and save the vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="edaea-115">考慮事項</span><span class="sxs-lookup"><span data-stu-id="edaea-115">Things to consider</span></span>

1. <span data-ttu-id="edaea-116">追加のフィルター機能は、接続コンテンツに存在します。</span><span class="sxs-lookup"><span data-stu-id="edaea-116">Additional filter capabilities exist on connection content.</span></span>

    - <span data-ttu-id="edaea-117">コネクタ ソース プロパティのエイリアスに対するフィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="edaea-117">You can also create filter on an alias to connector source properties</span></span>
    - <span data-ttu-id="edaea-118">垂直に複数の接続がある場合は、これらの接続間で共通のフィルタを作成できます。</span><span class="sxs-lookup"><span data-stu-id="edaea-118">If a vertical has multiple connections, you can create a common filter across these connections.</span></span> <span data-ttu-id="edaea-119">これは、異なる接続間でソース プロパティをエイリアスする共通エイリアスにフィルターを作成することで実行できます。</span><span class="sxs-lookup"><span data-stu-id="edaea-119">This can be done by creating the filter on an common alias which aliases source properties across across the different connections.</span></span> <span data-ttu-id="edaea-120">たとえば、次のようにエイリアスを作成することで、ServiceNow 接続と Jira 接続に対して **作成者** フィルターを作成できます。</span><span class="sxs-lookup"><span data-stu-id="edaea-120">For example you can create an **Author** filter across a ServiceNow and a Jira connection by creating aliases as follows:</span></span>

    | <span data-ttu-id="edaea-121">Connection</span><span class="sxs-lookup"><span data-stu-id="edaea-121">Connection</span></span> | <span data-ttu-id="edaea-122">プロパティ</span><span class="sxs-lookup"><span data-stu-id="edaea-122">Property</span></span> | <span data-ttu-id="edaea-123">エイリアス</span><span class="sxs-lookup"><span data-stu-id="edaea-123">Alias</span></span> |
    | --- | --- | --- |
    | <span data-ttu-id="edaea-124">今すぐサービス</span><span class="sxs-lookup"><span data-stu-id="edaea-124">Service Now</span></span> | <span data-ttu-id="edaea-125">所有者</span><span class="sxs-lookup"><span data-stu-id="edaea-125">Owner</span></span> | <span data-ttu-id="edaea-126">設定元</span><span class="sxs-lookup"><span data-stu-id="edaea-126">Author</span></span> |
    | <span data-ttu-id="edaea-127">ジラ</span><span class="sxs-lookup"><span data-stu-id="edaea-127">Jira</span></span> | <span data-ttu-id="edaea-128">発行者</span><span class="sxs-lookup"><span data-stu-id="edaea-128">Publisher</span></span> | <span data-ttu-id="edaea-129">設定元</span><span class="sxs-lookup"><span data-stu-id="edaea-129">Author</span></span> |

1. <span data-ttu-id="edaea-130">フィルターは、垂直の範囲内に存在します。</span><span class="sxs-lookup"><span data-stu-id="edaea-130">Filters exist within the scope of a vertical.</span></span>

    - <span data-ttu-id="edaea-131">フィルターが組織レベルの垂直方向に作成された場合、フィルターは組織レベルでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="edaea-131">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
    - <span data-ttu-id="edaea-132">サイト レベルの垂直方向にフィルターを作成した場合、フィルターはサイト レベルでのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="edaea-132">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="edaea-133">既知の制限</span><span class="sxs-lookup"><span data-stu-id="edaea-133">Known Limitations</span></span>

1. <span data-ttu-id="edaea-134">現在、フィルターは、日付型の管理&文字列でのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="edaea-134">You can currently create filters only on string & date type managed properties.</span></span>
1. <span data-ttu-id="edaea-135">階層フィルターは作成できません。</span><span class="sxs-lookup"><span data-stu-id="edaea-135">You cannot create hierarchical filters.</span></span>

## <a name="resources"></a><span data-ttu-id="edaea-136">リソース</span><span class="sxs-lookup"><span data-stu-id="edaea-136">Resources</span></span>

[<span data-ttu-id="edaea-137">業界および結果の種類を管理する</span><span class="sxs-lookup"><span data-stu-id="edaea-137">Manage verticals and result types</span></span>](customize-search-page.md)
