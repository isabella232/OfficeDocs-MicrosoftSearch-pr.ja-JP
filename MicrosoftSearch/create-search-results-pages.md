---
title: SharePoint Online でカスタム検索結果ページを作成する
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: SharePoint Online サイトの独自の検索結果ページを作成する
ms.openlocfilehash: b5abb25f15795389dd8b6d5683ac336af7422e0a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031640"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>SharePoint Online でカスタム検索結果ページを作成する

SharePoint で検索エクスペリエンスをカスタマイズする 1 つの方法は、サイトのカスタム検索結果ページを作成することです。 これにより、Microsoft 検索結果ページの既定ではなく、作成したページを使用できます。 これにより、検索結果エクスペリエンスがユーザーに対してどのように表示されるのか、より柔軟に対応できます。

>[!NOTE]
> 既定で使用可能な既定の Microsoft 検索結果ページに変更を加える場合は、「検索結果のカスタマイズ」 [ページをご覧ください](customize-search-page.md)。

カスタム結果ページを使用すると、組織のニーズをサポートする検索結果のレイアウトとデザインを制御するために使用できる新しいページを作成できます。 SharePoint Patterns and Practices コミュニティの任意の組み込み Web パーツ、オープンソース検索 Web パーツ、および SharePoint Framework を使用して開発したカスタム Web パーツを使用できます。

## <a name="configure-a-results-page"></a>結果ページの構成

SharePoint Online でカスタム結果ページを構成するには、次の手順に従います。

1. カスタム結果ページを構成するサイトを参照し、[サイトの設定] >[検索設定] > **移動します**。

2. [検索設定] で、[親と同じ結果ページ設定を使用する]から選択を解除し、[カスタム結果ページにクエリを送信する] を選択し、[結果] ページの URL に値 **を指定します**。 次に、変更を保存します。 ここで使用する URL は、カスタム結果ページとして使用するために作成したページ用である必要があります。

>[!NOTE]
> カスタム結果ページは、サイトと同じドメイン上にある必要がありますが、同じサイト コレクション内に存在する必要はない。  

または、[サイトの設定] ページを使用する代わりに [、Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) コマンドを使用して値を設定することもできます。

設定が完了すると、ページの上部のナビゲーション バーに表示される Microsoft Search ボックスを使用して検索すると、カスタム検索結果ページが表示され、サイト ページまたはサイトのホーム ページから検索を入力するときに使用されます。 リスト、ライブラリ、またはサイト コンテンツ ページ内で検索する場合は使用されません。 リンクを使用して、リストとライブラリの検索結果から検索を展開して、カスタム結果ページに移動できます。

## <a name="change-the-layout-of-your-custom-results-page"></a>カスタム結果ページのレイアウトを変更する

**HeaderlessSearchResults** という名前のページ レイアウトを使用すると、検索結果ページを検索結果エクスペリエンスの近くに表示できます。 この新しいレイアウトは、カスタム検索結果ページに設定されているページでのみアクティブにできます。

ページ レイアウトを設定するには、-LayoutType HeaderlessSearchResults で [Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) コマンドを使用できます。

## <a name="use-sharepoint-framework-query-extensions"></a>SharePoint Framework クエリ拡張機能の使用

カスタム検索結果ページでは [、SharePoint Framework クエリ](/sharepoint/dev/spfx/building-search-extensions) 拡張機能を使用して、検索エンジンに送信される前にクエリを変更することもできます。

## <a name="additional-resources"></a>その他のリソース

カスタム結果ページの詳細については [、「Ignite 2019 Search Customization and Development session」を参照してください](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)。

オープン ソース プロジェクトの場合は、Microsoft Search API の使用を開始し、カスタマイズと拡張性のサンプルを追加するには [、GitHub の Microsoft Search を参照してください](https://github.com/microsoft-search)。