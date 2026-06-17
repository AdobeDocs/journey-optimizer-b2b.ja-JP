---
title: アクションノードを作成
description: プレースホルダー
autotag-review: '2026-06-12T22:58:21.806Z'
TQID: 'https://experienceleague.adobe.com/uR-WvNz3gA6V7yyN3RRXH-MggrmGb1qvu1CBhMZRuAc'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: af7eab5e-3580-4254-9f56-3c20b4f6ef42
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 1d0093ad5298593d291372d838794fe8cab5f646
workflow-type: tm+mt
source-wordcount: 821
ht-degree: 3%

---

# アクションノードを作成

個人ジャーニーでは、ノードパス上のすべてのユーザーに変更を適用する場合に、人物に対するアクションを使用します。

## アクションと制約 {#actions}

| アクション | 制約 |
| ------ | ----------- |
| **[!UICONTROL 宛先に対してアクティブ化]** | <li>静的リストの選択または作成 <li>リストにアクティベートされた宛先がない場合は、リストをアクティベートします |
| **[!UICONTROL ジャーニーにユーザーを追加]** | <li>スケジュール済みジャーニーまたはライブジャーニーの選択 <li>ターゲットジャーニーのオーディエンス基準が適用されない |
| **[!UICONTROL リストに追加]** | <li>新しい静的リストを作成するか、既存の静的リストを選択します |
| **[!UICONTROL Marketo リストに追加]** | <li>Marketo Engageで静的リストを選択する |
| **[!UICONTROL データ値の変更]** | <li>人物属性を選択 <li>新しい値を設定 |
| **[!UICONTROL プログラムデータの変更]** | <li>プログラム属性を選択 <li>新しい値を設定 |
| **[!UICONTROL プログラムステータスの変更]** | <li>プログラムを選択<li>新しいステータスを選択 |
| **[!UICONTROL リストから削除]** | <li>静的リストを選択 <li>メンバーでない場合は人物をスキップ |
| **[!UICONTROL Marketoリストから削除]** | <li>Marketo Engageで静的リストを選択する <li>メンバーでない場合は人物をスキップ |
| **[!UICONTROL ジャーニーからユーザーを削除]** | <li>ライブジャーニーの選択 <li>現在ターゲットジャーニーのメンバーではない場合、人物をスキップします |
| **[!UICONTROL Marketo Campaignをリクエスト]** | <li>Marketo Engage キャンペーンの選択 |
| **[!UICONTROL 電子メールを送信]** | <li>AIを活用してパーソナライズされた電子メールを作成、編集、利用 <li>配信時間の最適化（オプション） |
| **[!UICONTROL WhatsAppを送信]** | <li>WhatsApp メッセージの選択 |

## アクションノードの追加 {#add-an-action-node}

1. ジャーニーキャンバスに移動します。

1. パスのプラス（**+**）アイコンをクリックし、**[!UICONTROL アクションを実行]**&#x200B;を選択します。

   ![&#x200B; ジャーニーパスの追加アイコンをクリック &#x200B;](./assets/person-journey-canvas-add-node.png){width="200"}

1. 右側のノードプロパティで、リストからアクションを選択し、アクションの値を設定します。

+++宛先に対してアクティベート

このアクションを使用すると、ジャーニーから直接Experience Platformの宛先にユーザーをアクティベートできます。 宛先を選択し、オーディエンス名を入力して、宛先でアクティブ化されたオーディエンスを識別します。

![&#x200B; アクションを実行 – 宛先に対してアクティブ化](./assets/person-action-node-activate-to-destination.png){width="450"}

+++

+++[!UICONTROL ジャーニーにユーザーを追加]

このアクションを使用して、他のスケジュール済みジャーニーまたはライブジャーニーにユーザーを追加します。 このアクションを通じて追加された人物は、ターゲットジャーニーのオーディエンスにすぐに追加されます。ジャーニーのオーディエンス条件は適用されません。

![&#x200B; アクションを実行 – ジャーニーにユーザーを追加](./assets/person-action-node-add-to-journey.png){width="450"}

+++

+++[!UICONTROL &#x200B; リストに追加]

Journey Optimizer B2B Primeの静的リストにユーザーを追加するには、このアクションを使用します。

![&#x200B; アクションを実行 – リストに追加](./assets/person-action-node-add-to-list.png){width="450"}

次のいずれかのオプションを選択します。

* **[!UICONTROL 作成]** – 新しい静的リストアセットを作成し、それにユーザーを追加します。 このリストは、Journey Optimizer B2B Primeの他のアセットですぐに使用できます。
* **[!UICONTROL 選択]** — ノードに到達するユーザーを追加する既存の静的リストアセットを選択します。

+++

+++[!UICONTROL Marketo リストに追加 &#x200B;]

Marketo Engageの静的リストにユーザーを追加するには、このアクションを使用します。

![&#x200B; アクションを実行 – Marketo リストに追加](./assets/person-action-node-add-to-marketo-list.png){width="450"}

+++

+++[!UICONTROL &#x200B; データ値の変更]

このアクションを使用して、人物レコードの属性の値を更新します。 属性を選択し、新しい値を設定します。

>[!TIP]
>
>属性の値をクリアするには、値を`NULL`に設定します。

![&#x200B; アクションを実行 – データ値を変更](./assets/person-action-node-change-data-value.png){width="450"}

+++

+++[!UICONTROL &#x200B; プログラムデータの変更]

このアクションを使用して、プログラム属性の値を更新します。 プログラム属性を選択し、新しい値を設定します。

![&#x200B; アクションを実行 – プログラム データの変更](./assets/person-action-node-change-program-data.png){width="450"}

+++

+++[!UICONTROL &#x200B; プログラムステータスの変更]

Marketo Engage プログラムのユーザーのステータスを変更するには、このアクションを使用します。 プログラムを選択し、新しいステータスを選択します。

![&#x200B; アクションを実行 – プログラムの状態を変更](./assets/person-action-node-change-status-program.png){width="450"}

+++

+++[!UICONTROL リストから削除]

Journey Optimizer B2B Primeの静的リストからユーザーを削除するには、このアクションを使用します。 ユーザーが現在リストのメンバーではない場合、そのユーザーのアクションはスキップされます。

![&#x200B; アクションを実行 – リストから削除](./assets/person-action-node-remove-from-list.png){width="450"}

+++

+++[!UICONTROL Marketoリストから削除 &#x200B;]

Marketo Engageの静的リストからユーザーを削除するには、この操作を使用します。 ユーザーが現在リストのメンバーではない場合、そのユーザーのアクションはスキップされます。

![&#x200B; アクションを実行 – Marketo リストから削除](./assets/person-action-node-remove-from-marketo-list.png){width="450"}

+++

+++[!UICONTROL ジャーニーからユーザーを削除]

このアクションを使用して、他のライブ人物ジャーニーから人物を削除します。 その人物はターゲットジャーニーからすぐに削除され、それ以上のアクションは実行されません。 ユーザーが現在ターゲットジャーニーのメンバーではない場合、そのユーザーのアクションはスキップされます。

![&#x200B; アクションを実行 – ジャーニーからユーザーを削除](./assets/person-action-node-remove-from-journey.png){width="450"}

+++

+++[!UICONTROL Marketo Campaignをリクエスト &#x200B;]

このアクションを使用して、接続されたMarketo Engage インスタンスでリクエストキャンペーンにユーザーを追加します。 リクエストするMarketo Engage キャンペーンを選択します。

![&#x200B; アクションを実行 – Marketo キャンペーンをリクエスト &#x200B;](./assets/person-action-node-request-marketo-campaign.png){width="450"}

+++

+++[!UICONTROL 電子メールを送信]

このアクションを使用して、オプトインしたユーザーにメールを送信します。 購読解除、リストへの登録をブロック、メール配信の停止、マーケティング配信の停止を受けたユーザーは、このアクションをスキップします。

![&#x200B; アクションを実行 – メールを送信](./assets/person-action-node-send-email.png){width="450"}

電子メールを作成したり、既存の電子メールを編集したり、AIによってパーソナライズされた電子メールを使用したりできます。 電子メールの作成と編集について詳しくは、[電子メールオーサリング &#x200B;](../content/email-authoring.md)を参照してください。

[送信時間の最適化](../marketing/email-send-time-optimization.md)を使用して、各プロファイルがエンゲージする可能性が最も高いタイミングを予測し、メール配信のタイミングをパーソナライズできます。

+++

+++[!UICONTROL WhatsAppを送信]

このアクションを使用して、WhatsApp メッセージを送信します。 ビジュアルデザイン空間でWhatsApp メッセージを作成、パーソナライズ、プレビューできます（[WhatsApp オーサリング &#x200B;](../content/whatsapp-authoring.md)を参照）。

![&#x200B; アクションを実行 – WhatsAppを送信](./assets/person-action-node-send-whatsapp.png){width="450"}

+++
