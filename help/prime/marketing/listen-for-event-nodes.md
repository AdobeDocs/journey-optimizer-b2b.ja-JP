---
title: イベントノードをリッスン
description: プレースホルダー
autotag-review: '2026-06-12T23:00:36.531Z'
TQID: 'https://experienceleague.adobe.com/SBEfrrIKSCnO5x1tGXQTz1EZryH0IKhQx4tuqVn78FI'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: d0031543-532c-4a26-8f90-01af2b91e6d0
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: bf2854a777f62ba2f74f79942ee3336b6e8ab9dd
workflow-type: tm+mt
source-wordcount: 165
ht-degree: 11%

---

# イベントノードをリッスンします

イベントが発生したときにオーディエンスをジャーニーの次のステップに進めるために、_イベントをリッスン_ ノードを追加します。

## 人物イベントフィルター

| フィルター | 説明 |
| ------- | ----------- |
| アクティビティ履歴/メール | 選択した1つ以上のメールメッセージを使用して評価される条件に基づくメールアクティビティ： <li>メール内リンクをクリックした <li>メールを開封済み |
| アクティビティ履歴/変更されたデータ値 | 選択した人物属性に対して、値の変更が発生しました。 次の変更タイプがあります。 <li>新しい値 <li>前回の値 <li>理由 <li>ソース <li>アクティビティの日付 <li> 分 回数 |

## イベントノードの追加

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、**[!UICONTROL イベントをリッスン]**&#x200B;を選択します。

1. 右側のノードプロパティで、イベントタイプに「**[!UICONTROL 人]**」を選択します。

   <!-- ![Journey node - listen to events on people](./assets/node-listen-events-people.png){width="700" zoomable="yes"} -->

1. リストからイベントを選択します。

1. 「**[!UICONTROL イベントを編集]**」をクリックし、イベントの詳細を定義します。

>[!NOTE]
>
>イベントノードのリッスンのタイムアウト機能は現在機能せず、後のフェーズで有効になります。
