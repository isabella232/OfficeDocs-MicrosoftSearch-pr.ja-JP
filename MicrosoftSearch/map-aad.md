---
title: AAD id のマッピング
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: AAD id をマップする手順
ms.openlocfilehash: db0378e596c560edebd2ceb942e6327b47a5286b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367705"
---
# <a name="map-your-azure-ad-identities"></a><span data-ttu-id="48817-103">Azure AD Id をマップする</span><span class="sxs-lookup"><span data-stu-id="48817-103">Map your Azure AD Identities</span></span>  

<span data-ttu-id="48817-104">この記事では、azure ad id をデータソースの一意識別子 (非 Azure AD id) にマッピングする手順について説明します。これにより、非 Azure AD id を使用したアクセス制御リスト (ACL) 内のユーザーは、それらにスコープ設定されたコネクタ検索結果を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="48817-104">This article walks you through the steps of mapping your Azure AD identities to a unique identifier for your data source (non-Azure AD identity) so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="48817-105">これらの手順は、"このデータソースにアクセスできるユーザーのみ" AAD "の検索アクセス許可を使用して、Microsoft によって [Salesforce](salesforce-connector.md) コネクタを設定する検索管理者にのみ関連しています。</span><span class="sxs-lookup"><span data-stu-id="48817-105">These steps are only relevant to search administrators who are setting up a [Salesforce](salesforce-connector.md) connector by Microsoft with search permissions for "Only people with access to this data source" and identity type "AAD."</span></span> <span data-ttu-id="48817-106">次の手順では、Azure AD ユーザーのプロパティをユーザーの **フェデレーション id** にマップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48817-106">The following steps walk you through how to map your Azure AD user properties to your users' **Federation IDs**.</span></span>

>[!NOTE]
><span data-ttu-id="48817-107">[Salesforce コネクタ](salesforce-connector.md)を設定し、[アクセス許可] 画面で **AAD 以外** のユーザーに対してこのデータソースおよび id の種類 **へのアクセス権を持つユーザーのみ** を選択する場合は、非 azure ad id をマップする手順については、「 [azure ad の id をマップ](map-non-aad.md)する」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48817-107">If you are setting up a [Salesforce connector](salesforce-connector.md) and select **Only people with access to this data source** and identity type **non-AAD** on the search permissions screen, refer to the [Map your non-Azure AD Identities](map-non-aad.md) article for steps on how to map non-Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-azure-ad-properties"></a><span data-ttu-id="48817-108">Azure AD プロパティをマッピングする手順</span><span class="sxs-lookup"><span data-stu-id="48817-108">Steps for mapping your Azure AD properties</span></span>

### <a name="1-select-azure-ad-user-properties-to-map"></a><span data-ttu-id="48817-109">1. マッピングする Azure AD ユーザーのプロパティを選択する</span><span class="sxs-lookup"><span data-stu-id="48817-109">1. Select Azure AD user properties to map</span></span>

<span data-ttu-id="48817-110">フェデレーション ID にマップする必要がある Azure AD プロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="48817-110">You can select the Azure AD properties you need to map to the Federation ID.</span></span>

<span data-ttu-id="48817-111">ドロップダウンから Azure AD ユーザーのプロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="48817-111">You can select an Azure AD user property from the dropdown.</span></span> <span data-ttu-id="48817-112">組織のフェデレーション ID マッピングを作成するためにこれらのプロパティが必要な場合は、Azure AD ユーザーのプロパティをいくつでも追加できます。</span><span class="sxs-lookup"><span data-stu-id="48817-112">You can also add as many Azure AD user properties as you would like if these properties are necessary to create the Federation ID mapping for your organization.</span></span>

### <a name="2-create-formula-to-complete-mapping"></a><span data-ttu-id="48817-113">2. マッピングを完了するための数式を作成します。</span><span class="sxs-lookup"><span data-stu-id="48817-113">2. Create formula to complete mapping</span></span>

<span data-ttu-id="48817-114">Azure AD ユーザーのプロパティの値を組み合わせて、一意のフェデレーション ID を形成することができます。</span><span class="sxs-lookup"><span data-stu-id="48817-114">You can combine the values of the Azure AD user properties to form the unique Federation ID.</span></span>

<span data-ttu-id="48817-115">[式] ボックスで、"" は、 {0} 選択した *最初* の Azure AD プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="48817-115">In the formula box, "{0}" corresponds to the *first* Azure AD property you selected.</span></span> <span data-ttu-id="48817-116">" {1} " は、選択した *2 番目* の Azure AD プロパティに対応します。</span><span class="sxs-lookup"><span data-stu-id="48817-116">"{1}" corresponds to the *second* Azure AD property you selected.</span></span> <span data-ttu-id="48817-117">" {2} " は *3 番目* の Azure AD プロパティに対応します。以下同様になります。</span><span class="sxs-lookup"><span data-stu-id="48817-117">"{2}" corresponds to the *third* Azure AD property, and so on.</span></span>  

<span data-ttu-id="48817-118">次に、サンプルの正規表現出力と数式出力を含む数式の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="48817-118">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span>

| <span data-ttu-id="48817-119">サンプル式</span><span class="sxs-lookup"><span data-stu-id="48817-119">Sample formula</span></span>                  | <span data-ttu-id="48817-120">{0}サンプルユーザーのプロパティの値</span><span class="sxs-lookup"><span data-stu-id="48817-120">Value of property {0} for a sample user</span></span>                 | <span data-ttu-id="48817-121">{1}サンプルユーザーのプロパティの値</span><span class="sxs-lookup"><span data-stu-id="48817-121">Value of property {1} for a sample user</span></span>           | <span data-ttu-id="48817-122">数式の出力</span><span class="sxs-lookup"><span data-stu-id="48817-122">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="48817-123">{0}.{1}@contoso .com</span><span class="sxs-lookup"><span data-stu-id="48817-123">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="48817-124">担当</span><span class="sxs-lookup"><span data-stu-id="48817-124">firstname</span></span> | <span data-ttu-id="48817-125">社員</span><span class="sxs-lookup"><span data-stu-id="48817-125">lastname</span></span> |<span data-ttu-id="48817-126">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="48817-126">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="48817-127">{0}@domain .com</span><span class="sxs-lookup"><span data-stu-id="48817-127">{0}@domain.com</span></span>                 | <span data-ttu-id="48817-128">userid</span><span class="sxs-lookup"><span data-stu-id="48817-128">userid</span></span>                 |             |<span data-ttu-id="48817-129">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="48817-129">userid@domain.com</span></span>

<span data-ttu-id="48817-130">数式を入力した後で、必要に応じて、[ **プレビュー** ] をクリックして、データソースから5つのランダムユーザーのプレビューを表示し、それぞれのユーザーマッピングを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="48817-130">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="48817-131">プレビューの出力には、手順1でユーザーが選択した Azure AD ユーザープロパティの値と、そのユーザーの手順2で提供された最終的な式の出力が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48817-131">The output of the preview includes the value of the Azure AD user properties selected in step 1 for those users and the output of the final formula provided in step 2 for that user.</span></span> <span data-ttu-id="48817-132">また、「成功」または「失敗」アイコンを使用して、式の出力をテナントの Azure AD ユーザーに解決できるかどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="48817-132">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="48817-133">[ **プレビュー**] をクリックした後、1つ以上のユーザーマッピングの状態が "Failed" になっている場合でも、接続の作成を続行できます。</span><span class="sxs-lookup"><span data-stu-id="48817-133">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="48817-134">プレビューには、5つのランダムユーザーと、データソースからのマッピングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="48817-134">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="48817-135">指定したマッピングですべてのユーザーがマップされていない場合は、この場合に遭遇する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48817-135">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-azure-ad-mapping"></a><span data-ttu-id="48817-136">Azure AD マッピングの例</span><span class="sxs-lookup"><span data-stu-id="48817-136">Sample Azure AD mapping</span></span>

<span data-ttu-id="48817-137">Azure AD マッピングの例については、以下のスナップショットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="48817-137">See the snapshot below for a sample Azure AD mapping.</span></span>

![Azure AD マッピングページに記入する方法のサンプルスナップショット](media/aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="48817-139">制限事項</span><span class="sxs-lookup"><span data-stu-id="48817-139">Limitations</span></span>  

- <span data-ttu-id="48817-140">すべてのユーザーに対して1つのマッピングのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="48817-140">Only one mapping is supported for all users.</span></span> <span data-ttu-id="48817-141">条件付きマッピングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="48817-141">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="48817-142">接続が公開されると、マッピングを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="48817-142">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="48817-143">Azure ad ユーザープロパティに対して Regex ベースの式を使用することは、Azure AD からフェデレーション ID への変換ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="48817-143">Regex-based expressions against the Azure AD user properties are not supported for the Azure AD to Federation ID transformation.</span></span>