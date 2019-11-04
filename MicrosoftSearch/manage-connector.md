---
title: Microsoft 検索用の Microsoft Graph コネクタを管理する
ms.author: v-pamcn
author: monaray
manager: mnirkhe
ms.date: 11/04/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft 検索用の Microsoft Graph コネクタを管理します。
ms.openlocfilehash: 5aab310a05d073221918a8aaa80ea1e06c818e51
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949947"
---
# <a name="manage-your-connector-for-microsoft-search"></a>Microsoft Search のためにコネクタを管理する

コネクタにアクセスして管理するには、テナントの検索管理者として指定する必要があります。 テナント管理者に連絡して、検索管理者ロールのプロビジョニングを行います。

## <a name="get-started"></a>作業の開始

1. [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。
2. [**設定** > ]**Microsoft 検索** > **コネクタ**に移動します。

各コネクタの種類について、 [Microsoft 365 管理センター](https://admin.microsoft.com)は次の表に示す操作をサポートしています。

**操作** | **Microsoft が構築したコネクタ** | **パートナーまたはカスタム作成コネクタ**
--- | --- | ---
接続を追加する | : heavy_check_mark: ( [Microsoft が作成したコネクタを構成するを](configure-connector.md)参照) | : x: (パートナーまたはカスタム構築コネクタ管理者 UX を参照してください)
接続の削除 | :heavy_check_mark: | :heavy_check_mark:
公開された接続を編集する | : heavy_check_mark: Name<br></br> : heavy_check_mark: Description<br></br> : heavy_check_mark: 外部データソースの認証資格情報<br></br> : heavy_check_mark: オンプレミスのデータソースのゲートウェイ資格情報<br></br> : heavy_check_mark: 更新スケジュール<br></br> | : heavy_check_mark: Name<br></br> : heavy_check_mark: Description
下書き接続を編集する | :heavy_check_mark: | エックス

## <a name="monitor-your-connection-status"></a>接続の状態を監視する
接続を作成すると、[ **Microsoft Search** ] ページの [**コネクタ**] タブに、処理されたアイテムの数が表示されます。 最初のフルクロールが正常に完了すると、定期的な増分クロールの進行状況が表示されます。 このページでは、コネクタの毎日の操作に関する情報と、ログおよびエラー履歴の概要を提供します。

各接続に対して、[**状態**] 列に4つの状態が表示されます。
* **同期**します。 コネクタは、ソースからデータをクロールして、既存のアイテムのインデックスを作成し、更新を行います。
* **Enabled**: 接続が有効になっていますが、アクティブなクロールが実行されていません。 **最終同期時刻**は、最後に成功したクロールがいつ発生したかを示します。 この接続は、最後の同期時刻と同じになります。
* **一時停止**します。 クロールは、[一時停止] オプションを使用して管理者によって一時停止されます。 次のクロールは、手動で再開した場合にのみ実行されます。 ただし、この接続からのデータは引き続き検索できます。
* **失敗しました**。 接続で重大なエラーが発生しました。 このエラーには手動での介入が必要です。 表示されるエラーメッセージに基づいて、管理者は適切なアクションを実行する必要があります。 エラーが発生するまでにインデックスが作成されたデータは検索可能になります。

### <a name="monitor-errors"></a>エラーを監視する
[**コネクタ**] タブ上の**アクティブな各コネクタ**について、既存のクロールエラーが [**エラー** ] タブに表示されます。タブには、エラーコード、各数、およびエラーログのダウンロードオプションが一覧表示されます。 次の画像の例を参照してください。 エラー**コード**を選択して、エラーの詳細を表示します。

![コネクタが選択されていて、このコネクタの3つのエラーを示す詳細ウィンドウがあるコネクタリスト。](media/errormonitoring1.png)

エラーの具体的な詳細を表示するには、エラーコードを選択します。 エラーの詳細とリンクを含む画面が表示されます。 最新のエラーが一番上に表示されます。 次の表の例を参照してください。

![コネクタが選択された状態で、コネクタのエラーの一覧が表示されている詳細ウィンドウを含むコネクタリスト。 ](media/errormonitoring2.png)

## <a name="preview-limitations"></a>プレビューの制限事項
* Microsoft によって作成されたコネクタを**公開**する場合、接続が作成されるまで数分かかる場合があります。 その間、接続の状態は [保留中] と表示されます。 また、自動更新は行われないので、手動で更新する必要があります。
* [Microsoft 365 管理センター](https://admin.microsoft.com)は、接続が公開された後の**検索スキーマ**の表示と編集をサポートしていません。 検索スキーマを編集するには、接続を削除してから、新しい接続を作成します。
* 接続の**更新スケジュール**を管理すると、各セッション中に同期するアイテムの数が表示されます。 ただし、同期履歴は利用できません。
