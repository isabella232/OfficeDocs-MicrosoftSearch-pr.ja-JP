---
title: Confluence Cloud Graph コネクタ (Microsoft Search
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: アプリケーションの Confluence Cloud Graph コネクタをMicrosoft Search
ms.openlocfilehash: baf6139257c8bf8e40bc997e2a408efb4fc2549f
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/15/2021
ms.locfileid: "59376236"
---
<!---Previous ms.author: kam1 --->

# <a name="confluence-cloud-graph-connector-preview"></a>Confluence Cloud Graph コネクタ (プレビュー)

Confluence Cloud Graphコネクタを使用すると、組織は Confluence コンテンツのインデックスを作成できます。 Confluence サイトからコネクタとインデックス データを構成した後、エンド ユーザーは、これらのコンテンツを Microsoft Search。

>[!NOTE]
>Confluence Cloud Graph コネクタはプレビュー中です。 早期アクセスを取得して試す場合は、このフォームを使用して [<b> サインアップしてください </b>](https://forms.office.com/r/duLxv8Nf8U)。  

この記事は、Microsoft 365管理者、または Confluence Cloud アプリケーション コネクタを構成、実行、および監視するGraphです。 この記事では、「コネクタ コネクタのセットアップ」に記載されている一般的Graph[補足](configure-connector.md)します。 まだ実行していない場合は、「コネクタのセットアップ」の記事Graph一般的なセットアップ プロセスを理解してください。

セットアップ プロセスの各手順は、トラブルシューティングと制限事項に関する情報を含む Confluence Cloud Graph コネクタにのみ適用される一般的なセットアップ手順または他の手順に従う必要があるという[](#troubleshooting)メモと共[](#limitations)に、以下に示します。


## <a name="before-you-get-started"></a>使用を開始する前に
組織の M365 テナントの管理者である必要があります。また、組織の Confluence サイトの管理者である必要があります。

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>手順 1: Graphコネクタを追加Microsoft 365 管理センター
一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-2-name-the-connection"></a>手順 2: 接続に名前を付け
一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-3-configure-the-connection-settings"></a>手順 3: 接続設定を構成する
Confluence サイトに接続するには、サイトの URL を使用します。 Confluence クラウド サイトの URL は通常 *、https://<organization_name>.atlassian.net/ のように見えます*。 Confluence サイトへの認証には、基本認証または OAuth 2.0 (推奨) のいずれかを選択できます。

### <a name="basic-auth"></a>Basic Auth
基本認証を使用して認証するために、アカウントのユーザー名 (通常は電子メール ID) と API トークンを入力します。API トークンの生成の詳細については、Atlassian アカウントの API トークンを管理する方法に関する [Atlassian のドキュメントを参照してください](https://support.atlassian.com/atlassian-account/docs/manage-api-tokens-for-your-atlassian-account/)。

### <a name="oauth-20"></a>OAuth 2.0
アプリを Confluence Cloud に登録して、アプリMicrosoft Searchインスタンスにアクセスできます。 詳細については [、「OAuth 2.0](https://developer.atlassian.com/cloud/confluence/oauth-2-3lo-apps/#enabling-oauth-2-0--3lo-)を有効にする方法」の「Atlassian サポート」のドキュメントを参照してください。

次の手順では、アプリを登録する方法に関するガイダンスを提供します。

1. [Atlassian Confluence](https://developer.atlassian.com/console/myapps/)管理アカウントを使用して、Atlassian Developer コンソールにサインインします。
2. をクリック `Create` して選択する `OAuth 2.0 integration`
3. アプリケーションに適切な名前を指定し、新しいアプリを作成します。
4. 左側の `Permissions` ナビゲーション ウィンドウから移動します。 を `Add` クリックします `Confluence API` 。 追加したら、次のスコープ (、 ) をクリックして `Configure` `Read Confluence space summary` `Read Confluence content properties` `Read Confluence detailed content` `Read Confluence content summary` `Read content permission in Confluence` `Read user` `Read user groups` 追加します `Search Confluence content and space summaries` 。
5. 左側の `Authorization` ナビゲーション ウィンドウから移動します。 コールバック URL を追加 `https://gcs.office.com/v1.0/admin/oauth/callback` し、変更を保存します。
6. 左側の `Settings` ナビゲーション ウィンドウから移動します。 このページから `Client ID` と `Secret` を取得します。

上記の詳細でアプリを登録すると、クライアント ID と **シークレットが** 取得 **されます**。 これらを使用して接続設定手順を完了します。

## <a name="step-4-select-properties-and-filter-data"></a>手順 4: プロパティを選択し、データをフィルター処理する

この手順では、Confluence データ ソースから使用可能なプロパティを追加または削除できます。 Microsoft 365では、いくつかのプロパティが既に選択されています。

Confluence クエリ言語 (CQL) 文字列を使用すると、ページを同期する条件を指定できます。 これは、Select ステートメント **の Where** **句SQLです**。 たとえば、過去 2 年間に変更されたページのみをインデックス化できます。 独自のクエリ文字列を作成する方法については [、「CQL を使用した高度な検索」を参照してください](https://developer.atlassian.com/server/confluence/advanced-searching-using-cql/)。 既定では、すべてのブログとページがコネクタによってインデックス付けされます。

[プレビュー結果] ボタンを使用して、選択したプロパティと CQL 文字列のサンプル値を確認します。

## <a name="step-5-manage-search-permissions"></a>手順 5: 検索アクセス許可を管理する

Confluence Cloud Graph コネクタは、[すべてのユーザー] **** または [このデータ ソースにアクセスできるユーザーのみ] に表示される検索 **アクセス許可をサポートします**。 [すべてのユーザー] **を選択** すると、すべてのユーザーの検索結果にインデックス付きデータが表示されます。 [このデータ **ソースにアクセス** できるユーザーのみ] を選択すると、アクセス権を持つユーザーの検索結果にインデックス付きデータが表示されます。

Confluence Cloud では、ユーザーとグループのセキュリティアクセス許可は、スペースのアクセス許可とページ制限を使用して定義されます。 Confluence Cloud Graph コネクタは、ページ制限がない場合に領域のアクセス許可を適用します。 ページ レベルの制限 (存在する場合) は、スペースのアクセス許可よりも優先されます。

[このデータソースへのアクセス権を持つユーザーのみ] を選択する場合は、Confluence サイトに Azure Active Directory (AAD) プロビジョニング ユーザーまたは非 AAD ユーザーを含むかどうかをさらに選択する必要があります。

組織に適したオプションを特定するには、次の方法を使用します。

1. Confluence ユーザーのメール ID が AADのユーザーの UserPrincipalName (UPN) と同じ場合は **、AAD** オプションを選択します。
2. Confluence ユーザーの電子メール ID が AAD のユーザーの UserPrincipalName (UPN) と異なる場合は、[非 **AAD]** オプションを選択します。 

>[!NOTE]
> * ID ソースの種類として AAD を選択した場合、コネクタは Confluence から取得したユーザーのメール ID を AAD から UPN プロパティに直接マップします。
> * ID の種類に対して "Non-AAD" を選択した場合は、「Id のマッピングの手順については [、「Map your-Azure AD Id」](map-non-aad.md) を参照してください。 このオプションを使用すると、メール ID から UPN へのマッピング正規表現を指定できます。

## <a name="step-6-assign-property-labels"></a>手順 6: プロパティ ラベルを割り当てる

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-7-manage-schema"></a>手順 7: スキーマの管理

一般的なセットアップ [手順に従います](./configure-connector.md)。

## <a name="step-8-choose-refresh-settings"></a>手順 8: 更新設定を選択する

一般的なセットアップ [手順に従います](./configure-connector.md)。

>[!NOTE]
>アクセス許可の更新では、スケジュールされたフル クロールだけが適用されます。

## <a name="step-9-review-connection"></a>手順 9: 接続の確認

一般的なセットアップ [手順に従います](./configure-connector.md)。

接続を公開した後、検索結果ページをカスタマイズする必要があります。 検索結果のカスタマイズの詳細については、「検索結果のカスタマイズ [ページ」を参照してください](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)。

## <a name="troubleshooting"></a>トラブルシューティング
その下に、コネクタの構成中に発生する一般的なエラーとその考えられる理由の一覧を示します。

| 構成手順 | エラー メッセージ | 考えられる理由 |
| ------------ | ------------ | ------------ |
| 接続設定 | 要求は形式が正しくないか、無効です。 | 正しくない Confluence サイトの URL |
| 接続設定 | Confluence サイトの Confluence クラウド サービスにアクセスできません。 | 正しくない Confluence サイトの URL |
| 接続設定 | クライアントには、アクションを実行するアクセス許可はありません。 | Basic auth に対して提供された無効な API トークン |
| プロパティの選択 | エラー メッセージなし、プレビュー結果なし | CQL クエリが有効かどうかを確認する |

## <a name="limitations"></a>制限事項
Confluence Cloud Graph コネクタには、最新のリリースで次の既知の制限があります。

- Confluence Cloud Connector は、添付ファイルとコメントのインデックスを作成します。
- インデックス サーバーとデータ センターの展開は、別のコネクタとしてリリースされます。