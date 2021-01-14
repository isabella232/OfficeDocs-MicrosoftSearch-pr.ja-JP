---
title: コネクタのプレビュー
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の Microsoft Graph Connectors プレビューについて説明します。
ms.openlocfilehash: 47f7e1e417222c948f2916c70626278f9fe5b44a
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847512"
---
# <a name="microsoft-graph-connectors-preview-release-and-features"></a><span data-ttu-id="a21ef-103">Microsoft Graph コネクタのプレビュー リリースと機能</span><span class="sxs-lookup"><span data-stu-id="a21ef-103">Microsoft Graph connectors preview release and features</span></span>

<span data-ttu-id="a21ef-104">Microsoft Graph コネクタと Microsoft Search API が一般提供されます。</span><span class="sxs-lookup"><span data-stu-id="a21ef-104">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="a21ef-105">最初のロールアウトは、対象指定リリース用に構成されたユーザーに対して行います。</span><span class="sxs-lookup"><span data-stu-id="a21ef-105">The initial rollout will be to customers configured for Targeted Release.</span></span> <span data-ttu-id="a21ef-106">このロールアウトは、2021 年 2 月の終わりまで行います。</span><span class="sxs-lookup"><span data-stu-id="a21ef-106">This rollout will go on until the end of February 2021.</span></span> <span data-ttu-id="a21ef-107">すべてのテナントへのロールアウトが完了すると、コネクタ コンテンツからのインデックス クォータ使用率は課金の対象になります。</span><span class="sxs-lookup"><span data-stu-id="a21ef-107">Upon rollout completion to all tenants, index quota utilization from connectors content will become subject to billing.</span></span> <span data-ttu-id="a21ef-108">詳細 [については、「ライセンス要件と価格」](licensing.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21ef-108">See [Licensing requirements and pricing](licensing.md) for more information.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="a21ef-109">対象指定リリースのセットアップ</span><span class="sxs-lookup"><span data-stu-id="a21ef-109">Set up Targeted release</span></span>

<span data-ttu-id="a21ef-110">ロールアウト中にテナントで Graph コネクタを使用する場合は、対象指定 **リリース** にオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a21ef-110">If you want to use Graph connectors in your tenant during rollout, you **must** opt into Targeted release.</span></span> <span data-ttu-id="a21ef-111">対象指定リリース オプションと設定方法の詳細については、「Office [365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)で標準または対象指定リリース オプションを設定する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a21ef-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

## <a name="preview-features"></a><span data-ttu-id="a21ef-112">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="a21ef-112">Preview features</span></span>

<span data-ttu-id="a21ef-113">Microsoft Graph コネクタと Microsoft Search API が一般提供される現在ではありますが、プレビューのままのいくつかの機能があります。</span><span class="sxs-lookup"><span data-stu-id="a21ef-113">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that will remain in preview.</span></span>

<span data-ttu-id="a21ef-114">プレビューのコネクタと機能のセットは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a21ef-114">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="a21ef-115">Azure DevOps コネクタ</span><span class="sxs-lookup"><span data-stu-id="a21ef-115">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="a21ef-116">Salesforce コネクタ</span><span class="sxs-lookup"><span data-stu-id="a21ef-116">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="a21ef-117">[ソース ACL を](servicenow-connector.md) 使用する検索アクセス許可を持つ ServiceNow コネクタ</span><span class="sxs-lookup"><span data-stu-id="a21ef-117">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="a21ef-118">結果のクラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="a21ef-118">Manage result cluster</span></span>](result-cluster.md)