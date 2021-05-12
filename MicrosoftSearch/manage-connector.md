---
title: Microsoft 検索Graphコネクタを管理する
ms.author: mecampos
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
description: Microsoft 検索用の microsoft Graphコネクタを管理します。
ms.openlocfilehash: 685b501f3afe25d75c13a1fe6cc2c1b5db8a3511
ms.sourcegitcommit: e5d695c40b68c2f1fa082fa9de20b9aa6d5b8050
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52325170"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="088a3-103">接続を監視する</span><span class="sxs-lookup"><span data-stu-id="088a3-103">Monitor your connections</span></span>

<span data-ttu-id="088a3-104">コネクタにアクセスして管理するには、テナントの検索管理者として指定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="088a3-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="088a3-105">テナント管理者に問い合わせて、検索管理者の役割を準備します。</span><span class="sxs-lookup"><span data-stu-id="088a3-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="088a3-106">接続操作</span><span class="sxs-lookup"><span data-stu-id="088a3-106">Connection Operations</span></span>

<span data-ttu-id="088a3-107">管理センターの[[コネクタ]](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) [タブMicrosoft 365移動します](https://admin.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="088a3-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="088a3-108">コネクタの種類ごとに、Microsoft 365[管理センターは](https://admin.microsoft.com)、次の表に示す操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="088a3-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="088a3-109">Operation</span><span class="sxs-lookup"><span data-stu-id="088a3-109">Operation</span></span> | <span data-ttu-id="088a3-110">Microsoft 提供の Graph コネクタ</span><span class="sxs-lookup"><span data-stu-id="088a3-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="088a3-111">パートナーまたはGraphコネクタ</span><span class="sxs-lookup"><span data-stu-id="088a3-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="088a3-112">接続の追加</span><span class="sxs-lookup"><span data-stu-id="088a3-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="088a3-113">(「セットアップの概要[」を参照)](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="088a3-113">(See [Setup overview](configure-connector.md))</span></span> | :x: <span data-ttu-id="088a3-114">(パートナーまたはカスタムビルドのコネクタ管理者 UX を参照)</span><span class="sxs-lookup"><span data-stu-id="088a3-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="088a3-115">接続を削除する</span><span class="sxs-lookup"><span data-stu-id="088a3-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="088a3-118">発行済み接続の編集</span><span class="sxs-lookup"><span data-stu-id="088a3-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="088a3-119">名前と説明</span><span class="sxs-lookup"><span data-stu-id="088a3-119">Name and Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="088a3-120">接続設定</span><span class="sxs-lookup"><span data-stu-id="088a3-120">Connection settings</span></span><br></br> :heavy_check_mark: <span data-ttu-id="088a3-121">プロパティ ラベル</span><span class="sxs-lookup"><span data-stu-id="088a3-121">Property labels</span></span><br></br> :heavy_check_mark: <span data-ttu-id="088a3-122">スキーマ</span><span class="sxs-lookup"><span data-stu-id="088a3-122">Schema</span></span><br></br> :heavy_check_mark: <span data-ttu-id="088a3-123">更新スケジュール</span><span class="sxs-lookup"><span data-stu-id="088a3-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="088a3-124">名前</span><span class="sxs-lookup"><span data-stu-id="088a3-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="088a3-125">説明</span><span class="sxs-lookup"><span data-stu-id="088a3-125">Description</span></span>
<span data-ttu-id="088a3-126">下書き接続の編集</span><span class="sxs-lookup"><span data-stu-id="088a3-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="088a3-129">接続状態を監視する</span><span class="sxs-lookup"><span data-stu-id="088a3-129">Monitor your connection state</span></span>

<span data-ttu-id="088a3-130">接続を作成すると、Microsoft Search ページの [コネクタ]タブに処理されたアイテムの数 **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="088a3-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="088a3-131">最初のフル クロールが正常に完了すると、定期的な増分クロールの進行状況が表示されます。</span><span class="sxs-lookup"><span data-stu-id="088a3-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="088a3-132">このページでは、コネクタの毎日の操作とログとエラー履歴の概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="088a3-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="088a3-133">5 つの状態が各接続 **に対して [状態** ] 列に表示されます。</span><span class="sxs-lookup"><span data-stu-id="088a3-133">Five states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="088a3-134">**同期します**。</span><span class="sxs-lookup"><span data-stu-id="088a3-134">**Syncing**.</span></span> <span data-ttu-id="088a3-135">コネクタは、ソースからのデータをクロールして、既存のアイテムにインデックスを付け、更新を行います。</span><span class="sxs-lookup"><span data-stu-id="088a3-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="088a3-136">**準備** 完了: 接続の準備が完了し、アクティブなクロールが実行されている状態はありません。</span><span class="sxs-lookup"><span data-stu-id="088a3-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="088a3-137">**前回の同期時間は** 、最後に成功したクロールが発生した時期を示します。</span><span class="sxs-lookup"><span data-stu-id="088a3-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="088a3-138">接続は、最後の同期時間と同じ新しい値です。</span><span class="sxs-lookup"><span data-stu-id="088a3-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="088a3-139">**一時停止しました**。</span><span class="sxs-lookup"><span data-stu-id="088a3-139">**Paused**.</span></span> <span data-ttu-id="088a3-140">クロールは、一時停止オプションを使用して管理者によって一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="088a3-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="088a3-141">次のクロールは、手動で再開された場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="088a3-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="088a3-142">ただし、この接続のデータは引き続き検索可能です。</span><span class="sxs-lookup"><span data-stu-id="088a3-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="088a3-143">**失敗**。</span><span class="sxs-lookup"><span data-stu-id="088a3-143">**Failed**.</span></span> <span data-ttu-id="088a3-144">接続に重大な障害が発生しました。</span><span class="sxs-lookup"><span data-stu-id="088a3-144">The connection had a critical failure.</span></span> <span data-ttu-id="088a3-145">このエラーには、手動による介入が必要です。</span><span class="sxs-lookup"><span data-stu-id="088a3-145">This error requires manual intervention.</span></span> <span data-ttu-id="088a3-146">管理者は、表示されるエラー メッセージに基づいて適切なアクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="088a3-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="088a3-147">エラーが発生するまでインデックスが作成されたデータは検索可能です。</span><span class="sxs-lookup"><span data-stu-id="088a3-147">Data that was indexed until the error occurred is searchable.</span></span>

* <span data-ttu-id="088a3-148">**Delete Failed**.</span><span class="sxs-lookup"><span data-stu-id="088a3-148">**Delete Failed**.</span></span> <span data-ttu-id="088a3-149">接続の削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="088a3-149">The deletion of connection failed.</span></span> <span data-ttu-id="088a3-150">エラーの理由によっては、データに引き続きインデックスが作成される場合があります。アイテム クォータは引き続き使用され、接続に対してクロールが実行される場合があります。</span><span class="sxs-lookup"><span data-stu-id="088a3-150">Depending upon the failure reason, the data might still be indexed, item quota may still be consumed and crawls might still run for the connection.</span></span> <span data-ttu-id="088a3-151">この状態でもう一度接続を削除してみてください。</span><span class="sxs-lookup"><span data-stu-id="088a3-151">It is recommended to try deleting the connection again in this state.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="088a3-152">インデックス クォータの使用率を監視する</span><span class="sxs-lookup"><span data-stu-id="088a3-152">Monitor your index quota utilization</span></span>

<span data-ttu-id="088a3-153">使用可能なインデックスクォータと使用量は、コネクタのランディング ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="088a3-153">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![インデックス クォータ使用率バー](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="088a3-155">プレビュー期間中、すべての組織がコネクタを試Graph、すべての接続で最大 200 万アイテムの無料の固定クォータが提供されました。</span><span class="sxs-lookup"><span data-stu-id="088a3-155">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="088a3-156">Graphコネクタが一般に利用可能になると、プレビューで Graph コネクタを使用している組織の無料クォータは 2021 年 4 月 1 日に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="088a3-156">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="088a3-157">Microsoft が[Graph"Preview"](./connectors-overview.md)というラベルのコネクタは、組織の合計課金インデックス クォータに含まれません。</span><span class="sxs-lookup"><span data-stu-id="088a3-157">Microsoft-built Graph connectors labeled as ["Preview"](./connectors-overview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="088a3-158">ただし、組織に対して構成できる最大接続数 10 と、組織が接続間でインデックスを作成できる最大 700 万アイテムの数にカウントされます。各接続は 700,000 アイテムに制限されます。</span><span class="sxs-lookup"><span data-stu-id="088a3-158">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="088a3-159">クォータ使用率バーは、組織によるクォータの消費に基づいてさまざまな状態を示します。</span><span class="sxs-lookup"><span data-stu-id="088a3-159">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="088a3-160">状態</span><span class="sxs-lookup"><span data-stu-id="088a3-160">State</span></span> | <span data-ttu-id="088a3-161">クォータ使用率レベル</span><span class="sxs-lookup"><span data-stu-id="088a3-161">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="088a3-162">標準</span><span class="sxs-lookup"><span data-stu-id="088a3-162">Normal</span></span> | <span data-ttu-id="088a3-163">0-79%</span><span class="sxs-lookup"><span data-stu-id="088a3-163">0-79%</span></span>
<span data-ttu-id="088a3-164">高い</span><span class="sxs-lookup"><span data-stu-id="088a3-164">High</span></span> | <span data-ttu-id="088a3-165">80-89%</span><span class="sxs-lookup"><span data-stu-id="088a3-165">80-89%</span></span>
<span data-ttu-id="088a3-166">重大</span><span class="sxs-lookup"><span data-stu-id="088a3-166">Critical</span></span> | <span data-ttu-id="088a3-167">90%-99%</span><span class="sxs-lookup"><span data-stu-id="088a3-167">90%-99%</span></span>
<span data-ttu-id="088a3-168">Full</span><span class="sxs-lookup"><span data-stu-id="088a3-168">Full</span></span> | <span data-ttu-id="088a3-169">100%</span><span class="sxs-lookup"><span data-stu-id="088a3-169">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="088a3-170">インデックスが作成されたアイテムの数も、接続ごとに表示されます。</span><span class="sxs-lookup"><span data-stu-id="088a3-170">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="088a3-171">各接続によってインデックス付けされたアイテムの数は、組織で使用可能な合計クォータに貢献します。</span><span class="sxs-lookup"><span data-stu-id="088a3-171">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="088a3-172">組織のインデックス クォータを超えると、すべてのアクティブな接続が影響を受け、それらの接続は制限を超 **えた状態で動作** します。</span><span class="sxs-lookup"><span data-stu-id="088a3-172">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="088a3-173">この状態では、アクティブな接続</span><span class="sxs-lookup"><span data-stu-id="088a3-173">In this state, your active connections</span></span>  

* <span data-ttu-id="088a3-174">新しいアイテムを追加できない。</span><span class="sxs-lookup"><span data-stu-id="088a3-174">Will not be able to add new items.</span></span>

* <span data-ttu-id="088a3-175">既存のアイテムを更新または削除できます。</span><span class="sxs-lookup"><span data-stu-id="088a3-175">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="088a3-176">これを修正するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="088a3-176">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="088a3-177">組織のインデックス クォータを購入する方法については、「ライセンス要件と価格」 [を参照してください](licensing.md)。</span><span class="sxs-lookup"><span data-stu-id="088a3-177">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="088a3-178">コンテンツが取り込み過ぎた接続を特定し、それらを更新して、割り当て量を設定するためにインデックスを作成する項目が少なすぎます。</span><span class="sxs-lookup"><span data-stu-id="088a3-178">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="088a3-179">接続を更新するには、削除して、少ないアイテムをもたらす新しい取り込みフィルターを使用して新しい接続を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="088a3-179">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="088a3-180">1 つ以上の接続を完全に削除する</span><span class="sxs-lookup"><span data-stu-id="088a3-180">Permanently delete one or more connections</span></span>