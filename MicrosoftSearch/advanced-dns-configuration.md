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
description: CNAME を使用する DNS サーバーを構成することによって、ユーザーにシームレスなサインイン エクスペリエンスを確保します。
ms.openlocfilehash: fa797b95f346d6d03bd020da146bb330c715e392
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612443"
---
# <a name="advanced-dns-configuration"></a>高度な DNS 構成

Bing が常に、組織内のユーザーを識別し、職場、学校のアカウントに正常にサインインすることを確認、構成、内部 DNS サーバーまたはプロキシ サーバーから解決するのには`www.bing.com`を`ms.bing.com`。DNS エントリを作成するには、`www.bing.com`の CNAME を使用する`ms.bing.com`。
  
****

|**Name**|**種類**|**値**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
CNAME は引き続き IP アドレスが変更された場合の動作なので、IP アドレスではなく、CNAME を使用することが推奨されます。この DNS の変更を行ったら、結果が引き続き表示されます、ユーザーから来たかのように`www.bing.com`。 
  
これはクライアント ・ マシンの追加構成は必要ありません、ユーザーにシームレスなエクスペリエンスを提供します。移動すると`bing.com`に自動的にサインインしてさらに、一貫したするように指示されますがすることはできませんする署名されている場合自動的に、します。
