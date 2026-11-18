---
title: 静的な人物リスト
description: Journey Optimizer B2B Editionの静的な人物リストのメンバーを追加および削除します。
feature: Audiences
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
source-git-commit: d713d57bddf2ac6f8cf7e7a7d163281f607d729c
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 2%
---

# 静的な人物リスト

静的な[ ユーザーリスト ](./people-lists.md)は、ユーザーを追加または削除した場合にのみメンバーシップが変更される人物プロファイルのコレクションです。 個人の属性とアクティビティを参照するシンプルなフィルターにより、静的なリストメンバーシップが定義されます。 メンバーシップは、メンバーを追加または削除した場合にのみ変更されます。 次の操作が可能です。

* [1回評価されたフィルターセットを適用して、適用するときにユーザー](#static-list-add-members)を追加します。
* アカウントまたはユーザージャーニーを通じてユーザーを追加および削除するには、[!UICONTROL  ユーザーリストに追加]および[!UICONTROL  ユーザーリストから削除] アクションを使用します。 （[ ジャーニーでユーザーリストを使用](./people-lists-journeys.md)を参照）
<!-- * [Activate the list to a destination](#static-list-activate) to sync its membership downstream. -->

>[!NOTE]
>
>静的リストフィルター定義は、リストにメンバーを追加するときに1回適用されます。 定義されたフィルターは、後で使用できません。 フィルターを使用して一貫したオーディエンス定義を維持する場合は、代わりに[動的リスト ](./people-lists-dynamic.md)を使用してください。

## メンバーを追加 {#static-list-add-members}

>[!NOTE]
>
>静的リストを空で開始する場合は、フィルターを適用しないでください。 空の静的リストは、ジャーニーを通じてメンバーを追加する計画がある場合に便利です。

1. 静的リストを開き、右上の「**[!UICONTROL 人物を追加]**」をクリックします。

   ![静的な人物リストに人物を追加](./assets/people-list-static-add-people.png){width="700" zoomable="yes"}

1. _[!UICONTROL 人物を追加]_ ダイアログで、左側のパネルからフィルターをドラッグして、適格プロファイルのルールを定義します。

   次のいずれかの組み合わせを使用してプロファイルをフィルタリングします。

   * アクティビティ履歴
   * Experience Platformが有効な人物フィールド
   * カスタムフィールド
   * インテントデータ
   * 顧客属性
   * ジャーニーメンバーシップなどの特別なフィルター

   フィルターはカテゴリーフォルダーにネストされます。 各フォルダーを展開し、使用可能なフィルターをスクロールするか、上部の&#x200B;_検索_ フィールドを使用して、必要なフィルターを見つけます。 追加した各フィルターについて：

   * 左パネルからフィルター定義スペースにフィルターをドラッグします。
   * 一致評価の定義を完了します。
   * 「**[!UICONTROL 制約を追加]**」をクリックして、一致する条件を絞り込みます。

   上部の&#x200B;**[!UICONTROL フィルターロジック]**&#x200B;を適用して、条件を微調整します。 すべての条件、任意の条件を一致させるか、高度なロジックを定義するかを選択できます。

   ![静的リストにユーザーを追加するための制約を含むフィルターを追加](./assets/people-list-static-add-people-filters.png){width="800" zoomable="yes"}

1. **[!UICONTROL 完了]**&#x200B;をクリックして変更を保存します。

   ユーザーが追加されると、システムはリクエストを処理し、確認メッセージを表示します。 処理時間は、評価する人数と選択したフィルター条件によって異なります。 リストの入力が続く場合は、_[!UICONTROL 詳細]_ メニューの&#x200B;**[!UICONTROL メンバーの更新]**&#x200B;を使用して、リストを更新します。

   適格なメンバーは、短い遅延の後にリストに表示されます。 フィルターセットは1回評価されるので、後でフィルターに一致するユーザーは自動的に追加されません。 このプロセスをいつでも繰り返して、より多くのユーザーをリストに追加できます。

   ![静的な人物リストのメンバー](./assets/people-list-static-members.png){width="700" zoomable="yes"}

## メンバーを削除 {#static-list-remove-members}

「[!UICONTROL  ユーザーリストから削除]」アクションを使用すると、ジャーニーを通じて、静的リストからユーザーを自動的に削除できます。 （[ ジャーニーでユーザーリストを使用](./people-lists-journeys.md)を参照）

<!--
TODO: Restore this section when the activate to a destination function is released.

## Activate to a destination {#static-list-activate}

Activating a static people list sends its membership to a connected destination, with ongoing sync instead of a one-time export. This is useful for paid media targeting, suppression, and downstream orchestration.

* The static list acts as a container for the people.
* The activation sends and syncs that membership to a destination.
* People added to the list later are propagated automatically.
* People removed later are deactivated automatically.

>[!PREREQUISITES]
>
>You must have one or more configured destinations for your [!DNL Journey Optimizer B2B Edition] sandbox before you can activate a static list to a destination. See [Destinations](./destinations.md).

1. Select the **[!UICONTROL Static lists]** tab.

1. Locate the static list that you want to activate, click the _More menu_ ( **...** ) icon next to the list, and choose **[!UICONTROL Activate to destination]**.

   ![Access the More menu for a static people list](./assets/people-lists-static-more-menu.png){width="450"}

   You can also open the static list and use the **[!UICONTROL More]** menu at the top right.

1. Select the check box for the configured destination connection.

   ![Configured destinations available for activation](./assets/people-list-activate-destination-select.png){width="600" zoomable="yes"}

1. Click **[!UICONTROL Save]**.

1. In the _[!UICONTROL Activate list to destination]_ dialog, click **[!UICONTROL Activate]** to confirm.

When activation completes, a confirmation message appears and the destination shows as **[!UICONTROL Active]** on the **[!UICONTROL Destinations]** tab of the list. You can activate a static list to more than one destination at a time. Membership syncs to all of them.

To review the destinations that a static list is activated to, open the list and select the **[!UICONTROL Destinations]** tab.

### Deactivate a destination {#deactivate-destination}

Remove a destination connection from a static list when you no longer want its membership synced downstream.

1. Open the static list and select the **[!UICONTROL Destinations]** tab.

1. Use the row action to remove the destination that you want to disconnect.

1. Confirm in the _[!UICONTROL Deactivate destination]_ dialog.

Deactivating removes the destination from the list. The people in the list are also removed from the connected destination audience.

-->
