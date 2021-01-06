---
title: Power BI の回答を管理する
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
robots: NOINDEX:NOFOLLOW
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Power BI のレポートとデータが検索結果に表示される方法を管理する
ms.openlocfilehash: d775647b7cb2fca08ca7f693d4e1c8dd246d3599
ms.sourcegitcommit: f17d81385b304f379bdc75d44580f59c3242e672
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760877"
---
# <a name="manage-power-bi-answers"></a>Power BI の回答を管理する

ユーザーが情報に基づいた意思決定に必要なデータと分析を簡単に見つけやすくするために、Microsoft Search では Power BI ダッシュボードとレポートのサポートが追加されました。 Power BI 検索の利点の一部を次に示します。

* **使いやすい:** このすぐに利用できる検索機能は、組織全体で Power BI ダッシュボードとレポートを簡単かつ迅速に見つけるのに役立ちます。
* **より豊富なコンテンツ:** Power BI の検索結果をより便利にするために、コンテンツの種類 (ダッシュボードまたはレポート) や、そのコンテンツを所有するチームまたはユーザーなどの重要な情報が含まれます。
* **組み込みのデータ保護:** Power BI の結果は、ダッシュボードまたはレポートにアクセスできるユーザーにのみ表示されます。
* **統合検索エクスペリエンス:** 一貫性のあるエクスペリエンスを維持するために、Power BI の結果は、すべての検索エントリ ポイントで一貫しています。 どの場所を検索する場合でも、同じ外観で同じ結果が得られます。

## <a name="what-users-experience"></a>ユーザーのエクスぺリエンス

Microsoft Search ユーザーは、Windows 検索ボックス、SharePoint、Office 365、Bing から Power BI の結果を検索できます。 ユーザーは、次のようなクエリを使用してレポートとダッシュボードを検索できます。

* Power BI の概要 `<topic>`
* Power BI for `<topic>`
* `<topic>` Power BI ダッシュボードまたは Power BI ダッシュボード `<topic>`
* `<topic>` Power BI レポートまたは Power BI レポート `<topic>`
* `<topic>` Power BI 指標または Power BI 指標 `<topic>`
* `<topic>` Power BI スコアカードまたは Power BI スコアカード `<topic>`

上記の例を、販売、使用状況、容量、2021、Q1 など、探している情報に置き換え、Power BI から関連する結果を確認します。 `<topic>`

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="Power BI の回答と垂直方向の SERP のスクリーンショット" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>Power BI 検索を有効またはオフにする

Power BI の結果は、既定で組織に対して有効になっています。 Power BI 管理者は、いつでも無効にできます。 Power BI 管理ポータルで、[テナントの設定] に移動し、[Power BI のグローバル検索を使用 **する] 設定を無効** にします。 詳細については、管理ポータルの [「Power BI の管理」を参照してください](https://docs.microsoft.com/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview)。

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="Power BI の回答を有効または無効にする設定のスクリーンショット" border="true":::

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q: Power BI 検索は既定で有効になっていますか?**

**A:** うん。 Power BI 検索は、Microsoft Search に対して既定で有効になっています。 この機能には、テナント管理者が初めてセットアップする必要はありません。

**Q: 特定のグループまたはユーザーに対して Power BI 検索を有効または無効にできますか。**

**A:** 現時点では、組織全体でのみ有効または無効にできます。

**Q: Power BI 検索が無効になっている場合、Power BI の検索結果ページは非表示になりますか。**

**A:** いいえ。 Power BI の検索結果ページに、組織で現在利用できないというメッセージが表示されます。

**Q: Power BI ライセンスを持ってない場合、Power BI の検索結果ページが表示されますか。**

**A:** いいえ。 検索ユーザーが Power BI ライセンスを持たなかった場合、Power BI 検索結果ページは Microsoft Search の結果に表示されません。

**Q: アクセスできない Power BI 検索結果は表示されますか?**

**A:** いいえ。 Microsoft Search は、アクセスできる Power BI の結果のみを返します。

**Q: Power BI の検索結果 (レポートの種類やレポートの所有者など) をカスタマイズできますか。**

**A:** 現時点では、Power BI 検索結果に含まれるフィールドのカスタマイズはサポートされていません。
