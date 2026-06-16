---
title: 人物オーディエンスジャーニーノード
description: 個人ジャーニーのプレースホルダーページ：
autotag-review: '2026-06-16T21:21:01.614Z'
TQID: 'https://experienceleague.adobe.com/pk1NGg3M67oRieuCOZFdaguKl2bVkiZyEPVnJDTUBJs'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: beb5f4be-cec3-471a-9db6-831a77dd3ac9id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: ba367494-9862-4596-bd6f-299c7e10a46bid: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: b7cb8c2a43b8a562e55923d709f518b8f1d74b2a
workflow-type: tm+mt
source-wordcount: 212
ht-degree: 0%

---

# 人物オーディエンスノード

_人物オーディエンス_ ノードは、ジャーニーにエントリする人物プロファイルを指定します。 ユーザーのジャーニー[を作成する場合、ジャーニーは常に、入力を定義するユーザーのオーディエンスノードから始まります。 ](./person-journeys.md)人物オーディエンスノードには、静的な人物リストまたは動的な人物リストの2つのオーディエンス入力タイプのいずれかを使用できます。

ユーザージャーニーに必要なユーザーリストが既に存在しない場合は、[ ユーザーリストを作成](../audiences/audience-management.md#create-a-people-list)してから、ユーザーオーディエンスノードを設定します。

## 個人オーディエンスノードのオーディエンスの設定

1. 「**[!UICONTROL 人物オーディエンス]**」ノードをクリックします。

   このアクションは、右側にノードプロパティを表示します。

   <!-- ![Person audience journey node](./assets/person-journey-person-audience-node.png){width="700" zoomable="yes"} -->

1. 右側のノードプロパティパネルで、人物オーディエンスジャーニーノードに次のいずれかの入力オプションを使用します。

   * **[!UICONTROL 動的リスト]** – 動的なルールベースの人物リストを使用します。 リストルールは、ジャーニー実行時に評価され、ジャーニーのメンバーが選定されます。 後で動的リストの資格を失ったユーザーは、ジャーニーから削除されません。

   * **[!UICONTROL 静的リスト]** - ジャーニーのメンバーとして人物の静的リストを使用します。 現在のリストメンバーシップは、ジャーニー実行時に評価され、ジャーニーのメンバーが選定されます。 後で静的リストから削除されたユーザーは、ジャーニーから削除されません。

