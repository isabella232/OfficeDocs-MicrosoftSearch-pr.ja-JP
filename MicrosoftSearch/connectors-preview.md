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
ms.openlocfilehash: 4bcd8360957be69bc701e8b356cd222de32bfc5f
ms.sourcegitcommit: 64eea81f8c1db9ee955013462a7b51612fb7d0b7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604385"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="421f2-103">Microsoft Graph コネクタのプレビュー</span><span class="sxs-lookup"><span data-stu-id="421f2-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="421f2-104">Microsoft Graph のコネクタと Microsoft Search Api (クエリとインデックス) は現在プレビュー状態になっています。</span><span class="sxs-lookup"><span data-stu-id="421f2-104">Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status.</span></span> <span data-ttu-id="421f2-105">コネクタ機能へのアクセスを取得するには、テナントで対象のリリースオプションをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="421f2-105">To gain access to connectors functionality, you must turn on the Targeted release option in your tenant.</span></span> <span data-ttu-id="421f2-106">これは初期のプレビューであり、サービスレベルの保証はありません。</span><span class="sxs-lookup"><span data-stu-id="421f2-106">This is an early preview, and there's no service level guarantee.</span></span> <span data-ttu-id="421f2-107">お客様には、コネクタの機能を試してフィードバックを提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="421f2-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="421f2-108">プレビュー期間中は、運用のためにコネクタを使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="421f2-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="421f2-109">対象となるリリースのセットアップ</span><span class="sxs-lookup"><span data-stu-id="421f2-109">Set up Targeted release</span></span>

<span data-ttu-id="421f2-110">コネクタを試行するには、組織内のすべてのユーザーに対して**対象となるリリース**オプションが設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="421f2-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="421f2-111">対象となるリリースオプションの詳細と設定方法については、「 [Office 365 で標準または対象指定リリースオプションを設定](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="421f2-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="421f2-112">プレビュー環境を選択する</span><span class="sxs-lookup"><span data-stu-id="421f2-112">Choose a preview environment</span></span>

<span data-ttu-id="421f2-113">コネクタ、インデックス Api、および検索 Api を試すには、次の2つの方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="421f2-113">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>

1. <span data-ttu-id="421f2-114">**テナントをテスト**します。</span><span class="sxs-lookup"><span data-stu-id="421f2-114">**Test tenant**.</span></span>  <span data-ttu-id="421f2-115">テストテナントを使用して、Microsoft Graph コネクタのプレビューを試してみることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="421f2-115">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>

2. <span data-ttu-id="421f2-116">**サイトコレクションをテスト**します。</span><span class="sxs-lookup"><span data-stu-id="421f2-116">**Test site collection**.</span></span> <span data-ttu-id="421f2-117">テストテナントがない場合は、テストサイトコレクションを作成してコネクタ機能を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="421f2-117">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="421f2-118">組織内の他の場所にある検索ページに影響を及ぼさずに、コネクタからの結果を表示するには、そのサイトコレクションの検索機能のみをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="421f2-118">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="421f2-119">プレビューの制限事項</span><span class="sxs-lookup"><span data-stu-id="421f2-119">Preview limitations</span></span>

<span data-ttu-id="421f2-120">プレビューリリースには、次の制限があります。</span><span class="sxs-lookup"><span data-stu-id="421f2-120">The preview release has the following limitations:</span></span>

* <span data-ttu-id="421f2-121">取り込みスループットは、1秒あたり約4アイテムに調整されます。</span><span class="sxs-lookup"><span data-stu-id="421f2-121">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="421f2-122">スキーマの更新はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="421f2-122">There's no support for schema updates.</span></span> <span data-ttu-id="421f2-123">接続設定を作成した後、スキーマを更新する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="421f2-123">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="421f2-124">接続を削除して再作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="421f2-124">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="421f2-125">インデックスが作成されたコンテンツは、カスタム縦の下にある検索結果ページにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="421f2-125">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="421f2-126">この制限は、ユーザー設定の種類のコンテンツに適用されます。</span><span class="sxs-lookup"><span data-stu-id="421f2-126">This restriction applies to content with custom types.</span></span>

* <span data-ttu-id="421f2-127">プレビュー期間中にセットアップした接続は、削除して再作成する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="421f2-127">Any connection you set up during the preview period might need to be deleted and re-created.</span></span> <span data-ttu-id="421f2-128">これらの接続は、製品の改善に加えられた変更に互換性がない場合は機能しません。</span><span class="sxs-lookup"><span data-stu-id="421f2-128">Those connections won't work anymore if they're incompatible with changes made to improve the product.</span></span>

* <span data-ttu-id="421f2-129">接続制限があります。</span><span class="sxs-lookup"><span data-stu-id="421f2-129">There's a connections limit.</span></span> <span data-ttu-id="421f2-130">各テナントは最大10個の接続を作成できます。</span><span class="sxs-lookup"><span data-stu-id="421f2-130">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="421f2-131">ソースリポジトリのサイズ。</span><span class="sxs-lookup"><span data-stu-id="421f2-131">Source repository size.</span></span> <span data-ttu-id="421f2-132">テスト済み検索スケールの制限である場合は、20万アイテムのソースリポジトリがあるコネクタをプレビューすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="421f2-132">We recommend that you preview connectors with a source repository of about 200,000 items as this is our tested search scale limit.</span></span> <span data-ttu-id="421f2-133">検索のパフォーマンスの向上に取り組んでいますが、近い将来、より大きなリポジトリサイズのサポートが期待されています。</span><span class="sxs-lookup"><span data-stu-id="421f2-133">We are working on improving the performance of search, and we expect to support for larger repository sizes in the near future.</span></span>

* <span data-ttu-id="421f2-134">接続の編集サポートを利用できません。</span><span class="sxs-lookup"><span data-stu-id="421f2-134">Edit support for connection is not available.</span></span> <span data-ttu-id="421f2-135">接続が作成されたら、編集または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="421f2-135">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="421f2-136">詳細を変更する必要がある場合は、接続を削除して再作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="421f2-136">If you need to change any details, you must delete and recreate the connection.</span></span>

* <span data-ttu-id="421f2-137">コネクタコンテンツは、カスタムの業種でのみ検索できます。</span><span class="sxs-lookup"><span data-stu-id="421f2-137">Connector content can only be searched on custom verticals.</span></span>

* <span data-ttu-id="421f2-138">コネクタのコンテンツは、1つの接続でのみ、各カスタム縦に表示でき、結果の種類の作成が必要になります。</span><span class="sxs-lookup"><span data-stu-id="421f2-138">Connector content from only one connection can be displayed in each custom vertical and requires result type creation.</span></span>
