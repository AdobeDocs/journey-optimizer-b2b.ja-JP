---
title: 動的な人物リスト
description: Journey Optimizer B2B Editionでメンバーシップルールを定義し、動的な人物リストを複製します。
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
source-git-commit: 734966636b6d2addf014905431fa755f6fe92ee6
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 2%
---

# 動的な人物リスト

動的な[人物リスト &#x200B;](./people-lists.md)は、ルール （フィルター）によって定義される人物プロファイルのコレクションです。 動的リストメンバーシップは、個人の属性とアクティビティを参照するシンプルなフィルターを使用して定義されます。 プロファイルがフィルターロジックに従って選定および非選定されると、メンバーシップは自動的に維持されます。

動的リストから個々のユーザーを追加または削除することはできません。 リストのメンバーシップを変更するには、そのルールを更新します。 メンバーシップを手動またはジャーニーを通じて管理する必要がある場合は、代わりに[静的リスト &#x200B;](./people-lists-static.md)を使用してください。

## メンバーシップルールの設定 {#set-membership-rules}

>[!NOTE]
>
>ルールのない動的リストにはメンバーがありません。 リストに入力するには、少なくとも1つのフィルターを追加します。

1. 動的リストを開き、「**[!UICONTROL ルール]**」タブを選択します。

1. 「**[!UICONTROL ルールを編集]**」をクリックします。

   ![動的な人物リストを作成するためのルールにアクセス &#x200B;](./assets/people-list-dynamic-rules-edit.png){width="700" zoomable="yes"}

1. _[!UICONTROL ルールを編集]_ ダイアログで、左側のパネルからフィルターをドラッグして、条件を満たすプロファイルのルールを定義します。

   次のいずれかの組み合わせを使用して、リストのプロファイルを選定します。

   * アクティビティ履歴
   * [!DNL Experience Platform]件の有効な人物フィールド
   * カスタムフィールド
   * インテントデータ
   * 顧客属性
   * ジャーニーメンバーシップなどの特別なフィルター

   追加する各フィルターについて、**[!UICONTROL 制約を追加]**&#x200B;をクリックして、一致する条件を調整します。 上部の&#x200B;**[!UICONTROL フィルターロジック]**&#x200B;を適用して、条件を微調整します。 すべての条件、任意の条件を一致させるか、高度なロジックを定義するかを選択できます。

   ![制約を含むフィルターを追加して、動的リストに入力します](./assets/people-list-dynamic-rules-edit-filter.png){width="700" zoomable="yes"}

1. **[!UICONTROL 完了]**&#x200B;をクリックして変更を保存します。

   「**[!UICONTROL ルール]**」タブには、リストのフィルターとフィルターロジックが表示され、**[!UICONTROL メンバー]** タブが更新され、更新されたメンバーシップが反映されます。 最新のオーディエンスの条件を見つけるには、**[!UICONTROL 詳細]** メニューの&#x200B;**[!UICONTROL メンバーの更新]**&#x200B;を使用します。

1. 「**[!UICONTROL メンバー]**」タブを選択します。

   適格なメンバーは、短い遅延の後にリストに表示されます。

   ![動的な人物リストのメンバーを生成](./assets/people-list-dynamic-members.png){width="700" zoomable="yes"}

>[!NOTE]
>
>リストルールをいつでも変更するには、次の手順を繰り返します。 保存されたフィルターに基づいて、リストメンバーシップが更新されます。

<!--

## Duplicate a dynamic list {#duplicate-dynamic-list}

Duplicating a dynamic list replicates its membership filtering so that you can reuse it in a different context.

1. In the _[!UICONTROL Dynamic lists]_ tab, click the _More menu_ ( **...** ) icon next to the list and choose **[!UICONTROL Duplicate]**.

1. Enter a unique **[!UICONTROL Name]** (required) and a **[!UICONTROL Description]** (optional).

   By default, the dialog appends `_copy` to the name of the originating list. Enter a different unique name as needed.

   ![Duplicate list dialog](./assets/people-list-duplicate-dialog.png){width="375"}

1. Click **[!UICONTROL Duplicate]**.
-->
