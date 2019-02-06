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
description: CNAME を使用して DNS サーバーを構成することにより、ユーザーがシームレスなサインイン エクスペリエンスを利用できるようにします
ms.openlocfilehash: fa797b95f346d6d03bd020da146bb330c715e392
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612443"
---
# <a name="advanced-dns-configuration"></a>高度な DNS 構成

Bing で組織内のユーザーを特定し、ユーザーが職場または学校のアカウントに正常にサインインできるようにするには、内部 DNS サーバーまたはプロキシを構成し、`www.bing.com` から `ms.bing.com` に解決できるようにします。そのためには、`ms.bing.com` の CNAME となるように `www.bing.com` の DNS エントリを作成します。
  
****

|**名前**|**Type**|**値**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
IP アドレスではなく CNAME を使用する方が推奨されているのは、IP アドレスが変更した場合であっても CNAME は引き続き機能するためです。このように DNS を変更すると、ユーザーが `www.bing.com` からアクセスする場合でも結果が表示されます。 
  
この場合、クライアント マシンで追加構成は必要なく、ユーザーにシームレスはエクスペリエンスを提供できます。ユーザーが `bing.com` にアクセスすると、一貫性のある方法で自動的にサインインできます。自動的にサインインできない場合には、サインインするようメッセージが表示されます。
