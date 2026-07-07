---
title: 宛先
description: Journey Optimizer B2B Primeで宛先を接続し、静的な人物リストをアクティベートして、オーディエンスデータを広告、電子メール、その他のマーケティングプラットフォームに書き出す方法を説明します。
autotag-review: '2026-06-17T18:30:02.442Z'
TQID: 'https://experienceleague.adobe.com/xO1p-VvIfv1KB77g0l2-fFRHQ0w2hy97vnG1QHpMw8c'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: aed878b8-11d0-487c-828b-d23b2051ec37id: beb5f4be-cec3-471a-9db6-831a77dd3ac9id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 4632a06ce5a17713fdcaecf6eac8c051bc984e28
workflow-type: tm+mt
source-wordcount: 289
ht-degree: 2%

---

# 宛先

宛先は、[!DNL Adobe Journey Optimizer B2B Prime]から広告ネットワーク、メールサービスプロバイダー、CRM システムなどの外部マーケティングプラットフォームに人物リストデータを書き出すことができる事前定義済みの統合です。 [!DNL Journey Optimizer B2B Prime]では、[静的な人物リスト ](./people-lists.md#static-list) （Marketo Engageの人物レコードで構成）を宛先にアクティベートして、これらのオーディエンスを下流チャネルでのターゲティングとエンゲージメントに利用できるようにします。

<!-- 
Does not align w/AEP info for Beta

Activating a static list to a destination follows a three-step process:

1. **Connect** — Authenticate and configure a connection to a destination platform.
1. **Map** — Select the static list and map its people attributes to the fields required by the destination.
1. **Schedule** — Define when and how often the list data is exported to the destination.

Destination activations reflect the membership state of the static list at the time of each synch.

## Destination types {#destination-types}

[!DNL Journey Optimizer B2B Prime] supports the following destination types for activating static people lists:

| Type | Description |
|--- |--- |
| Streaming | Real-time API-based connections that push audience membership updates to the destination as they occur. |
| File-based (batch) | Scheduled exports that deliver audience data as structured files to cloud storage or SFTP locations, which the destination platform then ingests. |

-->

## 宛先を接続 {#connect-destination}

1. 左側のナビゲーションで、**[!UICONTROL 接続]**&#x200B;を展開し、**[!UICONTROL 宛先]**&#x200B;を選択します。

1. 「_[!UICONTROL カタログ]_」タブで、外部宛先タイプのコネクタを探します。

   >[!TIP]
   >
   >検索ボックスに`LinkedIn`などの名前を入力すると、コネクタをすばやく見つけることができます。

   ![使用可能なコネクタタイプにアクセス ](./assets/destinations-catalog.png){width="800" zoomable="yes"}

1. コネクタカードで、**[!UICONTROL 新しい宛先の設定]**&#x200B;をクリックします。

1. **[!UICONTROL 新しいアカウント]**&#x200B;を選択し、アカウントの資格情報を入力します。

   ![新しい宛先アカウントを接続](./assets/destinations-configure-new.png){width="500"}

1. 「**[!UICONTROL 宛先に接続]**」をクリックします。

   >[!IMPORTANT]
   >
   >この時点で、**は&#x200B;_[!UICONTROL 宛先の詳細]_を入力しません**。 接続だけが必要です。

1. データガバナンスとマーケティングアクションの設定を確認し、**[!UICONTROL 保存]**&#x200B;をクリックします。

接続された宛先は、_[!UICONTROL 参照]_ タブのリストに表示され、静的リストのアクティブ化に使用できます。

## 宛先への静的リストのアクティブ化 {#activate}

>[!NOTE]
>
>[!DNL Journey Optimizer B2B Prime]の宛先に対してアクティブ化できるのは、[静的人物リスト ](./people-lists.md#static-list)のみです。 [動的リスト ](./people-lists.md#dynamic-lists)は、宛先のアクティブ化の対象ではありません。

1. 左側のナビゲーションで、**[!UICONTROL マーケティング管理]**&#x200B;を展開します。

1. **[!UICONTROL マーケティング]**&#x200B;のリソースリストの右側で、**[!UICONTROL 人物リスト]**&#x200B;を選択します。

   ![ ユーザーリストにアクセスしてオーディエンスを管理](./assets/people-lists.png){width="800" zoomable="yes"}

1. 「**[!UICONTROL 静的リスト]**」タブを選択します。

1. 宛先に対してアクティブ化する静的リストを探します。

1. 静的リスト名の横にある&#x200B;_アクティブ化_ （![ アクティブ化アイコン ](../../assets/do-not-localize/icon-falco-activate-dest.svg)）アイコンをクリックします。

1. 設定済みの宛先接続のチェックボックスをオンにします。

   ![ アクティブ化に使用できる設定済みの宛先](./assets/static-list-activate-destination-select.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。

<!--

This method not working for Beta

1. On the _[!UICONTROL Browse]_ tab, locate the destination you want to use for the activation and click the name to open it.

1. Select the **[!UICONTROL Activation data]** tab.

1. Click **[!UICONTROL Activate people lists]**.

1. Select the static people list you want to export and click **[!UICONTROL Next]**.

1. Map the people list attributes to the required fields of the destination schema and click **[!UICONTROL Next]**.

1. Set the export schedule:

   * **[!UICONTROL Frequency]** — Choose how often the list is exported (for example, daily or weekly).
   * **[!UICONTROL Start date]** — Set when the first export should run.

1. Review the activation summary and click **[!UICONTROL Finish]**.

The activation is created and the static list data is exported to the destination according to the defined schedule.

-->

