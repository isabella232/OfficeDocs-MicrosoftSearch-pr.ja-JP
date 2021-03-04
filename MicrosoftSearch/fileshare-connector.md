---
title: Microsoft Search のファイル共有グラフ コネクタ
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
description: Microsoft Search のファイル共有グラフ コネクタをセットアップする
ms.openlocfilehash: ed1c148a018ba9492a8a93685327bf43153d65d3
ms.sourcegitcommit: 6a7522d9aeaedeedaac096c485d3f343ce98d3d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421079"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>ファイル共有グラフ コネクタ

ファイル共有グラフ コネクタを使用すると、組織内のユーザーはオンプレミスの Windows ファイル共有を検索できます。

> [!NOTE]
> グラフ コネクタ [**の一般的なセットアップ**](configure-connector.md) プロセスについて詳しくは、Graph コネクタのセットアップに関する記事をご覧ください。

## <a name="before-you-get-started"></a>使用を開始する前に

### <a name="install-the-graph-connector-agent"></a>Graph コネクタ エージェントのインストール

Windows ファイル共有のインデックスを作成するには、Graph コネクタ エージェントをインストールして登録する必要があります。 詳細については [、「Graph コネクタ エージェントのインストール](on-prem-agent.md) 」を参照してください。  

### <a name="content-requirements"></a>コンテンツ要件

### <a name="file-types"></a>ファイルの種類

次の形式のコンテンツは、インデックスを作成して検索できます。DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPTM、PPTX、PPTX、TXT、XLB、XLC、XLSB、XLSX、XLT、XML、XML、XPS、および ZIP。 これらの形式のテキスト コンテンツだけがインデックス付けされます。 すべてのマルチメディア コンテンツは無視されます。 この形式に属していないファイルの場合は、メタデータだけでインデックスが作成されます。

### <a name="file-size-limits"></a>ファイル サイズの制限を超えている

サポートされるファイルの最大サイズは 100 MB です。 100 MB を超えるファイルはインデックス付けされません。 処理後の最大サイズ制限は 4 MB です。 ファイルのサイズが 4 MB に達すると、処理が停止します。 したがって、ファイルに存在する一部の語句が検索に使用できない場合があります。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターに Graph コネクタを追加する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

[データ **ソースへの接続] ページで、[** ファイル共有] **を** 選択し、名前、接続 ID、および説明を指定します。 次のページで、ファイル共有へのパスを指定し、以前にインストールした Graph コネクタ エージェントを選択します。 ファイル共有内のすべてのファイルへの読み取りアクセス権を持つ [Microsoft Windows](https://microsoft.com/windows) ユーザー アカウントの資格情報を入力します。

### <a name="preserve-last-access-time"></a>最後のアクセス時間を保持する

コネクタがファイルをクロールしようとすると、そのメタデータ内の "最終アクセス時刻" フィールドが更新されます。 アーカイブソリューションとバックアップ ソリューションのフィールドに依存し、コネクタがアクセスするときに更新しない場合は、[詳細設定] ページでこのオプション **を構成** できます。

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する

[検索アクセス許可の管理] ページで目的のオプションを選択することにより、Share Access Control Lists または New Technology File System (NTFS) Access Control Lists に基づいて任意のファイルを検索するアクセス許可を制限できます。  これらのアクセス制御リストで提供されるユーザー アカウントとグループは、Active Directory (AD) によって管理する必要があります。 ユーザー アカウント管理に他のシステムを使用している場合は、[すべてのユーザー] オプションを選択して、ユーザーがアクセス制限なしですべてのファイルを検索できます。 ただし、ユーザーがファイルを開く場合は、ソースで設定されたアクセス制御が適用されます。

既定では、フォルダーがネットワーク上で共有されている場合、Windows は Share ACL の 'Everyone' に対する 「読み取り」 アクセス許可を提供します。 [検索アクセス許可の管理] で [ACLの共有] を選択している場合、ユーザーはすべてのファイルを検索できます。 アクセスを制限する場合は、ファイル共有の 'Everyone' の 'Read' アクセスを削除し、目的のユーザーとグループにのみアクセスを提供します。 コネクタは次に、これらのアクセス制限を読み取り、それらを検索に適用します。

[ACL の共有] を選択できるのは、指定した共有パスが UNC パス形式に従う場合のみです。 UNC 形式のパスを作成するには、[共有] オプションの [高度な共有] に進む必要があります。

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](https://docs.microsoft.com/microsoftsearch/configure-connector)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
