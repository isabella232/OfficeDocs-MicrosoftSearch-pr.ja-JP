---
title: Microsoft Search 用の Microsoft Graph コネクタを管理する
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用の Microsoft Graph コネクタを管理します。
ms.openlocfilehash: 5258f26a5c97be4ee9f90c7a8b2b9bb8fec447bc
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905932"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a>接続を監視する

コネクタにアクセスして管理するには、テナントの検索管理者として指定する必要があります。 テナント管理者に問い合わせて、検索管理者ロールのプロビジョニングを行います。

## <a name="connection-operations"></a>接続操作

Microsoft 365 [管理センターの](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) [ [コネクタ] タブに移動します](https://admin.microsoft.com)。

コネクタの種類ごとに [、Microsoft 365 管理](https://admin.microsoft.com) センターは次の表に示す操作をサポートします。

操作 | Microsoft が構築したコネクタ | パートナーまたはカスタムのコネクタ
--- | --- | ---
接続を追加する | :heavy_check_mark: [(「Microsoft が構築したコネクタを構成する」を参照)](configure-connector.md) | :x: (パートナーまたはカスタムビルドのコネクタ管理者 UX を参照)
接続を削除する | :heavy_check_mark: | :heavy_check_mark:
発行済み接続を編集する | :heavy_check_mark: 名前<br></br> :heavy_check_mark: 説明<br></br> :heavy_check_mark: 外部データ ソースの認証資格情報<br></br> :heavy_check_mark: オンプレミス データ ソースのゲートウェイ資格情報<br></br> :heavy_check_mark: 更新スケジュール<br></br> | :heavy_check_mark: 名前<br></br> :heavy_check_mark: 説明
下書き接続を編集する | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a>接続状態を監視する

接続を作成すると、処理されたアイテムの数が Microsoft Searchページの [コネクタ] タブ **に表示** されます。 最初のフル クロールが正常に完了すると、定期的な増分クロールの進行状況が表示されます。 このページには、コネクタの毎日の操作に関する情報と、ログとエラー履歴の概要が表示されます。

各接続に対して、[状態] 列に **次の 4** つの状態が表示されます。

* **同期中** です。 コネクタは、ソースからのデータをクロールして既存のアイテムのインデックスを作成し、更新を行います。

* **有効**: 接続が有効で、アクティブなクロールが実行されません。 **前回の同期時刻** は、前回成功したクロールがいつ行ったかを示します。 接続は最後の同期時刻と同じ最新の値です。

* **一時停止しました**。 クロールは、一時停止オプションを使用して管理者によって一時停止されます。 次のクロールは、手動で再開された場合にのみ実行されます。 ただし、この接続からのデータは引き続き検索可能です。

* **失敗**。 接続に重大な障害が発生しました。 このエラーには手動による介入が必要です。 管理者は、表示されたエラー メッセージに基づいて適切なアクションを実行する必要があります。 エラーが発生するまでインデックスが作成されたデータは検索可能です。

## <a name="monitor-your-index-quota-utilization"></a>インデックス クォータの使用率を監視する

使用可能なインデックス クォータと使用量は、コネクタのランディング ページに表示されます。

![インデックス クォータ使用率バー](media/quota_utilization.png)

>[!NOTE]
>プレビュー期間中に、Graph コネクタを試しているすべての組織に、すべての接続で最大 200 万アイテムの無料の固定クォータが提供されました。 Graph コネクタが一般公開される中、プレビューで Graph コネクタを使用している組織では、2021 年 2 月 1 日に無料クォータの有効期限が切れます。
>「プレビュー」とラベル付けされた[](connectors-preview.md)Microsoft が作成した Graph コネクタは、組織の課金インデックス クォータの合計には含まれません。 ただし、組織で構成できる接続の最大数は 10 件、接続間でインデックスを作成できるアイテムの最大数は 700 万アイテムにカウントされます。各接続は 700,000 アイテムに制限されています。 

クォータ使用率バーには、組織によるクォータの消費に基づいて、さまざまな状態が表示されます。

状態 | クォータの使用量
--- | ---
標準 | 1-69%
高い | 70-89%
重大 | 90%-99%
Full | 100%

インデックスが作成されたアイテムの数も、接続ごとに表示されます。 各接続によってインデックスが作成されたアイテムの数は、組織で使用可能なクォータの合計に貢献します。

組織のインデックス クォータを超えると、すべてのアクティブな接続が影響を受け、それらの接続は制限を超 **えた状態で動作** します。 この状態では、アクティブな接続  

* 新しいアイテムを追加できない。

* 既存のアイテムを更新または削除できます。

この問題を解決するには、次の操作を行います。

* ライセンス要件と価格で組織のインデックス クォータを [購入する方法について説明します](licensing.md)。

* 取り込まれたコンテンツが多すぎる接続を特定し、インデックスを作成する項目が少なく、クォータを使用できる容量を作り出すまで更新します。 接続を更新するには、新しい取り込みフィルターを使用して削除して新しい接続を作成する必要があります。このフィルターを使用すると、アイテム数が少なめになります。

* 1 つ以上の接続を完全に削除する