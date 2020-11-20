---
title: AAD 以外の id のマッピング
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
description: AAD 以外の id をマップする手順
ms.openlocfilehash: cd7d0eb17678d69ec1966e4472b38c1f18c30809
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367660"
---
# <a name="map-your-non-azure-ad-identities"></a><span data-ttu-id="121d2-103">非 Azure AD Id をマップする</span><span class="sxs-lookup"><span data-stu-id="121d2-103">Map your non-Azure AD Identities</span></span>  

<span data-ttu-id="121d2-104">この記事では、azure ad id 以外のアクセス制御リスト (ACL) を使用しているユーザーが、それらにスコープ設定されたコネクタ検索結果を表示できるように、azure ad id に非 Azure AD id をマッピングする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="121d2-104">This article walks you through the steps of mapping your non-Azure AD identities to your Azure AD identities so that people in your Access Control List (ACL) with non-Azure AD identities can see connector search results scoped to them.</span></span>

<span data-ttu-id="121d2-105">これらの手順は、Microsoft によって [ServiceNow](servicenow-connector.md) または [Salesforce](salesforce-connector.md) のコネクタを設定している管理者のみが、"このデータソースへのアクセス権を持つユーザーのみ" および "identity type" という名前の "AAD" の検索アクセス許可を使用して設定している場合にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="121d2-105">These steps are only relevant to search administrators who are setting up a [ServiceNow](servicenow-connector.md) or [Salesforce](salesforce-connector.md) connectors by Microsoft with search permissions for "Only people with access to this data source" and identity type "Non-AAD."</span></span>

>[!NOTE]
><span data-ttu-id="121d2-106">Salesforce コネクタを設定して、[アクセス許可] 画面で [このデータソースおよび id の種類 **AAD** **にアクセスできるユーザーのみ**] を選択する場合は、「azure ad id をマップする方法」の手順については、「 [azure ad identity のマップ](map-aad.md)」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="121d2-106">If you are setting up a Salesforce connector and select **Only people with access to this data source** and identity type **AAD** on the search permissions screen, refer to the [Map your Azure AD Identities](map-aad.md) article for steps on how to map Azure AD identities.</span></span>  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a><span data-ttu-id="121d2-107">非 Azure AD プロパティをマッピングする手順</span><span class="sxs-lookup"><span data-stu-id="121d2-107">Steps for mapping your non-Azure AD properties</span></span>

### <a name="1-select-an-azure-ad-user-property"></a><span data-ttu-id="121d2-108">1. Azure AD ユーザープロパティを選択する</span><span class="sxs-lookup"><span data-stu-id="121d2-108">1. Select an Azure AD user property</span></span>  

<span data-ttu-id="121d2-109">マッピングを作成する Azure AD ユーザーのプロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="121d2-109">You can select the Azure AD user property you are creating the mapping for.</span></span> <span data-ttu-id="121d2-110">これは、非 Azure AD id をにマップするターゲットプロパティです。</span><span class="sxs-lookup"><span data-stu-id="121d2-110">This is the target property you are aiming to map your non-Azure AD identities to.</span></span>  

<span data-ttu-id="121d2-111">次のいずれかの Azure AD プロパティを選択できます。</span><span class="sxs-lookup"><span data-stu-id="121d2-111">You can select one of the following Azure AD properties:</span></span>

| <span data-ttu-id="121d2-112">Azure AD プロパティ</span><span class="sxs-lookup"><span data-stu-id="121d2-112">Azure AD property</span></span>    | <span data-ttu-id="121d2-113">定義</span><span class="sxs-lookup"><span data-stu-id="121d2-113">Definition</span></span>           | <span data-ttu-id="121d2-114">例</span><span class="sxs-lookup"><span data-stu-id="121d2-114">Example</span></span>         |
| :------------------- | :------------------- |:--------------- |
| <span data-ttu-id="121d2-115">ユーザー プリンシパル名 (UPN)</span><span class="sxs-lookup"><span data-stu-id="121d2-115">User Principal Name (UPN)</span></span>  | <span data-ttu-id="121d2-116">UPN は、UPN プレフィックス (ユーザーアカウント名) と UPN サフィックス (DNS ドメイン名) で構成されます。</span><span class="sxs-lookup"><span data-stu-id="121d2-116">A UPN consists of a UPN prefix (the user account name) and a UPN suffix (a DNS domain name).</span></span> <span data-ttu-id="121d2-117">プレフィックスは、"@" 記号を使用してサフィックスと共に結合されます。</span><span class="sxs-lookup"><span data-stu-id="121d2-117">The prefix is joined with the suffix using the "@" symbol.</span></span> | <span data-ttu-id="121d2-118">us1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="121d2-118">us1@contoso.onmicrosoft.com</span></span> |
| <span data-ttu-id="121d2-119">Azure AD ID</span><span class="sxs-lookup"><span data-stu-id="121d2-119">Azure AD ID</span></span>                 | <span data-ttu-id="121d2-120">特定のユーザーの Azure AD ID は、ユーザーの一意の GUID です。</span><span class="sxs-lookup"><span data-stu-id="121d2-120">An Azure AD ID for a given user is the unique GUID of the user.</span></span>                 | <span data-ttu-id="121d2-121">58006c96-9e6e-45ea-8c88-4a56851eefad</span><span class="sxs-lookup"><span data-stu-id="121d2-121">58006c96-9e6e-45ea-8c88-4a56851eefad</span></span>            |
| <span data-ttu-id="121d2-122">Active Directory のセキュリティ ID (SID)</span><span class="sxs-lookup"><span data-stu-id="121d2-122">Active Directory Security ID (SID)</span></span>                  | <span data-ttu-id="121d2-123">SID (セキュリティ識別子) は、Active Directory がオブジェクトをセキュリティプリンシパルとして識別するために使用する一意の識別子です。</span><span class="sxs-lookup"><span data-stu-id="121d2-123">SID (Security Identifier) is a unique identifier that Active Directory uses to identify objects as security principal.</span></span>                  | <span data-ttu-id="121d2-124">S-1-5-21-453406510-812318184-4183662089</span><span class="sxs-lookup"><span data-stu-id="121d2-124">S-1-5-21-453406510-812318184-4183662089</span></span>             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a><span data-ttu-id="121d2-125">2. マッピングする Azure AD 以外のユーザーのプロパティを選択する</span><span class="sxs-lookup"><span data-stu-id="121d2-125">2. Select non-Azure AD user properties to map</span></span>

<span data-ttu-id="121d2-126">データソースから引き出された非 Azure AD プロパティを選択して、に正規表現を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="121d2-126">You can select non-Azure AD properties pulled from your data source to apply regular expressions on.</span></span> <span data-ttu-id="121d2-127">データソース内のこれらのプロパティの詳細については、「 [ServiceNow](servicenow-connector.md) 」および「 [Salesforce](salesforce-connector.md) 」のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="121d2-127">To learn more about where to find these properties in your data source, see the [ServiceNow](servicenow-connector.md) and [Salesforce](salesforce-connector.md) pages.</span></span>  

<span data-ttu-id="121d2-128">ドロップダウンから非 Azure AD ユーザープロパティを選択し、それらのユーザープロパティ値に適用する正規表現を指定できます。</span><span class="sxs-lookup"><span data-stu-id="121d2-128">You can select a non-Azure AD user property from the dropdown and provide a regular expression to be applied on those user property values.</span></span> <span data-ttu-id="121d2-129">正規表現の詳細については、「 [正規表現の参照]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="121d2-129">To learn more about regular expressions, see [regular expression reference]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference).</span></span>  

<span data-ttu-id="121d2-130">正規表現と、サンプル文字列に適用される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="121d2-130">Below are some examples of regular expressions and their outputs applied to a sample string:</span></span> 

| <span data-ttu-id="121d2-131">サンプル文字列</span><span class="sxs-lookup"><span data-stu-id="121d2-131">Sample String</span></span>                  | <span data-ttu-id="121d2-132">正規表現</span><span class="sxs-lookup"><span data-stu-id="121d2-132">Regular expression</span></span>                 | <span data-ttu-id="121d2-133">サンプル文字列の正規表現の出力</span><span class="sxs-lookup"><span data-stu-id="121d2-133">Output of regular expression on sample string</span></span>           |
| :------------------- | :------------------- |:---------------|
| <span data-ttu-id="121d2-134">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="121d2-134">Alexis Vasquez</span></span>  | <span data-ttu-id="121d2-135">.\*</span><span class="sxs-lookup"><span data-stu-id="121d2-135">.\*</span></span> | <span data-ttu-id="121d2-136">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="121d2-136">Alexis Vasquez</span></span> |
| <span data-ttu-id="121d2-137">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="121d2-137">Alexis Vasquez</span></span>                 | <span data-ttu-id="121d2-138">..$</span><span class="sxs-lookup"><span data-stu-id="121d2-138">..$</span></span>                 | <span data-ttu-id="121d2-139">ez</span><span class="sxs-lookup"><span data-stu-id="121d2-139">ez</span></span>            |
| <span data-ttu-id="121d2-140">Alexis Vasquez</span><span class="sxs-lookup"><span data-stu-id="121d2-140">Alexis Vasquez</span></span>                  | <span data-ttu-id="121d2-141">(\w +) $</span><span class="sxs-lookup"><span data-stu-id="121d2-141">(\w+)$</span></span>                  | <span data-ttu-id="121d2-142">Vasquez</span><span class="sxs-lookup"><span data-stu-id="121d2-142">Vasquez</span></span>             |

<span data-ttu-id="121d2-143">の式と同じ数の非 Azure AD ユーザープロパティを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="121d2-143">You can add as many non-Azure AD user properties as you would like expressions for.</span></span> <span data-ttu-id="121d2-144">最終的な式で保証されている場合は、異なる正規表現を同じユーザープロパティに適用できます。</span><span class="sxs-lookup"><span data-stu-id="121d2-144">You can apply different regular expressions to the same user property if your final formula warrants that.</span></span>  

### <a name="3-create-formula-to-complete-mapping"></a><span data-ttu-id="121d2-145">3. マッピングを完了するための数式を作成します。</span><span class="sxs-lookup"><span data-stu-id="121d2-145">3. Create formula to complete mapping</span></span>

<span data-ttu-id="121d2-146">Azure 以外の各 AD ユーザープロパティに適用された正規表現の出力を結合して、手順1で選択した Azure AD プロパティを形成できます。</span><span class="sxs-lookup"><span data-stu-id="121d2-146">You can combine the outputs of the regular expressions applied to each of your non-Azure AD user properties to form the Azure AD property selected in step 1.</span></span>

<span data-ttu-id="121d2-147">[式] ボックスで、"" は、 {0} 選択した *最初* の非 Azure 広告プロパティに適用された正規表現の出力に対応しています。</span><span class="sxs-lookup"><span data-stu-id="121d2-147">In the formula box, "{0}" corresponds to the output of the regular expression applied to the *first* non-Azure AD property you selected.</span></span> <span data-ttu-id="121d2-148">" {1} " は、選択した *2 番目* の非 Azure 広告プロパティに適用された正規表現の出力に対応しています。</span><span class="sxs-lookup"><span data-stu-id="121d2-148">"{1}" corresponds to the output of the regular expression applied to the *second* non-Azure AD property you selected.</span></span> <span data-ttu-id="121d2-149">" {2} " は、 *3 番目* の非 Azure AD プロパティに適用された正規表現の出力に対応しています。</span><span class="sxs-lookup"><span data-stu-id="121d2-149">"{2}" corresponds to the output of the regular expression applied to the *third* non-Azure AD property, and so on.</span></span>  

<span data-ttu-id="121d2-150">次に、サンプルの正規表現出力と数式出力を含む数式の例をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="121d2-150">Below are some examples of formulas with sample regular expression outputs and formula outputs:</span></span> 

| <span data-ttu-id="121d2-151">サンプル式</span><span class="sxs-lookup"><span data-stu-id="121d2-151">Sample formula</span></span>                  | <span data-ttu-id="121d2-152">{0}サンプルユーザーの値</span><span class="sxs-lookup"><span data-stu-id="121d2-152">Value of {0} on sample user</span></span>                 | <span data-ttu-id="121d2-153">{1}サンプルユーザーの値</span><span class="sxs-lookup"><span data-stu-id="121d2-153">Value of {1} on sample user</span></span>           | <span data-ttu-id="121d2-154">数式の出力</span><span class="sxs-lookup"><span data-stu-id="121d2-154">Output of formula</span></span>                  |
| :------------------- | :------------------- |:---------------|:---------------|
| <span data-ttu-id="121d2-155">{0}.{1}@contoso .com</span><span class="sxs-lookup"><span data-stu-id="121d2-155">{0}.{1}@contoso.com</span></span>  | <span data-ttu-id="121d2-156">担当</span><span class="sxs-lookup"><span data-stu-id="121d2-156">firstname</span></span> | <span data-ttu-id="121d2-157">社員</span><span class="sxs-lookup"><span data-stu-id="121d2-157">lastname</span></span> |<span data-ttu-id="121d2-158">firstname.lastname@contoso.com</span><span class="sxs-lookup"><span data-stu-id="121d2-158">firstname.lastname@contoso.com</span></span>
| <span data-ttu-id="121d2-159">{0}@domain .com</span><span class="sxs-lookup"><span data-stu-id="121d2-159">{0}@domain.com</span></span>                 | <span data-ttu-id="121d2-160">userid</span><span class="sxs-lookup"><span data-stu-id="121d2-160">userid</span></span>                 |             |<span data-ttu-id="121d2-161">userid@domain.com</span><span class="sxs-lookup"><span data-stu-id="121d2-161">userid@domain.com</span></span>

<span data-ttu-id="121d2-162">数式を入力した後で、必要に応じて、[ **プレビュー** ] をクリックして、データソースから5つのランダムユーザーのプレビューを表示し、それぞれのユーザーマッピングを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="121d2-162">After you provide your formula, you can optionally click **Preview** to see a preview of 5 random users from your data source with their respective user mappings applied.</span></span> <span data-ttu-id="121d2-163">プレビューの出力には、手順2でユーザーが選択した非 Azure AD ユーザープロパティの値と、そのユーザーの手順3で提供された最終的な式の出力が含まれています。</span><span class="sxs-lookup"><span data-stu-id="121d2-163">The output of the preview includes the value of the non-Azure AD user properties selected in step 2 for those users and the output of the final formula provided in step 3 for that user.</span></span> <span data-ttu-id="121d2-164">また、「成功」または「失敗」アイコンを使用して、式の出力をテナントの Azure AD ユーザーに解決できるかどうかも示します。</span><span class="sxs-lookup"><span data-stu-id="121d2-164">It also indicates whether the output of the formula could be resolved to an Azure AD user in your tenant via a "Success" or "Failed" icon.</span></span>  

>[!NOTE]
><span data-ttu-id="121d2-165">[ **プレビュー**] をクリックした後、1つ以上のユーザーマッピングの状態が "Failed" になっている場合でも、接続の作成を続行できます。</span><span class="sxs-lookup"><span data-stu-id="121d2-165">You can still proceed with creating your connection if one or more user mappings have a "Failed" status after you click **Preview**.</span></span> <span data-ttu-id="121d2-166">プレビューには、5つのランダムユーザーと、データソースからのマッピングが表示されます。</span><span class="sxs-lookup"><span data-stu-id="121d2-166">The preview shows 5 random users and their mappings from your data source.</span></span> <span data-ttu-id="121d2-167">指定したマッピングですべてのユーザーがマップされていない場合は、この場合に遭遇する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="121d2-167">If the mapping you provide does not map all users, you may experience this case.</span></span>

## <a name="sample-non-azure-ad-mapping"></a><span data-ttu-id="121d2-168">サンプルの非 Azure AD マッピング</span><span class="sxs-lookup"><span data-stu-id="121d2-168">Sample non-Azure AD mapping</span></span>

<span data-ttu-id="121d2-169">サンプルの非 Azure AD マッピングについては、以下のスナップショットを参照してください。</span><span class="sxs-lookup"><span data-stu-id="121d2-169">See the snapshot below for a sample non-Azure AD mapping.</span></span>

![非 Azure AD マッピングページに記入する方法のサンプルスナップショット](media/non-aad-mapping.png)

## <a name="limitations"></a><span data-ttu-id="121d2-171">制限事項</span><span class="sxs-lookup"><span data-stu-id="121d2-171">Limitations</span></span>  

- <span data-ttu-id="121d2-172">すべてのユーザーに対して1つのマッピングのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="121d2-172">Only one mapping is supported for all users.</span></span> <span data-ttu-id="121d2-173">条件付きマッピングはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="121d2-173">Conditional mappings are not supported.</span></span>  

- <span data-ttu-id="121d2-174">接続が公開されると、マッピングを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="121d2-174">You cannot change your mapping once the connection is published.</span></span>  

- <span data-ttu-id="121d2-175">現時点では、非 AAD ユーザープロパティに対する regex ベースの式のみが変換に対してサポートされています。</span><span class="sxs-lookup"><span data-stu-id="121d2-175">Only regex-based expressions against the non-AAD user properties are currently supported for the transformation.</span></span>

- <span data-ttu-id="121d2-176">マッピング先として選択できる Azure AD id は3つだけです (UPN、Azure AD ID、および AD SID)。</span><span class="sxs-lookup"><span data-stu-id="121d2-176">There are only 3 Azure AD identities you can choose to map to (UPN, Azure AD ID, and AD SID).</span></span>