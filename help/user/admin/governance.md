---
title: ガバナンスとプライバシー機能
description: Journey Optimizer B2B editionで現在利用可能なガバナンス機能について説明します。
feature: Setup
role: Admin
exl-id: 2845272b-987c-4a37-adf4-6ee5bfd59fc0
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: d6e625c1-468f-4d73-9f32-fd1edb87f96bid: f2da1b69-6919-4386-a5d2-9c7b5c9033db
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
autotag-review: 2026-03-27T23:18:44.352Z
TQID: https://experienceleague.adobe.com/PwH34suDPc84nB9eiAWtrkVzsOw82RRGw4hrRogf9zE
source-git-commit: 61481d57fb8eca805d9a9bc545124aed568b5416
workflow-type: tm+mt
source-wordcount: 697
ht-degree: 2%

---

# ガバナンスとプライバシー機能

[!DNL Journey Optimizer B2B Edition]は統合Adobe Experience Platform アプリです。 企業慣行、法的義務、開発プロセスに準拠して、収集したエクスペリエンスデータを管理するためのツールとサービスをいくつか導入しています。 以下の節では、これらの各ガバナンス機能の概要を説明します。

## プライバシー

上記の各地域または国（EU、カリフォルニア州、タイ、ブラジル、ニュージーランド）に居住するデータ主体のデータを保有する[!DNL Journey Optimizer B2B Edition]のお客様には、さまざまな規制が適用されます。 このページ上のこの情報は、法的なアドバイスではなく、適用法の遵守を保証するものではありません。

### GDPR

一般データ保護規則（GDPR）とは、EU加盟国の[ データ保護要件](https://commission.europa.eu/law/law-topic/data-protection/data-protection-explained_en){target="_blank"}を調整および近代化する欧州連合（EU）のプライバシー法です。

[!DNL Journey Optimizer B2B Edition]は、Privacy ServiceおよびMarketo Privacy Broker Serviceが提供する既存のMarketo Engage GDPR ガバナンス機能を使用しています。

### CNIL

2026年4月14日、Commission nationale de l&#39;informatique et des libertés （CNIL） [は、メール内でのトラッキングピクセルの使用に関する推奨事項](https://cnil.fr/sites/default/files/2026-05/recommandation_tracking_pixels_emails.pdf)を公開しました。 このガイダンスでは、同意が必要なタイミングを明確にし、メールのピクセル追跡における適切な同意管理の重要性を強調しています。 このポリシーは、フランスに拠点を置く購読者にメールを送信するあらゆるエンティティに影響します。

CNILは、企業がトラッキングピクセルの存在、目的、および受信者のオプトアウトの権利をメール受信者に通知するための推奨事項の日付から3か月間を提供しました。 この移行期間中、Marketo Engage ユーザーは、受信者にピクセルトラッキングについて通知し、必要に応じてオプトアウトを提供することが求められます。 CNILは、2026年7月14日以降に強制執行活動を開始する予定です。

CNILおよびその他の規制当局がピクセルのトラッキングおよび関連する問題に関するガイダンスを明確にするため、Adobeは引き続きアップデートを監視し、技術能力の変化を通知します。

[!DNL Journey Optimizer B2B Edition]では、電子メール レベルでのオープン トラッキングの管理に役立つコントロールを提供しています。 ユーザーは、適用されるCNILのガイダンスやその他の法律に基づいて、独自のコンプライアンス義務を決定する責任があります。 これらの機能を使用して電子メールの開封トラッキングを管理する方法について詳しくは、[_電子メールトラッキングの管理_](../content/email-tracking-manage.md)&#x200B;を参照してください。

## 役割ベースのアクセス制御（RBAC）

Journey Optimizer B2B editionとAdobe Admin Consoleへのアクセスを使用すると、管理者はエンティティタイプ（view-segments、manage-segments、manage-journeysなど）に対するユーザー権限を付与できます。 この機能は、すべてのAdobe Experience Platformのお客様が自社の役割と権限を定義および管理できるようにする統合権限フレームワーク（UPF）の一部です。

## データ暗号化

**_保存中のデータの暗号化_** - Adobe Experience PlatformからJourney Optimizer B2B editionに転送されるすべてのアカウントおよび人物プロファイルデータは、Experience Platformの既存のコンプライアンスを維持するために暗号化されます。 ジャーニーや購買グループなど、Journey Optimizer B2B editionを起源とするすべてのエンティティも暗号化されています。

**_転送中のデータの暗号化_** （パブリックネットワーク経由） – すべてのJourney Optimizer B2B edition APIとエンティティは、TLS 1.2を使用して転送中に暗号化されます。

## 同意オプトイン/オプトアウト

Journey Optimizer B2B editionは、Adobe Experience Platform XDM プロファイルに保存されている個人ごとの同意設定を読み取り、メール、SMS、WhatsApp チャネルのメッセージ配信時に適用します。 チャネルをオプトアウトしたユーザーは、コンテンツがチャネルまたは下流のメッセージプロバイダーから送信される前に、配信から除外されます。

同意は、プロファイル同意フィールドグループのXDM フィールドを使用して配信時に評価されます。 デフォルトの同意行動はチャネルによって異なります。デフォルトでは、メールは環境設定が設定されていない場合にオプトインされ、SMSとWhatsAppはデフォルトでオプトアウトされます。

各チャネルについて評価されるXDM属性とデフォルトの動作について詳しくは、[同意設定](../content/channels-consent-preferences.md)を参照してください。

## サンドボックスのリセット

サンドボックスリセットは&#x200B;**現在Adobe Journey Optimizer B2B editionではサポートされていません**。 Journey Optimizer B2B editionにマッピングされたサンドボックスをリセットまたは削除すると、永続的なデータ損失が発生し、新しいインスタンスのプロビジョニングが必要になる場合があります。

## まだ利用できません

次のガバナンス機能はまだ使用できません。

* データ使用ラベルの適用（DULE）/使用ポリシー
* データハイジーン
* 同意ポリシー
* フィールドレベルのアクセス制御（FLAC）
* オブジェクトレベルのアクセス制御（OLAC）
* 保存データのCMK暗号化
* Platform監査サービス
