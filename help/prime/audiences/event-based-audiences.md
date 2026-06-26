---
title: イベントベースのオーディエンス
description: Journey Optimizer B2B Primeのイベントベースのオーディエンスを使用して、Marketo Engageのアクティビティにもとづいてカスタマージャーニーのエントリをほぼリアルタイムでトリガーできます。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
autotag-review: '2026-06-25T17:59:01.953Z'
TQID: 'https://experienceleague.adobe.com/04J58rjKw0hCoTOeYheZIPaX-YR8GwP-k6-Wn3XCetU'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 263e15040990a48475ffdd2b0b25d1cb557d5abf
workflow-type: tm+mt
source-wordcount: 332
ht-degree: 3%

---

# イベントベースのオーディエンス

[!DNL Adobe Journey Optimizer B2B Prime]では、_イベントベースのオーディエンス_&#x200B;が、[!DNL Marketo Engage]のアクティビティが発生したときに、ほぼリアルタイムでライブ [人のジャーニー](../marketing/person-journeys.md)にオーディエンスメンバーを追加できます。 イベントベースのオーディエンスは、ジャーニーキャンバスのオーディエンスノードで設定します。

* 対象となるイベントとして、1つ以上の[!DNL Marketo Engage] アクティビティ（標準またはカスタム）を選択します。
* オプションで、個人プロファイルフィルター（業界、地域、ライフサイクルステージなど）を追加して、入力できる個人を絞り込みます。
* オプションで、アクティビティ属性の制約（特定のフォーム、URL、プログラムなど）を定義して、各アクティビティの出現箇所を絞り込みます。

適格なアクティビティがリードの[!DNL Marketo Engage]にログインして[!DNL Adobe Journey Optimizer B2B Prime]にレプリケートされると、システムは、対応する人物レコードを設定されたフィルターと制約に照らして評価します。 条件が満たされると、オーディエンスは直ちにオーディエンスノードを通じてジャーニーに入ります。

_個人ジャーニーのイベントベースのオーディエンスを定義するには&#x200B;:_

1. [_人物オーディエンス_ ノード &#x200B;](../marketing/person-audience-node.md)を選択します。

1. 右側のノードプロパティで、エントリタイプとして「**[!UICONTROL イベントオーディエンス]**」を選択します。

   ![人物オーディエンスジャーニーノードをイベントベースのオーディエンスに設定](./assets/event-based-audience-node.png){width="400"}

1. 「**[!UICONTROL イベント条件を追加]**」をクリックします。

1. _[!UICONTROL イベント条件を編集]_ ダイアログで、次のように、1つ以上の[!DNL Marketo Engage] アクティビティを対象イベントとして追加します。

   * _ウェビナーに参加_
   * _電子メールが配信されました_
   * _電子メール内のリンクをクリック_

   >[!NOTE]
   >
   >関連する[!DNL Marketo Engage] インスタンスで定義されたカスタムアクティビティを選択することもできます。

   各アクティビティの一致する演算子と値を設定します。

   ![&#x200B; イベントベースのオーディエンスのアクティビティトリガー](./assets/event-based-audience-triggers.png){width="700" zoomable="yes"}

   設定されたアクティビティのいずれかがリード用にログに記録されると、ジャーニーの対象となります。

1. （オプション）イベントとフィルターの組み合わせをオーディエンスの選定に使用するには、個人レベルのフィルターを追加します。

   * 「**[!UICONTROL フィルター]**」タブを選択します。
   * 各フィルターをドラッグして、一致する条件を設定します。

   ![&#x200B; イベントベースのオーディエンスの人物フィルター](./assets/event-based-audience-filters.png){width="700" zoomable="yes"}

   フィルターを追加する場合、ユーザーは少なくとも1つの設定されたアクティビティ条件と設定されたフィルターを満たす必要があります。

1. 「**[!UICONTROL 保存]**」をクリックします。

