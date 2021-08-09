---
title: Q&A の管理
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: 回答を個別に検索して更新するか、Microsoft Searchツールを使用して Q&を一度に編集します。
ms.openlocfilehash: 2e54169a6196ec78bd96b33aa1ba71fc498b6ff13d8d872ad06ca0db1d9fc2c0
ms.sourcegitcommit: 71ac2a38971ca4452d1bddfc773ff8f45e1ffd77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2021
ms.locfileid: "54532868"
---
# <a name="manage-qas"></a>Q&A の管理

Q&A の作成は、ブックマークの作成と似ています。 Q&Web ページへのリンクを提供する代わりに、ユーザーの質問に回答できます。 リッチ テキストで回答の書式を設定できます。 ブックマークと Q ファイルが同&同じキーワードを共有している場合、ブックマークの結果が最初に表示されます。 ブックマークと同様に、Q&A が追加または変更された直後に、Q インデックス&更新されます。

## <a name="add-or-edit-a-single-qa"></a>1 つの Q&A を追加または編集する

1. [[Microsoft 365 管理センター]](https://admin.microsoft.com)で [**、[Q] に移動&します。**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Q ファイルを A に&するには、[追加] を **選択します**。
Q&A を編集するには、関連する Q&A の一覧で Q&A を選択します。 情報を追加または編集すると、プレビューが自動的に更新されます。
1. 変更内容を保存します。

### <a name="supported-html-tags"></a>サポートされている HTML タグ

回答 (説明) に既存の HTML コンテンツを使用したり、HTML タグを追加したりできます。 サポート対象外のタグは無視されます。

次の HTML タグがサポートされています。

- blockquote
- div
- em
- h1、h2、h3、h4
- ol、ul、li
- p
- pre
- span
- strong
- table、thead、tbody、tr、th、td
- u
- a
- code
- br
- hr
- img

## <a name="add-or-edit-qas-using-browser-extensions"></a>ブラウザー拡張機能を使用して Q&を追加または編集する

検索管理者は、ブラウザーの拡張機能を使用して検索コンテンツを簡単に作成できます。 ブラウザー拡張機能をインストールし、Q ファイルを生成するサイトに移動し、&します。 次に、Q ファイル A を&、ソース サイトへのリンクを含めできます。

現在、ブラウザー拡張機能は、ユーザーと Chrome Microsoft Edge利用できます。

- Edge (Legacy) の拡張機能をダウンロードするには、次のページ[にMicrosoft Store。](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab)
- 拡張機能 Chrome または Edge (Chromium) をダウンロードするには[、Chrome Web ストアに移動します](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm)。

## <a name="bulk-add-or-edit-qas"></a>Q&A を一括して追加または編集する

管理者は、インポート機能とエクスポート機能を使用して、Q ファイルの一括作成または編集&できます。

次のImport/Export機能を使用します。

- Q ファイルを一&追加する - テンプレート ファイルの Q&詳細を追加し、インポートします。
- Q&As - Export Q&As を .csv ファイルに一括編集し、エクスポートしたファイルで Q&A の詳細を編集してから、ファイルをインポートします。
- Q&をバックアップする - Q&を別のファイル.csvします。

Q ファイルをインポートまたはエクスポートするには、次&使用します。

1. [Q&A] タブの右上隅にある **[インポート]** を選択します。
[ **エクスポート] を** 選択して、既存のすべての Q&As をダウンロード.csvします。
1. 右側のウィンドウで、新しいファイルを使用してインポートする.csvします。 テンプレート ファイルをダウンロードして、必要なフィールドと詳細の一覧を取得します。
1. Q ファイルを追加または編集&テンプレート ファイルの詳細を追加または編集し、コンピューターに保存します。
1. [Q ファイル **のインポート]&ウィンドウ** で、[参照] を選択し、インポート.csvファイルを選択します。
1. **[インポート]** を選択します。

重要なテンプレート ファイルのヒント:

- 次のフィールドのデータは決して編集しないでください: **ID**、**最終更新日時**、**最終更新者**
- 既存のブックマークの **ID** を含めると、インポート ファイルの情報に置き換えられます。
- 同じタイトルまたは URL を持つ既存のブックマークがある場合、ブックマークはインポート ファイル内の情報で更新されます。
- テンプレート ファイル内のすべてのフィールドが必要で、必要なフィールドはブックマークの状態によって異なります。
- [状態]**フィールドに** 基づいて、ブックマークは下書き、提案、またはスケジュール済みとして保存されます。またはブックマークが自動的に発行されます。  
- 複数の組織を管理するパートナーの場合: ブックマークをある組織からエクスポートし、別の組織にインポートできます。 ただし、インポートする前に **ID** 列のデータを削除する必要があります。

> [!NOTE]
> Q ファイルをインポート&テンプレート ファイルにエラーが発生した場合と同様です。 エラーを回避するには、インポート ファイルの形式が正しく設定されていることを確認し、必要なすべての情報を含める必要があります。

エラーを回避する方法の詳細については、「インポート エラーを [防止する」を参照してください](manage-bookmarks.md#prevent-import-errors)。
