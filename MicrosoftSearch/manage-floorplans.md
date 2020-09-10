---
title: 間取図を管理する
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Microsoft Search のフロアプラン機能を使用すると、建物内の人、オフィス、その他の amenities をユーザーが見つけやすくなります。
ms.openlocfilehash: c1a3c30f98408a6d98f34c41f4132bcca0bd316e
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422921"
---
# <a name="manage-floor-plans"></a>間取図を管理する

**Microsoft Search**のフロアプランは、ユーザーが建物内の人物や会議室を見つけられるように支援します。 フロアプランでは、次の質問に回答します。

- Allan の office はどこにありますか?
- ビル2階3
- 2/11173 を検索する

## <a name="add-floor-plans"></a>フロアプランを追加する

次の手順に従って、 **Microsoft Search**でフロアプランの回答を設定します。

### <a name="step-1-determine-your-building-codes"></a>手順 1: 建物コードを決定する

作成コードは、ユーザーのオフィスの場所の一部として使用されます。 ユーザープロファイルを更新するときには、次のコードを使用します。 たとえば、次のような場所に組織があるとします。 *ビル2、350 5 の3要素、ニューヨーク市、NY 10016*

この建物のコードには、2、B2、Building2、建物2、NYCB2 のいずれかの適切な例があります。 各建物に固有のコードを指定する必要があります。

### <a name="step-2-review-your-floor-plans"></a>手順 2: フロアプランを確認する

フロアプランファイルは、DWG 形式である必要があります。DWG ファイルには、テキストラベルを含めることができます。 テキストラベルがルームをマークすると、そのラベルはルームラベルと呼ばれます。 DWG ファイルには、ラベルが付いている少なくとも **10 個のルーム** が必要です。 ラベルの種類が異なる DWG ファイルの例を次に示します。

|**部屋のラベルを含むテキストラベル**|**スペースラベルのないテキストラベル**|**テキストラベルなし**|
|:-----:|:-----:|:-----:|
|![floorplans-textandroomlabels.png](media/floorplans-textandroomlabels.png)|![floorplans-textnoroomlabels.png](media/floorplans-textnoroomlabels.png)|![floorplans-nolabels.png](media/floorplans-nolabels.png)|

DWG ファイルの表示と更新の詳細については、「 [FAQ](#frequently-asked-questions) 」セクションを参照してください。

### <a name="step-3-update-office-locations-on-user-profiles"></a>手順 3: ユーザープロファイルのオフィスの場所を更新する

ユーザーのオフィスの場所とは、建物コードとルームラベルの組み合わせです。 たとえば、建物のコードが *2* で、会議室のラベルが *1173*の場合、オフィスの場所は *2/1173*になります。

組織内の各ユーザーのオフィスの場所を追加または更新します。 [Microsoft 365 管理センター](https://admin.microsoft.com)のユーザープロファイルでオフィスの場所を変更するか、オンプレミスの active directory を変更して Azure active directory と同期することができます。 *Physicaldeliveryofficename* は、office の場所として使用されるフィールドです。 部屋のラベルに床数字が含まれていない場合は、ヒントについての FAQ を参照してください。

この例では、すべての office がビル2のフロア1の部屋1173にあります。
![floorplans-userlestview.png](media/floorplans-userlistview.png)

> [!NOTE]
> フロアプランを検索するときに更新された office の場所を表示するには、各フロアで少なくとも **10 人** のオフィスの場所を更新する必要があります。

### <a name="step-4-verify-office-location"></a>手順 4: office の場所を確認する

**Microsoft Search**を使用して、ユーザーを検索し、オフィスの場所が正しく表示されていることを確認します。 場所が更新されたばかりの場合は、更新プログラムが検索結果に表示されるまで最大 **72 時間** 待機する必要があります。

![floorplans-peoplecard.png](media/floorplans-peoplecard.png)

### <a name="step-5-add-building-locations"></a>手順 5: 建物の場所を追加する

フロアプランでは、 [場所](manage-locations.md) を使用して建物を定義します。 [Microsoft 365 管理センター](https://admin.microsoft.com)で、[[**場所**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)] に移動し、[**追加**] を選択します。 建物の名前、アドレス、およびキーワードを入力します。 必要な数の建物を追加します。

![floorplans-locations.png](media/floorplans-locations.png)

場所の詳細については、「[場所を管理](manage-locations.md)する」を参照してください。

### <a name="step-6-gather-and-organize-office-locations"></a>手順 6: オフィスの場所を収集して整理する

フロアプランを使用するには、office の場所にインデックスを付ける必要があります。 これは、完了するまでに最大48時間かかる1回限りの操作です。 合計時間は、組織の規模によって異なります。

[管理センター](https://admin.microsoft.com)で、[[**フロアプラン**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)] に移動し、[**開始**] を選択します。 この通知が表示されていない場合、この手順は組織に対して既に完了しています。

![floorplans_hydrationstep.png](media/floorplans_hydrationstep.png)

### <a name="step-7-upload-floor-plans"></a>手順 7: フロアプランをアップロードする

1. [管理センター](https://admin.microsoft.com)で、[[**フロアプラン**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)] に移動します。
2. ドロップダウンリストで建物を選択し、[ **次へ**] を選択します。 建物が表示されていない場合は、前の手順に戻って、 [建物の場所を追加](#step-5-add-building-locations)します。
3. [ **ファイルのアップロード**] を選択し、アップロードするフロアプランを選択します。
4. アップロードが完了すると、フロアプランファイルに表示されるフロア番号を入力する必要があります。 [**次へ**] を選択します。
5. オプションフロアに翼または領域がある場合は、その詳細を入力します。
6. フロアプランにマップされたオフィスの場所の一覧を示すレビュー画面が表示されます。 [ **詳細** ] を選択して、マッピングが正しいことを確認します。
    - マップされているユーザーがない場合、またはマッピングに満足していない場合は、[ **マッピングの続行**] を選択します。 発行するには、[ **スキップして発行**] を選択します。
7. このフロアプランの建物コードを入力します。 構築コードは、ユーザーの office location プロパティにあります。 たとえば、ユーザーのオフィスの場所が **2/1173**の場合、建物のコードは **2**になります。
8. [確認] 画面で、手順6を繰り返して、マッピングが正しいことを確認します。
9. オプションアップロードされたすべてのフロアプランの場所パターンを確認して特定し、[ **次へ**] を選択します。
10. [確認] 画面で、手順6を繰り返して、マッピングが正しいことを確認します。
11. 準備が整ったら、[ **発行** ] を選択して、 **Microsoft Search**でフロアプランを使用できるようにします。

> [!NOTE]
> **フロアプランを公開するには、48時間かかります。** その後、ユーザーが共同作業者のオフィスを検索するときに、次のようなフロアプラン結果が表示されます。

![floorplans-officelocation.png](media/floorplans-officelocation.png)

### <a name="step-8-optional-specify-location-patterns"></a>手順 8: (オプション) 場所のパターンを指定する

フロアプランをアップロードすると、テキストラベルがユーザーのプロファイル内のオフィスの場所と比較されます。 一致するものが10未満の場合は、[ **場所のパターンの指定** ] 画面が表示されます。 場所パターンは、オフィスの場所からフロア、ウィング、および部屋情報を抽出するために使用されます。

![floorplans-locationpattern.png](media/floorplans-locationpattern.png)

必要に応じて場所を省略することができますが、フロアと主翼は省略可能です。

## <a name="edit-floor-plans"></a>フロアプランを編集する

既存のフロアプランを更新するには、変更するフロアプランを選択し、[ **編集**] を選択します。 変更を行って保存します。

## <a name="troubleshooting"></a>トラブルシューティング

|**手順**|**エラー メッセージ**|**型**|**操作**|
|:-----|:-----|:-----|:-----|
|フロアプランをアップロードする|CC_1 .dwg を読み取ることができません。 フロアプランを再アップロードまたは削除してください。|Error|ファイルをもう一度アップロードしてください。 それでも問題が解決しない場合は、ファイルを削除して、もう一度実行してください。|
|フロアプランをアップロードする|CC_1 .dwg という名前のファイルが2つあります。 いずれかを削除するか、別の名前で再アップロードしてください。|Error|ファイル名が正しくない場合は、floor またはウィング情報を追加してファイル名を一意にしてから、もう一度ファイルをアップロードしてください。 同じファイルを重複して追加した場合は、そのファイルを削除するだけです。|
|フロアプランをアップロードする|データが見つかりません。|Error|ファイルが正しいことを確認してから、もう一度アップロードするか、削除してください。|
|フロアプランをアップロードする|このファイルに外部参照が含まれていません。 CC_1_furniture .dwg をアップロードするか、このファイルを削除します。|警告|外部参照ファイルをアップロードするか、削除します。|
|フロアプランをアップロードする|DWG ファイルの部屋番号またはタグを読み取ることができませんでした。 このファイルを削除してください。|警告|DWG ファイルを調べてデータが含まれていることを確認してから、ファイルを削除して、もう一度実行してください。|
|Office の場所をリンクする|Azure Active Directory にオフィスの場所がありません。 フロアプランを設定する前に、Azure Active Directory に場所データを追加します。|Error|[ユーザープロファイルのオフィスの場所を更新する](#step-3-update-office-locations-on-user-profiles) |

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q:** DWG ファイルを表示して編集するにはどうすればよいですか?

**A:** 次のいずれかのオプションを使用して、DWG ファイルを表示します。

- ファイルを SharePoint にアップロードして開きます。
- [Microsoft Visio](https://support.office.com/article/Open-insert-convert-and-save-DWG-and-DXF-AutoCAD-drawings-60cab691-0f4c-4fc9-b775-583273c8dac5)または[Autodesk DWG TrueView](https://www.autodesk.com/products/dwg)でファイルを開きます。
- ファイルを [Autodesk のオンラインビューアー](https://viewer.autodesk.com/)にアップロードします。

**Q:** マークのない部屋にテキストラベルを追加するにはどうすればよいですか?

**A:** エディターで DWG ファイルを開き、 [ルームラベルを追加](https://knowledge.autodesk.com/support/autocad-map-3d/learn-explore/caas/CloudHelp/cloudhelp/2019/ENU/MAP3D-Learn/files/GUID-4854F184-6279-4E0C-9487-34A4759017F6-htm.html)します。

**Q:** テスト用に DWG ファイルを作成または編集するにはどうすればよいですか?

**A:** Microsoft Visio、Autodesk AutoCAD、またはその他の DWG エディターで DWG ファイルを作成します。 ファイルに10以上の部屋のラベルが付けられていることを確認します。

**Q:** DWG ファイルのテキストラベルの最適な形式は何ですか。

**A:** 最良の結果を得るために、テキストラベルにはフロア番号と部屋番号を含める必要があります。 次の例では、建物コードに2または SC を使用しています。
<!-- markdownlint-disable no-inline-html -->
|会議室ラベルの種類|Floor|Room|サンプルテキストのラベル|オフィスの場所 (コード/テキストラベルを作成する)|
|:-----|:-----|:-----|:-----|:-----|
|フロアおよび部屋番号がある|1-d|173|1173|2/1173|
|| 21|45|21045|2/21045|
||最高|10万|23 ~ 10 万人|2/23-10万|
||1-d|G06-07|1G06-07|2/1G06-07|
||pbm-2|1024 4A|02.1024 a|2/02.1024 a|
||pbm-2|1024 4A|02.1024 a|2/02.1024 a|
||pbm-2|105.01|2105.01|2/2105.01|
|コード、フロア、および部屋番号の作成|.0|X-11-M-12|2-0-X-11-12|2/2-0-12-12<br/>2-0-X-11-12|
||pbm-2|128 a|22128A|2/22128A<br/>22128A|
||1-d|B2-11|21-B2-11|2/21-B2-11<br/>21-B2-11|
||pbm-2|45|SC2045|SC/SC2045<br/>SC2045|

**Q:** フロア番号を含まない DWG ファイルを使用できますか。

**A:** はいできますよ。 ユーザーの Azure Active Directory プロファイル内のオフィスの場所を更新するときは、DWG ファイルに含まれていない場合でも、部屋番号の一部として床番号を含めます。 ファイルをアップロードすると、[場所のパターンの指定] 画面が表示され、両方の値を指定することができます。

たとえば、部屋番号を含む DWG ファイルは、次のように表示されることがあります。

![floorplans-nofloors.png](media/floorplans-nofloors.png)

ユーザーのプロファイル内のオフィスの場所は2/1175 で、' 2 ' は建物のコード、' 1 ' はフロア番号、' 175 ' は部屋番号です。
