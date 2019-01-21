---
title: 高度な DNS の構成
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
description: CNAME を使用する DNS サーバーを構成することによって、ユーザーにシームレスなサインイン エクスペリエンスを確保します。
ms.openlocfilehash: f08fc4c29c4c4356a1616faab67fdebdd6c85839
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/18/2019
ms.locfileid: "29379025"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="06516-103">高度な DNS の構成</span><span class="sxs-lookup"><span data-stu-id="06516-103">Advanced DNS configuration</span></span>

<span data-ttu-id="06516-p101">Bing が常に、組織内のユーザーを識別し、職場、学校のアカウントに正常にサインインすることを確認、構成、内部 DNS サーバーまたはプロキシ サーバーから解決するのには`www.bing.com`を`ms.bing.com`。DNS エントリを作成するには、`www.bing.com`の CNAME を使用する`ms.bing.com`。</span><span class="sxs-lookup"><span data-stu-id="06516-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="06516-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="06516-106">**Name**</span></span>|<span data-ttu-id="06516-107">**種類**</span><span class="sxs-lookup"><span data-stu-id="06516-107">**Type**</span></span>|<span data-ttu-id="06516-108">**値**</span><span class="sxs-lookup"><span data-stu-id="06516-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="06516-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="06516-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="06516-p102">CNAME は引き続き IP アドレスが変更された場合の動作なので、IP アドレスではなく、CNAME を使用することが推奨されます。この DNS の変更を行ったら、結果が引き続き表示されます、ユーザーから来たかのように`www.bing.com`。</span><span class="sxs-lookup"><span data-stu-id="06516-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="06516-p103">これはクライアント ・ マシンの追加構成は必要ありません、ユーザーにシームレスなエクスペリエンスを提供します。移動すると`bing.com`に自動的にサインインしてさらに、一貫したするように指示されますがすることはできませんする署名されている場合自動的に、します。</span><span class="sxs-lookup"><span data-stu-id="06516-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
