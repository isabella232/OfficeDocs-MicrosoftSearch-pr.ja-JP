---
title: Dynamics 365 フェデレーション検索 (プレビュー)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: 検索結果での Dynamics 365 コンテンツの表示方法を管理する
ms.openlocfilehash: 5f642bcb026358e57258e5e736fc263616fc4b05
ms.sourcegitcommit: f07a2e578b6c9ed5a1a3b22266cca371782870a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53067931"
---
# <a name="dynamics-365-federation-search-preview"></a>Dynamics 365 フェデレーション検索 (プレビュー)

## <a name="microsoft-search-federation-and-connectors"></a>Microsoft Searchフェデレーションとコネクタ

この機能をよりMicrosoft Searchするために、フェデレーションを導入Microsoft Searchしています。 フェデレーション検索を使用すると、組織は次のシナリオのデータを次の場所でアクセスMicrosoft Search。

* 厳密なコンプライアンス要件の対象となるシステム内のデータ
* システム境界から離れきらないデータ
* 組織がクラウドにインデックスを作成したくない、事前に保存された機密データ

フェデレーション検索接続を介してアクセスされるデータは、フェデレーション検索接続でインデックスMicrosoft Search。 また、Microsoft の組み込みコネクタを使用すると、フェデレーション検索接続を簡単にセットアップできます。 Dynamics 365 コネクタは現在プレビュー中です。 プレビューへの参加に興味がある場合は、次のページ[aka.ms/D365FederationSearchPreview。](https://aka.ms/D365FederationSearchPreview)

## <a name="dynamics-365-federation-connector"></a>Dynamics 365 フェデレーション コネクタ

Microsoft Dynamics 365 は、エンタープライズ リソース計画と顧客関係管理用に設計されたインテリジェント なビジネス アプリケーションです。 Dynamics 365 フェデレーションを使用すると、Microsoft Search はシームレスな検索エクスペリエンスを提供し、ユーザーは Dynamics 365 に格納されている最も関連性の高い顧客およびビジネス データを簡単に見つくことができます。 Dynamics 365 フェデレーション コネクタには、次の主な利点があります。

* **管理が簡単:** Dynamics 365 インスタンスへの検索接続を構成および維持するための合理化されたプロセス。
* **使いやすい:** ユーザーは、アカウント、連絡先、オープン 機会など、Dynamics 365 に格納されている主要な情報を簡単かつ迅速に見つくことができます。
* **よりリッチなコンテンツ:** Dynamics 365 検索結果をより便利にするために、リード、連絡先、アカウントの詳細などの重要な情報が含まれます。
* **組み込みのデータ保護:** Dynamics 365 の結果は、接続されたインスタンスにアクセスできるユーザーにのみ表示されます。
* **統合検索エクスペリエンス:** 一貫性のあるエクスペリエンスを維持するために、Dynamics 365 の結果は、すべての検索エントリ ポイントで一貫しています。 検索の場所を問い合っても、同じ外観で同じ結果が得られます。

## <a name="what-users-experience"></a>ユーザーのエクスぺリエンス

Dynamics 365 の回答は、SharePoint Online、Bing、および Office を含むすべての Microsoft Search キャンバスの検索結果に表示されます。

:::image type="content" alt-text="Dynamics 365 の回答のスクリーンショット (SharePoint、Bing、およびOffice" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

この答えから、[その他の Dynamics 365 の結果] リンクを使用すると、より多くの **Dynamics 365 検索結果を簡単に確認** できます。 ユーザーは、クエリに関連する結果が多い、専用の Dynamics 365 結果ページに移動します。

:::image type="content" alt-text="Dynamics 365 の垂直方向のスクリーンショットと、SharePoint、Bing、およびOffice" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

結果をクリックまたはタップすると、Dynamics 365 が開き、詳細情報が表示されます。

:::image type="content" alt-text="Dynamics 365 の詳細ページのスクリーンショット" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

ユーザーが検索を開始する場所に関係なく、ユーザーのエクスペリエンスは一貫性があり、最も関連性の高い Dynamics 365 の結果をすばやく見つけるのに役立ちます。 デモについては、Microsoft ビルド 2021 ビデオをご覧ください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a>サポートされているクエリ パターン

Dynamics 365 の結果を検索する際に、自然言語クエリと製品Microsoft Searchクエリの両方がサポートされます。 また、Dynamics 365 クエリでは大文字と小文字が区別されません。 自然言語パターンを使用して、連絡先、アカウント、および商談を検索します。顧客名または場所別、その他の頻繁に使用されるクエリ。 いくつかの例を示します。

* Who Contoso の連絡先
* Contoso のオープン な機会
* シアトルでのオープンな機会
* シアトルのアカウントは何か
* シアトルの連絡先
* 今月の閉じる見込み客の情報
* 優先度の高い電話
* 連絡先の不足しているメール

製品名パターンは、Dynamics 365 アプリケーションの範囲をサポートし、クエリに表示される場所に関係なく Dynamics 365 の結果をトリガーします。

* D365
* Dynamics 365
* Dynamics365
* Dynamics CRM
* Dynamics Sales
* Dynamics Customer Service
* Dynamics Service
* Dynamics Field Service

## <a name="configure-the-dynamics-365-connector"></a>Dynamics 365 コネクタの構成

この簡単な構成により、組織内のユーザーに対して Dynamics 365 フェデレーション検索エクスペリエンスを有効にできます。

1. [データ[ソースMicrosoft 365 管理センター]](https://admin.microsoft.com)[に移動します](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors)。

2. [Microsoft アプリとサービス] セクションの [Microsoft Dynamics 365] で、[管理] を選択して Microsoft Dynamics 365 パネルを開きます。 

3. 組織のコネクタを有効にします。

4. [エンドポイント **] リストで** 、Dynamics 365 環境を選択します。

5. [接続 **ID] に**、この接続の一意の ID を入力します。

6. [同意] チェック ボックスをオンにします。

7. [保存 **] を** 選択して、接続のセットアップを完了します。

:::image type="content" alt-text="画面の Dynamics 365 セットアップ パネルのスクリーンショットMicrosoft 365 管理センター" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

セットアップが完了すると、Dynamics 365 の回答と垂直は、有効な Dynamics 365 ライセンスを持ち、接続されている Dynamics 365 環境へのアクセス権を持つユーザーにのみ表示されます。 これらの設定に戻り、接続エンドポイント環境を変更したり、接続を非アクティブ化したりすることもできます。
