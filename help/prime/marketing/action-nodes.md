---
title: アクションノードを作成
description: プレースホルダー
autotag-review: '2026-06-12T22:58:21.806Z'
TQID: 'https://experienceleague.adobe.com/uR-WvNz3gA6V7yyN3RRXH-MggrmGb1qvu1CBhMZRuAc'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: af7eab5e-3580-4254-9f56-3c20b4f6ef42id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: bf2854a777f62ba2f74f79942ee3336b6e8ab9dd
workflow-type: tm+mt
source-wordcount: 197
ht-degree: 2%

---

# アクションノードを作成

個人ジャーニーでは、ノードパス上のすべてのユーザーに変更を適用する場合に、人物に対するアクションを使用します。 アカウントジャーニーの場合、このノードタイプは、分割パス内でユーザーが使用することも、アカウントが分割パス内で使用することもできます。

## アクションと制約

| アクション | 制約事項 |
| ------ | ---------- |
| **[!UICONTROL 電子メールを送信]** | <li>メールを作成 <li>配信時間の最適化（オプション） |
| **[!UICONTROL データ値の変更]** | <li>人物属性を選択 <li>新しい値を設定 |

## アクションノードの追加 {#add-an-action-node}

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、**[!UICONTROL アクションを実行]**&#x200B;を選択します。

1. 右側のノードプロパティで、リストからアクションを選択し、アクションの値を設定します。

<!-- ![Person journey node - take an action](./assets/node-take-action-people.png){width="700" zoomable="yes"} -->

+++[!UICONTROL 電子メールを送信]

このアクションを使用してメールを送信します。 ノードのメールを作成した後、メールデザインスペースでメールメッセージをデザイン、パーソナライズ、プレビューできます（[ メールオーサリング ](../content/email-authoring.md)を参照）。

<!-- ![Take an action - Send email](./assets/node-action-send-email-from-marketo.png){width="300"} -->

[送信時間の最適化](../marketing/email-send-time-optimization.md)を使用して、各プロファイルがエンゲージする可能性が最も高いタイミングを予測し、メール配信のタイミングをパーソナライズできます。

<!--
>[!NOTE]
>
>You can use email deduplication in account journeys to ensure that the same email is not sent multiple times to the same email address within a journey. For more information, see [Email deduplication](../content/email-deduplication.md).
-->

+++

+++[!UICONTROL  データ値の変更]

このアクションを使用して、データベース内の人物プロファイル属性の値を変更します。 属性を選択し、新しい値を設定します。

<!-- ![Take an action - Update person profile](./assets/node-action-update-person-profile.png){width="300"} -->

+++
