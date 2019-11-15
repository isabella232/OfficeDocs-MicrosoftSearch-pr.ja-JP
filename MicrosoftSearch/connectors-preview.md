---
title: コネクタのプレビュー
ms.author: mounika.narayanan
author: monaray
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
ms.openlocfilehash: 3ac27bd1e859f9ffc825e5e77d96f0de56b13647
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626266"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="13857-103">Microsoft Graph コネクタのプレビュー</span><span class="sxs-lookup"><span data-stu-id="13857-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="13857-104">Microsoft Graph のコネクタ、インデックス Api、および検索 Api は現在プレビュー段階です。</span><span class="sxs-lookup"><span data-stu-id="13857-104">Microsoft Graph connectors, indexing APIs, and search APIs are currently in preview.</span></span> <span data-ttu-id="13857-105">コネクタ機能へのアクセスを取得するには、 <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">Microsoft Graph Connector preview のサインアップフォーム</a>を送信して、プレビュープログラムへの参加を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="13857-105">To gain access to connectors functionality, you must request to join the preview program by submitting the <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">Microsoft Graph Connectors Preview Sign up Form</a>.</span></span> <span data-ttu-id="13857-106">これは初期のプレビューであり、サービスレベルの保証はありません。</span><span class="sxs-lookup"><span data-stu-id="13857-106">This is an early preview, and there is no service level guarantee.</span></span> <span data-ttu-id="13857-107">お客様には、コネクタの機能を試してフィードバックを提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13857-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="13857-108">プレビュー期間中は、運用のためにコネクタを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="13857-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="13857-109">対象となるリリースのセットアップ</span><span class="sxs-lookup"><span data-stu-id="13857-109">Set up targeted release</span></span>
<span data-ttu-id="13857-110">コネクタを試行するには、組織内のすべてのユーザーに対して**対象となるリリース**オプションが設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="13857-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="13857-111">対象となるリリース要件は、選択した次のプレビュー環境に関係なく適用されます。</span><span class="sxs-lookup"><span data-stu-id="13857-111">The Targeted release requirement applies no matter which of the following preview environments you choose.</span></span>
<span data-ttu-id="13857-112">対象となるリリースオプションの詳細と設定方法については、「 <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">Office 365 で標準または対象指定リリースオプションを設定</a>する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="13857-112">To learn more about the Targeted release option and how to set it, see <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">Set up the Standard or Targeted release options in Office 365</a>.</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="13857-113">プレビュー環境を選択する</span><span class="sxs-lookup"><span data-stu-id="13857-113">Choose a preview environment</span></span> 
<span data-ttu-id="13857-114">コネクタ、インデックス Api、および検索 Api を試すには、次の2つの方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13857-114">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>
1. <span data-ttu-id="13857-115">**テナントをテスト**します。</span><span class="sxs-lookup"><span data-stu-id="13857-115">**Test tenant**.</span></span>  <span data-ttu-id="13857-116">テストテナントを使用して、Microsoft Graph コネクタのプレビューを試してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="13857-116">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>
2. <span data-ttu-id="13857-117">**サイトコレクションをテスト**します。</span><span class="sxs-lookup"><span data-stu-id="13857-117">**Test site collection**.</span></span> <span data-ttu-id="13857-118">テストテナントがない場合は、テストサイトコレクションを作成してコネクタ機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="13857-118">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="13857-119">組織内の他の場所にある検索ページに影響を及ぼさずに、コネクタからの結果を表示するには、そのサイトコレクションの検索機能のみをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="13857-119">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="13857-120">プレビューの制限事項</span><span class="sxs-lookup"><span data-stu-id="13857-120">Preview limitations</span></span>
<span data-ttu-id="13857-121">プレビューリリースには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="13857-121">The preview release has the following limitations:</span></span>
* <span data-ttu-id="13857-122">取り込みスループットは、1秒あたり約4アイテムに調整されます。</span><span class="sxs-lookup"><span data-stu-id="13857-122">Ingestion throughput is throttled at about four items per second.</span></span>
* <span data-ttu-id="13857-123">スキーマの更新はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="13857-123">There's no support for schema updates.</span></span> <span data-ttu-id="13857-124">接続設定を作成した後、スキーマを更新する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="13857-124">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="13857-125">接続を削除して再作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="13857-125">You can only delete and re-create the connection.</span></span>
* <span data-ttu-id="13857-126">インデックスが作成されたコンテンツは、カスタム縦の下にある検索結果ページにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="13857-126">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="13857-127">この制限は、ユーザー設定の種類のコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="13857-127">This restriction applies to content with custom types.</span></span>
* <span data-ttu-id="13857-128">一般的な使用を開始する前に、プレビュー期間中にセットアップした接続を削除して再作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="13857-128">Before general availability, any connection you set up during the preview period may need to be deleted and re-created.</span></span> <span data-ttu-id="13857-129">これらの接続は、製品の改善に加えられた変更に互換性がない場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="13857-129">Those connections won't work anymore if they are incompatible with changes made to improve the product.</span></span>
* <span data-ttu-id="13857-130">接続の制限。</span><span class="sxs-lookup"><span data-stu-id="13857-130">Connections limit.</span></span> <span data-ttu-id="13857-131">各テナントは最大10個の接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="13857-131">Each tenant can create up to 10 connections.</span></span>
