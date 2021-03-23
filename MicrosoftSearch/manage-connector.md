---
title: Microsoft Search の Microsoft Graph コネクタを管理する
ms.author: monaray
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の Microsoft Graph コネクタを管理します。
ms.openlocfilehash: cba50d8eb558b4d74ed46554dc155d4f275b1332
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031721"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>接続を監視する

コネクタにアクセスして管理するには、テナントの検索管理者として指定されている必要があります。 テナント管理者に問い合わせて、検索管理者の役割を準備します。

## <a name="connection-operations"></a>接続操作

Microsoft 365 [管理センターの](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) [[コネクタ] タブに移動します](https://admin.microsoft.com)。

コネクタの種類ごとに [、Microsoft 365 管理](https://admin.microsoft.com) センターは次の表に示す操作をサポートしています。

Operation | Microsoft 提供の Graph コネクタ | パートナーコネクタまたはグラフ コネクタ
--- | --- | ---
接続の追加 | :heavy_check_mark: (「セットアップの概要[」を参照)](configure-connector.md) | :x: (パートナーまたはカスタムビルドのコネクタ管理者 UX を参照)
接続を削除する | :heavy_check_mark: | :heavy_check_mark:
発行済み接続の編集 | :heavy_check_mark: 名前と説明<br></br> :heavy_check_mark: 接続設定<br></br> :heavy_check_mark: プロパティ ラベル<br></br> :heavy_check_mark: スキーマ<br></br> :heavy_check_mark: 更新スケジュール<br></br> | :heavy_check_mark: 名前<br></br> :heavy_check_mark: 説明
下書き接続の編集 | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>接続状態を監視する

接続を作成すると、Microsoft Search ページの [コネクタ]タブに処理されたアイテムの数 **が表示** されます。 最初のフル クロールが正常に完了すると、定期的な増分クロールの進行状況が表示されます。 このページでは、コネクタの毎日の操作とログとエラー履歴の概要について説明します。

4 つの状態が各接続に対 **して [状態** ] 列に表示されます。

* **同期します**。 コネクタは、ソースからのデータをクロールして、既存のアイテムにインデックスを付け、更新を行います。

* **準備** 完了: 接続の準備が完了し、アクティブなクロールが実行されている状態はありません。 **前回の同期時間は** 、最後に成功したクロールが発生した時期を示します。 接続は、最後の同期時間と同じ新しい値です。

* **一時停止しました**。 クロールは、一時停止オプションを使用して管理者によって一時停止されます。 次のクロールは、手動で再開された場合にのみ実行されます。 ただし、この接続のデータは引き続き検索可能です。

* **失敗**。 接続に重大な障害が発生しました。 このエラーには、手動による介入が必要です。 管理者は、表示されるエラー メッセージに基づいて適切なアクションを実行する必要があります。 エラーが発生するまでインデックスが作成されたデータは検索可能です。

## <a name="monitor-your-index-quota-utilization"></a>インデックス クォータの使用率を監視する

使用可能なインデックスクォータと使用量は、コネクタのランディング ページに表示されます。

![インデックス クォータ使用率バー](media/quota_utilization.png)
 
>[!NOTE]
>プレビュー期間中、Graph コネクタを試しているすべての組織に、すべての接続で最大 200 万アイテムの無料の固定クォータが提供されました。 Graph コネクタが一般公開されている場合、プレビューで Graph コネクタを使用している組織では、2021 年 4 月 1 日に無料のクォータが期限切れになります。
>Microsoft が作成した ["Preview"](./connectors-overview.md) というラベルのグラフ コネクタは、組織の合計課金インデックス クォータには含まれません。 ただし、組織に対して構成できる最大接続数 10 と、組織が接続間でインデックスを作成できる最大 700 万アイテムの数にカウントされます。各接続は 700,000 アイテムに制限されます。 

クォータ使用率バーは、組織によるクォータの消費に基づいてさまざまな状態を示します。

状態 | クォータ使用率レベル
--- | --- 
標準 | 0-79%
高 | 80-89%
重大 | 90%-99%
Full | 100%

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

インデックスが作成されたアイテムの数も、接続ごとに表示されます。 各接続によってインデックス付けされたアイテムの数は、組織で使用可能な合計クォータに貢献します。

組織のインデックス クォータを超えると、すべてのアクティブな接続が影響を受け、それらの接続は制限を超 **えた状態で動作** します。 この状態では、アクティブな接続  

* 新しいアイテムを追加できない。

* 既存のアイテムを更新または削除できます。

これを修正するには、次の操作を行います。

* 組織のインデックス クォータを購入する方法については、「ライセンス要件と価格」 [を参照してください](licensing.md)。

* コンテンツが取り込み過ぎた接続を特定し、それらを更新して、割り当て量を設定するためにインデックスを作成する項目が少なすぎます。 接続を更新するには、削除して、少ないアイテムをもたらす新しい取り込みフィルターを使用して新しい接続を作成する必要があります。

* 1 つ以上の接続を完全に削除する