---
title: AAD ID のマッピング
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: AAD ID をマップする方法の手順
ms.openlocfilehash: d0292d77b3a0936ed60682b8388de1bb82ac43bb
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59334517"
---
# <a name="map-your-azure-ad-identities"></a>Azure AD の ID をマッピング  

この記事では、Azure AD ID をデータ ソースの一意の識別子 (Azure AD 以外の ID) にマッピングし、Azure AD 以外の ID を持つアクセス制御リスト (ACL) のユーザーが対象範囲のコネクタ検索結果を確認する手順について説明します。

これらの手順は、"このデータ ソースへのアクセス権を持つユーザーのみ" と ID の種類 "AAD" の検索権限を持つ Microsoft による [Salesforce](salesforce-connector.md) コネクタを設定している検索管理者にのみ関連します。 次の手順では、Azure のユーザー プロパティをユーザー ADフェデレーション ID にマップする方法 **について説明します**。

>[!NOTE]
>[Salesforce](salesforce-connector.md)コネクタを設定し、[検索アクセス許可] 画面で [このデータ ソースとID タイプにアクセスできるユーザーのみ] を選択する場合は、Azure 以外の AD ID をマップする方法の手順については、「Map your [Azure AD Identitys」](map-non-aad.md)の記事を参照してください。  

## <a name="steps-for-mapping-your-azure-ad-properties"></a>Azure のプロパティをマッピングAD手順

### <a name="1-select-azure-ad-user-properties-to-map"></a>1. マップする Azure ADユーザー プロパティを選択します。

フェデレーション ID にマップする必要AD Azure プロパティを選択できます。

ドロップダウンから Azure ADユーザー プロパティを選択できます。 組織のフェデレーション ID マッピングADこれらのプロパティが必要な場合は、必要な数の Azure ユーザー プロパティを追加することもできます。

### <a name="2-create-formula-to-complete-mapping"></a>2. マッピングを完了する数式を作成する

Azure のユーザー プロパティの値を組みAD一意のフェデレーション ID を形成できます。

数式ボックスの " {0} " は、選択した最初の Azure ADプロパティに対応します。 " {1} " は、選択した *2* 番目の Azure ADプロパティに対応します。 " {2} は、3番目の Azure ADプロパティに対応します。  

次に、正規表現出力と数式出力のサンプルを含む数式の例を示します。

| サンプル数式                  | サンプル ユーザーの {0} プロパティの値                 | サンプル ユーザーの {1} プロパティの値           | 数式の出力                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1}@contoso.com  | firstname | lastname |firstname.lastname@contoso.com
| {0}@domain.com                 | userid                 |             |userid@domain.com

数式を指定した後、必要に応じて[プレビュー] をクリックして、それぞれのユーザー マッピングが適用されたデータ ソースから 5 人のランダム ユーザーのプレビューを表示できます。 プレビューの出力には、手順 1 で選択した Azure AD ユーザー プロパティの値と、そのユーザーの手順 2 で示した最終数式の出力が含まれます。 また、数式の出力を "成功" または "Failed" アイコンを使用して、テナント内の Azure AD ユーザーに解決できるかどうかも示します。  

>[!NOTE]
>[プレビュー] をクリックした後に、1 つ以上のユーザー マッピングの状態が "Failed" の場合は、接続の作成を続行 **できます**。 プレビューには、データ ソースから 5 人のランダム なユーザーとそのマッピングが表示されます。 指定したマッピングですべてのユーザーがマップされない場合は、このケースが発生する可能性があります。

## <a name="sample-azure-ad-mapping"></a>Azure のサンプル ADマッピング

Azure のマッピングのサンプルについては、以下のスナップショットADしてください。

![Azure の [マッピング] ページに入力する方法のADスナップショットです。](media/aad-mapping.png)

## <a name="limitations"></a>制限事項  

- すべてのユーザーに対してサポートされているマッピングは 1 つのみです。 条件付きマッピングはサポートされていません。  

- 接続が公開された後は、マッピングを変更できません。  

- Azure のユーザー プロパティに対AD正規表現ベースの式は、Azure のフェデレーション ID 変換ADサポートされていません。