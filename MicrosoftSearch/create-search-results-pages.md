---
title: SharePoint Online でカスタム検索結果ページを作成する
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: SharePoint Online サイト用の独自の検索結果ページを作成する
ms.openlocfilehash: 9b168dccaa6126148c877b5841b91c63f7bdc2ac
ms.sourcegitcommit: 5fb46a04e86fb49477f8ce7ab3caa1b503215b8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503241"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>SharePoint Online でカスタム検索結果ページを作成する

SharePoint での検索の動作をカスタマイズする方法の1つは、サイトのカスタム検索結果ページを作成することです。 これにより、Microsoft の検索結果ページの既定値ではなく、作成したページを使用できるようになります。 これにより、検索結果がユーザーに対してどのように表示されるかをより柔軟にすることができます。

>[!NOTE]
> 既定で利用できる既定の Microsoft 検索結果ページに変更を加えるには、「[検索結果ページをカスタマイズ](customize-search-page.md)する」を参照してください。

カスタム結果ページを使用すると、組織のニーズをサポートするための検索結果のレイアウトと設計を制御するために使用できる新しいページを作成できます。 Sharepoint のパターンとプラクティスコミュニティから、任意の組み込み web パーツ、オープンソース検索 web パーツを使用することができます。また、SharePoint Framework を使用して開発したカスタム web パーツを使用することもできます。

## <a name="configure-a-results-page"></a>結果ページを構成する

SharePoint Online でカスタムの結果ページを構成するには、次の手順を実行します。

1. カスタムの結果ページを構成するサイトを参照し、[サイトの設定] **> サイトコレクションの設定 > 検索**の設定] に移動します。

2. [検索の設定] で、 **[親と同じ結果ページの設定を使用**する] をオフにし、[**カスタムの結果ページにクエリを送信**] を選択して、 **結果ページの URL**の値を指定します。次に、変更内容を保存します。 ここで使用する URL は、カスタムの結果ページとして使用するために作成したページに対して使用する必要があります。

>[!NOTE]
> カスタムの結果ページは、サイトと同じドメインにある必要がありますが、同じサイトコレクションに存在する必要はありません。  

または、 [PnPSearchSettings SharePoint PnP PowerShell コマンド](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps)を使用して、[サイトの設定] ページを使用する代わりに値を設定することもできます。

設定すると、ページの上部にあるナビゲーションバーに表示される Microsoft 検索ボックスを使用して検索すると、カスタム検索結果ページが表示され、サイトページまたはサイトのホームページから検索を入力したときに使用されます。 リスト、ライブラリ、または [サイトコンテンツ] ページ内で検索する場合は、使用されません。 このリンクを使用すると、リストとライブラリの検索結果から検索を拡張して、カスタムの結果ページにアクセスすることができます。

## <a name="change-the-layout-of-your-custom-results-page"></a>カスタム結果ページのレイアウトを変更する

[ **Header狭く Searchresults** ] という名前のページレイアウトを使用して、検索結果ページを、不在時の検索結果ページに近い状態で表示することができます。この新しいレイアウトは、カスタム検索結果ページになるように設定されたページに対してのみアクティブにできます。

ページレイアウトを設定するには、 [PnPClientSidePageSharePoint PnP PowerShell コマンド](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps)を-Layouttype HeaderlessSearchResults で使用できます。

## <a name="use-sharepoint-framework-query-extensions"></a>SharePoint Framework のクエリ拡張機能を使用する

カスタム検索結果ページでは、 [SharePoint Framework クエリ拡張機能](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions)を使用してクエリを変更してから、検索エンジンに送信することもできます。

## <a name="additional-resources"></a>その他のリソース

カスタム結果ページの詳細については、「 [Ignite 2019 Search Customization And Development session](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)」を参照してください。

オープンソースプロジェクト、Microsoft Search Api の概要、およびカスタマイズと拡張機能のサンプルについては、 [GitHub の Microsoft search](https://github.com/microsoft-search)を参照してください。
