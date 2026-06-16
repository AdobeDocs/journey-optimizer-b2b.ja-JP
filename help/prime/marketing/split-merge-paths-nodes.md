---
title: パスの分割と結合ノード
description: プレースホルダー
autotag-review: '2026-06-12T23:04:27.208Z'
TQID: 'https://experienceleague.adobe.com/TZlkuuES1Q2ZlG-ND-tIu6cVBRA65hIfotDcroER9Mc'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
  - id: c3d6e661-d372-4e98-9fd9-eac771e7e4ee
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: bf2854a777f62ba2f74f79942ee3336b6e8ab9dd
workflow-type: tm+mt
source-wordcount: 569
ht-degree: 0%

---

# パスノードの分割と結合



## パス ノードの分割

分割ノードを使用して、定義した条件に従ってユーザーをセグメント化します。 条件に従ってオーディエンスリストのパスを作成し、セグメントのアクションノードとイベントノードで各パスを定義し、パスを組み合わせてジャーニーを続行します。

「パスを分割」ノードは、人物フィルターに基づいて、1つ以上のセグメント化されたパスを定義します。

<!-- A split based on a people filter is automatically closed with a merge paths node so that all people can move forward to the next step. Split by people paths can include only people actions. These paths cannot be split again and automatically join back. _not currently true_ -->


_&#x200B;**ユーザー別の分割パスの仕組み**&#x200B;_

* 各パスの評価は上から下まで行われます。 人が最初と2番目のパスに一致した場合、最初のパスに沿ってのみ進みます。
* ノードは、_その他のユーザー_ パスの定義をサポートしています。このパスでは、定義されたセグメントまたはパスのいずれかに一致しないユーザーのアクションまたはイベントを追加できます。

### 一致するフィルター

ノードに定義する各パスに対して、次のフィルタータイプを使用して、1つ以上の条件に従ってユーザーを照合します。

* アクティビティ履歴 – 次に関連するユーザーのアクティビティに応じてパスを定義できます。

   * メールメッセージ
   * データ値の変更

* 人物属性 – 国、役職、リストメンバーシップなど、人物の属性に応じて条件を定義します。

### 分割パスノードの追加

<!--
>[!NOTE]
>
>When you split paths by people, a _Close split paths_ node is automatically inserted to end the split. A split-by-people path allows only _Take an action_ on people nodes.
-->

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、「**[!UICONTROL パスを分割]**」を選択します。

   <!-- ![Add journey node - split paths](./assets/add-node-split.png){width="300" zoomable="no"} -->

1. _[!UICONTROL パス 1]_&#x200B;に適用できる条件を定義するには、「**[!UICONTROL 条件を適用]**」をクリックします。

1. 条件エディターで、分割パスを定義する1つ以上のフィルターを追加します。

   * 左側のナビゲーションから人物フィルターのいずれかをドラッグ&amp;ドロップして、一致定義を完了します。

   * 上部の&#x200B;**[!UICONTROL フィルターロジック]**&#x200B;を適用して、条件を微調整します。 すべての条件または1つの条件を一致させます。

     <!-- ![Split path node - conditions person filter logic](./assets/node-split-conditions-people.png){width="700" zoomable="yes"} -->

   * 「**[!UICONTROL 完了]**」をクリックします。

1. パスをさらに追加するには、**[!UICONTROL パスを追加]**&#x200B;をクリックし、前の手順を繰り返して、パスに適用できる条件を追加します。

   これらの条件に基づいて各パスにラベルを付けることも、デフォルトのラベルを使用することもできます。

1. 必要に応じて、分割する優先度に従ってパスを並べ替えます。

   パスのフィルタリングは、トップダウンの順序で評価されます。 各人は一致する最初のパスに沿って進みます。

   各パスカードの右上にある上下の矢印をクリックして、パスのリストで上下に移動します。

   <!-- ![Split path node - reorder paths](./assets/node-split-reorder-paths-people.png){width="500" zoomable="yes"} -->

1. 定義されたパスと一致しないユーザーのデフォルトパスを追加するには、**[!UICONTROL その他のユーザー]** オプションを有効にします。

   このオプションが有効になっていない場合、定義されたセグメント/パスに一致しないユーザーは分割を超えて、ジャーニーの次のステップに進みます。

各パスに条件を定義している場合は、パス上のユーザーに適用するアクションノードまたはイベントノードを追加できます。

## パス ノードを結合

1. ジャーニーマップに移動し、2つ以上のパスがある分割パスノードを見つけます。

   各パスには、各パス上のアクションとイベントの組み合わせが必要です。

1. これらのパスの最後にあるプラス（**+**）アイコンをクリックし、表示されたオプションから「**[!UICONTROL パスを結合]**」を選択します。

   <!-- ![Journey node - merge paths](./assets/node-plus-icon-merge-paths.png){width="400" zoomable="no"} -->

1. 右側のノードプロパティで、結合するパスを選択します。

   <!-- ![Journey node - merge paths](./assets/node-merge-select-paths.png){width="600" zoomable="yes"} -->

   この時点で、パスが結合され、選択したパスのユーザーが単一のパスに結合され、ジャーニーを進み続けることができます。

1. 必要に応じて、結合パスのノードプロパティに戻り、削除するパスのチェックボックスをオフにすることで、パスを結合できます。