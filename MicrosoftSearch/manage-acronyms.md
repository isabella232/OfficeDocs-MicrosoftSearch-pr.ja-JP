---
title: Microsoft Search で頭字語の回答を管理する
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search で頭字語の回答を作成および更新する
ms.openlocfilehash: 68e62884898e3aa081fc32438ad9a80068092738
ms.sourcegitcommit: b3738f5ab02bfba9dedf099e035f3850607be480
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2020
ms.locfileid: "46591510"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Microsoft Search で頭字語の回答を管理する

ユーザーは、組織やチームで使用されている頭字語や略語に慣れていないことがよくあります。 組織またはチームに固有の用語は、チーム間を移動したり、内部パートナーチームと連携したり、組織にとって新しくなったりするユーザーにとって新しいものになる可能性があります。

組織の標準的な用語には、常に単一の参照があるとは限りません。 単一の参照がないと、これらの頭字語の定義や展開が難しくなります。 Microsoft Search は、頭字語の問題を解決します。

## <a name="what-users-experience"></a>ユーザーのエクスぺリエンス

Microsoft 検索ユーザーは、 [Bing](https://Bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)、および[Office 365](https://Office.com)の頭字語を使用して定義を取得できます。 **[検索]** ボックスで、次の例のようにクエリを入力します:

- DNN *とは*
- DNN *を定義する*
- DNN *の定義*
- DNN *を展開する*
- DNN *の展開*
- DNN *の意味*
- DNN *は意味する*

結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。

> [!NOTE]
> ユーザーは、対応する回答をトリガーするために、頭字語で指定された *キーワード* を含むクエリを入力する必要があります。 頭字語のクエリでは、大文字と小文字は区別されません。

## <a name="set-up-acronyms-answers"></a>頭字語の回答を設定する

Microsoft 365 [管理センター](https://admin.microsoft.com) で、**[設定]** > **[Microsoft Search]** > ** [回答]** > [**[頭字語]**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の順に移動し、**[頭字語の追加]** を選択します。

Microsoft Search は、2 つのデータ ソースをクエリして、頭字語の回答をユーザーの検索に提供します:

1. **編集上の頭字語**。 [管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) の IT 管理者によって提供されます。
2. **採掘された頭字語**。 ユーザーの個人的なメールと文書、および組織内で公開されているデータから Microsoft Search によって採掘されます。

### <a name="set-up-editorial-acronyms"></a>編集上の頭字語を設定する

検索管理者は、[Microsoft Search 管理センター](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) の [[頭字語] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) で編集上の頭字語を設定できます。 すべての内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。 編集上の頭字語は、**公開** または **下書き** の状態に追加されます:

**公開状態**。 頭字語は、Microsoft Search を通じて組織の従業員が利用できます。

> [!NOTE]
> 公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかる場合があります。

**下書き状態**。 Microsoft Search で使用できるようにする前に、管理者が頭字語の回答を確認したい場合は、頭字語を下書き状態に追加できます。 下書き状態に追加された略語は、Microsoft Search では使用できません。 管理者は、使用できるようにするには、頭字語を公開状態に追加する必要があります。

管理者は、頭字語を個別に追加するか、CSV ファイルに一括インポートすることができます。 次の表に示すフィールドを使用して CSV ファイルをアップロードします:

| 頭字語 (必須) | 展開 (必須) | 説明  | ソース | 状態 (必須) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *略語のスペル* |  | *URL* | *公開または下書き* |

### <a name="csv-fields"></a>CSV フィールド

**頭字語**。 実際の短い形式または頭字語を含みます。 たとえば、*DNN* などです。

**展開**。 頭字語の展開を含みます。 たとえば、*Deep Neural Network* などです。

**説明**。 頭字語とその拡張に関する情報をユーザーに提供する略語の簡単な説明。 たとえば、*deep neural network とは、特定の複雑さを持つニューラル ネットワーク、2 つ以上の層を持つニューラル ネットワークです*。

**ソース**。 頭字語についての詳細情報をユーザーに表示するページまたは Web サイトの URL。

**状態**。 このフィールドには 2 つの値を指定できます:

- **下書き**。 頭字語を下書き状態に追加します。
- **公開**。 公開状態に頭字語を追加して、Microsoft Search で使用できるようにします。

### <a name="mined-acronyms"></a>採掘された頭字語

管理者にとって、組織内で使用されているすべての頭字語を回答に追加するのは難しいかもしれません。 この機能により、検索管理者が認識していない頭字語を見つけることができます。 そのために、Microsoft Search は次のソースから頭字語を採掘します:

- ユーザーのメール。
- [SharePoint](https://products.office.com/sharepoint/collaboration)、 [Microsoft OneDrive]( https://onedrive.live.com/about/)、 [microsoft OneNote](https://www.onenote.com/)のドキュメント。
- ユーザーが SharePoint、OneDrive、または OneNote でアクセスできる組織内の公開文書。

Microsoft Search は、文書に対してアクセス権を持つユーザーのみが、その文書から採掘された頭字語を見ることができるようにします。 頭字語がユーザーのメールボックスから採掘されると、そのユーザーのみがその頭字語を見ることができます。

> [!NOTE]
> 採掘された頭字語に設定は必要はありません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q: 編集上の採掘されたデータはどのようにランク付けされていますか?**

**A:** この機能は現在、編集上の頭字語を採掘された頭字語より上にランク付けしています。

**Q: 編集上の頭字語が公開されてから Microsoft Search に表示されるまで、どのくらいの時間がかかりますか?**

**A:** 公開状態に追加された頭字語が Microsoft Search で利用可能になるまで、最大 3 日かかります。

**Q: ユーザーが頭字語の回答をトリガーするにはどうすればよいですか?**

**A**: 頭字語の回答を取得するには、ユーザーは[Bing](https://bing.com)、 [SharePoint](https://products.office.com/sharepoint/collaboration)、または[Office 365](https://Office.com)の**検索**ボックスに特定のクエリパターンを入力する必要があります。

**Q: 新しいメールや文書の送受信後に、採掘された頭字語が表示されるまで、どのくらいの時間がかかりますか?**

**A:** 新しいメールまたは文書から採掘された頭字語がMicrosoft Search 結果に表示されるまでには、最大 7 日かかります。

**Q: 文書から採掘するには、文書が特定の形式である必要がありますか?**

**A:** いいえ。 画像、フォルダー、および zip ファイル以外のすべての種類のファイルをサポートしています。

**Q: Microsoft はすべての言語の文書から頭字語を採掘しますか?**

**A**: Microsoft は、英語の文書からの採掘のみをサポートしています。 その他の言語のサポートは段階的に追加されます。

**Q: 組織内の採掘された頭字語を表示する必要がない場合はどうすればよいですか? 採掘された頭字語を検索結果に表示しないようにすることはできますか?**

**A**: 検索結果に採掘された頭字語が表示されないようにするには、[「ビジネス製品のサポートに問い合わせる」](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support) の説明に従って、カスタマー サポート チケットを作成します。
サポート チケットを作成してから、採掘された頭字語が検索結果に表示されなくなるまでに最大 48 時間かかります。
