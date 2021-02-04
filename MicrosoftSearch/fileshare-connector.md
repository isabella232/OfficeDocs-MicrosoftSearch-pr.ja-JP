---
title: Microsoft Search 用のファイル共有 Graph コネクタ
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Microsoft Search のファイル共有 Graph コネクタをセットアップする
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097423"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>ファイル共有 Graph コネクタ

ファイル共有 Graph コネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有を検索できます。

> [!NOTE]
> Graph コネクタ [**のセットアップに関する記事を読**](configure-connector.md) んで、Graph コネクタの一般的なセットアップ プロセスを理解してください。

## <a name="before-you-get-started"></a>使用を開始する前に

### <a name="install-the-graph-connector-agent"></a>Graph コネクタ エージェントをインストールする

Windows ファイル共有のインデックスを作成するには、Graph コネクタ エージェントをインストールして登録する必要があります。 詳細 [については、「Graph コネクタ エージェントのインストール」](on-prem-agent.md) を参照してください。  

### <a name="content-requirements"></a>コンテンツの要件

### <a name="file-types"></a>ファイルの種類

インデックスを作成して検索できる形式は DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPTM、PPTM、PPTX、TXT、XLB、XLC、XLSB、XLS、XLSX、XLT、XLXM、XML、XPS、ZIP。 これらの形式のテキスト コンテンツだけがインデックス付けされます。 すべてのマルチメディア コンテンツは無視されます。 この形式に属さないファイルでは、メタデータだけではインデックスが作成されます。

### <a name="file-size-limits"></a>ファイル サイズの制限を超えている

サポートされるファイル の最大サイズは 100 MB です。 100 MB を超えるファイルにはインデックスが作成されません。 処理後の最大サイズ制限は 4 MB です。 ファイルのサイズが 4 MB に達すると処理が停止します。 したがって、ファイル内に存在する一部の語句は検索に使用できない場合があります。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターで Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

[データ ソース **への接続] ページ** で、[ **ファイル共有]** を選択し、名前、接続 ID、および説明を入力します。 次のページで、ファイル共有へのパスを指定し、以前にインストールした Graph コネクタ エージェントを選択します。 ファイル共有内のすべてのファイルへの読み取りアクセス権を持つ [Microsoft Windows](https://microsoft.com/windows) ユーザー アカウントの資格情報を入力します。

### <a name="preserve-last-access-time"></a>最終アクセス時刻を保持する

コネクタがファイルをクロールしようとすると、そのメタデータの "最終アクセス時刻" フィールドが更新されます。 アーカイブ ソリューションとバックアップ ソリューションのフィールドに依存し、コネクタがアクセスするときに更新しない場合は、[詳細設定] ページでこのオプション **を構成** できます。

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する

共有アクセス制御リストまたは新しいテクノロジ ファイル システム (NTFS) アクセス制御リストに基づいて、任意のファイルを検索するアクセス許可を制限できます。 アクセス制御リストの共有を使用する場合は、[詳細設定] ページで適切 **なオプションを選択** します。 NTFS アクセス制御リストを使用する場合は、[検索アクセス許可の管理] ページ **で適切なオプションを選択** します。

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>手順 8: 接続を確認する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
