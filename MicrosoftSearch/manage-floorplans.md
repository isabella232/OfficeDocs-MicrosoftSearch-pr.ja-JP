---
title: 間取図を管理する
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: フロア プラン機能は、Microsoft Search内のユーザー、オフィス、その他の設備を見つけるのに役立ちます。
ms.openlocfilehash: beeef26cc7413da654cc3ab01d92aa6cdc74e5cb
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702023"
---
# <a name="manage-floor-plans"></a>間取図を管理する

フロア プランは **、Microsoft Search** 内のユーザーと会議室を見つけるのに役立ちます。 間取りは次の質問に答えます。

- Allan Deyoungのオフィスはどこにいますか?
- 建物 2 階 3
- 検索 2/11173

## <a name="add-floor-plans"></a>間取りを追加する

次の手順に従って、フロア プランの回答を設定 **Microsoft Search。**

### <a name="step-1-determine-your-building-codes"></a>手順 1: 建物コードを決定する

建物コードは、ユーザーのオフィスの場所の一部として使用されます。 これらのコードは、ユーザー プロファイルの更新時に使用します。 たとえば、組織にこの場所に建物があるとします *。Building 2, 350 5th Avenue, New York City, NY 10016*

この建物のコードの良い例を次に示します。2、B2、Building2、Building 2、または NYCB2。 各建物には一意のコードが必要です。

### <a name="step-2-review-your-floor-plans"></a>手順 2: 間取りを確認する

間取り図ファイルは、DWG 形式である必要があります。DWG ファイルには、テキスト ラベルを含めることもできます。 テキスト ラベルが部屋にマークを付け、ルーム ラベルと呼ばれる。 DWG ファイルには、少なくとも **10 室の部屋にラベルが** 付いている必要があります。 ラベルの種類が異なる DWG ファイルの例を次に示します。

|**ルーム ラベルを含むテキスト ラベル**|**テキスト ラベルが部屋ラベルなし**|**テキスト ラベルなし**|
|:-----:|:-----:|:-----:|
|![floorplans-textandroomlabels.png。](media/floorplans-textandroomlabels.png)|![floorplans-textnoroomlabels.png](media/floorplans-textnoroomlabels.png)|![floorplans-nolabels.png](media/floorplans-nolabels.png)|

DWG ファイル [の表示](#frequently-asked-questions) と更新については、「FAQ」セクションを参照してください。

### <a name="step-3-update-office-locations-on-user-profiles"></a>手順 3: ユーザー プロファイルのオフィスの場所を更新する

ユーザーのオフィスの場所は、建物コードと部屋ラベルの組み合わせです。 たとえば、建物コードが *2* で、部屋ラベルが *1173* の場合、オフィスの場所は *2/1173 になります*。

組織内の各ユーザーのオフィスの場所を追加または更新します。 ユーザー プロファイルのオフィスの場所は、Microsoft 365 管理センターで[](https://admin.microsoft.com)変更するか、オンプレミスの Active Directory を変更して、ユーザープロファイルに同期Azure Active Directory。 *PhysicalDeliveryOfficeName* は、オフィスの場所に使用されるフィールドです。 部屋のラベルにフロア番号が含されていない場合は、「FAQ」のヒントを参照してください。

この例では、Allan のオフィスは、2 号館の 1 階の 1173 号室にあります。
![floorplans-userlestview.png。](media/floorplans-userlistview.png)

> [!NOTE]
> 間取りを検索するときに更新されたオフィスの場所を表示するには、各フロアで少なくとも **10** 人のオフィスの場所を更新する必要があります。

### <a name="step-4-verify-office-location"></a>手順 4: オフィスの場所を確認する

**[Microsoft Search** を使用して、ユーザーを検索し、自分のオフィスの場所が正しく表示されていることを確認します。 場所を更新したばかりの場合は、検索結果に更新プログラムが表示されるまで **最大 72** 時間待機する必要があります。

![floorplans-peoplecard.png。](media/floorplans-peoplecard.png)

### <a name="step-5-add-building-locations"></a>手順 5: 建物の場所を追加する

間取り図では [、場所を使用](manage-locations.md) して建物を定義します。 [場所] [Microsoft 365 管理センター](https://admin.microsoft.com)移動し、[[](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)追加] を **選択します**。 建物の名前、住所、キーワードを入力します。 必要な数の建物を追加します。

![floorplans-locations.png。](media/floorplans-locations.png)

場所の詳細については、「場所の管理 [」を参照してください。](manage-locations.md)

### <a name="step-6-gather-and-organize-office-locations"></a>手順 6: オフィスの場所を収集して整理する

間取りを使用する前に、オフィスの場所にインデックスを作成する必要があります。 これは、完了に最大 48 時間かかる 1 回の操作です。 合計時間は、組織のサイズによって異なります。

管理 [センターで、[](https://admin.microsoft.com)フロア プラン] [**に移動し**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)、[開始する] **を選択します**。 この通知が表示されていない場合、この手順は組織で既に完了しています

![floorplans_hydrationstep.png。](media/floorplans_hydrationstep.png)

### <a name="step-7-upload-floor-plans"></a>手順 7: アップロード計画を作成する

1. 管理センター [で、[](https://admin.microsoft.com)フロア プラン] [**に移動します**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)。
2. ドロップダウン リストで建物を選択し、[次へ] を **選択します**。 建物が一覧に表示されていない場合は、戻って建物の [場所を追加します](#step-5-add-building-locations)。
3. **[アップロード] を** 選択し、アップロードする間取りを選択します。
4. アップロードが完了したら、フロア プラン ファイルに表されるフロア番号を入力する必要があります。 [**次へ**] を選択します。
5. (省略可能)床に翼や領域がある場合は、その詳細を入力します。
6. フロア プランにマップされたオフィスの場所の数を示すレビュー画面が表示されます。 [ **詳細] を** 選択して、マッピングが正しいか確認します。
    - ユーザーがマップされていないか、マッピングに満足できない場合は、[マッピングの続行] **を選択します**。 発行するには、[スキップして発行 **する] を選択します**。
7. この間取り図の建物コードを入力します。 建物コードは、ユーザーのオフィスの場所プロパティにあります。 たとえば、ユーザーのオフィスの場所が **2/1173** の場合、建物コードは **2 です**。
8. 確認画面で、手順 6 を繰り返してマッピングが正しいか確認します。
9. (省略可能)アップロードされたフロア プランの場所パターンを確認して特定し、[次へ] を **選択します**。
10. 確認画面で、手順 6 を繰り返してマッピングが正しいか確認します。
11. 準備ができたら、[発行]**を選択** して、フロア プランを [公開] で **Microsoft Search。**

> [!NOTE]
> **間取りが公開されるには 48 時間かかります。** その後、同僚のオフィスを検索すると、以下のような間取り図の結果が表示されます。

![floorplans-officelocation.png。](media/floorplans-officelocation.png)

### <a name="step-8-optional-specify-location-patterns"></a>手順 8: (オプション) 場所のパターンを指定する

間取り図をアップロードすると、テキスト ラベルがユーザーのプロファイル内のオフィスの場所と比較されます。 一致が 10 未満の場合は、[場所パターンの **指定** ] 画面が表示されます。 場所パターンは、オフィスの場所から床、翼、および部屋の情報を抽出するために使用されます。

![floorplans-locationpattern.png。](media/floorplans-locationpattern.png)

必要な部屋のみ、床と翼はオプションで、必要に応じて場所をスキップできます。

## <a name="edit-floor-plans"></a>間取りを編集する

既存の間取り図を更新するには、変更する間取りを選択し、[編集] を **選択します**。 変更を加え、保存します。

## <a name="troubleshooting"></a>トラブルシューティング

|**手順**|**エラー メッセージ**|**型**|**操作**|
|:-----|:-----|:-----|:-----|
|アップロード間取り図|CC_1.dwg を読み取りできません。 間取り図を再アップロードまたは削除してください。|Error|ファイルのアップロードを再試行してください。 それでも問題が生じなかった場合は、ファイルを削除してやり直してください。|
|アップロード間取り図|CC_1.dwg という名前の 2 つのファイルがあります。 そのうちの 1 つを削除するか、別の名前で再アップロードしてください。|Error|ファイル名が正しくない場合は、フロアまたはウィングの情報を追加してファイル名を一意にしてから、ファイルを再度アップロードします。 誤って同じファイルを 2 回追加した場合は、削除してください。|
|アップロード間取り図|データが見つかりません。|Error|ファイルを確認して、ファイルが正しいファイルか確認してから、もう一度アップロードするか、削除します。|
|アップロード間取り図|このファイルに外部参照がありません。 CC_1_furniture.dwg をアップロードするか、このファイルを削除します。|警告|アップロード参照ファイルを削除または削除します。|
|アップロード間取り図|DWG ファイル内の部屋番号またはタグを読み取る必要があります。 このファイルを削除してください。|警告|DWG ファイルを確認して、データが含まれているか確認してから、ファイルを削除してもう一度やり直してください。|
|オフィスの場所をリンクする|この場所にオフィスの場所Azure Active Directory。 フロア プランを設定する前Azure Active Directoryに場所データを追加します。|Error|[ユーザー プロファイルのオフィスの場所を更新する](#step-3-update-office-locations-on-user-profiles) |

## <a name="frequently-asked-questions"></a>よく寄せられる質問

**Q:** DWG ファイルを表示および編集する方法

**A:** 次のオプションを使用して、DWG ファイルを表示します。

- アップロードファイルを開SharePoint開きます。
- Microsoft ファイルまたは[Autodesk DWG](https://support.office.com/article/Open-insert-convert-and-save-DWG-and-DXF-AutoCAD-drawings-60cab691-0f4c-4fc9-b775-583273c8dac5) TrueView Visio[ファイルを開きます](https://www.autodesk.com/products/dwg)。
- アップロードを[Autodesk のオンライン ビューアーに保存します](https://viewer.autodesk.com/)。

**Q:** マークされていない会議室にテキスト ラベルを追加する方法

**A:** エディターで DWG ファイルを開き、部屋 [のラベルを追加します](https://knowledge.autodesk.com/support/autocad-map-3d/learn-explore/caas/CloudHelp/cloudhelp/2019/ENU/MAP3D-Learn/files/GUID-4854F184-6279-4E0C-9487-34A4759017F6-htm.html)。

**Q:** テスト目的で DWG ファイルを作成または編集する方法

**A:** Microsoft Visio、Autodesk AutoCAD、その他の DWG エディターで DWG ファイルを作成します。 ファイルに 10 室以上の部屋のラベルが付けられているか確認します。

**Q:** DWG ファイルのテキスト ラベルに最適な形式は何ですか?

**A:** 最適な結果を得る場合は、テキスト ラベルにフロア番号と部屋番号を含む必要があります。 次の例では、建物コードに 2 または SC を使用します。
<!-- markdownlint-disable no-inline-html -->
|ルーム ラベルの種類|Floor|Room|サンプル テキスト ラベル|Office場所 (建物コード/テキスト ラベル)|
|:-----|:-----|:-----|:-----|:-----|
|床と部屋の番号を持つ|1|173|1173|2/1173|
|| 21|45|21045|2/21045|
||23|100K|23-100K|2/23-100K|
||1|G06-07|1G06-07|2/1G06-07|
||2|1024A|02.1024A|2/02.1024A|
||2|1024A|02.1024A|2/02.1024A|
||2|105.01|2105.01|2/2105.01|
|建物コード、フロア番号、および部屋番号を持つ|0|X-11-M-12|2-0-X-11-M-12|2/2-0-X-11-M-12<br/>2-0-X-11-M-12|
||2|128A|22128A|2/22128A<br/>22128A|
||1|B2-11|21-B2-11|2/21-B2-11<br/>21-B2-11|
||2|45|SC2045|SC/SC2045<br/>SC2045|

**Q:** フロア番号を含めない DWG ファイルを使用できますか?

**A:** はいできますよ。 ユーザーの Azure Active Directory プロファイルでオフィスの場所を更新する場合は、DWG ファイルから見つからない場合でも、フロア番号を部屋番号の一部として含める必要があります。 ファイルをアップロードすると、[場所パターンの指定] 画面が表示され、両方の値を指定できます。

たとえば、部屋番号が含まれるが、フロア番号がない DWG ファイルは、次のようになります。

![floorplans-nofloors.png。](media/floorplans-nofloors.png)

ユーザーのプロファイルのオフィスの場所は 2/1175 で、'2' は建物コード、'1' はフロア番号、'175' は部屋番号である必要があります。
