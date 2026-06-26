---
title: 人物オーディエンスジャーニーノード
description: Journey Optimizer B2Bの人物オーディエンスノードを設定して、動的な人物リストまたはイベントベースのオーディエンスを使用して、ジャーニーに参加するプロファイルを指定します。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
autotag-review: '2026-06-16T21:21:01.614Z'
TQID: 'https://experienceleague.adobe.com/pk1NGg3M67oRieuCOZFdaguKl2bVkiZyEPVnJDTUBJs'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: beb5f4be-cec3-471a-9db6-831a77dd3ac9id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: ba367494-9862-4596-bd6f-299c7e10a46bid: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 263e15040990a48475ffdd2b0b25d1cb557d5abf
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 4%

---

# 人物オーディエンスノード

_人物オーディエンス_ ノードは、ジャーニーにエントリする人物プロファイルを指定します。 ユーザーのジャーニー[を作成する場合、ジャーニーは常に、入力を定義するユーザーのオーディエンスノードから始まります。 ](./person-journeys.md)人物オーディエンスノードには、動的な人物リストまたはイベントトリガーの2つのオーディエンス入力タイプのいずれかを使用できます。

ユーザージャーニーに必要な動的ユーザーリストが既に存在しない場合は、[ ユーザーリストを作成](../audiences/people-lists.md#create-a-people-list)してから、ユーザーオーディエンスノードを設定します。

_ジャーニーオーディエンスを設定するには&#x200B;:_

1. 「**[!UICONTROL 人物オーディエンス]**」ノードをクリックします。

   このアクションは、右側にノードプロパティを表示します。

   ![人物オーディエンスジャーニーノード ](./assets/person-audience-node-properties.png){width="500" zoomable="yes"}

1. 人物オーディエンスに対して、次のいずれかのオーディエンス設定オプションを使用します。

   * **[!UICONTROL 動的リスト]** – 動的なルールベースの人物リストを使用します。 リストルールは、ジャーニー実行時に評価され、ジャーニーのメンバーが選定されます。 後で動的リストの資格を失ったユーザーは、ジャーニーから削除されません。 _[動的リスト](../audiences/people-lists.md#dynamic-lists)_&#x200B;を参照してください。

   * **[!UICONTROL イベントオーディエンス]** - イベントオーディエンスを使用すると、条件を満たすイベントに基づいてジャーニーオーディエンスを定義できます。 イベント条件による人物プロファイルフィルタリングとトリガージャーニー入力を使用して、オーディエンスメンバーを定義します。 _[イベントベースのオーディエンス](../audiences/event-based-audiences.md)_&#x200B;を参照してください。

