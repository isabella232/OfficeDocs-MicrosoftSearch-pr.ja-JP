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
description: Microsoft Search の Microsoft Graph コネクタプレビューに関する情報を確認します。
ms.openlocfilehash: 592e108fe0333e4faf8ff2e4618f9d5216847b8a
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367669"
---
# <a name="microsoft-graph-connectors-preview-release-and-features"></a><span data-ttu-id="0ef7b-103">Microsoft Graph コネクタのプレビューリリースおよび機能</span><span class="sxs-lookup"><span data-stu-id="0ef7b-103">Microsoft Graph connectors preview release and features</span></span>

<span data-ttu-id="0ef7b-104">Microsoft Graph のコネクタと Microsoft 検索 Api は、一般公開されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="0ef7b-104">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="0ef7b-105">最初のロールアウトは、対象となるリリース用に構成された顧客に対して行われます。</span><span class="sxs-lookup"><span data-stu-id="0ef7b-105">The initial rollout will be to customers configured for Targeted Release.</span></span> <span data-ttu-id="0ef7b-106">すべてのテナントに対する処理が完了すると、コネクタのインデックスクォータ使用率が請求される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0ef7b-106">Upon rollout completion to all tenants, index quota utilization from connectors content will become subject to billing.</span></span> <span data-ttu-id="0ef7b-107">詳細については [、「ライセンス要件と料金](licensing.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ef7b-107">See [Licensing requirements and pricing](licensing.md) for more information.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="0ef7b-108">対象となるリリースのセットアップ</span><span class="sxs-lookup"><span data-stu-id="0ef7b-108">Set up Targeted release</span></span>

<span data-ttu-id="0ef7b-109">ロールアウト中にテナントでグラフコネクタを使用する場合は、対象となるリリースにオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ef7b-109">If you want to use Graph connectors in your tenant during rollout, you must opt into Targeted release.</span></span> <span data-ttu-id="0ef7b-110">対象となるリリースオプションの詳細と設定方法については、「 [Office 365 で標準または対象指定リリースオプションを設定](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ef7b-110">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="preview-features"></a><span data-ttu-id="0ef7b-111">プレビュー機能</span><span class="sxs-lookup"><span data-stu-id="0ef7b-111">Preview features</span></span>

<span data-ttu-id="0ef7b-112">Microsoft Graph のコネクタと Microsoft 検索 Api は一般公開されるようになりましたが、いくつかの機能がプレビューのままになります。</span><span class="sxs-lookup"><span data-stu-id="0ef7b-112">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that will remain in preview.</span></span>

<span data-ttu-id="0ef7b-113">次に、プレビューのコネクタと機能のセットを示します。</span><span class="sxs-lookup"><span data-stu-id="0ef7b-113">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="0ef7b-114">Azure DevOps コネクタ</span><span class="sxs-lookup"><span data-stu-id="0ef7b-114">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="0ef7b-115">Salesforce コネクタ</span><span class="sxs-lookup"><span data-stu-id="0ef7b-115">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="0ef7b-116">ソース Acl を使用する検索権限を持つ[ServiceNow コネクタ](servicenow.md)</span><span class="sxs-lookup"><span data-stu-id="0ef7b-116">[ServiceNow connector](servicenow.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="0ef7b-117">検索結果クラスターを管理する</span><span class="sxs-lookup"><span data-stu-id="0ef7b-117">Manage result cluster</span></span>](result-cluster.md)