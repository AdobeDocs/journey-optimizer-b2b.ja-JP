---
title: セットアップチェックリスト
description: ユーザーアクセス設定やメール配信品質インフラストラクチャなど、Journey Optimizer B2B Primeインスタンスの初期セットアップタスクを完了します。
autotag-review: '2026-06-12T23:06:52.179Z'
TQID: 'https://experienceleague.adobe.com/D8qXM-F4anA8IVYmdlaclUoxgTwqQptN36xYFpsuvHY'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
  - id: f467931a-9b22-4ca8-869f-adfbd64061ce
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
  - id: f6df9def-cdf7-4728-9ec8-3f65716828c7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: de83abd4ca48e2dfda8a1900f7c8074232bb9d8e
workflow-type: tm+mt
source-wordcount: 218
ht-degree: 12%

---

# チェックリストを設定

プロビジョニングされた[!DNL Journey Optimizer B2B Prime] インスタンスで機能を有効にするには、次のタスクを実行します。

## ユーザーアクセスを有効にする {#enable-user-access}

プロビジョニングが完了し、サンドボックスがバインドされている場合は、チームとユーザーに[!DNL Journey Optimizer B2B Edition] アクセスを設定します。

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong> 製品へのアクセスおよび権限の提供 </strong> ユーザーの場合</td>
<td></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Admin ConsoleでJourney Optimizer B2B edition製品プロファイルを作成する（1回限り/初期設定のみ）</td>
<td><a href="./user-management.md#create-profile">プロファイルを作成</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Admin Consoleでのユーザーグループの追加</td>
<td><a href="./user-management.md#add-user-group">ユーザーグループを追加</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>組み込みの役割を編集するか、製品権限でカスタム役割を作成できます</td>
<td><a href="./user-management.md#edit-role-permissions">役割の編集</a> <br/> <a href="./user-management.md#create-a-custom-role"> カスタム役割の作成</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Adobe Experience Platformのロールにユーザーまたはグループを追加する</td>
<td><a href="./user-management.md#add-users-to-a-role"> ユーザーを追加</a> <br/><a href="./user-management.md#add-user-groups-to-a-role"> グループを追加</a></td>
</tr>
</tbody>
</table>

## メールの配信品質 {#email-deliverability}

マーケターがジャーニーから電子メールを送信できるようにする前に、サブドメインのデリゲーション、電子メール認証、チャネル設定など、組織向けの送信インフラストラクチャを設定します。

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>メールの配信品質とチャネル設定</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>Adobeへのサブドメインのデリゲート（完全デリゲートまたはCNAME）</td>
<td><a href="./admin/configuration-email-deliverability.md#delegate-fully-delegated">完全に委任</a> <br/> <a href="./admin/configuration-email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>サブドメインのDMARCの設定</td>
<td><a href="./admin/configuration-email-deliverability.md#configure-dmarc">DMARCの設定</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>IP プールの確認と割り当て</td>
<td><a href="./admin/configuration-email-deliverability.md#review-ip-pool">IP プールの確認</a></td>
</tr>
<tr>
<td><img src="../../assets/do-not-localize/icon-checkbox.svg" width="25" alt="タスクのチェックボックス"/></td>
<td>メールチャネル設定の作成</td>
<td><a href="./admin/configuration-email-deliverability.md#create-email-channel-configuration">メールチャネルの設定</a></td>
</tr>
</tbody>
