---
title: Microsoft Graph コネクタの管理Microsoft Search
ms.author: mecampos
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
description: Microsoft Graph コネクタを管理Microsoft Search。
ms.openlocfilehash: 0a4165af84cc11fbba4239f0204a3a7f3ce4fb25
ms.sourcegitcommit: d276bfd1e03d1cdc1f51f70368df333da1d0111a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2021
ms.locfileid: "58408210"
---
# <a name="monitor-your-connections"></a>接続を監視する

コネクタにアクセスして管理するには、テナントの検索管理者として指定されている必要があります。 テナント管理者に問い合わせて、検索管理者の役割を準備します。

## <a name="connection-operations"></a>接続操作

[コネクタ][タブの [コネクタ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)] タブに[移動](https://admin.microsoft.com)Microsoft 365 管理センター。

コネクタの種類ごとに[、次Microsoft 365 管理センター](https://admin.microsoft.com)に示す操作がサポートされます。

操作​​ | Microsoft 提供の Graph コネクタ | パートナーまたはGraphコネクタ
--- | --- | ---
接続の追加 | :heavy_check_mark: (「セットアップの概要[」を参照)](configure-connector.md) | :x: (パートナーまたはカスタムビルドのコネクタ管理者 UX を参照)
接続を削除する | :heavy_check_mark: | :heavy_check_mark:
発行済み接続の編集 | :heavy_check_mark: 名前と説明<br></br> :heavy_check_mark: 接続設定<br></br> :heavy_check_mark: プロパティ ラベル<br></br> :heavy_check_mark: スキーマ<br></br> :heavy_check_mark: 更新スケジュール<br></br> | :heavy_check_mark: 名前<br></br> :heavy_check_mark: 説明
下書き接続の編集 | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a>接続状態を監視する

接続を作成すると、処理されたアイテムの数が [コネクタ]タブの [コネクタ]**ページにMicrosoft Search** されます。 最初のフル クロールが正常に完了すると、定期的な増分クロールの進行状況が表示されます。 このページでは、コネクタの毎日の操作とログとエラー履歴の概要について説明します。

5 つの状態が各接続 **に対して [状態** ] 列に表示されます。

* **同期します**。 コネクタは、ソースからのデータをクロールして、既存のアイテムにインデックスを付け、更新を行います。

* **準備** 完了: 接続の準備が完了し、アクティブなクロールが実行されている状態はありません。 **前回の同期時間は** 、最後に成功したクロールが発生した時期を示します。 接続は、最後の同期時間と同じ新しい値です。

* **一時停止しました**。 クロールは、一時停止オプションを使用して管理者によって一時停止されます。 次のクロールは、手動で再開された場合にのみ実行されます。 ただし、この接続のデータは引き続き検索可能です。

* **失敗**。 接続に重大な障害が発生しました。 このエラーには、手動による介入が必要です。 管理者は、表示されるエラー メッセージに基づいて適切なアクションを実行する必要があります。 エラーが発生するまでインデックスが作成されたデータは検索可能です。

* **Delete Failed**. 接続の削除に失敗しました。 エラーの理由によっては、データに引き続きインデックスが作成される場合があります。アイテム クォータは引き続き使用され、接続に対してクロールが実行される場合があります。 この状態でもう一度接続を削除してみてください。

## <a name="monitor-your-index-quota-utilization"></a>インデックス クォータの使用率を監視する

使用可能なインデックスクォータと使用量は、コネクタのランディング ページに表示されます。

:::image type="content" alt-text="インデックス クォータ使用率バー。" source="media/quota_utilization.png" lightbox="media/quota_utilization.png":::

クォータ使用率バーは、組織によるクォータの消費に基づいてさまざまな状態を示します。

状態 | クォータ使用率レベル
--- | --- 
標準 | 0-79%
高い | 80-89%
致命的 | 90%-99%
Full | 100%

インデックスが作成されたアイテムの数も、接続ごとに表示されます。 各接続によってインデックス付けされたアイテムの数は、組織で使用可能な合計クォータに貢献します。

組織のインデックス クォータを超えると、すべてのアクティブな接続が影響を受け、それらの接続は制限を超 **えた状態で動作** します。 この状態では、アクティブな接続  

* 新しいアイテムを追加できない。

* 既存のアイテムを更新または削除できます。

これを修正するには、次の操作を行います。

* 組織のインデックス クォータを購入する方法については、「ライセンス要件と価格」 [を参照してください](licensing.md)。

* コンテンツが取り込み過ぎた接続を特定し、それらを更新して、割り当て量を設定するためにインデックスを作成する項目が少なすぎます。 接続を更新するには、削除して、少ないアイテムをもたらす新しい取り込みフィルターを使用して新しい接続を作成する必要があります。

* 1 つ以上の接続を完全に削除します。
