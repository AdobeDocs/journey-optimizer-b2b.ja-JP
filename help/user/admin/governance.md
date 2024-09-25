---
title: ガバナンス機能
description: Journey Optimizer B2B Edition で現在利用可能なガバナンス機能について説明します。
exl-id: 2845272b-987c-4a37-adf4-6ee5bfd59fc0
source-git-commit: 8c191cd86a9aa9e7094b7d3464b3179cfdb4789e
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 3%

---

# ガバナンス機能

統合Adobe Experience Platform アプリであるJourney Optimizer B2B Edition には、ビジネスプラクティス、法的義務および開発プロセスに準拠するように、収集されたエクスペリエンスデータを確信を持って制御できるいくつかのサービスおよびツールが使用されています。 以下の節では、これらの各ガバナンス機能の概要を説明します。

## プライバシー – GDPR

Journey Optimizer B2B Edition では、Privacy ServiceおよびMarketo Privacy Broker Service が提供する GDPR ガバナンス機能の既存のMarketo Engageを使用します。

## 役割ベースのアクセス制御（RBAC）

Journey Optimizer B2B Edition とAdobe Admin Consoleへのアクセス権を使用すると、管理者は、エンティティタイプ（view-segments、manage-segments、manage-journeys など）に対する権限をユーザーに付与できます。 この機能は、Unified Permissions Framework （UPF）の一部であり、すべてのAdobe Experience Platformのお客様が、組織のロールと権限を定義および管理できます。

## データ暗号化

**_保存中のデータの暗号化_** - Adobe Experience PlatformからJourney Optimizer B2B Edition に転送されるすべてのアカウントおよびユーザープロファイルのデータは、Experience Platformに対する既存のコンプライアンスを維持するために暗号化されます。 ジャーニーや購買グループなど、Journey Optimizer B2B Edition から派生するすべてのエンティティも暗号化されます。

**_転送中のデータの暗号化_** （パブリックネットワーク経由） – すべてのJourney Optimizer B2B Edition API およびエンティティは、TLS 1.2 を使用して転送中に暗号化されます。

## 同意のオプトイン/オプトアウト

同意のオプトイン/オプトアウトは、プロファイルがメールや SMS などの通信チャネルからオプトアウトでき、そのような通信チャネルからプロファイルを除外する必要がある、ガバナンスの一種です。

Journey Optimizer B2B Edition を使用すると、メールおよび SMS 配信のユースケースを作成および管理できます。 これらの同意環境設定は、XDM プロファイル同意フィールドグループ内に保存され、Data Sync Framework の一部としてJourney Optimizer B2B Edition に同期されたり、Edition から同期されたりします。 これらの環境設定は、オプトアウトプロファイルを配信から除外するために、配信時に使用されます。

## まだ利用できません

次のガバナンス機能は、まだ使用できません。

* データ使用ラベルの適用（DULE）/使用ポリシー
* データハイジーン
* サンドボックスのリセット
* 同意ポリシー
* フィールドレベルのアクセス制御（FLAC）
* オブジェクトレベルのアクセス制御（OLAC）
* 保存時のデータの CMK 暗号化
* Platform 監査サービス
