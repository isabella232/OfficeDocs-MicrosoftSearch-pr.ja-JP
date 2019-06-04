---
title: 高度な DNS 構成
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: CNAME を使用して DNS サーバーを構成することにより、ユーザーがシームレスなサインイン エクスペリエンスを利用できるようにします
ms.openlocfilehash: 6a291165df33f8acc99d247104e8e88cd35c3a0e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591361"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="57a69-103">高度な DNS 構成</span><span class="sxs-lookup"><span data-stu-id="57a69-103">Advanced DNS configuration</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57a69-104">この記事は、Bing 管理ポータルの Microsoft Search に適用されます。</span><span class="sxs-lookup"><span data-stu-id="57a69-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="57a69-105">ポータルを Microsoft 365 管理センターに移動しており、後で削除されます。</span><span class="sxs-lookup"><span data-stu-id="57a69-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="57a69-106">Microsoft 365 管理センターを使用して作業を開始することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57a69-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="57a69-107">[Microsoft Search の概要](overview-microsoft-search.md)。</span><span class="sxs-lookup"><span data-stu-id="57a69-107">Overview of Microsoft Search</span></span>
    
<span data-ttu-id="57a69-p102">Bing で組織内のユーザーを特定し、ユーザーが職場または学校のアカウントに正常にサインインできるようにするには、内部 DNS サーバーまたはプロキシを構成し、`www.bing.com` から `ms.bing.com` に解決できるようにします。そのためには、`ms.bing.com` の CNAME となるように `www.bing.com` の DNS エントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="57a69-p102">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="57a69-110">**名前**</span><span class="sxs-lookup"><span data-stu-id="57a69-110">**Name**</span></span>|<span data-ttu-id="57a69-111">**Type**</span><span class="sxs-lookup"><span data-stu-id="57a69-111">**Type**</span></span>|<span data-ttu-id="57a69-112">**値**</span><span class="sxs-lookup"><span data-stu-id="57a69-112">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="57a69-113">CNAME</span><span class="sxs-lookup"><span data-stu-id="57a69-113">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="57a69-p103">IP アドレスではなく CNAME を使用する方が推奨されているのは、IP アドレスが変更した場合であっても CNAME は引き続き機能するためです。このように DNS を変更すると、ユーザーが `www.bing.com` からアクセスする場合でも結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="57a69-p103">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="57a69-p104">この場合、クライアント マシンで追加構成は必要なく、ユーザーにシームレスはエクスペリエンスを提供できます。ユーザーが `bing.com` にアクセスすると、一貫性のある方法で自動的にサインインできます。自動的にサインインできない場合には、サインインするようメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="57a69-p104">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
