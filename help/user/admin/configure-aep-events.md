---
title: エクスペリエンスイベントとフィールドを選択
description: Experience Platformのイベントとフィールドを選択し、お客様の行動に基づいて、ジャーニーでリアルタイムの意思決定をトリガーにします。
feature: Setup, Integrations
role: Admin
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は現在ベータ版です"
solution: Journey Optimizer B2B Edition, Experience Platform
exl-id: a7696d03-f4c4-4f64-8ef2-b15e59b59770
source-git-commit: 046d3648c5e482a69719d0095c297a766dd852ea
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# エクスペリエンスイベントとフィールドを選択

管理者は、[AEPの特定のエクスペリエンスイベント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/classes/experienceevent){target="_blank"} およびエクスペリエンスイベントの和集合スキーマ内のそれらの関連フィールドを選択できます。 選択後、ユーザーは、これらのエクスペリエンスイベントをリッスンするように決定ルールを設定し、ほぼリアルタイムイベントデータに基づいて動的でターゲット設定されたキャンペーンアクションを有効にすることができます。

<!-- ![Video](../../assets/do-not-localize/icon-video.svg){width="30"} [Watch the video overview](#overview-video) -->
ジャーニーでAEP エクスペリエンスイベントを使用するには、次の 2 つの手順があります。

1. Journey Optimizer B2B edition設定での管理者 [AEP エクスペリエンスイベントとフィールドを追加する &#x200B;](#add-an-event)。

2. マーケターはジャーニーで _イベントをリッスン_ ノードおよび [&#x200B; エクスペリエンスイベントを選択 &#x200B;](../journeys/listen-for-event-nodes.md#listen-for-an-experience-event) を追加します。

   * ノードで使用するイベントを選択します。
   * 制約として使用するフィールドを選択します。

>[!BEGINSHADEBOX]

## ガイドラインと制限事項

組織の目標を満たすイベントを選択する際は、次の点に注意してください。

* イベントごとに最大 50 個、最大 100 個のフィールドを選択できます。

* ジャーニーは、Web SDKや HTTP API などのExperience Platform ストリーミング機能を使用して取り込まれたエクスペリエンスイベントをリッスンできます。

* エクスペリエンスイベントは、ジャーニー内で決定目的で使用できますが、保持されません。 したがって、Journey Optimizer B2B edition内でエクスペリエンスイベントの履歴レコードを利用することはできません。

* エクスペリエンスイベントを使用してジャーニーを公開する場合、さらにフィールドを追加できますが、以前に選択したフィールドを削除することはできません。

* 1 つのエクスペリエンスイベントを複数のジャーニーで参照することも、同じジャーニー内で複数回使用することもできます。

>[!ENDSHADEBOX]

## エクスペリエンスイベントの管理

1. 左側のナビゲーションで **[!UICONTROL 管理]**/**[!UICONTROL 設定]** を選択します。

1. 中間パネルで **[!UICONTROL XDM クラス]** をクリックし、「**[!UICONTROL イベント]**」タブをクリックして、使用可能なイベントのリストを表示します。

   ![&#x200B; 選択したエクスペリエンスイベントへのアクセス &#x200B;](./assets/configurations-xdm-classes-events.png){width="800" zoomable="yes"}

   テーブルは _[!UICONTROL 最終更新]_ 列で並べ替えられ、デフォルトでは最近更新されたイベントが先頭に表示されます。

   このページから、ジャーニーで使用するイベントを [&#x200B; 選択 &#x200B;](#add-an-event) および [&#x200B; 編集 &#x200B;](#edit-an-event) できます。

   選択したイベントの詳細にアクセスするには、イベント名をクリックします。

### イベントリストのフィルタリング

「_[!UICONTROL 検索]_」フィールドにテキストを入力し、表示されるイベントをイベント名と一致するようにフィルタリングします。

![&#x200B; 選択したイベントのリストを名前でフィルタリング &#x200B;](./assets/configurations-xdm-classes-events-search.png){width="600" zoomable="yes"}

### イベントを追加

ジャーニーの _イベントをリッスン_ ノードでエクスペリエンスイベントを使用できるようにするには、イベントとサポートされているフィールドを選択します。

>[!NOTE]
>
>ベータ版リリースでは、リストからイベントを削除できません。 追加する各イベントが、組織での使用を目的としていることを確認してください。

1. 右上で **[!UICONTROL エクスペリエンスイベントを選択]** をクリックします。

   イベントの詳細ページが表示されます。 このページから、イベントタイプとフィールドを選択できます。

   ![&#x200B; 新しいイベントのイベントの詳細 &#x200B;](./assets/configurations-xdm-classes-events-select-new.png){width="700" zoomable="yes"}

1. イベントタイプを選択します。

   * **[!UICONTROL イベントタイプを選択]** をクリックします。

   * ダイアログで、イベントタイプを選択します。

     「_[!UICONTROL 検索]_」フィールドを使用して、表示されたリストを名前でフィルタリングします。 **[!UICONTROL 選択したフィールドのみを表示]** スライダーを使用して、現在の選択を確認します。

     ![&#x200B; イベントタイプを選択ダイアログ &#x200B;](./assets/configurations-xdm-classes-select-event-type-dialog.png){width="450" zoomable="yes"}

   * 「**[!UICONTROL 選択]**」をクリックします。

1. イベントタイプに対して 1 つ以上のフィールドを選択します。

   * **[!UICONTROL フィールドを選択]** をクリックします。

   * ダイアログで、一致するイベントの制約として使用するフィールドを選択します。

     「_[!UICONTROL 検索]_」フィールドを使用して、表示されたリストを名前でフィルタリングします。 **[!UICONTROL 選択したフィールドのみを表示]** スライダーを使用して、現在の選択を確認します。

     ![&#x200B; フィールドの選択ダイアログ &#x200B;](./assets/configurations-xdm-classes-select-fields-dialog.png){width="450" zoomable="yes"}

   * 「**[!UICONTROL 選択]**」をクリックします。

1. イベントの詳細ページで、「**[!UICONTROL 保存]**」をクリックします。

保存したイベントは、「_[!UICONTROL イベント]_」タブのリストに表示されます。

### イベントの編集

イベントの詳細を編集してフィールドを変更します。

1. イベント名をクリックするか、_詳細メニュー_ （**...**）アイコンをクリックして **[!UICONTROL 編集]** を選択します。

   ![[ その他 ] メニューアイコンをクリック &#x200B;](./assets/configurations-xdm-classes-events-more-menu.png){width="500" zoomable="yes"}

1. 「**[!UICONTROL フィールドを編集]**」をクリックして、フィールドをさらに追加するか、_[!UICONTROL フィールドを選択]_ ダイアログでの既存の選択内容を削除します。

1. 「**[!UICONTROL 選択]**」をクリックして選択内容を保存します。

### イベントの削除

>[!NOTE]
>
>この機能のBeta リリースでは、選択したイベントのリストからイベントを削除できません。 イベントの削除は GA リリースで予定されています。

<!-- ## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3448637/?learn=on) -->