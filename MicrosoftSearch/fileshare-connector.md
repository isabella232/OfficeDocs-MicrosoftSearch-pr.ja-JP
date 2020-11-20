---
title: ファイル共有コネクタ
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search 用のファイル共有コネクタをセットアップする
ms.openlocfilehash: c11c407016315e638205adddddd17d90bbe6b33d
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367740"
---
# <a name="file-share-connector"></a>ファイル共有コネクタ

ファイル共有グラフコネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有を検索できます。

この記事は、Microsoft 365 管理者またはファイル共有コネクタを構成、実行、および監視するユーザーを対象としています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

## <a name="install-graph-connector-agent"></a>Graph connector エージェントのインストール

Windows ファイル共有にインデックスを作成するために、 [Graph connector エージェント](on-prem-agent.md) ソフトウェアをインストールして登録する必要があります。

## <a name="content-requirements"></a>コンテンツの要件

### <a name="file-types"></a>ファイルの種類

次の形式のコンテンツをインデックス処理して検索することができます。 DOC、.DOCM、.DOCX、ドット、.DOTX、EML、GIF、HTML、JPEG、.MHT、MHTML、MSG、NWS、OBD、OBD、ODP、XLB、PPT、PPTM、.PPTX、TXT、、XLC、.XLSB、XLS、.XLSX、、XLXM、XML、XPS、および ZIP。 これらの書式のテキストの内容のみがインデックス化されます。 すべてのマルチメディアコンテンツは無視されます。 この形式に属さないファイルでは、メタデータのみがインデックス化されます。

### <a name="file-size-limits"></a>ファイル サイズの制限を超えている

サポートされているファイルの最大サイズは 100 MB です。 100 MB を超えるファイルはインデックス付けされません。 処理後の最大サイズ制限は 4 MB です。 ファイルのサイズが 4 MB に達すると、処理は停止します。 そのため、ファイルに含まれる一部の語句は検索に使用できない場合があります。

## <a name="connect-to-a-data-source"></a>データソースへの接続

[ **データソースへの接続** ] ページで、[ **ファイル共有** ] を選択し、名前、接続 ID、および説明を指定します。 次のページで、ファイル共有へのパスを指定し、以前にインストールしたグラフコネクタエージェントを選択します。 ファイル共有内のすべてのファイルに対する読み取りアクセス権を持つ [Microsoft Windows](https://microsoft.com/windows) ユーザーアカウントの資格情報を入力します。

## <a name="preserve-last-access-time"></a>最終アクセス時刻を保持する

コネクタがファイルをクロールしようとすると、そのメタデータの "最終アクセス時刻" フィールドが更新されます。 そのフィールドに依存していて、コネクタがアクセスするときにそのフィールドを更新したくない場合は、 **[詳細設定** ] ページでこのオプションを構成できます。

## <a name="manage-search-permissions"></a>検索アクセス許可を管理する

共有アクセス制御リストまたは新しいテクノロジファイルシステム (NTFS) アクセス制御リストに基づいて、任意のファイルを検索するアクセス許可を制限することができます。 [共有アクセス制御リスト] を使用する場合は、[ **詳細設定** ] ページで適切なオプションを選択します。 NTFS アクセス制御リストを使用する場合は、[ **検索権限の管理** ] ページで適切なオプションを選択します。

## <a name="assign-property-labels"></a>プロパティのラベルを割り当てる

各ラベルに source プロパティを割り当てるには、オプションのメニューから選択します。 この手順は必須ではありませんが、いくつかのプロパティラベルを使用することで、検索の関連性が向上し、エンドユーザーの検索結果がより正確になります。

## <a name="manage-schema"></a>スキーマを管理する

[**スキーマの管理**] 画面で、プロパティに関連付けられているスキーマの属性 (**クエリ** 可能、**検索****可能、取得可能、および****絞り込み可能な**) を変更し、オプションのエイリアスを追加して、 **Content** プロパティを選択することができます。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する

推奨される既定の更新スケジュール間隔は15分ですが、ユーザーの設定に基づいて変更することができます。
