---
title: Microsoft Search 用の Microsoft Graph コネクタを管理する
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の Microsoft Graph コネクタを管理します。
ms.openlocfilehash: 5258f26a5c97be4ee9f90c7a8b2b9bb8fec447bc
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905932"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="68dfc-103">接続を監視する</span><span class="sxs-lookup"><span data-stu-id="68dfc-103">Monitor your connections</span></span>

<span data-ttu-id="68dfc-104">コネクタにアクセスして管理するには、テナントの検索管理者として指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68dfc-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="68dfc-105">テナント管理者に問い合わせて、検索管理者ロールのプロビジョニングを行います。</span><span class="sxs-lookup"><span data-stu-id="68dfc-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="68dfc-106">接続操作</span><span class="sxs-lookup"><span data-stu-id="68dfc-106">Connection Operations</span></span>

<span data-ttu-id="68dfc-107">Microsoft 365 [管理センターの](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) [ [コネクタ] タブに移動します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="68dfc-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="68dfc-108">コネクタの種類ごとに [、Microsoft 365 管理](https://admin.microsoft.com) センターは次の表に示す操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="68dfc-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="68dfc-109">操作</span><span class="sxs-lookup"><span data-stu-id="68dfc-109">Operation</span></span> | <span data-ttu-id="68dfc-110">Microsoft が構築したコネクタ</span><span class="sxs-lookup"><span data-stu-id="68dfc-110">Microsoft-built connector</span></span> | <span data-ttu-id="68dfc-111">パートナーまたはカスタムのコネクタ</span><span class="sxs-lookup"><span data-stu-id="68dfc-111">Partner or custom-built connector</span></span>
--- | --- | ---
<span data-ttu-id="68dfc-112">接続を追加する</span><span class="sxs-lookup"><span data-stu-id="68dfc-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="68dfc-113">[(「Microsoft が構築したコネクタを構成する」を参照)](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="68dfc-113">(See [Configure your Microsoft-built connector](configure-connector.md))</span></span> | :x: <span data-ttu-id="68dfc-114">(パートナーまたはカスタムビルドのコネクタ管理者 UX を参照)</span><span class="sxs-lookup"><span data-stu-id="68dfc-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="68dfc-115">接続を削除する</span><span class="sxs-lookup"><span data-stu-id="68dfc-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="68dfc-118">発行済み接続を編集する</span><span class="sxs-lookup"><span data-stu-id="68dfc-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="68dfc-119">名前</span><span class="sxs-lookup"><span data-stu-id="68dfc-119">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="68dfc-120">説明</span><span class="sxs-lookup"><span data-stu-id="68dfc-120">Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="68dfc-121">外部データ ソースの認証資格情報</span><span class="sxs-lookup"><span data-stu-id="68dfc-121">Authentication credentials for your external data source</span></span><br></br> :heavy_check_mark: <span data-ttu-id="68dfc-122">オンプレミス データ ソースのゲートウェイ資格情報</span><span class="sxs-lookup"><span data-stu-id="68dfc-122">Gateway credentials for your on-premises data source</span></span><br></br> :heavy_check_mark: <span data-ttu-id="68dfc-123">更新スケジュール</span><span class="sxs-lookup"><span data-stu-id="68dfc-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="68dfc-124">名前</span><span class="sxs-lookup"><span data-stu-id="68dfc-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="68dfc-125">説明</span><span class="sxs-lookup"><span data-stu-id="68dfc-125">Description</span></span>
<span data-ttu-id="68dfc-126">下書き接続を編集する</span><span class="sxs-lookup"><span data-stu-id="68dfc-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a><span data-ttu-id="68dfc-129">接続状態を監視する</span><span class="sxs-lookup"><span data-stu-id="68dfc-129">Monitor your connection status</span></span>

<span data-ttu-id="68dfc-130">接続を作成すると、処理されたアイテムの数が Microsoft Searchページの [コネクタ] タブ **に表示** されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="68dfc-131">最初のフル クロールが正常に完了すると、定期的な増分クロールの進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="68dfc-132">このページには、コネクタの毎日の操作に関する情報と、ログとエラー履歴の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="68dfc-133">各接続に対して、[状態] 列に **次の 4** つの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-133">Four states show up in the **Status** column against each connection:</span></span>

* <span data-ttu-id="68dfc-134">**同期中** です。</span><span class="sxs-lookup"><span data-stu-id="68dfc-134">**Syncing**.</span></span> <span data-ttu-id="68dfc-135">コネクタは、ソースからのデータをクロールして既存のアイテムのインデックスを作成し、更新を行います。</span><span class="sxs-lookup"><span data-stu-id="68dfc-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="68dfc-136">**有効**: 接続が有効で、アクティブなクロールが実行されません。</span><span class="sxs-lookup"><span data-stu-id="68dfc-136">**Enabled**: The connection is enabled, and there's no active crawl running against it.</span></span> <span data-ttu-id="68dfc-137">**前回の同期時刻** は、前回成功したクロールがいつ行ったかを示します。</span><span class="sxs-lookup"><span data-stu-id="68dfc-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="68dfc-138">接続は最後の同期時刻と同じ最新の値です。</span><span class="sxs-lookup"><span data-stu-id="68dfc-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="68dfc-139">**一時停止しました**。</span><span class="sxs-lookup"><span data-stu-id="68dfc-139">**Paused**.</span></span> <span data-ttu-id="68dfc-140">クロールは、一時停止オプションを使用して管理者によって一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="68dfc-141">次のクロールは、手動で再開された場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="68dfc-142">ただし、この接続からのデータは引き続き検索可能です。</span><span class="sxs-lookup"><span data-stu-id="68dfc-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="68dfc-143">**失敗**。</span><span class="sxs-lookup"><span data-stu-id="68dfc-143">**Failed**.</span></span> <span data-ttu-id="68dfc-144">接続に重大な障害が発生しました。</span><span class="sxs-lookup"><span data-stu-id="68dfc-144">The connection had a critical failure.</span></span> <span data-ttu-id="68dfc-145">このエラーには手動による介入が必要です。</span><span class="sxs-lookup"><span data-stu-id="68dfc-145">This error requires manual intervention.</span></span> <span data-ttu-id="68dfc-146">管理者は、表示されたエラー メッセージに基づいて適切なアクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="68dfc-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="68dfc-147">エラーが発生するまでインデックスが作成されたデータは検索可能です。</span><span class="sxs-lookup"><span data-stu-id="68dfc-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="68dfc-148">インデックス クォータの使用率を監視する</span><span class="sxs-lookup"><span data-stu-id="68dfc-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="68dfc-149">使用可能なインデックス クォータと使用量は、コネクタのランディング ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![インデックス クォータ使用率バー](media/quota_utilization.png)

>[!NOTE]
><span data-ttu-id="68dfc-151">プレビュー期間中に、Graph コネクタを試しているすべての組織に、すべての接続で最大 200 万アイテムの無料の固定クォータが提供されました。</span><span class="sxs-lookup"><span data-stu-id="68dfc-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="68dfc-152">Graph コネクタが一般公開される中、プレビューで Graph コネクタを使用している組織では、2021 年 2 月 1 日に無料クォータの有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-152">With Graph connectors being generally available, the free quota will expire on Feb 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="68dfc-153">「プレビュー」とラベル付けされた[](connectors-preview.md)Microsoft が作成した Graph コネクタは、組織の課金インデックス クォータの合計には含まれません。</span><span class="sxs-lookup"><span data-stu-id="68dfc-153">Microsoft-built Graph connectors labeled as ["Preview"](connectors-preview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="68dfc-154">ただし、組織で構成できる接続の最大数は 10 件、接続間でインデックスを作成できるアイテムの最大数は 700 万アイテムにカウントされます。各接続は 700,000 アイテムに制限されています。</span><span class="sxs-lookup"><span data-stu-id="68dfc-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="68dfc-155">クォータ使用率バーには、組織によるクォータの消費に基づいて、さまざまな状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="68dfc-156">状態</span><span class="sxs-lookup"><span data-stu-id="68dfc-156">State</span></span> | <span data-ttu-id="68dfc-157">クォータの使用量</span><span class="sxs-lookup"><span data-stu-id="68dfc-157">Quota consumption</span></span>
--- | ---
<span data-ttu-id="68dfc-158">標準</span><span class="sxs-lookup"><span data-stu-id="68dfc-158">Normal</span></span> | <span data-ttu-id="68dfc-159">1-69%</span><span class="sxs-lookup"><span data-stu-id="68dfc-159">1-69%</span></span>
<span data-ttu-id="68dfc-160">高い</span><span class="sxs-lookup"><span data-stu-id="68dfc-160">High</span></span> | <span data-ttu-id="68dfc-161">70-89%</span><span class="sxs-lookup"><span data-stu-id="68dfc-161">70-89%</span></span>
<span data-ttu-id="68dfc-162">重大</span><span class="sxs-lookup"><span data-stu-id="68dfc-162">Critical</span></span> | <span data-ttu-id="68dfc-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="68dfc-163">90%-99%</span></span>
<span data-ttu-id="68dfc-164">Full</span><span class="sxs-lookup"><span data-stu-id="68dfc-164">Full</span></span> | <span data-ttu-id="68dfc-165">100%</span><span class="sxs-lookup"><span data-stu-id="68dfc-165">100%</span></span>

<span data-ttu-id="68dfc-166">インデックスが作成されたアイテムの数も、接続ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="68dfc-167">各接続によってインデックスが作成されたアイテムの数は、組織で使用可能なクォータの合計に貢献します。</span><span class="sxs-lookup"><span data-stu-id="68dfc-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="68dfc-168">組織のインデックス クォータを超えると、すべてのアクティブな接続が影響を受け、それらの接続は制限を超 **えた状態で動作** します。</span><span class="sxs-lookup"><span data-stu-id="68dfc-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="68dfc-169">この状態では、アクティブな接続</span><span class="sxs-lookup"><span data-stu-id="68dfc-169">In this state, your active connections</span></span>  

* <span data-ttu-id="68dfc-170">新しいアイテムを追加できない。</span><span class="sxs-lookup"><span data-stu-id="68dfc-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="68dfc-171">既存のアイテムを更新または削除できます。</span><span class="sxs-lookup"><span data-stu-id="68dfc-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="68dfc-172">この問題を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68dfc-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="68dfc-173">ライセンス要件と価格で組織のインデックス クォータを [購入する方法について説明します](licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="68dfc-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="68dfc-174">取り込まれたコンテンツが多すぎる接続を特定し、インデックスを作成する項目が少なく、クォータを使用できる容量を作り出すまで更新します。</span><span class="sxs-lookup"><span data-stu-id="68dfc-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="68dfc-175">接続を更新するには、新しい取り込みフィルターを使用して削除して新しい接続を作成する必要があります。このフィルターを使用すると、アイテム数が少なめになります。</span><span class="sxs-lookup"><span data-stu-id="68dfc-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="68dfc-176">1 つ以上の接続を完全に削除する</span><span class="sxs-lookup"><span data-stu-id="68dfc-176">Permanently delete one or more connections</span></span>