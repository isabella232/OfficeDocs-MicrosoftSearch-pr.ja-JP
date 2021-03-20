---
title: Microsoft Search の Microsoft Graph コネクタを管理する
ms.author: monaray
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の Microsoft Graph コネクタを管理します。
ms.openlocfilehash: 1c152f23e9b9d9982b957830d5f4bef0eef41347
ms.sourcegitcommit: 2f770de12b27546b18b2e86517d2c25522eb9022
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929589"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="40bc6-103">接続を監視する</span><span class="sxs-lookup"><span data-stu-id="40bc6-103">Monitor your connections</span></span>

<span data-ttu-id="40bc6-104">コネクタにアクセスして管理するには、テナントの検索管理者として指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="40bc6-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="40bc6-105">テナント管理者に問い合わせて、検索管理者の役割を準備します。</span><span class="sxs-lookup"><span data-stu-id="40bc6-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="40bc6-106">接続操作</span><span class="sxs-lookup"><span data-stu-id="40bc6-106">Connection Operations</span></span>

<span data-ttu-id="40bc6-107">Microsoft 365 [管理センターの](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) [[コネクタ] タブに移動します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="40bc6-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="40bc6-108">コネクタの種類ごとに [、Microsoft 365 管理](https://admin.microsoft.com) センターは次の表に示す操作をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="40bc6-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="40bc6-109">操作</span><span class="sxs-lookup"><span data-stu-id="40bc6-109">Operation</span></span> | <span data-ttu-id="40bc6-110">Microsoft 提供の Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="40bc6-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="40bc6-111">パートナーコネクタまたはグラフ コネクタ</span><span class="sxs-lookup"><span data-stu-id="40bc6-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="40bc6-112">接続の追加</span><span class="sxs-lookup"><span data-stu-id="40bc6-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="40bc6-113">(「セットアップの概要[」を参照)](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="40bc6-113">(See [Setup overview](configure-connector.md))</span></span> | :x: <span data-ttu-id="40bc6-114">(パートナーまたはカスタムビルドのコネクタ管理者 UX を参照)</span><span class="sxs-lookup"><span data-stu-id="40bc6-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="40bc6-115">接続を削除する</span><span class="sxs-lookup"><span data-stu-id="40bc6-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="40bc6-118">発行済み接続の編集</span><span class="sxs-lookup"><span data-stu-id="40bc6-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="40bc6-119">名前と説明</span><span class="sxs-lookup"><span data-stu-id="40bc6-119">Name and Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="40bc6-120">接続設定</span><span class="sxs-lookup"><span data-stu-id="40bc6-120">Connection settings</span></span><br></br> :heavy_check_mark: <span data-ttu-id="40bc6-121">プロパティ ラベル</span><span class="sxs-lookup"><span data-stu-id="40bc6-121">Property labels</span></span><br></br> :heavy_check_mark: <span data-ttu-id="40bc6-122">スキーマ</span><span class="sxs-lookup"><span data-stu-id="40bc6-122">Schema</span></span><br></br> :heavy_check_mark: <span data-ttu-id="40bc6-123">更新スケジュール</span><span class="sxs-lookup"><span data-stu-id="40bc6-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="40bc6-124">名前</span><span class="sxs-lookup"><span data-stu-id="40bc6-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="40bc6-125">説明</span><span class="sxs-lookup"><span data-stu-id="40bc6-125">Description</span></span>
<span data-ttu-id="40bc6-126">下書き接続の編集</span><span class="sxs-lookup"><span data-stu-id="40bc6-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="40bc6-129">接続状態を監視する</span><span class="sxs-lookup"><span data-stu-id="40bc6-129">Monitor your connection state</span></span>

<span data-ttu-id="40bc6-130">接続を作成すると、Microsoft Search ページの [コネクタ]タブに処理されたアイテムの数 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="40bc6-131">最初のフル クロールが正常に完了すると、定期的な増分クロールの進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="40bc6-132">このページでは、コネクタの毎日の操作とログとエラー履歴の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="40bc6-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="40bc6-133">4 つの状態が各接続に対 **して [状態** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-133">Four states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="40bc6-134">**同期します**。</span><span class="sxs-lookup"><span data-stu-id="40bc6-134">**Syncing**.</span></span> <span data-ttu-id="40bc6-135">コネクタは、ソースからのデータをクロールして、既存のアイテムにインデックスを付け、更新を行います。</span><span class="sxs-lookup"><span data-stu-id="40bc6-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="40bc6-136">**準備** 完了: 接続の準備が完了し、アクティブなクロールが実行されている状態はありません。</span><span class="sxs-lookup"><span data-stu-id="40bc6-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="40bc6-137">**前回の同期時間は** 、最後に成功したクロールが発生した時期を示します。</span><span class="sxs-lookup"><span data-stu-id="40bc6-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="40bc6-138">接続は、最後の同期時間と同じ新しい値です。</span><span class="sxs-lookup"><span data-stu-id="40bc6-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="40bc6-139">**一時停止しました**。</span><span class="sxs-lookup"><span data-stu-id="40bc6-139">**Paused**.</span></span> <span data-ttu-id="40bc6-140">クロールは、一時停止オプションを使用して管理者によって一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="40bc6-141">次のクロールは、手動で再開された場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="40bc6-142">ただし、この接続のデータは引き続き検索可能です。</span><span class="sxs-lookup"><span data-stu-id="40bc6-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="40bc6-143">**失敗**。</span><span class="sxs-lookup"><span data-stu-id="40bc6-143">**Failed**.</span></span> <span data-ttu-id="40bc6-144">接続に重大な障害が発生しました。</span><span class="sxs-lookup"><span data-stu-id="40bc6-144">The connection had a critical failure.</span></span> <span data-ttu-id="40bc6-145">このエラーには、手動による介入が必要です。</span><span class="sxs-lookup"><span data-stu-id="40bc6-145">This error requires manual intervention.</span></span> <span data-ttu-id="40bc6-146">管理者は、表示されるエラー メッセージに基づいて適切なアクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40bc6-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="40bc6-147">エラーが発生するまでインデックスが作成されたデータは検索可能です。</span><span class="sxs-lookup"><span data-stu-id="40bc6-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="40bc6-148">インデックス クォータの使用率を監視する</span><span class="sxs-lookup"><span data-stu-id="40bc6-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="40bc6-149">使用可能なインデックスクォータと使用量は、コネクタのランディング ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![インデックス クォータ使用率バー](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="40bc6-151">プレビュー期間中、Graph コネクタを試しているすべての組織に、すべての接続で最大 200 万アイテムの無料の固定クォータが提供されました。</span><span class="sxs-lookup"><span data-stu-id="40bc6-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="40bc6-152">Graph コネクタが一般公開されている場合、プレビューで Graph コネクタを使用している組織では、2021 年 4 月 1 日に無料のクォータが期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="40bc6-152">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="40bc6-153">Microsoft が作成した ["Preview"](connectors-preview.md) というラベルのグラフ コネクタは、組織の合計課金インデックス クォータには含まれません。</span><span class="sxs-lookup"><span data-stu-id="40bc6-153">Microsoft-built Graph connectors labeled as ["Preview"](connectors-preview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="40bc6-154">ただし、組織に対して構成できる最大接続数 10 と、組織が接続間でインデックスを作成できる最大 700 万アイテムの数にカウントされます。各接続は 700,000 アイテムに制限されます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="40bc6-155">クォータ使用率バーは、組織によるクォータの消費に基づいてさまざまな状態を示します。</span><span class="sxs-lookup"><span data-stu-id="40bc6-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="40bc6-156">状態</span><span class="sxs-lookup"><span data-stu-id="40bc6-156">State</span></span> | <span data-ttu-id="40bc6-157">クォータ使用率レベル</span><span class="sxs-lookup"><span data-stu-id="40bc6-157">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="40bc6-158">標準</span><span class="sxs-lookup"><span data-stu-id="40bc6-158">Normal</span></span> | <span data-ttu-id="40bc6-159">0-79%</span><span class="sxs-lookup"><span data-stu-id="40bc6-159">0-79%</span></span>
<span data-ttu-id="40bc6-160">高い</span><span class="sxs-lookup"><span data-stu-id="40bc6-160">High</span></span> | <span data-ttu-id="40bc6-161">80-89%</span><span class="sxs-lookup"><span data-stu-id="40bc6-161">80-89%</span></span>
<span data-ttu-id="40bc6-162">重大</span><span class="sxs-lookup"><span data-stu-id="40bc6-162">Critical</span></span> | <span data-ttu-id="40bc6-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="40bc6-163">90%-99%</span></span>
<span data-ttu-id="40bc6-164">Full</span><span class="sxs-lookup"><span data-stu-id="40bc6-164">Full</span></span> | <span data-ttu-id="40bc6-165">100%</span><span class="sxs-lookup"><span data-stu-id="40bc6-165">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="40bc6-166">インデックスが作成されたアイテムの数も、接続ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="40bc6-167">各接続によってインデックス付けされたアイテムの数は、組織で使用可能な合計クォータに貢献します。</span><span class="sxs-lookup"><span data-stu-id="40bc6-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="40bc6-168">組織のインデックス クォータを超えると、すべてのアクティブな接続が影響を受け、それらの接続は制限を超 **えた状態で動作** します。</span><span class="sxs-lookup"><span data-stu-id="40bc6-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="40bc6-169">この状態では、アクティブな接続</span><span class="sxs-lookup"><span data-stu-id="40bc6-169">In this state, your active connections</span></span>  

* <span data-ttu-id="40bc6-170">新しいアイテムを追加できない。</span><span class="sxs-lookup"><span data-stu-id="40bc6-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="40bc6-171">既存のアイテムを更新または削除できます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="40bc6-172">これを修正するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="40bc6-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="40bc6-173">組織のインデックス クォータを購入する方法については、「ライセンス要件と価格」 [を参照してください](licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="40bc6-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="40bc6-174">コンテンツが取り込み過ぎた接続を特定し、それらを更新して、割り当て量を設定するためにインデックスを作成する項目が少なすぎます。</span><span class="sxs-lookup"><span data-stu-id="40bc6-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="40bc6-175">接続を更新するには、削除して、少ないアイテムをもたらす新しい取り込みフィルターを使用して新しい接続を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40bc6-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="40bc6-176">1 つ以上の接続を完全に削除する</span><span class="sxs-lookup"><span data-stu-id="40bc6-176">Permanently delete one or more connections</span></span>
