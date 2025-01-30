---
title: ガバナンス機能
description: Journey Optimizer B2B editionで現在使用できるガバナンス機能について説明します。
exl-id: 2845272b-987c-4a37-adf4-6ee5bfd59fc0
source-git-commit: 3198ba223125c95263d8dcf5ee8cb285a888a26a
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 2%

---

# ガバナンス機能

Journey Optimizer B2B editionは統合Adobe Experience Platform アプリです。 ビジネスプラクティス、法的義務、開発プロセスに準拠して、収集したエクスペリエンスデータを制御できるツールやサービスをいくつか採用しています。 以下の節では、これらの各ガバナンス機能の概要を説明します。

## プライバシー – GDPR

Journey Optimizer B2B editionでは、Privacy ServiceおよびMarketo Privacy Broker Service が提供する GDPR ガバナンス機能の既存のMarketo Engageを使用します。

## 役割ベースのアクセス制御（RBAC）

Journey Optimizer B2B editionとAdobe Admin Consoleへのアクセス権を使用すると、管理者はエンティティタイプ（view-segments、manage-segments、manage-journeys など）に対するユーザー権限を付与できます。 この機能は、Unified Permissions Framework （UPF）の一部であり、すべてのAdobe Experience Platformのお客様が、組織のロールと権限を定義および管理できます。

## データ暗号化

**_保存中のデータの暗号化_** - Adobe Experience PlatformからJourney Optimizer B2B editionに転送されるすべてのアカウントおよびユーザープロファイルのデータは、Experience Platformの既存のコンプライアンスを維持するために暗号化されます。 ジャーニーや購入グループなど、Journey Optimizer B2B editionから派生するすべてのエンティティも暗号化されます。

**_転送中のデータの暗号化_** （パブリックネットワーク経由） – すべてのJourney Optimizer B2B edition API およびエンティティは、TLS 1.2 を使用して転送中に暗号化されます。

## 同意のオプトイン/オプトアウト

同意のオプトイン/オプトアウトは、プロファイルがメールや SMS などの通信チャネルからオプトアウトでき、その後プロファイルが通信チャネルから除外されるガバナンスの形態です。

Journey Optimizer B2B editionを使用すると、メールおよび SMS 配信のユースケースを作成および管理できます。 これらの同意環境設定は、XDM プロファイル同意フィールドグループ内に保存され、Data Sync Framework の一部としてJourney Optimizer B2B editionに同期されたり、から同期されたりします。 これらの環境設定は、オプトアウトプロファイルを配信から除外するために、配信時に使用されます。

## サンドボックスのリセット

Adobe Journey Optimizer B2B editionでは、サンドボックスのリセットは **現在サポートされていません** サポートされていません。 Journey Optimizer B2B editionにマッピングされているサンドボックスをリセットまたは削除すると、Journey Optimizer B2B editionのデータが恒久的に失われ、新しいJourney Optimizer B2B edition インスタンスのプロビジョニングが必要になる可能性があります。

## まだ利用できません

次のガバナンス機能は、まだ使用できません。

* データ使用ラベルの適用（DULE）/使用ポリシー
* データハイジーン
* 同意ポリシー
* フィールドレベルのアクセス制御（FLAC）
* オブジェクトレベルのアクセス制御（OLAC）
* 保存時のデータの CMK 暗号化
* Platform 監査サービス
