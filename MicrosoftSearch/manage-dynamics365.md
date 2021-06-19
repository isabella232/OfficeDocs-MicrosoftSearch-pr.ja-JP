---
title: Dynamics 365 フェデレーション検索 (プレビュー)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: 検索結果での Dynamics 365 コンテンツの表示方法を管理する
ms.openlocfilehash: 8818d2e6a412feb167c67f465f485b23e868a12a
ms.sourcegitcommit: be989950a7b63281c2348cfd9e6cc13e79b7c067
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53021856"
---
# <a name="dynamics-365-federation-search-preview"></a><span data-ttu-id="ea456-103">Dynamics 365 フェデレーション検索 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="ea456-103">Dynamics 365 federation search (preview)</span></span>

## <a name="microsoft-search-federation-and-connectors"></a><span data-ttu-id="ea456-104">Microsoft Searchフェデレーションとコネクタ</span><span class="sxs-lookup"><span data-stu-id="ea456-104">Microsoft Search Federation and connectors</span></span>

<span data-ttu-id="ea456-105">この機能をよりMicrosoft Searchするために、フェデレーションを導入Microsoft Searchしています。</span><span class="sxs-lookup"><span data-stu-id="ea456-105">To help make Microsoft Search more useful, we're introducing Microsoft Search Federation.</span></span> <span data-ttu-id="ea456-106">フェデレーション検索を使用すると、組織は次のシナリオのデータを次の場所でアクセスMicrosoft Search。</span><span class="sxs-lookup"><span data-stu-id="ea456-106">With federated search, organizations can make data in these scenarios accessible in Microsoft Search:</span></span>

* <span data-ttu-id="ea456-107">厳密なコンプライアンス要件の対象となるシステム内のデータ</span><span class="sxs-lookup"><span data-stu-id="ea456-107">Data in systems that are subject to strict compliance requirements</span></span>
* <span data-ttu-id="ea456-108">システム境界から離れきらないデータ</span><span class="sxs-lookup"><span data-stu-id="ea456-108">Data that can't leave system boundaries</span></span>
* <span data-ttu-id="ea456-109">組織がクラウドにインデックスを作成したくない、事前に保存された機密データ</span><span class="sxs-lookup"><span data-stu-id="ea456-109">Sensitive data stored on-prem that your organization doesn’t want indexed on the cloud</span></span>

<span data-ttu-id="ea456-110">フェデレーション検索接続を介してアクセスされるデータは、フェデレーション検索接続でインデックスMicrosoft Search。</span><span class="sxs-lookup"><span data-stu-id="ea456-110">Data accessed through a federated search connection isn't indexed in Microsoft Search.</span></span> <span data-ttu-id="ea456-111">また、Microsoft の組み込みコネクタを使用すると、フェデレーション検索接続を簡単にセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="ea456-111">Also, using built-in connectors from Microsoft, it's easy to set up federated search connections.</span></span> <span data-ttu-id="ea456-112">Dynamics 365 コネクタは現在プレビュー中です。</span><span class="sxs-lookup"><span data-stu-id="ea456-112">Our Dynamics 365 connector is currently in preview.</span></span> <span data-ttu-id="ea456-113">プレビューへの参加に興味がある場合は、次のページ[aka.ms/D365FederationSearchPreview。](https://aka.ms/D365FederationSearchPreview)</span><span class="sxs-lookup"><span data-stu-id="ea456-113">If you're interested in joining the preview, let us know at [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span></span>

## <a name="dynamics-365-federation-connector"></a><span data-ttu-id="ea456-114">Dynamics 365 フェデレーション コネクタ</span><span class="sxs-lookup"><span data-stu-id="ea456-114">Dynamics 365 federation connector</span></span>

<span data-ttu-id="ea456-115">Microsoft Dynamics 365 は、エンタープライズ リソース計画と顧客関係管理用に設計されたインテリジェント なビジネス アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="ea456-115">Microsoft Dynamics 365 is a line of intelligent business applications designed for enterprise resource planning and customer relationship management.</span></span> <span data-ttu-id="ea456-116">Dynamics 365 フェデレーションを使用すると、Microsoft Search はシームレスな検索エクスペリエンスを提供し、ユーザーは Dynamics 365 に格納されている最も関連性の高い顧客およびビジネス データを簡単に見つくことができます。</span><span class="sxs-lookup"><span data-stu-id="ea456-116">With Dynamics 365 federation, Microsoft Search provides a seamless search experience, enabling users to easily find the most relevant customer and business data stored in Dynamics 365.</span></span> <span data-ttu-id="ea456-117">Dynamics 365 フェデレーション コネクタには、次の主な利点があります。</span><span class="sxs-lookup"><span data-stu-id="ea456-117">The Dynamics 365 federation connector provides some key benefits:</span></span>

* <span data-ttu-id="ea456-118">**管理が簡単:** Dynamics 365 インスタンスへの検索接続を構成および維持するための合理化されたプロセス。</span><span class="sxs-lookup"><span data-stu-id="ea456-118">**Easy to administer:** Streamlined process to configure and maintain the search connection to a Dynamics 365 instance.</span></span>
* <span data-ttu-id="ea456-119">**使いやすい:** ユーザーは、アカウント、連絡先、オープン 機会など、Dynamics 365 に格納されている主要な情報を簡単かつ迅速に見つくことができます。</span><span class="sxs-lookup"><span data-stu-id="ea456-119">**Easy to use:** Users can easily and quickly find key information stored in Dynamics 365, including accounts, contacts, open opportunities, and more.</span></span>
* <span data-ttu-id="ea456-120">**よりリッチなコンテンツ:** Dynamics 365 検索結果をより便利にするために、リード、連絡先、アカウントの詳細などの重要な情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ea456-120">**Richer content:** To make Dynamics 365 search results more useful, they include key information like leads, contacts, and account details.</span></span>
* <span data-ttu-id="ea456-121">**組み込みのデータ保護:** Dynamics 365 の結果は、接続されたインスタンスにアクセスできるユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea456-121">**Built-in data protection:** Dynamics 365 results will only appear for users that have access to the connected instance.</span></span>
* <span data-ttu-id="ea456-122">**統合検索エクスペリエンス:** 一貫性のあるエクスペリエンスを維持するために、Dynamics 365 の結果は、すべての検索エントリ ポイントで一貫しています。</span><span class="sxs-lookup"><span data-stu-id="ea456-122">**Unified search experience:** To maintain a cohesive experience, Dynamics 365 results are consistent across all search entry points.</span></span> <span data-ttu-id="ea456-123">検索の場所を問い合っても、同じ外観で同じ結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="ea456-123">Wherever you search, you'll get the same results with the same look and feel.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="ea456-124">ユーザーのエクスぺリエンス</span><span class="sxs-lookup"><span data-stu-id="ea456-124">What users experience</span></span>

<span data-ttu-id="ea456-125">Dynamics 365 の回答は、SharePoint Online、Bing、および Office を含むすべての Microsoft Search キャンバスの検索結果に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea456-125">Dynamics 365 answers appear in search results across all Microsoft Search canvases, including SharePoint Online, Bing, and Office.</span></span>

:::image type="content" alt-text="Dynamics 365 の回答のスクリーンショット (SharePoint、Bing、およびOffice" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

<span data-ttu-id="ea456-127">この答えから、[その他の Dynamics 365 の結果] リンクを使用すると、より多くの **Dynamics 365 検索結果を簡単に確認** できます。</span><span class="sxs-lookup"><span data-stu-id="ea456-127">From the answer, it's easy to see more Dynamics 365 search results by using the **More Dynamics 365 results** link.</span></span> <span data-ttu-id="ea456-128">ユーザーは、クエリに関連する結果が多い、専用の Dynamics 365 結果ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="ea456-128">It takes users to a dedicated Dynamics 365 results page with more results relevant to their query.</span></span>

:::image type="content" alt-text="Dynamics 365 の垂直方向のスクリーンショットと、SharePoint、Bing、およびOffice" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

<span data-ttu-id="ea456-130">結果をクリックまたはタップすると、Dynamics 365 が開き、詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea456-130">Clicking or tapping any result opens Dynamics 365 and shows the detailed information.</span></span>

:::image type="content" alt-text="Dynamics 365 の詳細ページのスクリーンショット" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

<span data-ttu-id="ea456-132">ユーザーが検索を開始する場所に関係なく、ユーザーのエクスペリエンスは一貫性があり、最も関連性の高い Dynamics 365 の結果をすばやく見つけるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ea456-132">No matter where your users start their search their experience will be consistent and enable them to quickly find the most relevant Dynamics 365 results.</span></span> <span data-ttu-id="ea456-133">デモについては [、Microsoft ビルド 2021 ビデオ](https://youtu.be/TH9QUkQoEJM) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ea456-133">Check out our [Microsoft Build 2021 video](https://youtu.be/TH9QUkQoEJM) for a demonstration.</span></span>

## <a name="supported-query-patterns"></a><span data-ttu-id="ea456-134">サポートされているクエリ パターン</span><span class="sxs-lookup"><span data-stu-id="ea456-134">Supported query patterns</span></span>

<span data-ttu-id="ea456-135">Dynamics 365 の結果を検索する際に、自然言語クエリと製品Microsoft Searchクエリの両方がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="ea456-135">Both natural language and product name queries are supported when using Microsoft Search to find Dynamics 365 results.</span></span> <span data-ttu-id="ea456-136">また、Dynamics 365 クエリでは大文字と小文字が区別されません。</span><span class="sxs-lookup"><span data-stu-id="ea456-136">Also, Dynamics 365 queries aren't case sensitive.</span></span> <span data-ttu-id="ea456-137">自然言語パターンを使用して、連絡先、アカウント、および商談を検索します。顧客名または場所別、その他の頻繁に使用されるクエリ。</span><span class="sxs-lookup"><span data-stu-id="ea456-137">Use natural language patterns to find contact, account, and opportunities--by customer name or location--and other frequently used queries.</span></span> <span data-ttu-id="ea456-138">いくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="ea456-138">Here are a few examples:</span></span>

* <span data-ttu-id="ea456-139">Who Contoso の連絡先</span><span class="sxs-lookup"><span data-stu-id="ea456-139">Who is the contact for Contoso</span></span>
* <span data-ttu-id="ea456-140">Contoso のオープン な機会</span><span class="sxs-lookup"><span data-stu-id="ea456-140">Open opportunities for Contoso</span></span>
* <span data-ttu-id="ea456-141">シアトルでのオープンな機会</span><span class="sxs-lookup"><span data-stu-id="ea456-141">What are open opportunities in Seattle</span></span>
* <span data-ttu-id="ea456-142">シアトルのアカウントは何か</span><span class="sxs-lookup"><span data-stu-id="ea456-142">What are the accounts in Seattle</span></span>
* <span data-ttu-id="ea456-143">シアトルの連絡先</span><span class="sxs-lookup"><span data-stu-id="ea456-143">What are the contacts in Seattle</span></span>
* <span data-ttu-id="ea456-144">今月の閉じる見込み客の情報</span><span class="sxs-lookup"><span data-stu-id="ea456-144">What are my leads closing this month</span></span>
* <span data-ttu-id="ea456-145">優先度の高い電話</span><span class="sxs-lookup"><span data-stu-id="ea456-145">High priority phone call</span></span>
* <span data-ttu-id="ea456-146">連絡先の不足しているメール</span><span class="sxs-lookup"><span data-stu-id="ea456-146">Contact missing emails</span></span>

<span data-ttu-id="ea456-147">製品名パターンは、Dynamics 365 アプリケーションの範囲をサポートし、クエリに表示される場所に関係なく Dynamics 365 の結果をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="ea456-147">Product name patterns support a range of Dynamics 365 applications and will trigger Dynamics 365 results regardless of where they appear in a query:</span></span>

* <span data-ttu-id="ea456-148">D365</span><span class="sxs-lookup"><span data-stu-id="ea456-148">D365</span></span>
* <span data-ttu-id="ea456-149">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="ea456-149">Dynamics 365</span></span>
* <span data-ttu-id="ea456-150">Dynamics365</span><span class="sxs-lookup"><span data-stu-id="ea456-150">Dynamics365</span></span>
* <span data-ttu-id="ea456-151">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="ea456-151">Dynamics CRM</span></span>
* <span data-ttu-id="ea456-152">Dynamics Sales</span><span class="sxs-lookup"><span data-stu-id="ea456-152">Dynamics Sales</span></span>
* <span data-ttu-id="ea456-153">Dynamics Customer Service</span><span class="sxs-lookup"><span data-stu-id="ea456-153">Dynamics Customer Service</span></span>
* <span data-ttu-id="ea456-154">Dynamics Service</span><span class="sxs-lookup"><span data-stu-id="ea456-154">Dynamics Service</span></span>
* <span data-ttu-id="ea456-155">Dynamics Field Service</span><span class="sxs-lookup"><span data-stu-id="ea456-155">Dynamics Field Service</span></span>

## <a name="configure-the-dynamics-365-connector"></a><span data-ttu-id="ea456-156">Dynamics 365 コネクタの構成</span><span class="sxs-lookup"><span data-stu-id="ea456-156">Configure the Dynamics 365 connector</span></span>

<span data-ttu-id="ea456-157">この簡単な構成により、組織内のユーザーに対して Dynamics 365 フェデレーション検索エクスペリエンスを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ea456-157">With this simple configuration, you can enable the Dynamics 365 federation search experience for people in your organization.</span></span>

1. <span data-ttu-id="ea456-158">[データ[ソースMicrosoft 365 管理センター]](https://admin.microsoft.com)[に移動します](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors)。</span><span class="sxs-lookup"><span data-stu-id="ea456-158">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [Data sources](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span></span>

2. <span data-ttu-id="ea456-159">[Microsoft アプリとサービス] セクションの [Microsoft Dynamics 365] で、[管理] を選択して Microsoft Dynamics 365 パネルを開きます。 </span><span class="sxs-lookup"><span data-stu-id="ea456-159">In the Microsoft apps and services section, under Microsoft Dynamics 365, select **Manage** to open the Microsoft Dynamics 365 panel.</span></span>

3. <span data-ttu-id="ea456-160">組織のコネクタを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ea456-160">Enable the connector for your organization.</span></span>

4. <span data-ttu-id="ea456-161">[エンドポイント **] リストで** 、Dynamics 365 環境を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea456-161">In the **Endpoints** list, select your Dynamics 365 environment.</span></span>

5. <span data-ttu-id="ea456-162">[接続 **ID] に**、この接続の一意の ID を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea456-162">In the **Connection ID**, enter a unique ID for this connection.</span></span>

6. <span data-ttu-id="ea456-163">[同意] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ea456-163">Review and select the consent check box.</span></span>

7. <span data-ttu-id="ea456-164">[保存 **] を** 選択して、接続のセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="ea456-164">Select **Save** to finish the connection setup.</span></span>

:::image type="content" alt-text="画面の Dynamics 365 セットアップ パネルのスクリーンショットMicrosoft 365 管理センター" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

<span data-ttu-id="ea456-166">セットアップが完了すると、Dynamics 365 の回答と垂直は、有効な Dynamics 365 ライセンスを持ち、接続されている Dynamics 365 環境へのアクセス権を持つユーザーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ea456-166">When the setup is complete, Dynamics 365 answers and vertical will only appear for users with a valid Dynamics 365 license and access to the connected Dynamics 365 environment.</span></span> <span data-ttu-id="ea456-167">これらの設定に戻り、接続エンドポイント環境を変更したり、接続を非アクティブ化したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ea456-167">At any time, you can return to these settings and change the connection endpoint environment or deactivate the connection.</span></span>
