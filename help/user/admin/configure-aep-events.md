---
title: エクスペリエンスイベントとフィールドを選択
description: Experience Platformのイベントとフィールドを選択し、お客様の行動に基づいて、ジャーニーでリアルタイムの意思決定をトリガーにします。
feature: Setup, Integrations
role: Admin
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は現在ベータ版です"
solution: Journey Optimizer B2B Edition, Experience Platform
exl-id: a7696d03-f4c4-4f64-8ef2-b15e59b59770
source-git-commit: cefd98099bf6524d1d559a47d502990852de1468
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 10%

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
>ベータ版リリースでは、リストからイベントを削除できません。 追加する各イベントが、組織で使用するイベントであることを確認します。

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

## イベントとフィールド

[!DNL Journey Optimizer B2B Edition] えば、特定の人物レベルのアクティビティは [!DNL Experience Platform] Experience イベントとして取り込まれます。 これらのイベントは、XDM エクスペリエンスイベントスキーマを使用し、ジャーニー固有のフィールドグループを含むシステムデータセットに保存されます。 他のエクスペリエンスイベントと同様に [!UICONTROL 0&rbrace;Journey Optimizer B2B edition&rbrace; でこれらのイベントを使用できます。]

各イベントは、ジャーニー _イベントをリッスン）ノード（イベントに基づく決定_ で使用できる、定義済みのフィールドセットを公開します。 使用可能なイベントタイプとそのフィールドを確認し、これらのジャーニーノードで使用するイベントとフィールドを決定します。

### メール送信済み

このイベントは、マーケティングメールが人物に送信されたタイミングを追跡します。

イベントの種類：`directMarketing.emailSent`

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| メールソース ID | `directMarketing.emailSent.mailingKey.sourceID` |
| メールソースタイプ | `directMarketing.emailSent.mailingKey.sourceType` |
| メールソースインスタンス ID | `directMarketing.emailSent.mailingKey.sourceInstanceID ` |
| メールソースキー | `directMailing.emailSent.mailingKey.sourceKey` |
| メーリング名 | `directMarketing.emailSent.mailingName` |
| ジャーニーID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| ノード ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### メール到着

このイベントでは、ユーザーのメールサービスにメールが正常に配信されたタイミングを追跡します。

イベントの種類：`directMarketing.emailDelivered `

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| メーリングソース ID | `directMarketing.mailingKey.sourceID` |
| メーリングソースタイプ | `directMarketing.mailingKey.sourceType` |
| メーリングソースインスタンス ID | `directMarketing.mailingKey.sourceInstanceID` |
| メーリングソースキー | `directMarketing.mailingKey.sourceKey` |
| メーリング名 | `directMarketing.mailingName` |
| ジャーニーID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| ノード ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### メール開封済み

このイベントは、人物がマーケティングメールを開封したタイミングを追跡します。

イベントの種類：`directMarketing.emailOpened`

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| メーリングソース ID | `directMarketing.mailingKey.sourceID` |
| メーリングソースタイプ | `directMarketing.mailingKey.sourceType` |
| メーリングソースインスタンス ID | `directMarketing.mailingKey.sourceInstanceID` |
| メーリングソースキー | `directMarketing.mailingKey.sourceKey` |
| メーリング名 | `directMarketing.mailingName` |
| モバイルデバイスである | `device.isMobileDevice` |
| デバイスモデル | `device.model` |
| ユーザーエージェント | `environment.browserDetails.userAgent` |
| オペレーティングシステム | `environment.operatingSystem` |
| ジャーニーID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| ノード ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### 電子メールのクリック

このイベントは、マーケティングメール内のリンクをユーザーがクリックした際にトラッキングします。

イベントの種類：`directMarketing.emailClicked`

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| メーリングソース ID | `directMarketing.mailingKey.sourceID` |
| メーリングソースタイプ | `directMarketing.mailingKey.sourceType` |
| メーリングソースインスタンス ID | `directMarketing.mailingKey.sourceInstanceID` |
| メーリングソースキー | `directMarketing.mailingKey.sourceKey` |
| メーリング名 | `directMarketing.mailingName` |
| リンク URL | `directMarketing.linkURL` |
| モバイルデバイスである | `device.isMobileDevice` |
| モデル | `device.model` |
| ユーザーエージェント | `environment.browserDetails.userAgent` |
| オペレーティングシステム | `environment.operatingSystem` |
| ジャーニーID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| ノード ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### バウンスメール

このイベントは、人物へのメールがバウンスしたタイミングを追跡します。

イベントの種類：`directMarketing.emailBounced`

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| メーリングソース ID | `directMarketing.mailingKey.sourceID` |
| メーリングソースタイプ | `directMarketing.mailingKey.sourceType` |
| メーリングソースインスタンス ID | `directMarketing.mailingKey.sourceInstanceID` |
| メーリングソースキー | `directMarketing.mailingKey.sourceKey` |
| メーリング名 | `directMarketing.mailingName` |
| メール | `directMarketing.email` |
| 電子メールバウンスコード | `directMarketing.emailBouncedCode` |
| 電子メールバウンスの詳細 | `directMarketing.emailBouncedDetails` |
| ジャーニーID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| ノード ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### ソフトバウンスメール

このイベントは、人物へのメールがソフトバウンスしたタイミングを追跡します。

イベントの種類：`directMarketing.emailBouncedSoft`

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| メーリングソース ID | `directMarketing.mailingKey.sourceID` |
| メーリングソースタイプ | `directMarketing.mailingKey.sourceType` |
| メーリングソースインスタンス ID | `directMarketing.mailingKey.sourceInstanceID` |
| メーリングソースキー | `directMarketing.mailingKey.sourceKey` |
| メーリング名 | `directMarketing.mailingName` |
| メール | `directMarketing.email` |
| 電子メールバウンスコード | `directMarketing.emailBouncedCode` |
| 電子メールバウンスの詳細 | `directMarketing.emailBouncedDetails` |
| ジャーニーID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| ノード ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### メールの購読解除済み

このイベントは、ユーザーがマーケティングメールの購読を解除したタイミングを追跡します。

イベントの種類：`directMarketing.emailUnsubscribed `

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| メーリングソース ID | `directMarketing.mailingKey.sourceID` |
| メーリングソースタイプ | `directMarketing.mailingKey.sourceType` |
| メーリングソースインスタンス ID | `directMarketing.mailingKey.sourceInstanceID` |
| メーリングソースキー | `directMarketing.mailingKey.sourceKey` |
| メーリング名 | `directMarketing.mailingName` |
| ジャーニーID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| ノード ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

### Web ページにアクセス

このイベントタイプは、ヒットをページビューとしてマークするための標準的な方法です。

イベントの種類：`web.webpagedetails.pageViews`

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| Web ページソース ID | `web.webPageDetails.webPageKey.sourceID` |
| Web ページのソースタイプ | `web.webPageDetails.webPageKey.sourceType` |
| Web ページソースインスタンス ID | `web.webPageDetails.webPageKey.sourceInstanceID` |
| Web ページのソースキー | `web.webPageDetails.webPageKey.sourceKey` |
| Web ページ名 | `web.webPageDetails.name` |
| Web ページ URL | `web.webPageDetails.URL` |
| Web ページのクエリパラメーター | `web.webPageDetails.queryParameters` |
| Web ページ ID | `web.webPageDetails.webPageID` |
| ユーザーエージェント | `environment.browserDetails.userAgent` |
| リファラー URL | `web.webReferrer.URL` |

+++

### フォームに入力済み

このイベントは、人物が web ページ上のフォームに入力したタイミングを追跡します。

イベントの種類：`web.formFilledOut`

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| Web フォームソース ID | `web.fillOutForm.webFormKey.sourceID` |
| Web フォームのソースタイプ | `web.fillOutForm.webFormKey.sourceType` |
| Web フォームソースインスタンス ID | `web.fillOutForm.webFormKey.sourceInstanceID` |
| Web フォームのソースキー | `web.fillOutForm.webFormKey.sourceKey` |
| Web フォーム ID | `web.fillOutForm.webFormID` |
| Web フォーム名 | `web.fillOutForm.webFormName` |
| Web ページのクエリパラメーター | `web.webPageDetails.queryParameters` |
| Web ページ ID | `web.webPageDetails.webPageID` |
| ユーザーエージェント | `environment.browserDetails.userAgent` |
| リファラー URL | `web.webReferrer.URL` |

+++

### Web リンククリック済み

このイベントは、Web SDKがリンククリックを自動的に記録したことを示します。

イベントの種類：`web.webinteraction.linkClicks`

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| Web インタラクションソース ID | `web.webInteraction.webInteractionKey.sourceID` |
| Web インタラクションソースタイプ | `web.webInteraction.webInteractionKey.sourceType` |
| Web インタラクションソースインスタンス ID | `web.webInteraction.webInteractionKey.sourceInstanceID` |
| Web インタラクションソースキー | `web.webInteraction.webInteractionKey.sourceKey` |
| Web インタラクションリンク ID | `web.webInteraction.linkID` |
| Web インタラクションリンク URL | `web.webInteraction.linkURL` |
| Web ページのクエリパラメーター | `web.webPageDetails.queryParameters` |
| Web ページ ID | `web.webPageDetails.webPageID` |
| ユーザーエージェント | `environment.browserDetails.userAgent` |
| リファラー URL | `web.webReferrer.URL` |

+++

### 注目のアクション

このイベントは、ある人物にとって興味深い瞬間が録画された際にトラッキングします。

イベントの種類：`leadOperation.interestingMoment `

+++フィールド

| 表示名 | パス |
| ------------ | ---- |
| 識別子 | `_id` |
| イベントタイプ | `eventType` |
| タイムスタンプ | `timestamp` |
| 顧客 ID | `personID` |
| 人物ソース ID | `personKey.sourceID` |
| 人物ソースタイプ | `personKey.sourceType` |
| 人物ソースインスタンス ID | `personKey.sourceInstanceID` |
| 人物ソースキー | `personKey.sourceKey` |
| モーメント日 | `leadOperation.interestingMoment.date` |
| モーメントの説明 | `leadOperation.interestingMoment.description` |
| モーメントソース | `leadOperation.interestingMoment.source` |
| モーメントタイプ | `leadOperation.interestingMoment.type` |
| ジャーニーID | `_experience.journeyOrchestration.stepEvents.journeyID` |
| ノード ID | `_experience.journeyOrchestration.stepEvents.nodeID` |

+++

<!-- ## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3448684/?captions=jpn&learn=on) -->