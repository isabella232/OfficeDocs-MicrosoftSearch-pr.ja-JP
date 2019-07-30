---
title: Microsoft Search のセットアップ
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search を初めてセットアップする。
ms.openlocfilehash: 55ff009a17f63bfdaa1edf1e14fddfe132e20000
ms.sourcegitcommit: 4eeb78066fd13e906daed3add003398bd9d0f6ca
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2019
ms.locfileid: "35917580"
---
# <a name="set-up-microsoft-search"></a>Microsoft Search のセットアップ

Microsoft Search では、メール、ファイル、SharePoint ファイル、OneDrive コンテンツ、その他の共有リソース、ユーザーの組織内のインターネットを含む、すべてのデータソースに安全にアクセスすることにより、ファイルやドキュメント、内部サイトやビジネス ツール、ユーザーやグループ、場所や方向、会話や回答などの情報を検索するのに役立つユーザー フレンドリなインターフェイスを提供しています。

Microsoft Search の機能の詳細については、「[Microsoft Search の概要](overview-microsoft-search.md)」を参照してください。

## <a name="get-started"></a>はじめに

Microsoft Search は Microsoft 365 の一部であり、この機能をサポートしているすべての Microsoft アプリに対して既定で有効になっています。 ユーザーは、職場または学校のアカウントでサインインし、Bing のブラウザーを既定の検索プロバイダーとして設定するだけで、利用できます。

Microsoft Search の管理は、Microsoft 365 管理センターから行います。

1. Microsoft 365 管理センターで、[**設定**]  >  [**Microsoft**] に移動します。

**注:** [**設定**] の下に [Microsoft Search] が表示されない場合は、管理センターの任意のページの右上隅にある [**プレビューを試す**] スイッチを有効にしてください。

管理者として、効率的でユーザー フレンドリな Microsoft Search の操作性を組織内で実現するために、いくつかの点を考慮する必要があります。

## <a name="step-1-check-access-level-of-your-users"></a>手順 1: ユーザーのアクセス レベルを確認する

Microsoft Search では、コンテンツ ソースのセキュリティ設定を尊重されます。 検索結果としてユーザーに表示される内容は、アクセス許可のレベルによって異なります。 ユーザーが、自分がアクセスを許可されているコンテンツのみを見つけるように、組織内のユーザーのアクセス レベルを確認してください。

| サービス         | 説明                                                                                                                                                                                                                                         |
| --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| グループ          | [グループでメンバーを追加または削除する](https://docs.microsoft.com/office365/admin/create-groups/add-or-remove-members-from-groups)                                                                                                                     |
| ユーザー          | アドレス一覧で特定のユーザーが検索されないようにするには、[Set-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-user) ユーザー コマンドレットを使用して、パラメーター `HiddenFromAddressListEnabled` を `true` に設定します。 |
| Microsoft Teams | [Microsoft Teams へのユーザー アクセスを管理する](https://docs.microsoft.com/microsoftteams/user-access)                                                                                                                                                      |
| OneDrive        | [共有を管理する](https://docs.microsoft.com/OneDrive/manage-sharing)                                                                                                                                                                                |
| SharePoint      | 
  [アクセス許可の計画](https://docs.microsoft.com/ja-JP/sharepoint/plan-your-permissions-strategy)<br> 
  [アクセス許可レベルを作成する](https://docs.microsoft.com/ja-JP/sharepoint/how-to-create-and-edit-permission-levels)                          |
| OneNote         | OneNote に埋め込まれているファイルを検索することはできません。 [OneDrive でノートブックの権限を変更する](https://support.office.com/article/B9600CCF-045A-40E6-9913-4A7EB02869A5)                                                                    |
| Yammer          | [Yammer のセキュリティ設定](https://docs.microsoft.com/Yammer/manage-security-and-compliance/yammer-security-settings)                                                                                                                               |

## <a name="step-2-assign-search-admin-and-search-editor"></a>手順 2: Search 管理者と Search エディターを割り当てる

**Search 管理者**と **Search エディター**という 2 つの制限付き管理者ロールを利用して Microsoft Search をサポートできます。

> [!NOTE]
> Search 管理者と Search エディターの役割がアクセス許可の付与を行えるのは Microsoft 365 管理センターのみで、従来の **Microsoft Search in Bing 管理ポータル**では行えません。 従来のポータルで Microsoft Search を管理するには、全体管理者である必要があります。

Search 管理者は、エンド ユーザーの検索環境に直接影響を与えます。 これには、ユーザーに表示する結果の種類の選択が含まれます。 ユーザーが組織内で検索するさまざまなトピックに対して、信頼できるコンテンツを 1 人で選択して作成するのは難しい場合があります。 特定分野のエキスパート (SME) や他のユーザーを Search エディターとして追加して、その専門知識や知見を活用することをお勧めします。

Microsoft Search で組織の検索設定と検索コンテンツを管理するには、ユーザーに次の役割を割り当てます。

1. **Search 管理者:** この役割では、検索結果のコンテンツを作成したり管理したりして、組織内の検索結果を向上させるためのクエリ設定を定義できます。 Search 管理者は、Microsoft Search の構成を管理し、Search エディターが実行する権限を持つコンテンツ管理タスクをすべて実行できます。
2. **Search エディター:** Microsoft 365 管理センターで Microsoft Search のコンテンツを作成、管理、および削除します。 この役割には、よく寄せられる質問や回答、重要な場所や位置、頻繁に検索および使用されるサイトやアプリなどの編集コンテンツを作成および管理する権限があります。

現時点では、Search 管理者と Search エディターの役割は、全体管理者が割り当てる必要があります。詳細については、「[Assign admin roles (管理者の役割を割り当てる)](https://docs.microsoft.com/ja-JP/office365/admin/add-users/assign-admin-roles?view=o365-worldwide)」を参照してください。

## <a name="step-3-make-content-easy-to-find"></a>手順 3: コンテンツを見つけやすくする

Microsoft Search では、ユーザーのために堅牢な検索環境を構築するために使用できるツールを管理者に提供しています。 Microsoft Search では、管理者がより優れた検索機能を作成し、コンテンツの見つけやすさを向上させるために、次の 3 つの検索コンテンツを使用することができます。

- **ブックマーク:** ブックマークとは、SharePoint の昇格した結果に似たもので、ユーザーのクエリに対して最適な結果を検索結果の上位に昇格させ、重要な内部サイトをユーザーが簡単に見つけられるようにします。
- **質問と回答 (Q&A):** Q&A はよく寄せられる質問 (FAQ) に似たもので、通常は質問と回答の形式です。 ユーザーの作業に関連する質問に対する最適な回答を提供します。
- **場所:** 場所とは、ユーザーが組織の建物、オフィス、キャンパスを特定するのに役立つアドレスのことです。

ブックマーク、Q&A、場所の数が増えれば増えるほど、ユーザーにとって価値が高く、利点が多いものになります。 ただし、結果を適切かつ最新の状態に保つために定期的に確認および更新する必要があるため、数が増えすぎると管理上の負担が大幅に増加してしまいます。

ユーザーのためのブックマークを考慮する必要があるコンテンツの例を次に示します。

- 組織や製品やサービスの情報。
- すべてのユーザーが利用できる情報コンテンツ。たとえば、会社に関する情報、Windows や Office アプリ用のヘルプなどです。
- 組織内ユーザーが、日常業務で検索するコンテンツ。 従業員の福利厚生、時間と経費のレポート、発注書の発行、IT サービスからのヘルプの入手など、業務関連の一般的な検索項目です。

検索コンテンツの作成と管理の詳細については、「[簡単に見つけられるコンテンツ](make-content-easy-to-find.md)」を参照してください。

## <a name="step-4-test-single-sign-on"></a>手順 4: シングル サインオンのテスト

Microsoft Search では、組織のデータへのアクセスを認証および承認するために Azure Active Directory (AAD) を使用します。 つまり、ユーザーが Office 365 アプリまたは Windows 10 にサインインすると、自動的に職場または学校のアカウントにもサインインするという意味です。

ユーザーがサインインするように求められる回数が減るため、Microsoft Search ユーザーはシングル サインオンを使用するようお勧めします。 管理者は、ブロッキングの構成の問題を特定できるように、小規模なユーザー グループでシングル サインオンをテストする必要があります。

Windows 10 における Chrome ユーザーの場合、シングル サインオンが機能するのは、Chrome 向けの Windows 10 と AAD サインイン拡張機能がインストールされている場合のみです。 インストールが完了したら、Office 365 や Bing などのサポートされているサイトにサインインするときに、Chrome 拡張機能を使用して AAD で簡単に認証できます。 この機能は、承認されたユーザーのみが使用できます。

Chrome の Windows 10 および AAD サインイン拡張機能をダウンロードしてインストールするには、[Chrome Web ストア](https://go.microsoft.com/fwlink/?linkid=2090961) にアクセスしてください。

## <a name="step-5-training-and-communication"></a>手順 5: トレーニングおよびコミュニケーション

従業員が自分で簡単にアクセスできるセルフサービスのリソースを確立します。 これにより、お客様とチームの全体的な負担を軽減し、常にコミュニケーションを促進し、従業員の自己トレーニングと教育に役立てることができます。 ユーザーのコミュニケーション、FAQ、ビデオ、録画されたトレーニングやウェビナーを提供します。 まずは、次のリンクを参考にしてください。

- [Office の Microsoft Search で必要な情報を見つける](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Office 365 トレーニング センター](https://support.office.com/office-training-center)
- 
  [Microsoft Search センター](https://support.office.com/ja-JP/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

## <a name="trying-out-microsoft-search-in-bing"></a>Microsoft Search in Bing を試す

**Microsoft Search in Bing** は無効にすることができます。 無効にすると、Bing 検索では組織のコンテンツが表示されなくなります。 既定では、Microsoft Search in Bing は有効に設定されています。ユーザー エクスペリエンスを向上させるために、Bing で Microsoft Search を有効にしておくことをお勧めします。

[**設定**]  >  [**サービスとアドイン**]  >  [**Microsoft Search in Bing**] の順に移動して、オンとオフを切り替えます。
