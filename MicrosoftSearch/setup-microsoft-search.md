---
title: '**Microsoft Search** のセットアップ'
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 04/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search を初めてセットアップする。
ms.openlocfilehash: f4648988563245f6a61169d7e62b48c456dfa8fa
ms.sourcegitcommit: 06f995ae7696a8cafcd12d19ed16a35d059b6abb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/09/2019
ms.locfileid: "33858274"
---
# <a name="set-up-microsoft-search"></a>Microsoft Search のセットアップ

**Microsoft Search** では、メール、ファイル、SharePoint ファイル、OneDrive コンテンツ、その他の共有リソース、ユーザーの組織内のインターネットを含む、すべてのデータソースに安全にアクセスすることにより、ファイルやドキュメント、内部サイトやビジネス ツール、ユーザーやグループ、場所や方向、会話や回答などの情報を検索するのに役立つユーザー フレンドリなインターフェイスを提供しています。

**Microsoft Search** の機能の詳細については、「[Microsoft Search の概要](overview-microsoft-search.md)」を参照してください。

## <a name="get-started"></a>はじめに

**Microsoft Search** は Microsoft 365 の一部であり、この機能をサポートしているすべての Microsoft アプリに対して既定で有効になっています。 ユーザーは、職場または学校のアカウントでサインインし、Bing のブラウザーを既定の検索プロバイダーとして設定するだけで、利用できます。

しかし管理者であれば、組織内での効率的でユーザー フレンドリな **Microsoft Search** の操作性を実現するために、いくつかの点を考慮する必要があります。

### <a name="step-1-check-access-level-of-your-users"></a>手順 1: ユーザーのアクセス レベルを確認する

**Microsoft Search** は、コンテンツ ソースのセキュリティ設定を尊重します。 検索結果としてユーザーに表示される内容は、アクセス許可のレベルによって異なります。 ユーザーが、自分がアクセスを許可されているコンテンツのみを見つけるように、組織内のユーザーのアクセス レベルを確認してください。

[アクセス許可の計画](https://docs.microsoft.com/ja-JP/sharepoint/plan-your-permissions-strategy)や[アクセス許可レベルの作成](https://docs.microsoft.com/ja-JP/sharepoint/how-to-create-and-edit-permission-levels)について詳しくご確認ください。

### <a name="step-2-assign-search-admin-and-search-editor"></a>手順 2: Search 管理者と Search エディターを割り当てる

**Microsoft 管理センター** には 2 つの新しい役割があります。つまり、Search 管理者と Search エディターです。  すべての権限を持つグローバル管理者は、Search 管理者の役割を含む、管理者の役割をユーザーに割り当てます。 Search 管理者は、Search 管理者または Search エディターの役割を他のユーザーに委任できます。 異なる管理者の役割に関する詳細については、[Office 365 の管理者の役割について](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) を参照してください。

Search 管理者は、エンド ユーザーの検索エクスペリエンスに直接影響を与えます。 これには、ユーザーに表示する結果の種類の選択が含まれます。 ユーザーが組織内で検索するさまざまなトピックに対して、信頼できるコンテンツを 1 人で選択して作成するのは難しい場合があります。 SME や他のユーザーをエディターとして追加して、その専門知識や知見を活用することをお勧めします。 

**Microsoft Search** では、2 つの新しい役割を使用して、組織の検索設定とコンテンツを管理できます。
1. **Search 管理者:** この役割では、検索結果のコンテンツを作成したり管理したりして、組織内の検索結果を向上させるためのクエリ設定を定義できます。 Search 管理者は、**Microsoft Search** の構成を管理し、コンテンツを作成する Search エディターを指定します。
2. **Search エディター:** Microsoft 365 管理センターで **Microsoft Search** のコンテンツを作成、管理、および削除します。 この役割には、よく寄せられる質問や回答、重要な場所や位置、頻繁に検索および使用されるサイトやアプリなどの編集コンテンツを作成および管理する権限があります。ただし、検索設定を管理するアクセス権はありません。

**注:** これら 2 つの新しい役割である Search 管理者と Search エディターは、従来の管理ポータルではなく、**Microsoft 365 管理センター**でのみ利用できます。

管理者の役割の割り当てについては、「[一般法人向け Office 365 で管理者ロールを割り当てる](https://docs.microsoft.com/en-us/office365/admin/add-users/assign-admin-roles?view=o365-worldwide)」を参照してください。

### <a name="step-3-make-content-easy-to-find"></a>手順 3: コンテンツを見つけやすくする 

**Microsoft Search** では、ユーザーに対して堅牢な検索エクスペリエンスを構築するために使用できるツールを管理者に提供しています。 **Microsoft Search** では、管理者がより優れた検索機能を作成し、コンテンツの見つけやすさを向上させるために、次の 3 つの検索コンテンツを使用することができます。
- **ブックマーク:** ブックマークとは、SharePoint の昇格した結果に似たもので、ユーザーのクエリに対して最適な結果を検索結果の上位に昇格させ、重要な内部サイトをユーザーが簡単に見つけられるようにします。 
- **質問と回答 (Q&A):** Q&A はよく寄せられる質問 (FAQ) に似たもので、通常は質問と回答の形式です。 ユーザーの作業に関連する質問に対する最適な回答を提供します。
- **場所:** 場所とは、ユーザーが組織の建物、オフィス、キャンパスを特定するのに役立つ住所のことです。 

ブックマーク、Q&A、場所の数が増えれば増えるほど、ユーザーにとって価値が高く、利点が多いものになります。 ただし、結果を適切かつ最新の状態に保つために定期的に確認および更新する必要があるため、数が増えすぎると管理上の負担が大幅に増加してしまいます。

ユーザーのためのブックマークを考慮する必要があるコンテンツの例を次に示します。
- 組織や製品やサービスの情報。
- すべてのユーザーが利用できる情報コンテンツ。たとえば、会社に関する情報、Windows や Office アプリ用のヘルプなどです。 
- 組織内ユーザーが、日常業務で検索するコンテンツ。 従業員の福利厚生、時間と経費のレポート、発注書の発行、IT サービスからのヘルプの入手など、業務関連の一般的な検索項目です。 

検索コンテンツの作成と管理の詳細については、「[コンテンツを見つけやすくする](make-content-easy-to-find.md)」を参照してください。

### <a name="step-4-test-single-sign-on"></a>手順 4: シングル サインオンのテスト
**Microsoft Search** では、Azure Active Directory (AAD) を使用して、組織のデータへのアクセスを認証および承認します。  つまり、ユーザーが Office 365 アプリまたは Windows 10 にサインインすると、自動的に職場または学校のアカウントにもサインインするという意味です。

ユーザーがサインインするように求められる回数が減るため、**Microsoft Search** ユーザーはシングル サインオンを使用するようお勧めします。 管理者は、ブロッキングの構成の問題を特定できるように、小規模なユーザー グループでシングル サインオンをテストする必要があります。 

Windows 10 における Chrome ユーザーの場合、シングル サインオンが機能するのは、Chrome 向けの Windows 10 と AAD サインイン拡張機能がインストールされている場合のみです。 インストールが完了したら、Office 365 や Bing などのサポートされているサイトにサインインするときに、Chrome 拡張機能を使用して AAD で簡単に認証できます。 この機能は、承認されたユーザーのみが使用できます。 

Chrome の Windows 10 および AAD サインイン拡張機能をダウンロードしてインストールするには、[Chrome Web ストア](https://go.microsoft.com/fwlink/?linkid=2090961) にアクセスしてください。

### <a name="step-5-training-and-communication"></a>手順 5: トレーニングおよびコミュニケーション
従業員が自分で簡単にアクセスできるセルフサービスのリソースを確立します。 これにより、お客様とチームの全体的な負担を軽減し、常にコミュニケーションを促進し、従業員の自己トレーニングと教育に役立てることができます。 ユーザーのコミュニケーション、FAQ、ビデオ、録画されたトレーニングやウェビナーを提供します。 まずは、次のリンクを参考にしてください。
- [Office の Microsoft Search で必要な情報を見つける](https://support.office.com/article/find-what-you-need-with-microsoft-search-in-office-2457d4d8-48a8-4ad4-ab89-5a0657aa8446?ui=en-US&rs=en-US&ad=US)
- [Office 365 トレーニング センター](https://support.office.com/office-training-center)
- 
  [Microsoft Search センター](https://support.office.com/en-us/article/-working-title-microsoft-search-center-b8bf5a2c-7515-40a9-9a6a-b8ed382c86bc?ui=en-US&rs=en-US&ad=US)

### <a name="trying-out-microsoft-search-in-bing"></a>**Microsoft Search** in Bing を試す 
**Microsoft Search** 管理者は、Bing で **Microsoft Search** を無効にすることができます。 無効にすると、Bing 検索では組織のコンテンツが表示されなくなります。 既定では、**Microsoft Search** は Bing で有効になっています。 ユーザー エクスペリエンスを向上させるために、Bing で **Microsoft Search** を有効にしておくことをお勧めします。 

テスト テナントで **Microsoft Search** を試行する場合、またはすべてのユーザーが利用できるようにする前に検索エクスペリエンスをテストする場合は、**Microsoft Search** を無効にします。
Bing で **Microsoft Search** をオン/オフするには、**Microsoft 365 管理センター**の **[サービスとアドイン]** にアクセスし、**[Microsoft Search in Bing]** をオン/オフします。
