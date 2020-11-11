---
title: AAD 以外の id のマッピング
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: AAD 以外の id をマップする手順
ms.openlocfilehash: be479cfd9dad585e83b5a39ff3ce4a84b9d41676
ms.sourcegitcommit: 77ec27736f3c8434b2ac47e10897ac2606ee8a03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/11/2020
ms.locfileid: "48992898"
---
# <a name="map-your-non-azure-ad-identities"></a>非 Azure AD Id をマップする  

この記事では、azure ad id 以外のアクセス制御リスト (ACL) を使用しているユーザーが、それらにスコープ設定されたコネクタ検索結果を表示できるように、azure ad id に非 Azure AD id をマッピングする手順について説明します。

これらの手順は、Microsoft によって [ServiceNow](servicenow-connector.md) または [Salesforce](salesforce-connector.md) のコネクタを設定している管理者のみが、"このデータソースへのアクセス権を持つユーザーのみ" および "identity type" という名前の "AAD" の検索アクセス許可を使用して設定している場合にのみ関連します。

>[!NOTE]
>Salesforce コネクタを設定して、[アクセス許可] 画面で [このデータソースおよび id の種類 **AAD** **にアクセスできるユーザーのみ** ] を選択する場合は、「azure ad id をマップする方法」の手順については、「 [azure ad identity のマップ](map-aad.md)」の記事を参照してください。  

## <a name="steps-for-mapping-your-non-azure-ad-properties"></a>非 Azure AD プロパティをマッピングする手順

### <a name="1-select-an-azure-ad-user-property"></a>1. Azure AD ユーザープロパティを選択する  

マッピングを作成する Azure AD ユーザーのプロパティを選択できます。 これは、非 Azure AD id をにマップするターゲットプロパティです。  

次のいずれかの Azure AD プロパティを選択できます。

| Azure AD プロパティ    | 定義           | 例         |
| :------------------- | :------------------- |:--------------- |
| ユーザー プリンシパル名 (UPN)  | UPN は、UPN プレフィックス (ユーザーアカウント名) と UPN サフィックス (DNS ドメイン名) で構成されます。 プレフィックスは、"@" 記号を使用してサフィックスと共に結合されます。 | us1@contoso.onmicrosoft.com |
| Azure AD ID                 | 特定のユーザーの Azure AD ID は、ユーザーの一意の GUID です。                 | 58006c96-9e6e-45ea-8c88-4a56851eefad            |
| Active Directory のセキュリティ ID (SID)                  | SID (セキュリティ識別子) は、Active Directory がオブジェクトをセキュリティプリンシパルとして識別するために使用する一意の識別子です。                  | S-1-5-21-453406510-812318184-4183662089             |

### <a name="2-select-non-azure-ad-user-properties-to-map"></a>2. マッピングする Azure AD 以外のユーザーのプロパティを選択する

データソースから引き出された非 Azure AD プロパティを選択して、に正規表現を適用することができます。 データソース内のこれらのプロパティの詳細については、「 [ServiceNow](servicenow-connector.md) 」および「 [Salesforce](salesforce-connector.md) 」のページを参照してください。  

ドロップダウンから非 Azure AD ユーザープロパティを選択し、それらのユーザープロパティ値に適用する正規表現を指定できます。 正規表現の詳細については、「 [正規表現の参照]( https://docs.microsoft.com/dotnet/standard/base-types/regular-expression-language-quick-reference)」を参照してください。  

正規表現と、サンプル文字列に適用される出力の例を次に示します。 

| サンプル文字列                  | 正規表現                 | サンプル文字列の正規表現の出力           |
| :------------------- | :------------------- |:---------------|
| Alexis Vasquez  | .* | Alexis Vasquez |
| Alexis Vasquez                 | ..$                 | ez            |
| Alexis Vasquez                  | (\w +) $                  | Vasquez             |

の式と同じ数の非 Azure AD ユーザープロパティを追加することができます。 最終的な式で保証されている場合は、異なる正規表現を同じユーザープロパティに適用できます。  

### <a name="3-create-formula-to-complete-mapping"></a>3. マッピングを完了するための数式を作成します。

Azure 以外の各 AD ユーザープロパティに適用された正規表現の出力を結合して、手順1で選択した Azure AD プロパティを形成できます。

[式] ボックスで、"" は、 {0} 選択した *最初* の非 Azure 広告プロパティに適用された正規表現の出力に対応しています。 " {1} " は、選択した *2 番目* の非 Azure 広告プロパティに適用された正規表現の出力に対応しています。 " {2} " は、 *3 番目* の非 Azure AD プロパティに適用された正規表現の出力に対応しています。  

次に、サンプルの正規表現出力と数式出力を含む数式の例をいくつか示します。 

| サンプル式                  | {0}サンプルユーザーの値                 | {1}サンプルユーザーの値           | 数式の出力                  |
| :------------------- | :------------------- |:---------------|:---------------|
| {0}.{1}@contoso .com  | 担当 | 社員 |firstname.lastname@contoso.com
| {0}@domain .com                 | userid                 |             |userid@domain.com

数式を入力した後で、必要に応じて、[ **プレビュー** ] をクリックして、データソースから5つのランダムユーザーのプレビューを表示し、それぞれのユーザーマッピングを適用することができます。 プレビューの出力には、手順2でユーザーが選択した非 Azure AD ユーザープロパティの値と、そのユーザーの手順3で提供された最終的な式の出力が含まれています。 また、「成功」または「失敗」アイコンを使用して、式の出力をテナントの Azure AD ユーザーに解決できるかどうかも示します。  

>[!NOTE]
>[ **プレビュー** ] をクリックした後、1つ以上のユーザーマッピングの状態が "Failed" になっている場合でも、接続の作成を続行できます。 プレビューには、5つのランダムユーザーと、データソースからのマッピングが表示されます。 指定したマッピングですべてのユーザーがマップされていない場合は、この場合に遭遇する可能性があります。

## <a name="sample-non-azure-ad-mapping"></a>サンプルの非 Azure AD マッピング

サンプルの非 Azure AD マッピングについては、以下のスナップショットを参照してください。

![非 Azure AD マッピングページに記入する方法のサンプルスナップショット](media/non-aad-mapping.png)

## <a name="limitations"></a>制限事項  

- すべてのユーザーに対して1つのマッピングのみがサポートされます。 条件付きマッピングはサポートされていません。  

- 接続が公開されると、マッピングを変更することはできません。  

- 現時点では、非 AAD ユーザープロパティに対する regex ベースの式のみが変換に対してサポートされています。

- マッピング先として選択できる Azure AD id は3つだけです (UPN、Azure AD ID、および AD SID)。