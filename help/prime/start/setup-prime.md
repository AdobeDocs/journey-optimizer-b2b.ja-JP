---
title: セットアップ
description: ユーザーアクセス設定やメール配信品質インフラストラクチャなど、Journey Optimizer B2B Primeインスタンスの初期セットアップタスクを完了します。
autotag-review: '2026-06-12T23:06:52.179Z'
TQID: 'https://experienceleague.adobe.com/D8qXM-F4anA8IVYmdlaclUoxgTwqQptN36xYFpsuvHY'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: d6e625c1-468f-4d73-9f32-fd1edb87f96bid: f467931a-9b22-4ca8-869f-adfbd64061ceid: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1fid: f6df9def-cdf7-4728-9ec8-3f65716828c7
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: e849c9406dc83c6dc7c22ff56de32d6a73fed07d
workflow-type: tm+mt
source-wordcount: 190
ht-degree: 55%

---

# 設定

プロビジョニングされたジャーニー B2B Prime インスタンスで機能を有効にするには、次のタスクを実行します。

## ユーザーアクセスを有効にする

プロビジョニングが完了すると、サンドボックスがバインドされ、初期設定タスクが完了します。チームとユーザーに対して、Journey Optimizer B2B editionとMarketo Engageのアクセスを設定します。

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
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Adobe Admin ConsoleでMarketo Engage製品プロファイルを作成する（新しいMarketo Engage インスタンスのみ）</td>
<td><a href="./user-management.md#create-profile">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>プロファイル用のユーザーグループの追加</td>
<td><a href="./user-management.md#add-user-group">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>B2B ユーザーの役割の設定</td>
<td><a href="./user-management.md#edit-roles-for-product-permissions">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>役割にユーザーまたはグループを追加</td>
<td><a href="./user-management.md#add-users-to-a-role">詳細情報</a></td>
</tr>
</tbody>
</table>

## メールの配信品質

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
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Adobeへのサブドメインのデリゲート</td>
<td><a href="./admin/configuration-email-deliverability.md#delegate-fully-delegated">完全に委任</a>または<a href="./admin/configuration-email-deliverability.md#delegate-cname">CNAME</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>サブドメインのDMARCの設定</td>
<td><a href="./admin/configuration-email-deliverability.md#configure-dmarc">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>IP プールの確認と割り当て</td>
<td><a href="./admin/configuration-email-deliverability.md#review-ip-pool">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>メールチャネル設定の作成</td>
<td><a href="./admin/configuration-email-deliverability.md#create-email-channel-configuration">詳細</a></td>
</tr>
</tbody>
</table>

