---
title: ファイル共有GraphコネクタMicrosoft Search
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: ファイル共有コネクタをGraphするMicrosoft Search
ms.openlocfilehash: af4c3996fdc8ac753404f4b4519175a9054fa18bce3862b0c5841c7bd5369cdd
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54533028"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a>ファイル共有Graphコネクタ

[ファイル共有] Graphコネクタを使用すると、組織内のユーザーがオンプレミスのファイル共有Windows検索できます。

> [!NOTE]
> コネクタの [**セットアッププロセスの一Graphについては**](configure-connector.md)、「Graph」を参照してください。

## <a name="before-you-get-started"></a>使用を開始する前に

### <a name="install-the-graph-connector-agent"></a>コネクタ エージェントGraphインストールする

ファイル共有にインデックスWindowsするには、コネクタ エージェントをインストールして登録Graph必要があります。 詳細については[、「Graphコネクタ エージェントをインストール](graph-connector-agent.md)する」を参照してください。  

### <a name="content-requirements"></a>コンテンツ要件

### <a name="file-types"></a>ファイルの種類

次の形式のコンテンツは、インデックスを作成して検索できます。DOC、 DOCM、DOCX、DOT、DOTX、EML、GIF、HTML、JPEG、MHT、MHTML、MSG、NWS、OBD、OBT、ODP、ODS、ODT、ONE、PDF、POT、PPS、PPTM、PPTX、PPTX、TXT、XLB、XLC、XLSB、XLSX、XLT、XML、XML、XPS、および ZIP。 これらの形式のテキスト コンテンツだけがインデックス付けされます。 すべてのマルチメディア コンテンツは無視されます。 この形式に属していないファイルの場合は、メタデータだけでインデックスが作成されます。

### <a name="file-size-limits"></a>ファイル サイズの制限を超えている

サポートされるファイルの最大サイズは 100 MB です。 100 MB を超えるファイルはインデックス付けされません。 処理後の最大サイズ制限は 4 MB です。 ファイルのサイズが 4 MB に達すると、処理が停止します。 したがって、ファイルに存在する一部の語句が検索に使用できない場合があります。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Graphコネクタを追加Microsoft 365 管理センター

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する

[データ **ソースConnect] ページで**、[**ファイル** 共有] を選択し、名前、接続 ID、および説明を指定します。 次のページで、ファイル共有へのパスを指定し、以前にインストールしたコネクタ エージェントGraph選択します。 ファイル共有内のすべてのファイルへの読みWindowsアクセス権を持つ[Microsoft](https://microsoft.com/windows)ユーザー アカウントの資格情報を入力します。

### <a name="preserve-last-access-time"></a>最後のアクセス時間を保持する

コネクタがファイルをクロールしようとすると、そのメタデータ内の "最終アクセス時刻" フィールドが更新されます。 アーカイブソリューションとバックアップ ソリューションのフィールドに依存し、コネクタがアクセスするときに更新しない場合は、[詳細設定] ページでこのオプション **を構成** できます。

## <a name="step-4-manage-search-permissions"></a>手順 4: 検索アクセス許可を管理する

[検索アクセス許可の管理] ページで目的のオプションを選択することにより、Share Access Control Lists または New Technology File System (NTFS) Access Control Lists に基づいて任意のファイルを検索するアクセス許可を制限できます。  これらのアクセス制御リストで提供されるユーザー アカウントとグループは、Active Directory (AD) によって管理する必要があります。 ユーザー アカウント管理に他のシステムを使用している場合は、[すべてのユーザー] オプションを選択して、ユーザーがアクセス制限なしですべてのファイルを検索できます。 ただし、ユーザーがファイルを開く場合は、ソースで設定されたアクセス制御が適用されます。

既定では、フォルダーがネットワーク上で共有されている場合、Windows は Share ACL の 'Everyone' に対する 「読み取り」 アクセス許可を提供します。 [検索アクセス許可の管理] で [ACLの共有] を選択している場合、ユーザーはすべてのファイルを検索できます。 アクセスを制限する場合は、ファイル共有の 'Everyone' の 'Read' アクセスを削除し、目的のユーザーとグループにのみアクセスを提供します。 コネクタは次に、これらのアクセス制限を読み取り、それらを検索に適用します。

[ACL の共有] を選択できるのは、指定した共有パスが UNC パス形式に従う場合のみです。 UNC 形式のパスを作成するには、[共有] オプションの [高度な共有] に進む必要があります。

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a>手順 5: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a>手順 6: スキーマを管理する

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a>手順 7: 更新設定を選択する

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a>手順 8: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->