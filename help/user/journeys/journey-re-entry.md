---
title: ジャーニーの再入場
description: アカウントが同じアカウントジャーニーに再び参加できる時期と頻度を管理します。
feature: Account Journeys
role: User
level: Intermediate
exl-id: e5153125-6d5b-4835-bd19-c9b7ce67e46a
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
subfeature_v2: id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
autotag-review: '2026-04-29T23:21:59.633Z'
source-git-commit: bb44a295784fbdeab2583cf7c759b15c0808d7d5
workflow-type: tm+mt
source-wordcount: 419
ht-degree: 9%

---

# ジャーニーの再入場

_アカウントジャーニーのみ_

アカウントジャーニーの再入力を有効にすると、アカウントが同じジャーニーを再入力できるタイミングと頻度を制御できます。 再入力設定を使用して基準、制限、待機時間を設定し、アカウントが管理された方法でジャーニーに再評価されるようにします。

次の項目がtrueの場合、アカウントはジャーニーの再評価を行うことができます。

* アカウントは、ジャーニーに対して許可されている再入力の数以内です。
* アカウントは待機時間のしきい値（再評価する前に待機する最小時間）を満たしています。
* アカウントは現在ジャーニーにありません。

## アカウントジャーニーの再入力を有効にする

ジャーニーが&#x200B;_ドラフト_ ステータスの場合、再入力を有効にし、再入力設定を変更できます。

1. ドラフトアカウントジャーニーを開きます。

1. 右上の&#x200B;**[!UICONTROL その他…]** メニューをクリックし、**[!UICONTROL 再エントリ]**&#x200B;を選択します。

   ![右上の「詳細」をクリック](./assets/account-journey-draft-more-menu.png){width="450"}

1. _[!UICONTROL ジャーニーの再エントリ]_ ダイアログで、**[!UICONTROL 再エントリを有効にする]** オプションを切り替えます。

   この機能を有効にすると、タイミング、遅延、制限のオプションが表示されます。

   有効な機能を持つ![ジャーニー再入力ダイアログ ](./assets/journey-re-entry-dialog-enabled.png){width="450"}

1. **[!UICONTROL 再エントリのタイミング]**&#x200B;で、待機の計算方法を選択します。

   * **[!UICONTROL ジャーニーの終了から待機]** – 待機期間は、アカウントがジャーニーを終了または完了したときに開始されます。 例えば、「アカウントがジャーニーを完了してから30日後に再エントリできます。」

   * **[!UICONTROL ジャーニーの開始から待機]** – 待機期間は、アカウントがジャーニーに最初にエントリした日時に基づきます。 例えば、「アカウントがジャーニーを開始してから30日後に再エントリできます。」

1. 時間または日数の待機期間である&#x200B;**[!UICONTROL 再エントリ遅延]**&#x200B;を設定します。

   この設定は、アカウントがジャーニーを終了または開始してから再入力できるまでの待機時間を決定します。

1. アカウントがジャーニーに参加できる最大時間を定義するには、**[!UICONTROL エントリ制限]**&#x200B;を設定します。

   アカウントが制限に達すると、制限がリセットされるか、ジャーニーが新しい制限で再公開されるまで、エントリの資格がなくなります。

   この制限は、そのジャーニーのアカウントごとに適用されます。

1. 「**[!UICONTROL 保存]**」をクリックします。

## アカウントの進捗状況とアクティビティ

公開されたアカウントジャーニーの場合、ジャーニーマップには、ジャーニーノードの[ アカウントの進行状況](./journeys-overview.md#review-account-progression)が表示されます。 マップ上の各ノードには、そのノードに到達するアカウント数が表示されます。ライブジャーニーの場合は、現在そのノードにいるアカウント数が表示されます。 アカウントがジャーニーに再入力するたびに、別々のエントリとしてカウントされます。

<!-- 
You can see how many times accounts have entered the journey. ?? 

When you drill in to [account details](../accounts/account-details.md), the account activity shows each time the account entered the journey. It includes explicit activity and a recurrence count so that you can see re-entries clearly.
-->
