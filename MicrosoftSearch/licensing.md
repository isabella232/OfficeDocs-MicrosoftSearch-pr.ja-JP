---
title: ライセンス要件と価格
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Global or Billing Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Graph コネクタのライセンス要件 Microsoft Search のパブリックプレビュー
ms.openlocfilehash: 04683a0fe15d4f76286d6637d97345eda57a0330
ms.sourcegitcommit: 995ce23d4e47a3456a02dba0ba7c9cd0de64528a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920672"
---
# <a name="license-requirements-and-pricing"></a>ライセンス要件と価格

この記事は、組織に対して追加の Graph connector のクォータを購入する方法について学習する必要があるグローバルまたは課金管理者を対象としています。

検索結果のコネクタのデータを表示するには、組織に対して有効な Microsoft 365 または Office 365 のライセンスと十分なグラフコネクタのクォータが必要です。 [Microsoft によるすべての Graph コネクタ](configure-connector.md)は無料です。 ただし、これらのコネクタからコンテンツを取り込むには、十分なインデックスクォータを持っている必要があります。

各 Microsoft 365 または Office 365 E5 ライセンスには、インデックスクォータの500アイテムが含まれています。これは、Graph コネクタからの取り込むコンテンツに対する組織のクォータにカウントされます。 たとえば、組織に100の Microsoft 365 E5 ライセンスがある場合、組織では、Graph コネクタのインデックスクォータに 100 x 500 = 5万アイテムがあります。

追加の Graph connector のクォータを購入するには、Microsoft アカウントマネージャーを使用するか、次の手順を実行します。

1. [Microsoft 365 管理センター](https://admin.microsoft.com)のナビゲーションメニューで、[ **課金 > 購入サービス** ] に移動します。
2. [サービスを購入する] ページの下部で、 **[アドオン] を選択し** ます。
3. [その **他のグラフコネクタの容量** ] を選択します。
4. [ **購入** ] を選択して、注文の設定を完了します。
5. [ **今すぐチェックアウト** ] を選択します。

>[!NOTE]
>現在、グラフコネクタは最大700万個のインデックスクォータをサポートしています。これには、Microsoft 365 または Office 365 E5 ライセンスにバンドルされている組み込みクォータが含まれます。 プラットフォームは将来的により高い制限をサポートします。 ご質問がある場合は、Microsoft サポートまたは Microsoft アカウントマネージャーにお問い合わせください。
