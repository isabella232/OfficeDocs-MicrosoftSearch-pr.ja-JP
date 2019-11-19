---
title: コネクタのプレビュー
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search の Microsoft Graph コネクタプレビューに関する情報を確認します。
ms.openlocfilehash: 6080674e1a6b789cbe5b3492f93f5f932b536e53
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699370"
---
# <a name="microsoft-graph-connectors-preview"></a>Microsoft Graph コネクタのプレビュー

Microsoft Graph のコネクタ、インデックス Api、および検索 Api は現在プレビュー段階です。 コネクタ機能へのアクセスを取得するには、 <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">Microsoft Graph Connector preview のサインアップフォーム</a>を送信して、プレビュープログラムへの参加を要求する必要があります。 これは初期のプレビューであり、サービスレベルの保証はありません。 お客様には、コネクタの機能を試してフィードバックを提供することをお勧めします。 プレビュー期間中は、運用のためにコネクタを使用することはお勧めしません。

## <a name="set-up-targeted-release"></a>対象となるリリースのセットアップ
コネクタを試行するには、組織内のすべてのユーザーに対して**対象となるリリース**オプションが設定されている必要があります。 対象となるリリース要件は、選択した次のプレビュー環境に関係なく適用されます。
対象となるリリースオプションの詳細と設定方法については、「 <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">Office 365 で標準または対象指定リリースオプションを設定</a>する」を参照してください。

## <a name="choose-a-preview-environment"></a>プレビュー環境を選択する 
コネクタ、インデックス Api、および検索 Api を試すには、次の2つの方法をお勧めします。
1. **テナントをテスト**します。  テストテナントを使用して、Microsoft Graph コネクタのプレビューを試してみることをお勧めします。
2. **サイトコレクションをテスト**します。 テストテナントがない場合は、テストサイトコレクションを作成してコネクタ機能を試すことができます。 組織内の他の場所にある検索ページに影響を及ぼさずに、コネクタからの結果を表示するには、そのサイトコレクションの検索機能のみをカスタマイズします。

## <a name="preview-limitations"></a>プレビューの制限事項
プレビューリリースには、次の制限があります。
* 取り込みスループットは、1秒あたり約4アイテムに調整されます。
* スキーマの更新はサポートされていません。 接続設定を作成した後、スキーマを更新する方法はありません。 接続を削除して再作成することはできません。
* インデックスが作成されたコンテンツは、カスタム縦の下にある検索結果ページにのみ表示されます。 この制限は、ユーザー設定の種類のコンテンツに適用されます。
* 一般的な使用を開始する前に、プレビュー期間中にセットアップした接続を削除してから再作成する必要がある場合があります。 これらの接続は、製品の改善に加えられた変更に互換性がない場合は機能しません。
* 接続制限があります。 各テナントは最大10個の接続を作成できます。
