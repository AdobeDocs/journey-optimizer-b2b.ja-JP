---
title: データの可用性と同期のタイミング
description: '[!DNL Journey Optimizer B2B Edition]件のジャーニーでデータの変更がどれくらい速く表示され、どのタイムラインが正常であるかをご確認ください。'
feature: Journeys, Data Management
role: User
autotag-review: '2026-10-08T18:36:33.252Z'
TQID: 'https://experienceleague.adobe.com/PA1IeRHnGWHmBtDpffzveoWIHOn99-Ctt4Y0OQb7CwE'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
  - id: b27e5950-9033-45ac-9f86-eb22e567f615
    internal-label: Marketo Engage
feature_v2:
  - id: 095e8119-1425-57eb-9d8c-9e684f2c9771
    internal-label: Audiences
  - id: 33ca0c14-7e3b-55a1-8fd7-8a61b47da4e1
    internal-label: B2B
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: a50ad69b-1331-40e9-b634-531a085a6a54
    internal-label: Identities
  - id: afadf741-c5fe-42cd-8013-23bb6ff2d1bc
    internal-label: Buying Groups
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: eec185bd-7d60-4193-ba3f-da427569936a
    internal-label: Destinations
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: 827c313f032d482ac2b0a5fa8f41d6506e67b9cb
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 0%
---
# データの可用性と同期のタイミング {#data-availability}

このトピックでは、[!DNL Adobe Journey Optimizer B2B Edition] ジャーニーでデータの変更がどれだけ速く表示されるか、どのタイムラインが正常であるかを理解します。 予想されるタイミングを把握することで、それに応じてジャーニーを設計し、遅延が予想される動作を認識することができます。

## 予想待ち時間

| データタイプ | 一般的な可用性 |
| --- | --- |
| [&#x200B; オーディエンスメンバーシップ &#x200B;](#daily-refresh) | 最大24時間（1日サイクル） |
| [&#x200B; アカウントと人物の関係の変更](#daily-refresh) | 最大24時間（1日サイクル） |
| [&#x200B; データ： [!DNL Experience Platform] から [!DNL Journey Optimizer B2B Edition]](#platform-sync) | 最大30分（ほぼリアルタイム） |
| [&#x200B; データ： [!DNL Journey Optimizer B2B Edition] から [!DNL Experience Platform]](#platform-sync) | 最大4時間（マイクロバッチ） |
| [&#x200B; クリック数や開封数などのアクティビティイベント &#x200B;](#activity-and-actions) | 最大4時間 |
| [[!DNL Marketo Engage]  リストの追加または削除](#activity-and-actions) | 30分以内（ほぼリアルタイム） |
| [Journey Optimizer B2B Editionによって生成されたイベント &#x200B;](#activity-and-actions) | バッチオーディエンスでのみ使用できます |
| [LinkedIn オーディエンス母集団](#linkedin-timing) | 同日から36～40時間（最悪の場合） |

## オーディエンスおよび関係データ {#daily-refresh}

[!DNL Journey Optimizer B2B Edition]は、バッチジョブスケジューラーによってトリガーされ、1日に1回、アカウントと個人のオーディエンスメンバーシップを評価します。 これにより、

* オーディエンスの対象となるアカウントまたは新たに対象となるユーザーは、対象となるユーザーの24時間以内にジャーニーに参加する資格を得ます。
* オーディエンス基準の変更は、次の日次の評価サイクルで有効になります。
* 今日オーディエンスに適格であったアカウントが、ジャーニーにまだエントリしていない場合は、次の日次サイクルが完了するまで待ってから調査します。
* 例えば、連絡先が別のアカウントに移動した場合など、個人のアカウントの関連付けが変更されると、関係の更新は毎日の同期サイクルを通じて24時間以内に反映されます。 アカウントメンバーシップに依存するジャーニーは、次の日次サイクルの後に更新されたリレーションシップを反映します。 行動は必要ありません。

>[!TIP]
>
>オーディエンスメンバーシップは、リアルタイムではなく日々更新されることを理解して、ジャーニーを設計できます。 ほぼリアルタイムの回答が必要な場合は、オーディエンスベースのエントリの代わりに[&#x200B; イベントベースのトリガー](../journeys/listen-for-event-nodes.md)を使用します。

## [!DNL Experience Platform]とデータを同期 {#platform-sync}

[!DNL Experience Platform]はアカウント、人物、商談の主要なデータストアであり、[!DNL Journey Optimizer B2B Edition]はジャーニー、購買グループ、購買グループの役割を所有しています。 [&#x200B; アーキテクチャの詳細](../about-journey-optimizer-b2b-edition.md#high-level-architecture)。

データは、2つのシステム間で各方向に異なるペースで移動します。

* **[!DNL Experience Platform]～[!DNL Journey Optimizer B2B Edition]** - データはほぼリアルタイムで同期され、最大で30分かかる場合があります。
* **[!DNL Journey Optimizer B2B Edition]から[!DNL Experience Platform]** - データはマイクロバッチで同期され、最大4時間かかる場合があります。

## アクティビティイベントとジャーニーアクション {#activity-and-actions}

アクティビティデータとジャーニーアクションのタイミングは、システム間でデータがどのように移動するかによって異なります。

* **アクティビティデータ** – 電子メールの開封、リンクのクリック、フォーム入力などの個人のアクティビティレコードは、[!DNL Journey Optimizer B2B Edition]に表示されるまでに約4時間かかります。 このタイミングは、バッチアクティビティデータに適用されます。[!DNL Experience Platform] Experience Event トリガーはストリーミングデータを使用し、ほぼリアルタイムで対応できます。
* **[!DNL Marketo Engage]アクション** - [!DNL Marketo Engage]を呼び出すジャーニーアクションは、API呼び出しであるため、ほぼリアルタイムです。 例えば、ジャーニーの手順で[!DNL Marketo] リストからユーザーを追加または削除すると、通常、アクションは30分以内に完了します。 [&#x200B; ジャーニーアクションの詳細](../journeys/action-nodes.md)。
* **[!DNL Experience Platform]**&#x200B;を通過するアクション - [!DNL Experience Platform]に最初に戻るすべてのアクションはバッチ処理されるので、ほぼリアルタイムのタイミングではなくバッチ処理のタイミングが適用されます。
* **によって生成されたイベント - [!DNL Journey Optimizer B2B Edition]が[!DNL Experience Platform]で生成したイベントは、バッチオーディエンスでのみ使用できます。[!DNL Journey Optimizer B2B Edition]**

## [!DNL LinkedIn]個のオーディエンスの宛先 {#linkedin-timing}

ジャーニーに[!DNL LinkedIn]宛先アクションが含まれる場合は、ジャーニーを公開した後で次のタイムラインを想定してください。

| シナリオ | 予想待ち |
| --- | --- |
| ジャーニーが公開されたときには、アカウントはすでにオーディエンスにありました | 同じ日、処理が現地時間の午前0時前に完了した場合 |
| ジャーニーが公開された後にアカウントが到着した | 最大24時間 |
| 最初の日別同期ウィンドウの後にアカウントが到着しました | 最大36～40時間 |

[!DNL LinkedIn]個のオーディエンスサイズが直ちに更新されない可能性があります。 この遅延は、[!DNL Experience Platform]がオーディエンスファイルを処理して[!DNL LinkedIn]に配信する際に予想される遅延です。 48時間経過してもオーディエンスサイズがまだ0の場合は、調査します。 [LinkedIn Account Matched Audiences](./linkedin-account-matched-audiences.md)について詳しく見る。
