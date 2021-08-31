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
ms.openlocfilehash: 3b0f87fb252c3e88160f1b3753aad09b1e3f5083
ms.sourcegitcommit: e5d56d6ce1cd285c5af3e0472ce169cb34883017
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "58470250"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Microsoft Search で頭字語の回答を管理する

ユーザーは、組織やチームで使用されている頭字語や略語に慣れていないことがよくあります。 組織またはチームに固有の用語は、チーム間を移動したり、社内パートナーと共同で作業する人、または組織の新人には新しい場合があります。  

組織の標準的な用語には、常に単一の参照があるとは限りません。 1 つの参照がない場合、これらの頭字語の定義を見つけるのは難しです。 Microsoft Search は、頭字語の問題を解決します。

## <a name="what-users-experience"></a>ユーザーのエクスぺリエンス

Microsoft Searchユーザーは、Bing [、SharePoint、Office 365、Outlook on the web、Outlook](https://products.office.com/sharepoint/collaboration)Mobile (Android)、および[Teams](https://Bing.com)Mobile (iOS と Android) の頭字語で定義を取得できます。 [](https://Office.com) **[検索]** ボックスで、次の例のようにクエリを入力します:

- *What is* DNN
- *Define* DNN
- DNN *definition*
- *Expand* DNN
- DNN *expansion*
- *Meaning of* DNN
- DNN *means*
- DNN *の略*

結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。

> [!NOTE]
> ユーザーは、対応する回答をトリガーするために、頭字語で指定された *キーワード* を含むクエリを入力する必要があります。 頭字語のクエリでは、大文字と小文字は区別されません。

## <a name="set-up-acronyms-answers"></a>頭字語の回答を設定する

[Microsoft 365 管理センター](https://admin.microsoft.com)で、[**[頭字語]**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)に移動し、**[頭字語の追加]** を選択します。

Microsoft Search は、2 つのデータ ソースをクエリして、頭字語の回答をユーザーの検索に提供します:

1. **管理者が管理します**。 [管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の IT 管理者によって提供されます。
2. **System-curated**. ユーザーのMicrosoft Searchドキュメント、および組織内で公開されているデータから検出されます。

### <a name="set-up-admin-curated-acronyms"></a>管理者が指定した頭字語を設定する

検索管理者は、管理センターの [頭字[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)語] タブに頭字語[Microsoft Search追加できます](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)。 すべての内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。 これらの頭字語は、発行済みまたは下書 **き状態に****追加** できます。

**公開状態**。 頭字語は、組織のユーザーが使用できるデータを使用Microsoft Search。

> [!NOTE]
> 発行済み状態に追加された頭字語が、公開済み状態で使用可能になるには、最大で 1 日Microsoft Search。

**下書き状態**。 頭字語を確認してから、Microsoft Searchで使用する場合は、下書き状態で頭字語を追加できます。 下書き状態の頭字語は検索結果に表示されません。 検索結果に表示するには、頭字語を発行済み状態に移動する必要があります。

**除外された状態**。 データに頭字語が表示Microsoft Search場合は、[頭字語を除外する] を使用して追加します。 頭字語が除外されるのを止めるには、除外された頭字語を削除して追加するか、発行済みリストに含める必要があります。

頭字語を個別に追加するか、CSV ファイルに一括インポートできます。 次の表に示すフィールドを使用して CSV ファイルをアップロードします:

| 頭字語 (必須) | 略 (必須) | Url | 説明  | 状態 (必須) | 最終更新日時 | 最終変更者 | ID |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *略語のスペル* | *Source* |  | *公開、下書き、または除外* |  |  |  |

### <a name="csv-fields"></a>CSV フィールド

**頭字語**。 実際の短い形式または頭字語を含みます。 たとえば、*DNN* などです。

**を表します**。 頭字語の定義が含まれる。 たとえば、*Deep Neural Network* などです。

**説明**。 頭字語とその定義に関する詳細情報をユーザーに提供する頭字語の簡単な説明。 たとえば、*deep neural network とは、特定の複雑さを持つニューラル ネットワーク、2 つ以上の層を持つニューラル ネットワークです*。

**ソース**。 頭字語についての詳細情報をユーザーに表示するページまたは Web サイトの URL。

**状態**。 このフィールドには 2 つの値を指定できます:

- **下書き**。 下書き状態に頭字語を追加します。
- **公開**。 公開状態に頭字語を追加して、Microsoft Search で使用できるようにします。
- **除外します**。 頭字語を [除外] 状態に追加し、その頭字語が [除外] の状態Microsoft Search。

### <a name="system-curated-acronyms"></a>System-curated 頭字語

管理者にとって、組織内で使用されているすべての頭字語を回答に追加するのは難しいかもしれません。 この機能により、検索管理者が認識していない頭字語を見つけることができます。 この作業を行うには、Microsoft Searchの頭字語を検出してキュレートします。

- ユーザーのメール
- ドキュメント[](https://products.office.com/sharepoint/collaboration)、SharePoint、Microsoft OneDrive、および[]( https://onedrive.live.com/about/)[Microsoft OneNote](https://www.onenote.com/)
- ユーザーが組織内のパブリック ドキュメントにアクセスできるドキュメントは、SharePoint、OneDrive、またはOneNote

Microsoft Searchドキュメントへのアクセス権とアクセス許可を持つユーザーだけが、ドキュメントから検出された頭字語を確認できます。 ユーザーのメールボックスで頭字語が見つかった場合、その頭字語を表示できるのはそのユーザーのみです。

> [!NOTE]
> システムが指定した頭字語のセットアップは不要です。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q: 管理者が管理するデータとシステムで管理されたデータのランク付け方法**

**A:** 結果のランク付けは、結果が各ユーザーに合わせたものとして、個人ごとに異なる場合があります。 これらのどちらのカテゴリも、常に他のカテゴリよりも優先されます。

**Q: ユーザーが頭字語の回答をトリガーする方法**

**A:** 頭字語の回答を取得するには、Bing、SharePoint、Office 365、Outlook on the web、Outlook Mobile (Android)、または [Teams](https://bing.com)Mobile (iOS および **Android)** 検索ボックスに特定のクエリ パターンを入力する必要があります。 [](https://products.office.com/sharepoint/collaboration) [](https://Office.com)

**Q: ユーザーは検索時に頭字語を入力できますか?**

**A:** このBing、ユーザーは頭字語を検索するだけで頭字語の回答を見つけ、キーワードは必要なくなりました。 この同じエクスペリエンスは、フェーズ内の他のMicrosoft Searchに対して有効になります。

**Q: 管理者が指定した頭字語が公開された後に、Microsoft Search表示するにはどのくらいの時間が必要ですか?**

**A:** 発行済み状態に追加された頭字語が、公開済み状態で使用可能になるには、最大で 1 日Microsoft Search。

**Q: 新しい電子メールまたはドキュメントを受信または送信した後に、システムで指定された頭字語が表示されるのにどのくらいの時間が必要ですか?**

**A:** 新しい電子メールまたはドキュメントで見つかった頭字語は、検索結果に表示するには最大 7 Microsoft Searchします。

**Q: 頭字語が除外され、公開されている場合は、何が起こりますか?**

**A:** 除外された頭字語が優先され、発行された頭字語が検索結果に表示されません。 公開された頭字語は削除も削除もされません。

**Q: 頭字語が結果から除外されるのにMicrosoft Searchですか?**

**A:** 除外された頭字語が検索結果に表示されるのを停止するには、最大で 1 日かかる。

**Q: システムで指定された頭字語の場合、ドキュメントは特定の形式である必要がありますか?**

**A:** いいえ。 画像、フォルダー、zip ファイルを除くすべての種類のファイルをサポートしています。

**Q: Microsoft は、すべての言語のドキュメントから頭字語を検出しますか?**

**A:** Microsoft では、英語、スペイン語、フランス語、イタリア語、ドイツ語、ポルトガル語のドキュメントからのシステムキュキュアされた頭字語のみをサポートしています。 その他の言語のサポートは段階的に追加されます。

**Q: 組織がシステムで指定された頭字語を表示しない場合は、どうしますか。検索結果にこの種類の頭字語が表示されるのを停止できますか?**

**A:** 検索結果にシステムで指定された頭字語を表示するをオフにする場合は、「ビジネス製品のサポートに問い合わせ」の指示に従ってカスタマー サポート チケット [を作成します](/microsoft-365/admin/contact-support-for-business-products)。
サポート チケットを作成した後、システムでキュアされた頭字語が検索結果に表示されるのを停止するには、最大 48 時間かかります。
