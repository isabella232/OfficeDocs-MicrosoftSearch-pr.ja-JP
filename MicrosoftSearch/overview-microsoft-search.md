---
title: Microsoft Search の概要
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
description: Microsoft Search とは何か、その利点、Microsoft Search をサポートしているアプリの概要について説明します。
ms.openlocfilehash: fc21328f9a72ac77e37ae366bd138770509d6080
ms.sourcegitcommit: d40d44d01b27dfed92577446fe7a30008b28deb4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2020
ms.locfileid: "43914491"
---
# <a name="overview-of-microsoft-search"></a>Microsoft Search の概要

Microsoft 検索を使用すると、作業を完了するために必要な情報を見つけることができます。 人、ファイル、組織図、サイト、またはよく寄せられる質問に対する回答を検索する場合でも、就業中に Microsoft Search を使用して回答を得ることができます。

Microsoft Search を使用すると、ユーザーは適切な回答、他のユーザー、コンテンツを見つけて、既に作業しているアプリでタスクを完了することができます。

- 検索元のアプリの**コンテキスト**に応じた結果を取得できます。 たとえば、 [Microsoft Outlook](https://www.microsoft.com/outlook)で検索すると、 [SharePoint](http://sharepoint.com/)サイトではなくメールが検索されます。 SharePoint で検索すると、サイト、ページ、ファイルが見つかります。
- ユーザーがどのアプリで作業していても、Microsoft Search は**個人用**です。 Microsoft Search では、 [Microsoft Graph](https://developer.microsoft.com/graph/)の洞察を使用して、各ユーザーに関連する結果を表示します。 各ユーザーが同じ単語を検索しても、それぞれの結果は異なる可能性があります。 ユーザーには既にアクセス権のある結果のみが表示されます。Microsoft Search によってアクセス許可が変更されることはありません。
- 情報がある場所を覚えておく必要はありません。 たとえば、ユーザーが[Microsoft Word](https://products.office.com/word)で作業していて、自分の[OneDrive](https://onedrive.live.com/about/)から共有されている仕事仲間の情報を再利用する必要があるとします。 この場合、OneDrive に切り替えて、そのプレゼンテーションを検索する必要はなく、Word から検索するだけで済みます。
- [Bing](https://bing.com) を使用している場合、公開されている Web の検索結果に加えて組織内からの結果も取得できます。

## <a name="what-users-see"></a>ユーザーに対する表示

[Bing](https://bing.com)では、ユーザーは web 検索と同じ検索ボックスを使用します。 Office アプリでは、ユーザーはヘッダーバーに Microsoft 検索ボックスを検索します。 次のように表示されます。

![ヘッダー バーに Microsoft Search ボックスが表示されているアプリ ウィンドウのスクリーン ショット](media/Headings_520.png)

ユーザーが**検索**ボックスをクリックすると、Office 365 の以前のアクティビティに基づいて検索結果が表示され、組織内の傾向を示すコンテンツが検索されます。 検索で考慮されるアクティビティには、ユーザーが最近作業していたファイルや最近使用したコマンドだけでなく、そのユーザーが共同作業している他のユーザーなどがあります。 ユーザーが**検索**ボックスへの入力を開始すると、提示された結果が更新されます。 ユーザーは**検索ボックスから直接検索結果**を開くことができます。 [SharePoint](http://sharepoint.com/)での検索の例を次に示します。

![クエリと候補の検索結果が表示されている Microsoft Search ボックスのスクリーンショット](media/SERP_text_520.png)

検索ボックスに表示されている候補がユーザーにとって期待していない場合は、次のように**入力して**、結果の完全なリストを開きます。 アイテムの最終更新者、アイテムが保存された日時と場所などのメタデータを使用したり、メタデータをプレビューして、探しているものかどうかを判断したりできます。

![Microsoft Search の結果ページのスクリーンショット](media/search_box.png)

## <a name="benefits-of-microsoft-search"></a>Microsoft Search のメリット

**すべての Microsoft Search ボックスから Microsoft 365 全体を検索** - どの Microsoft Search ボックスからでも検索を実行し、作業していたタスクにすばやく戻ることができます。 Microsoft Search では、 [SharePoint](http://sharepoint.com/)、 [Microsoft OneDrive For Business](https://onedrive.live.com/about/business/)、 [Microsoft Exchange Server](https://products.office.com/exchange/microsoft-exchange-server)など、Office 365 のデータソースからの結果がまとめられています。

**検索が容易**– Microsoft search では、Office 365 のユーザーの以前のアクティビティに基づいて**検索**ボックスに、結果が表示されます。

**共有ファイルの検索** - Microsoft Search は高度なクエリ理解を利用して、共有ファイルの検索を容易にします。 ユーザーは共同作業しているファイルを簡単に見つけることができます。

**関連コンテンツの表示** - ポリシー、利点、リソース、ツールなどのタスクの完了に必要な情報および回答をより詳細に提供しています。 また、新入社員、リモートワーカー、さまざまな地域など、特定のグループを対象にすることもできます。

**すべてのアプリで管理可能** - Microsoft Search は既定で**オン**になっており、実行するあらゆる管理はすべてのアプリの Microsoft Search に適用されます。

## <a name="tailoring-microsoft-search-to-your-organization"></a>組織に合わせた Microsoft Search のカスタマイズ

管理者は、ユーザーに対してすばらしい Microsoft 検索機能を作成できます。

**有用なコンテンツを表示**–回答は、キーワードに基づいて検索クエリに高速で権限の高い結果を提供します。 [コンテンツを計画](plan-your-content.md)します。

**外部コンテンツを追加**する: Microsoft Graph コネクタを使用すると、外部コンテンツをインデックスに取り込むことができます。 コネクタを使用して、Microsoft 365 の外部にあるデータおよびファイルを検索する際の利便性を向上させます。 [Microsoft Graph コネクタの概要](connectors-overview.md)

**ユーザーの作業をカスタマイズ**する-業種およびその他の構成を使用してユーザーの作業をカスタマイズできます。 [Microsoft 検索ページをカスタマイズする](customize-search-page.md)

## <a name="what-content-is-searched"></a>検索されるコンテンツ

Microsoft Search は、組織が Microsoft 365 に保存されているコンテンツ、またはコネクタ経由でインデックス付けされたコンテンツを示します。 Microsoft Search では、複数のテナントを検索したり、他の組織によって共有されているコンテンツから結果を表示したりすることはありません。 組織でクラウド ハイブリッド検索を使用してハイブリッド SharePoint 環境をセットアップすると、Microsoft Search は SharePoint Server 環境に接続している外部コンテンツを含む、オンラインおよびオンプレミスの両方の SharePoint コンテンツからの検索結果を返します。 [ハイブリッド検索環境の詳細については、こちらを参照してください](https://docs.microsoft.com/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint)。

ユーザーは、他の場所から取得した同じ検索結果を取得し、インターネットからも結果を取得します。

## <a name="how-microsoft-search-works"></a>Microsoft Search のしくみ

ユーザーが検索すると、Microsoft Search ではクエリを処理し、より大きいフレーズから検索意図が解析されます。これは人工知能 (AI) を使用して、ユーザーがクエリに追加した、ユーザーの検索意図に影響を与えない一般的な余分なフレーズを Microsoft Search が学習することで実現されています。 たとえば、ユーザーが、「パスワードを変更する方法」という検索を行うと、重要度の低い単語はクエリから取り除かれ、「パスワードを変更」などの関連性の高い単語に基づいてトリガーされます。  
ユーザーが表示する**アクセス許可**を持っている検索結果は、検索結果ページに表示されます。 Microsoft Search では、インテリジェント ランキング アルゴリズムを使用して、結果を関連性に従って順序付けします。

## <a name="how-microsoft-search-in-bing-protects-your-company-data"></a>Bing での Microsoft Search による会社データの保護

[Bing での Microsoft Search のセキュリティとプライバシー](security-for-search.md)

## <a name="see-also"></a>関連項目

[Microsoft Search のセットアップ](setup-microsoft-search.md)
