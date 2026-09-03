---
title: ジャーニーでのアカウントリストの使用
description: ジャーニーオーケストレーションでアカウントリストを使用し、Journey Optimizer B2B editionでアカウントを動的に追加または削除します。
feature: Account Lists, Account Journeys
role: User
exl-id: 7cda080d-6263-4ccd-b144-432e4e78c298
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: e935834c-48b7-43d8-b754-a815196a1b05
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
autotag-review: 2026-03-27T22:29:03.719Z
TQID: https://experienceleague.adobe.com/FokJGxTj7abTN01WCcrVLDEuNLW0oI-i-8z0j-rFBO4
source-git-commit: aa6547c60d1b4c570601b5540d193eff57ec6b86
workflow-type: tm+mt
source-wordcount: 417
ht-degree: 0%

---

# ジャーニーでのアカウントリストの使用

ライブ（公開済み）アカウントリストをアカウントジャーニーに組み込む方法はいくつかあります。

## アカウントオーディエンスノード

すべてのアカウントジャーニーは、[_アカウントオーディエンス_ ノード &#x200B;](../journeys/account-audience-nodes.md)から始まります。 このノードをアカウントリストを使用するように設定すると、メンバーアカウントは公開時にジャーニーを移動します。

1. 開始&#x200B;_アカウントオーディエンス_ ノードの&#x200B;**[!UICONTROL アカウントリスト]** オプションを選択します。

   ![&#x200B; アカウントオーディエンスノードのアカウントリストオプションを選択](../journeys/assets/node-audience-account-list.png){width="500"}

1. 「**[!UICONTROL アカウントリストを追加]**」をクリックします。

1. アカウントリストのチェックボックスを選択し、**[!UICONTROL 保存]**&#x200B;をクリックします。

   ![&#x200B; アカウントオーディエンスノードのアカウントリストオプションを選択](../journeys/assets/node-audience-account-list-select-dialog.png){width="600" zoomable="yes"}

## アクションノードを作成 – アカウントに追加

**_静的アカウントリストのみ_**

アカウントジャーニー内で、[a _アクションを実行_ ノード &#x200B;](../journeys/action-nodes.md)を使用してアカウントを静的アカウントリストに追加します。

たとえば、電子メールを送信するジャーニーパスがあり、一部のアカウントが応答としてさまざまなアクションを実行するとします。 このアクティビティは、ジャーニーの選定ポイントとみなされます。 クオリフィケーションを使用すると、クオリファイドアカウントに対して異なるフローを持つ別のジャーニーのオーディエンスとして使用されるアカウントリストにこれらを追加します。

>[!NOTE]
>
>ノードの実行時にアカウントがリストに既に存在する場合、そのアクションは無視されます。

1. 「_&#x200B;**[!UICONTROL アカウント]**」の「_ アクション」オプションを選択します。

1. _[!UICONTROL アカウントに対するアクション]_&#x200B;で、**[!UICONTROL アカウントリストに追加]**&#x200B;を選択します。

   ![&#x200B; アカウントリストに追加を選択](../journeys/assets/node-action-account-add-to-account-list.png){width="500"}

1. **[!UICONTROL ライブ静的アカウントリストを選択]**&#x200B;するには、アカウントを追加するアカウントリストを選択します。

   ![&#x200B; アカウントリストに追加を選択](../journeys/assets/node-action-account-add-to-account-list-select.png){width="500"}

## アクションノードを作成 – アカウントから削除

**_静的アカウントリストのみ_**

アカウントジャーニー内で、[a _アクションを実行_ ノード &#x200B;](../journeys/action-nodes.md)を使用して、静的アカウントリストからアカウントを削除します。

たとえば、電子メールを送信するジャーニーパスがあり、一部のアカウントが応答としてさまざまなアクションを実行するとします。 このアクティビティは、ジャーニーの選定ポイントとみなされます。 この選定では、アカウントリストからこれらを削除します。 このリストは、資格に関するコミュニケーションが重複しないように、追加のメールを送信する別のジャーニーのオーディエンスとして使用されます。

>[!NOTE]
>
>削除がスケジュールされているリストにアカウントが含まれていない場合、アクションは無視されます。

1. 「_&#x200B;**[!UICONTROL アカウント]**」の「_ アクション」オプションを選択します。

1. _[!UICONTROL アカウントに対するアクション]_&#x200B;で、**[!UICONTROL アカウントリストから削除]**&#x200B;を選択します。

   ![&#x200B; アカウントリストから削除を選択](../journeys/assets/node-action-account-remove-from-account-list.png){width="500"}

1. **[!UICONTROL ライブ静的アカウントリストを選択]**&#x200B;するには、アカウントを削除するアカウントリストを選択します。

   ![&#x200B; アカウントリストから削除を選択](../journeys/assets/node-action-account-remove-from-account-list-select.png){width="500"}
