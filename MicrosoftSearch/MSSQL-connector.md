---
title: Microsoft Search の microsoft SQL connector
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の Microsoft SQL コネクタをセットアップします。
ms.openlocfilehash: a073a6d3f226e5f8b0ea297494a8889f1f50bab1
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626758"
---
# <a name="microsoft-sql-server-connector"></a><span data-ttu-id="ceadd-103">Microsoft SQL server コネクタ</span><span class="sxs-lookup"><span data-stu-id="ceadd-103">Microsoft SQL server connector</span></span>

<span data-ttu-id="ceadd-104">Microsoft SQL server コネクタを使用すると、組織は社内の SQL Server データベースからデータを検出し、インデックスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-104">With a Microsoft SQL server connector, your organization can discover and index data from an on-premises SQL Server database.</span></span> <span data-ttu-id="ceadd-105">コネクタは、指定されたコンテンツを Microsoft Search にインデックス付けします。</span><span class="sxs-lookup"><span data-stu-id="ceadd-105">The connector indexes specified content into Microsoft Search.</span></span> <span data-ttu-id="ceadd-106">ソースデータのインデックスを最新の状態に保つために、フルクロールと増分クロールを定期的に行います。</span><span class="sxs-lookup"><span data-stu-id="ceadd-106">To keep the index up to date with source data, it supports periodic full and incremental crawls.</span></span> <span data-ttu-id="ceadd-107">SQL Server コネクタを使用すると、特定のユーザーに対する検索結果へのアクセスを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-107">With the SQL Server connector, you can also restrict access to search results for certain users.</span></span>

<span data-ttu-id="ceadd-108">この記事は、Microsoft 365 管理者または Microsoft SQL server コネクタを構成、実行、および監視するユーザーを対象としています。</span><span class="sxs-lookup"><span data-stu-id="ceadd-108">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a Microsoft SQL server connector.</span></span> <span data-ttu-id="ceadd-109">コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-109">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-a-data-gateway"></a><span data-ttu-id="ceadd-110">Data gateway をインストールする</span><span class="sxs-lookup"><span data-stu-id="ceadd-110">Install a data gateway</span></span>
<span data-ttu-id="ceadd-111">サードパーティのデータにアクセスするためには、Microsoft Power BI ゲートウェイをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-111">In order to access your third-party data, you must install and configure a Microsoft Power BI gateway.</span></span> <span data-ttu-id="ceadd-112">詳細については[、「Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ceadd-112">See [Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) to learn more.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="ceadd-113">データソースへの接続</span><span class="sxs-lookup"><span data-stu-id="ceadd-113">Connect to a data source</span></span>
<span data-ttu-id="ceadd-114">Microsoft SQL server コネクタをデータソースに接続するには、クロールするデータベースサーバーとオンプレミスゲートウェイを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-114">To connect your Microsoft SQL server connector to a data source, you must configure the database server you want crawled and the on-premises gateway.</span></span> <span data-ttu-id="ceadd-115">その後、必要な認証方法を使用してデータベースに接続できます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-115">You can then connect to the database with the required authentication method.</span></span>

> [!NOTE]
> <span data-ttu-id="ceadd-116">データベースでは、SQL server バージョン2008以降を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-116">Your database must run SQL server version 2008 or later.</span></span>

<span data-ttu-id="ceadd-117">データベースコンテンツを検索するには、コネクタを構成するときに SQL クエリを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-117">To search your database content, you must specify SQL queries when you configure the connector.</span></span> <span data-ttu-id="ceadd-118">これらの SQL クエリは、すべての列を取得するために実行する必要があるすべての SQL 結合を含む、インデックスを作成するすべてのデータベース列に名前を付ける必要があります (つまり、ソースプロパティ)。</span><span class="sxs-lookup"><span data-stu-id="ceadd-118">These SQL queries need to name all the database columns that you want to index (i.e. source properties), including any SQL joins that need to be performed to get all the columns.</span></span> <span data-ttu-id="ceadd-119">検索結果へのアクセスを制限するには、Microsoft SQL server コネクタを構成するときに、SQL クエリでアクセス制御リスト (Acl) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-119">To restrict access to search results, you must specify Access Control Lists (ACLs) with SQL queries when you configure the Microsoft SQL server connector.</span></span>

## <a name="full-crawl-required"></a><span data-ttu-id="ceadd-120">フルクロール (必須)</span><span class="sxs-lookup"><span data-stu-id="ceadd-120">Full crawl (Required)</span></span>
<span data-ttu-id="ceadd-121">この手順では、データベースのフルクロールを実行する SQL クエリを構成します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-121">In this step, you configure the SQL query that runs a full crawl of the database.</span></span> <span data-ttu-id="ceadd-122">フルクロールでは、**クエリ**可能、**検索**可能、または取得可能にするすべての列またはプロパティが選択**されます。**</span><span class="sxs-lookup"><span data-stu-id="ceadd-122">The full crawl selects all the columns or properties you want to be made **queryable**, **searchable**, or **retrievable**.</span></span> <span data-ttu-id="ceadd-123">また、ACL 列を指定して、検索結果のアクセスを特定のユーザーまたはグループに制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-123">You can also specify ACL columns to restrict access of search results to specific users or groups.</span></span>

> [!Tip]
> <span data-ttu-id="ceadd-124">必要なすべての列を取得するには、複数のテーブルに結合することができます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-124">To get all the columns that you need, you can join multiple tables.</span></span>

![プロパティの例を使用して、OrderTable と AclTable を示すスクリプト](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a><span data-ttu-id="ceadd-126">データ列の選択 (必須) と ACL 列 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="ceadd-126">Select data columns (Required) and ACL columns (Optional)</span></span>
<span data-ttu-id="ceadd-127">この例では、検索のデータを保持する5つのデータ列 (OrderId、OrderTitle、Ordertitle、Htmldatetime、および IsDeleted) の選択例を示します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-127">The example demonstrates selection of five data columns that hold the data for the search: OrderId, OrderTitle, OrderDesc, CreatedDateTime, and IsDeleted.</span></span> <span data-ttu-id="ceadd-128">データの各行に対して表示権限を設定するには、必要に応じて、次の ACL 列を選択できます。 AllowedUsers、Allowedusers、DeniedUsers、および DeniedGroups。</span><span class="sxs-lookup"><span data-stu-id="ceadd-128">To set view permissions for each row of data, you can optionally select these ACL columns: AllowedUsers, AllowedGroups, DeniedUsers, and DeniedGroups.</span></span> <span data-ttu-id="ceadd-129">これらのすべてのデータ列は、**クエリ**可能、**検索**可能 **、または**取得可能にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-129">All these data columns can be made **queryable**, **searchable**, or **retrievable**.</span></span>

<span data-ttu-id="ceadd-130">次のクエリ例に示すように、データ列を選択します。`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span><span class="sxs-lookup"><span data-stu-id="ceadd-130">Select data columns as shown in this example query: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`</span></span>

### <a name="watermark-required"></a><span data-ttu-id="ceadd-131">ウォーターマーク (必須)</span><span class="sxs-lookup"><span data-stu-id="ceadd-131">Watermark (Required)</span></span>
<span data-ttu-id="ceadd-132">データベースが過負荷にならないようにするために、コネクタはフルクロールのウォーターマーク列を使用して、フルクロールクエリをバッチ処理および再開します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-132">To prevent overloading the database, the connector batches and resumes full-crawl queries with a full-crawl watermark column.</span></span> <span data-ttu-id="ceadd-133">[すかし] 列の値を使用すると、以降の各バッチが取得され、最後のチェックポイントからクエリが再開されます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-133">By using the value of the watermark column, each subsequent batch is fetched, and querying is resumed from the last checkpoint.</span></span> <span data-ttu-id="ceadd-134">基本的には、フルクロールのデータ更新を制御するメカニズムを示します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-134">Essentially this is a mechanism to control data refresh for full crawls.</span></span>

<span data-ttu-id="ceadd-135">次の例に示すように、ウォーターマークに対してクエリスニペットを作成します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-135">Create query snippets for watermarks as shown in these examples:</span></span>
* <span data-ttu-id="ceadd-136">`WHERE (CreatedDateTime > @watermark)`.</span><span class="sxs-lookup"><span data-stu-id="ceadd-136"></span></span> <span data-ttu-id="ceadd-137">予約済みのキーワード`@watermark`を使用して、ウォーターマーク列名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-137">Cite the watermark column name with the reserved keyword `@watermark`.</span></span> <span data-ttu-id="ceadd-138">[すかし] 列の並べ替え順序が昇順の場合は`>`、を使用します。それ以外の`<`場合は、を使用します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-138">If the sort order of the watermark column is ascending, use `>`; otherwise, use `<`.</span></span>
* <span data-ttu-id="ceadd-139">`ORDER BY CreatedDateTime ASC`.</span><span class="sxs-lookup"><span data-stu-id="ceadd-139"></span></span> <span data-ttu-id="ceadd-140">[すかし] 列の昇順または降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-140">Sort on the watermark column in ascending or descending order.</span></span>

<span data-ttu-id="ceadd-141">次の図に示す構成では、 `CreatedDateTime` [選択されたウォーターマーク] 列が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ceadd-141">In the configuration shown in the following image, `CreatedDateTime` is the selected watermark column.</span></span> <span data-ttu-id="ceadd-142">行の最初のバッチをフェッチするには、[すかし] 列のデータ型を指定します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-142">To fetch the first batch of rows, specify the data type of the watermark column.</span></span> <span data-ttu-id="ceadd-143">この例では、データ型は`DateTime`です。</span><span class="sxs-lookup"><span data-stu-id="ceadd-143">In this case, the data type is `DateTime`.</span></span>

![](media/MSSQL-watermark.png)

<span data-ttu-id="ceadd-144">最初のクエリは、次の値を使用して、最初の**N 個**の行をフェッチします。 "/1 月1日 > 1753 00:00:00" (datetime データ型の最小値)。</span><span class="sxs-lookup"><span data-stu-id="ceadd-144">The first query fetches the first **N** amount of rows by using: "CreatedDateTime > January 1, 1753 00:00:00" (min value of DateTime data type).</span></span> <span data-ttu-id="ceadd-145">最初のバッチをフェッチした後、バッチで`CreatedDateTime`返される最大値は、行が昇順で並べ替えられている場合に、チェックポイントとして保存されます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-145">After the first batch is fetched, the highest value of `CreatedDateTime` returned in the batch is saved as the checkpoint if the rows are sorted in ascending order.</span></span> <span data-ttu-id="ceadd-146">例としては、2019年3月1日、03:00:00 があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-146">An example is March 1, 2019 03:00:00.</span></span> <span data-ttu-id="ceadd-147">その後、 **N**行の次のバッチは、クエリ内の "/datetime > 03:00:00 2019 年3月1日を使用してフェッチされます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-147">Then the next batch of **N** rows is fetched by using "CreatedDateTime > March 1, 2019 03:00:00" in the query.</span></span>

### <a name="skipping-soft-deleted-rows-optional"></a><span data-ttu-id="ceadd-148">削除された削除済みの行をスキップする (オプション)</span><span class="sxs-lookup"><span data-stu-id="ceadd-148">Skipping soft-deleted rows (Optional)</span></span>
<span data-ttu-id="ceadd-149">データベース内の削除済みの行をインデックス作成から除外するには、その行が削除されたことを示す、回復可能な削除の列名と値を指定します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-149">To exclude soft-deleted rows in your database from being indexed, specify the soft-delete column name and value that indicates the row is deleted.</span></span>

![論理削除の設定: "削除済みの行を示す" 論理削除列 "および" 値 (論理削除列) "](media/MSSQL-softdelete.png)

## <a name="incremental-crawl-optional"></a><span data-ttu-id="ceadd-151">増分クロール (オプション)</span><span class="sxs-lookup"><span data-stu-id="ceadd-151">Incremental crawl (Optional)</span></span>
<span data-ttu-id="ceadd-152">このオプションの手順では、データベースの増分クロールを実行するための SQL クエリを指定します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-152">In this optional step, provide a SQL query to run an incremental crawl of the database.</span></span> <span data-ttu-id="ceadd-153">このクエリを使用すると、Microsoft SQL server コネクタによって、前回の増分クロール以降のデータが変更されます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-153">With this query, the Microsoft SQL server connector makes any changes to the data since the last incremental crawl.</span></span> <span data-ttu-id="ceadd-154">フルクロールの場合と同様に、**クエリ**可能、**検索**可能、または取得可能にするすべての列を**選択します**。</span><span class="sxs-lookup"><span data-stu-id="ceadd-154">As in the full crawl, select all columns that you want to be made **queryable**, **searchable**, or **retrievable**.</span></span> <span data-ttu-id="ceadd-155">フルクロールクエリで指定したものと同じ ACL 列のセットを指定します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-155">Specify the same set of ACL columns that you specified in the full crawl query.</span></span>

<span data-ttu-id="ceadd-156">次の図のコンポーネントは、完全なクロールコンポーネントに似ていますが、1つの例外があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-156">The components in the following image resemble the full crawl components with one exception.</span></span> <span data-ttu-id="ceadd-157">この例では、"ModifiedDateTime" は選択された透かし列です。</span><span class="sxs-lookup"><span data-stu-id="ceadd-157">In this case, "ModifiedDateTime" is the selected watermark column.</span></span> <span data-ttu-id="ceadd-158">[フルクロールの手順](#full-crawl-required)を確認して、増分クロールクエリを記述する方法を説明し、次の画像を例として示します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-158">Review the [full crawl steps](#full-crawl-required) to learn how to write your incremental crawl query and see the following image as an example.</span></span>

![OrderTable、AclTable、使用できるプロパティの例を示す増分クロールスクリプト。](media/MSSQL-incrcrawl.png)

## <a name="limitations"></a><span data-ttu-id="ceadd-160">制限事項</span><span class="sxs-lookup"><span data-stu-id="ceadd-160">Limitations</span></span>
<span data-ttu-id="ceadd-161">Microsoft SQL server コネクタには、次のようなプレビューリリースの制限があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-161">The Microsoft SQL server connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="ceadd-162">オンプレミスデータベースでは、SQL server バージョン2008以降を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ceadd-162">The on-premises database must run SQL server version 2008 or later.</span></span>
* <span data-ttu-id="ceadd-163">Acl は、ユーザープリンシパル名 (UPN)、Azure Active Directory (Azure AD)、または Active Directory セキュリティを使用する場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ceadd-163">ACLs are only supported by using a User Principal Name (UPN), Azure Active Directory (Azure AD), or Active Directory Security.</span></span>
* <span data-ttu-id="ceadd-164">データベース列内のリッチコンテンツのインデックス作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ceadd-164">Indexing rich content inside database columns is not supported.</span></span> <span data-ttu-id="ceadd-165">このようなコンテンツの例としては、HTML、JSON、XML、blob、ドキュメント parsings などがあります。これらは、データベース列内のリンクとして存在します。</span><span class="sxs-lookup"><span data-stu-id="ceadd-165">Examples of such content are HTML, JSON, XML, blobs, and document parsings that exist as links inside the database columns.</span></span>

