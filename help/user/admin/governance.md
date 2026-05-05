---
title: ガバナンス機能
description: Journey Optimizer B2B editionで現在利用可能なガバナンス機能について説明します。
feature: Setup
role: Admin
exl-id: 2845272b-987c-4a37-adf4-6ee5bfd59fc0
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
autotag-review: '2026-03-27T23:18:44.352Z'
source-git-commit: 1e7ba951f8cf4d8583a93badc78add4eba503ca6
workflow-type: tm+mt
source-wordcount: 425
ht-degree: 3%

---

# ガバナンス機能

Journey Optimizer B2B editionは、Adobe Experience Platformの統合アプリです。 企業慣行、法的義務、開発プロセスに準拠して、収集したエクスペリエンスデータを管理するためのツールとサービスをいくつか導入しています。 以下の節では、これらの各ガバナンス機能の概要を説明します。

## プライバシー – GDPR

Journey Optimizer B2B editionでは、Privacy ServiceおよびMarketo Privacy Broker Serviceが提供する既存のMarketo Engage GDPR ガバナンス機能を使用しています。

## 役割ベースのアクセス制御（RBAC）

Journey Optimizer B2B editionとAdobe Admin Consoleへのアクセスを使用すると、管理者はエンティティタイプ（view-segments、manage-segments、manage-journeysなど）に対するユーザー権限を付与できます。 この機能は、すべてのAdobe Experience Platformのお客様が自社の役割と権限を定義および管理できるようにする統合権限フレームワーク（UPF）の一部です。

## データ暗号化

**_保存中のデータの暗号化_** - Adobe Experience PlatformからJourney Optimizer B2B editionに転送されるすべてのアカウントおよび人物プロファイルデータは、Experience Platformの既存のコンプライアンスを維持するために暗号化されます。 ジャーニーや購買グループなど、Journey Optimizer B2B editionを起源とするすべてのエンティティも暗号化されています。

**_転送中のデータの暗号化_** （パブリックネットワーク経由） – すべてのJourney Optimizer B2B edition APIとエンティティは、TLS 1.2を使用して転送中に暗号化されます。

## 同意オプトイン/オプトアウト

同意のオプトイン/オプトアウトは、プロファイルが電子メールやSMSなどのコミュニケーションチャネルからオプトアウトできるガバナンスの一形態であり、その後、プロファイルがコミュニケーションチャネルから除外されます。

Journey Optimizer B2B editionなら、電子メールやSMS配信のユースケースにおいて、購読/登録解除のユースケースを構築および管理できます。 これらの同意設定は、XDM プロファイルの同意フィールドグループ内に保存され、Data Sync Frameworkの一部としてJourney Optimizer B2B editionとの間で同期されます。 これらの環境設定は、配信時に使用され、オプトアウトされたプロファイルを配信から除外します。

## サンドボックスのリセット

サンドボックスリセットは&#x200B;**現在Adobe Journey Optimizer B2B editionではサポートされていません**。 Journey Optimizer B2B editionにマッピングされているサンドボックスをリセットまたは削除すると、Journey Optimizer B2B editionのデータが永続的に失われる可能性があり、新しいJourney Optimizer B2B edition インスタンスのプロビジョニングが必要になる場合があります。

## まだ利用できません

次のガバナンス機能はまだ使用できません。

* データ使用ラベルの適用（DULE）/使用ポリシー
* データハイジーン
* 同意ポリシー
* フィールドレベルのアクセス制御（FLAC）
* オブジェクトレベルのアクセス制御（OLAC）
* 保存データのCMK暗号化
* Platform監査サービス
