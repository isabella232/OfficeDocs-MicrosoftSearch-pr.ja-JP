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
ROBOTS: NoIndex
description: Microsoft Search のファイル共有コネクタをセットアップする
ms.openlocfilehash: bf9fb730abd4ca6e42b681893525bbe3dd8a1419
ms.sourcegitcommit: 249f41723dd6fda1e93ee1a8f3f7571ef066454b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750899"
---
# <a name="file-share-connector"></a>ファイル共有コネクタ

ファイル共有 Graph コネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有を検索できます。

この記事は、Microsoft 365 管理者またはファイル共有コネクタを構成、実行、および監視するユーザーを対象にしています。 コネクタとコネクタの機能、制限事項、およびトラブルシューティングの手法を構成する方法について説明します。

## <a name="install-graph-connector-agent"></a>Graph コネクタ エージェントをインストールする

Windows ファイル共有のインデックスを作成するには、Graph コネクタ エージェント ソフトウェアをインストール [して登録する必要](on-prem-agent.md) があります。

## <a name="content-requirements"></a>コンテンツの要件

### <a name="file-types"></a>ファイルの種類

インデックスを作成して検索できる形式は DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPTM、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLSX、XLT、XLXM、XML、XPS、ZIP。 これらの形式のテキスト コンテンツだけがインデックス付けされます。 すべてのマルチメディア コンテンツは無視されます。 この形式に属さないファイルでは、メタデータだけではインデックスが作成されます。

### <a name="file-size-limits"></a>ファイル サイズの制限を超えている

サポートされるファイル の最大サイズは 100 MB です。 100 MB を超えるファイルにはインデックスが作成されません。 処理後の最大サイズ制限は 4 MB です。 ファイルのサイズが 4 MB に達すると処理が停止します。 したがって、ファイル内に存在する一部の語句は検索に使用できない場合があります。

## <a name="connect-to-a-data-source"></a>データ ソースに接続する

[データ ソース **への接続] ページ** で、[ **ファイル共有]** を選択し、名前、接続 ID、および説明を入力します。 次のページで、ファイル共有へのパスを指定し、以前にインストールした Graph コネクタ エージェントを選択します。 ファイル共有内のすべてのファイルへの読み取りアクセス権を持つ [Microsoft Windows](https://microsoft.com/windows) ユーザー アカウントの資格情報を入力します。

## <a name="preserve-last-access-time"></a>最終アクセス時刻を保持する

コネクタがファイルをクロールしようとすると、そのメタデータの "最終アクセス時刻" フィールドが更新されます。 アーカイブ ソリューションとバックアップ ソリューションのフィールドに依存し、コネクタがアクセスするときに更新しない場合は、[詳細設定] ページでこのオプション **を構成** できます。

## <a name="manage-search-permissions"></a>検索のアクセス許可を管理する

共有アクセス制御リストまたは新しいテクノロジ ファイル システム (NTFS) アクセス制御リストに基づいて、任意のファイルを検索するアクセス許可を制限できます。 アクセス制御リストの共有を使用する場合は、[詳細設定] ページで適切 **なオプションを選択** します。 NTFS アクセス制御リストを使用する場合は、[検索アクセス許可の管理] ページ **で適切なオプションを選択** します。

## <a name="assign-property-labels"></a>プロパティ ラベルを割り当てる

オプションのメニューから選択すると、各ラベルにソース プロパティを割り当てできます。 この手順は必須ではありませんが、一部のプロパティ ラベルを使用すると、検索の関連性が向上し、エンド ユーザーの検索結果の精度が向上します。

## <a name="manage-schema"></a>スキーマを管理する

[スキーマの管理] 画面で、プロパティに関連付けられているスキーマ属性 **(クエリ** 可能、**検索** 可能、取得可能、絞り込み **可能)** を変更し、オプションのエイリアスを追加して **、Content** プロパティを選択できます。

## <a name="set-the-refresh-schedule"></a>更新スケジュールを設定する

推奨される既定の更新スケジュール間隔は 15 分ですが、設定に基づいて変更できます。

## <a name="result-layout"></a>結果レイアウト

ファイル 共有コネクタには、ファイル パスへの移動に役立つ適切なアイコンとコントロールが含まれていますので、既定の結果レイアウトを使用してファイル共有コネクタの結果を表示することをお勧めします。 新しい結果レイアウトを作成すると、既定のレイアウトが上書きされます。
