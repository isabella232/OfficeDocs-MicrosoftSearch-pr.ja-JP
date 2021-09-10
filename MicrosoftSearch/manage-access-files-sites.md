---
title: ファイルとサイトへのアクセスを管理する
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: 管理者がサイトとファイルへのアクセスを組織内で適切に制限する方法の概要。
ms.openlocfilehash: c19442e1d89ddfe65a772213a8b0225ca680d699
ms.sourcegitcommit: 3e069fd920b5fcdfe97a0261930447e9e87d9013
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973820"
---
# <a name="manage-access-to-files-and-sites"></a>ファイルとサイトへのアクセスを管理する

すべてのファイルまたはサイトを組織内のすべてのユーザーが利用できるとは言いません。 管理者とユーザーは、特定の問題に最適なソリューションを使用して、機密情報や機密情報へのアクセスを管理できます。 適切なアクセス制御が一貫して適用されない場合、"oversharing" と参照される結果になります。 組織内で共有される情報を簡単に見つけやすくすることで、不適切な制限を持つファイルやサイトに、誤ってアクセスMicrosoft Search。

検索管理者は、これらのオーバーシェアリングの問題を解決できない。 アクセスが制限のないファイルやサイトは、内部検索結果や他の検出方法を通じて表示されます。 ただし、オーバーシェアリングを防止するコントロールが配置されている場合、検索を含むすべての道は閉じられます。

## <a name="solutions-to-prevent-oversharing"></a>オーバーシェアリングを防止するソリューション

以下のツール、ポリシー、および手法を使用して、情報へのアクセスを制限または難読化して、過剰なアクセスを防止します。 これらのソリューションを実装するには、グローバル、コンプライアンス、またはセキュリティ管理者のアクセスが必要です。 また、サイトとファイルを適切に保護、ラベル付け、およびアクセス許可する方法についてユーザーに教育するための内部キャンペーンをお勧めします。

### <a name="public-sites-or-sites-with-public-groups-as-owners"></a>パブリック グループを所有者として持つパブリック サイトまたはサイト

すべてのユーザーとファイルを共有できる方法の 1 つは、パブリック サイトまたはパブリック グループを所有者として持つサイトを通じて行います。 感度ラベルを使用すると、ユーザーがパブリック グループまたはサイトを作成することはできません。 すべてのラベルを構成してプライベート グループ/サイトを作成し、グループ/サイトのラベルを管理する方法の詳細については[、「Microsoft Teams、Microsoft 365](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)グループ、および SharePoint サイトのコンテンツを保護するために、感度ラベルを使用する」を参照してください。

もう 1 つのオプションは、組織内でグループを作成Microsoft 365を制御する方法です。 詳細については、「グループを作成する必要があるユーザーのグループを作成する」を参照Microsoft 365[してください](/microsoft-365/solutions/manage-creation-of-groups#step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups)。

これらのソリューションのいずれかを実装する場合は、ユーザーがパブリック グループの作成を要求し、変更についてユーザーに通知するプロセスをセットアップすることもできます。

組織でグループを作成する機能を制限できない場合は、監査を通じてグループの作成を含むアクティビティを監視できます。 基本的な監査と高度な監査の詳細については、「監査ソリューション」を参照[Microsoft 365。](/microsoft-365/compliance/auditing-solutions-overview)

### <a name="shared-files"></a>共有ファイル

ビジネス機密として分類されたファイルへのアクセスを制限するには、組織にデータ分類を定義して適用できます。 新しい分類子のトレーニングに役立つサンプル データを収集する必要があります。 前提条件とアクセス許可の詳細については、「データ分類について [」を参照してください](/microsoft-365/compliance/data-classification-overview)。

エグゼクティブなど、特定のグループのメンバーへのファイル アクセスを制限するには、セキュリティ グループを対象にしたカスタム ラベルを作成できます。 次に、セキュリティ グループ メンバーがラベルを適用すると、グループへのアクセスが自動的に制限されます。 カスタム ラベルの詳細については、「感度[](/microsoft-365/compliance/create-sensitivity-labels)ラベルとそのポリシーを作成して構成する」および「暗号化を適用する感度ラベルを使用してコンテンツへのアクセスを制限する」[を参照してください](/microsoft-365/compliance/encryption-sensitivity-labels)。

ドキュメントとメールに適切なラベルが付けされていることを確認するために、管理者は既定のラベル ポリシーを設定し、ユーザーにラベルを付け要求できます。 詳細については、「[メールとドキュメントにラベルを適用することをユーザーに義務付ける。](/microsoft-365/compliance/sensitivity-labels-office-apps#require-users-to-apply-a-label-to-their-email-and-documents)」を参照してください。

また、検索時に最近のファイルが表示されるのを防ぐことで、ファイルのオーバーシェアリングを最小限に抑えることもできます。 これは、グループ レベルまたは組織内のすべてのユーザーに対して実行できます。 グループに対する最近のファイルの表示を停止するには、「Microsoft Graph でアイテムインサイトのプライバシー[をカスタマイズする」を参照してください](/graph/insights-customize-item-insights-privacy)。 グループ メンバーは、独自の最近のファイルを表示できますが、他のメンバーは結果が見つからないというメッセージを受け取ります。 組織内のすべてのユーザーに対して最近使用したファイルをオフにする場合は、そのファイルをオフにするDelve。 詳細については、「Control [access to Delve」 を参照してください](/sharepoint/delve-for-office-365-admins#control-access-to-delve)。

> [!Note]
> ユーザーは引き続き、ユーザーと共有されているファイルを検索結果Microsoft Searchできます。 アイテムの分析情報をカスタマイズしたり、Delveをオフにしたりすると、ユーザーの最近使用したファイルの一覧にファイルが表示されるのを停止するだけになります。

### <a name="sites-and-files-between-groups"></a>グループ間のサイトとファイル

グループ間のファイルとサイトの共有 (たとえば、マーケティング チームで機密プロジェクトを管理する財務チーム) を制限するには、情報バリア ポリシーを定義して実装できます。 また、これらの障壁により、コミュニケーションやコラボレーションの他の側面Microsoft Teams、SharePoint、OneDrive。 詳細については、「情報バリア[について」を参照Microsoft 365。](/microsoft-365/compliance/information-barriers)

## <a name="get-access-insights"></a>アクセスインサイトの取得

アクセス ガバナンスは、組織内で最も機密性の高いドキュメントと過剰共有サイトを持つサイトに関する分析情報を提供します。 概要については、「セキュリティとコンプライアンスの新機能」を参照SharePoint[およびOneDrive。](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/what-s-new-in-security-and-compliance-in-sharepoint-and-onedrive/ba-p/1696705) このプレビューに組織 [を指名](https://forms.microsoft.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) する必要があります。
