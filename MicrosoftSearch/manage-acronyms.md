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
ms.openlocfilehash: af5b82aa2c578fde67a36980cfceef131f605b4e
ms.sourcegitcommit: d4f49d51fa7d07b3bfd9ba93ed14f4c46d310154
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412677"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Microsoft Search で頭字語の回答を管理する

ユーザーは、組織やチームによって使用される見慣れない頭字語や略語を使用することがよくあります。 組織またはチームに固有の用語は、チーム間の移行、社内パートナーと連携しているユーザー、または組織にとって新しいユーザーにとって新しいものである場合があります。

組織では、標準的な用語を常に参照することはありません。 単一の参照がないと、これらの略語の定義や拡張を見つけるのが困難になります。 Microsoft Search は、頭字語に問題があることを解決します。

## <a name="what-users-experience"></a>ユーザーの作業
Microsoft 検索ユーザーは、 [Bing](https://Bing.com)で頭字語を使用して定義を取得できます。 **検索**ボックスには、次の例のようなクエリが入力されます。

- *機能*DNN
- を*定義*するDNN
- DNN*定義*
- *展開*DNN
- DNN*拡張*
- *の意味*DNN
- DNN*は*

結果には、ユーザーの組織内に存在する DNN のすべての意味が含まれます。

> [!NOTE]
> ユーザーは、頭字語の指定された*キーワード*を含むクエリを入力して、対応する回答をトリガーする必要があります。 頭字語のクエリでは大文字と小文字は区別されません。 

## <a name="set-up-acronyms-answers"></a>頭字語の回答を設定する
Microsoft 365[管理センター](https://admin.microsoft.com)で、[microsoft Search の**設定**] に移動し、[頭字語の  >  **Microsoft Search**  > **Acronyms****追加**] を選択します。 

Microsoft Search では、ユーザーの検索に頭字語の回答を提供するために2つのデータソースをクエリします。

1.  **編集の略語** [管理センター](https://admin.microsoft.com)の IT 管理者によって提供されます。
2.  抽出した**略語**。 ユーザーの個人電子メールやドキュメントから組織内の一般に利用可能なデータから、Microsoft Search によってマイニングされます。

### <a name="set-up-editorial-acronyms"></a>編集の略語を設定する
検索管理者は、 [Microsoft 365 管理センター]( https://admin.microsoft.com)の [[頭字] タブ](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)で編集の略語を設定できます。 任意の内部サイトまたはリポジトリから管理センターに頭字語を追加することができます。 編集の略語は、**発行済み**または**下書き**の状態に追加できます。

**公開**された状態。 頭字語は、組織の従業員が Microsoft Search を通じて使用できます。

> [!NOTE]
> 発行済みの状態に追加された頭字語が Microsoft Search で利用できるようになるまで、最大で3日かかる場合があります。

**下書きの状態**です。 Microsoft Search で使用できるようにする前に、管理者が頭字語の回答を確認する必要がある場合は、略語を下書き状態に追加できます。 下書き状態に追加された頭字語は、Microsoft Search では使用できません。 管理者は、略語を公開済み状態に追加して利用できるようにする必要があります。

管理者は、頭文字を個別に追加するか、または CSV ファイルに一括インポートすることができます。 次の表に示すフィールドを使用して CSV ファイルをアップロードします。

| 頭字語 (必須) | 拡張 (必須) | 説明  | ソース | 状態 (必須) |
| --------- | --------- | ---------- | --------- |--------- |
| *xxx* | *スペルミスの省略形* |  | *URL* | *公開または下書き* |

### <a name="csv-fields"></a>CSV フィールド
**頭字語** 実際の短い形式または頭字語を含みます。 例として、 *Dnn*が挙げられます。

**拡張**。 頭字語の拡張が含まれています。 例としては、*ディープニューラルネットワーク*があります。

**説明**。 頭字語とその拡張の意味をユーザーにすばやく理解できるようにするための、略語の簡単な説明。 たとえば、*深いニューラルネットワークとは、一定レベルの複雑な、3つ以上のレイヤーを持つニューラルネットワークのニューラルネットワーク*のことです。

**ソース**。 頭字語の詳細については、ユーザーが移動するページまたは web サイトの URL。

**状態**。 このフィールドには、次の2つの値を指定できます。

- **下書き**。 頭字語を下書き状態に追加します。
- **発行済み**。 頭字語を公開された状態に追加し、Microsoft Search で使用できるようにします。

### <a name="mined-acronyms"></a>マイニング頭字語
管理者が組織内で使用されているすべての略語を回答に追加することが課題となる場合があります。 この機能は、検索管理者が認識していない略語を見つけることができます。 この作業を行うために、Microsoft Search では、これらのソースからの略語も地雷しています。

- ユーザーの電子メール。
- [SharePoint](https://products.office.com/sharepoint/collaboration)、 [Microsoft OneDrive]( https://onedrive.live.com/about/) 、 [microsoft OneNote](http://www.onenote.com/)のドキュメント。
- ユーザーが SharePoint、OneDrive、または OneNote でアクセスできる組織内のパブリックドキュメント。

Microsoft Search を使用すると、ドキュメントに対するアクセスとアクセス許可を持つユーザーのみが、その文書から抽出された頭字語を表示できるようになります。 頭字語がユーザーのメールボックスからマイニングされる場合、そのユーザーのみがその略語を表示できます。

> [!NOTE]
> マイニングされた頭字語にはセットアップは必要ありません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問
**Q: どのように編集とマイニングされたデータがランク付けされるのですか?**

**A:** 現在、機能は、抽出された略語の上に編集上の略語をランク付けします。

**Q: 発行後に編集者の略語が Microsoft Search に表示されるまでにどのくらいの時間がかかりますか?**

**A:** 発行済みの状態に追加された頭字語が Microsoft Search で利用できるようになるまでに最大3日間かかります。 

**Q: ユーザーが頭字語の回答を開始する方法を教えてください。**

**A**: 頭字語の回答を取得するには、ユーザーは[Bing](https://bing.com) **検索**ボックスに特定のクエリパターンを入力する必要があります。 現時点では、 [Office 365](https://Office.com)または[SharePoint](https://products.office.com/sharepoint/collaboration)では、頭字語の回答は使用できません。

**Q: 新しい電子メールやドキュメントを受信または送信した後に、マイニングされた頭字語が表示されるまでにどのくらいの時間がかかりますか?**

**A:** 新しい電子メールまたはドキュメントから抽出された略語は、Microsoft 検索結果に表示されるまでに最大7日間かかります。

**Q: ドキュメントを選択するために、ドキュメントをマイニングの特定の形式にする必要がありますか。**

**A:** 違います。 画像、フォルダー、および zip ファイル以外のすべてのファイルの種類をサポートしています。

**Q: Microsoft はすべての言語のドキュメントから頭字語を地雷していますか?**

**A**: Microsoft は、ドキュメントからのマイニングのみを英語でサポートしています。 他の言語のサポートは、フェーズで追加されます。

**Q: 組織でマイニングされた頭字語を表示したくない場合はどうすればよいですか?抽出された略語が検索結果に表示されないようにすることはできますか?**

**A**: 検索結果での抽出された略語を表示しないようにするには、「[ビジネス製品についてのサポート](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support)」の手順に従ってカスタマーサポートチケットを作成します。
サポートチケットを作成した後は、検索結果に表示されなくなるまでに最大48時間かかります。 

**Q: [Office 365](https://Office.com)と[SharePoint Online](https://products.office.com/sharepoint/collaboration)で頭字語の回答が表示されるのはいつですか。**

**A**: Office 365 と SharePoint Online での頭字語の回答は製品ロードマップの一部ですが、現在、日付または時間枠を提供することはできません。
