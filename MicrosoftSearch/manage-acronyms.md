---
title: Microsoft Search で頭字語の回答を管理する
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search で頭字語の回答を作成および更新する
ms.openlocfilehash: 45d3cc7b33f27d2f4e77d8099fbfa91e01aabcbb
ms.sourcegitcommit: ef94ffd6111acb929c8343f0f4f82ea109b68fb6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122158"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Microsoft Search で頭字語の回答を管理する

ユーザーは、組織やチームで使用されている頭字語や略語に慣れていないことがよくあります。 組織またはチームに固有の用語は、チーム間を移動したり、社内パートナーと共同で作業する人、または組織の新人には新しい場合があります。  

組織の標準的な用語には、常に単一の参照があるとは限りません。 単一の参照がないと、これらの頭字語の定義や展開が難しくなります。 Microsoft Search は、頭字語の問題を解決します。

## <a name="what-users-experience"></a>ユーザーのエクスぺリエンス

Microsoft Search のユーザーは [Bing](https://Bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)および[Office 365](https://Office.com)の頭字語を使用して、定義を入手できます。 **[検索]** ボックスで、次の例のようにクエリを入力します:

- *What is* DNN
- *Define* DNN
- DNN *definition*
- *Expand* DNN
- DNN *expansion*
- *Meaning of* DNN
- DNN *means*

結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。

> [!NOTE]
> ユーザーは、対応する回答をトリガーするために、頭字語で指定された *キーワード* を含むクエリを入力する必要があります。 頭字語のクエリでは、大文字と小文字は区別されません。

## <a name="set-up-acronyms-answers"></a>頭字語の回答を設定する

[Microsoft 365 管理センター](https://admin.microsoft.com)で、[**[頭字語]**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)に移動し、**[頭字語の追加]** を選択します。

Microsoft Search は、2 つのデータ ソースをクエリして、頭字語の回答をユーザーの検索に提供します:

1. **管理者が選択しました**。 [管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の IT 管理者によって提供されます。
2. **システムによって選択されます**。 ユーザーの電子メールとドキュメント、および組織内で一般に利用可能なデータから Microsoft Search によって検出されます。

### <a name="set-up-admin-curated-acronyms"></a>管理者が選択した頭字語を設定する

検索管理者は、Microsoft Search 管理センターの[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)[頭字語] タブに頭字語[を追加できます](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。 すべての内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。 これらの頭字語は、発行済みまたは下書き **状態** に **追加** できます。

**公開状態**。 頭字語は、Microsoft Search を通じて組織のユーザーが使用できます。

> [!NOTE]
> 公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかる場合があります。

**下書き状態**。 Microsoft Search で使用する前に頭字語を確認する場合は、下書き状態で頭字語を追加できます。 下書き状態の頭字語は検索結果に表示されません。 検索結果に表示するには、頭字語を発行済み状態に移動する必要があります。

頭字語を個別に追加したり、CSV ファイルに一括インポートすることができます。 次の表に示すフィールドを使用して CSV ファイルをアップロードします:

| 頭字語 (必須) | 拡張 (必須) | Url | 説明  | State (Mandatory) | 最終更新日時 | 最終更新日者 | ID |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *略語のスペル* | *Source* |  | *公開または下書き* |  |  |  |

### <a name="csv-fields"></a>CSV フィールド

**頭字語**。 実際の短い形式または頭字語を含みます。 たとえば、*DNN* などです。

**展開**。 頭字語の展開を含みます。 たとえば、*Deep Neural Network* などです。

**説明**。 頭字語とその展開についての詳細情報をユーザーに伝える頭字語の簡単な説明。 たとえば、*deep neural network とは、特定の複雑さを持つニューラル ネットワーク、2 つ以上の層を持つニューラル ネットワークです*。

**ソース**。 頭字語についての詳細情報をユーザーに表示するページまたは Web サイトの URL。

**状態**。 このフィールドには 2 つの値を指定できます:

- **下書き**。 頭字語を下書き状態に追加します。
- **公開**。 公開状態に頭字語を追加して、Microsoft Search で使用できるようにします。

### <a name="system-curated-acronyms"></a>システムで選択された頭字語

管理者にとって、組織内で使用されているすべての頭字語を回答に追加するのは難しいかもしれません。 この機能により、検索管理者が認識していない頭字語を見つけることができます。 これを行うには、Microsoft Search は次のソースから頭字語を検出して作成します。

- ユーザーのメール
- [SharePoint、Microsoft](https://products.office.com/sharepoint/collaboration) [OneDrive、Microsoft OneNote]( https://onedrive.live.com/about/)[のドキュメント](https://www.onenote.com/)
- SharePoint、OneDrive、または OneNote でユーザーがアクセスできる組織内のパブリック ドキュメント

Microsoft Search では、ドキュメントに対するアクセス権とアクセス許可を持つユーザーだけが、ドキュメントから検出された頭字語を確認できます。 ユーザーのメールボックスで頭字語が見つかると、そのユーザーだけがその頭字語を見る可能性があります。

> [!NOTE]
> 管理者が選択した頭字語にはセットアップは必要ない。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q: 管理者が選択したデータとシステムで管理されたデータは、どのようにランク付けされますか。**

**A:** 結果のランク付けは、結果がユーザーごとにカスタマイズされるので、人によって異なる場合があります。 これらのカテゴリはどちらも常に他のカテゴリよりも優先されます。

**Q: 管理者が選択した頭字語が Microsoft Search に公開された後に表示されるのに、どれくらいの時間が必要ですか。**

**A:** 公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかります。

**Q: ユーザーが頭字語の回答をトリガーする方法**

**A**: 頭字語の回答を取得するには、ユーザーは [Bing、SharePoint、](https://bing.com)または [](https://products.office.com/sharepoint/collaboration)Office [365](https://Office.com)検索ボックスに特定のクエリ パターンを入力する **必要** があります。

**Q: 新しいメールやドキュメントを受信または送信した後に、システムで指定された頭字語が表示されるのにどれくらい時間がですか。**

**A:** 新しいメールまたはドキュメントで見つかった頭字語は、Microsoft Search の結果に表示されるのに最大 7 日間かかる。

**Q: 文書から採掘するには、文書が特定の形式である必要がありますか?**

**A:** いいえ。 画像、フォルダー、および zip ファイル以外のすべての種類のファイルをサポートしています。

**Q: Microsoft は、すべての言語のドキュメントから頭字語を見つけるのか。**

**A**: Microsoft は、英語の文書からの採掘のみをサポートしています。 その他の言語のサポートは段階的に追加されます。

**Q: 組織でシステムで作成された頭字語を表示しない場合は、どうでしょうか。この種の頭字語が検索結果に表示されるのを停止できますか。**

**A**: 検索結果にシステム指定の頭字語が表示されるのをオフにする場合は、ビジネス製品のサポートに問い合わせの指示に従ってカスタマー サポート チケット [を作成します](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)。
サポート チケットを作成した後、システムが選択した頭字語が検索結果に表示されな最大 48 時間かかります。
