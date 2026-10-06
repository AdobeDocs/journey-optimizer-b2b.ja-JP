---
title: チャネルメッセージの同意
description: Journey Optimizer B2B EditionがAEP XDM プロファイルの同意設定を読み取り、メール、SMS、WhatsApp チャネルのメッセージ配信時間にオプトインとオプトアウトを適用する方法について説明します。
feature: Setup, Channels
role: Admin, User
autotag-review: '2026-05-19T16:18:37.228Z'
TQID: 'https://experienceleague.adobe.com/-c0dJnpfiIcj0B5gViyEQ7E1Ws0BwP864OLF003rOjw'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
    internal-label: Communication channels
  - id: d77af7eb-afc3-53f3-a50c-dabc0d05ecfd
    internal-label: Channels
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
    internal-label: Administration
subfeature_v2:
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
    internal-label: Email channel
  - id: a22f05f6-0fcf-40c0-a70e-e13a3db185f7
    internal-label: SMS channel
  - id: f6df9def-cdf7-4728-9ec8-3f65716828c7
    internal-label: Setup
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 21fbce544faf291ad01a3301a9981add95442097
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 2%
---
# チャネルメッセージにおける同意

Adobe Journey Optimizer B2B Editionは、Adobe Experience Platform XDM プロファイルに保存されている1人あたりの同意設定を読み取り、アプリの[ ガバナンスコントロール ](../admin/governance.md)の一部として、メッセージ配信時に適用します。 チャネルをオプトアウトしたユーザーは、コンテンツがチャネルまたは下流のメッセージプロバイダーから送信される前に、配信から除外されます。

次の節では、サポートされている各チャネルについて、Journey Optimizer B2B Editionがメッセージ送信時の同意をどのように評価するかを説明します。

## メール {#email}

Journey Optimizer B2B Editionは、[ メールチャネル ](../admin/configure-channels-emails.md)でメッセージを送信する際に、メール同意に対して次のXDM属性を評価します。

| XDM 属性 | `y` | `n` | 値なし |
| --- | --- | --- | --- |
| `consents.marketing.email.val` | オプトイン | オプトアウト | オプトイン |

メール同意については、次の点を考慮してください。

* メールを世界中からオプトアウトした人は、業務用とマークされたメールを受け取ることができます。
* サブスクリプションレベルの環境設定はサポートされていません。

送信された電子メールの購読解除アクティビティを確認するには、[電子メールパフォーマンスレポート ](../dashboards/email-performance-dashboard.md)を参照してください。

## SMS {#sms}

Journey Optimizer B2B Editionは、[SMS チャネル ](../admin/configure-channels-sms.md)を介してメッセージを送信する際に、SMS同意に対して次のXDM属性を評価します。

| XDM 属性 | `y` | `n` | 値なし |
| --- | --- | --- | --- |
| `consents.marketing.sms.val` | オプトイン | オプトアウト | オプトアウト |
| `consents.marketing.subscriptions.<senderID>` | オプトイン | オプトアウト | オプトアウト |
| `consents.marketing.sms.subscriptions.<senderId>.subscribers.<phoneNumber>` | オプトイン | オプトアウト | オプトアウト |

SMS同意については、次の点を考慮してください。

* リード（人物）レコードがSMSからオプトアウトされると、レコードは完全に除外され、ダウンストリーム SMS プロバイダーに渡されません。
* 可能な場合、購読レベルの同意が評価されます。 サブスクリプションレベルの同意が得られない場合、グローバルオプトアウトはフォールバックとして使用されます。
* SMSからオプトアウトしたユーザーは、引き続き運用中とマークされたメッセージを受信できます。
* 複数のリードレコードが同じ電話番号を共有している場合、同じオプトインまたはオプトアウトステータスを共有します。

## WhatsApp {#whatsapp}

Journey Optimizer B2B Editionは、設定された[WhatsApp チャネル ](../admin/configure-channels-whatsapp.md)を通じてメッセージを送信する際に、WhatsApp同意に対して次のXDM属性を評価します。

| XDM 属性 | `y` | `n` | 値なし |
| --- | --- | --- | --- |
| `consents.marketing.whatsApp.val` | オプトイン | オプトアウト | オプトアウト |
| `consents.idSpecific.Phone.<number>.marketing.whatsApp.val` | オプトイン | オプトアウト | オプトアウト |

WhatsAppの同意については、次の点を考慮してください。

* グローバル WhatsApp属性値（`consents.marketing.whatsApp.val`）が存在する場合、同意評価に使用されます。
* グローバル属性値が存在しないが、送信者固有のエントリが存在する場合、送信者固有のエントリが同意評価に使用されます。
* いずれかの属性に値が存在しない場合、その人物はオプトアウトとして扱われます。

## サポートなし {#not-supported}

次の同意関連の機能は、現在Journey Optimizer B2B Editionではサポートされていません。

* AEPの同意ポリシー
* マーケティング優先属性（`consents.marketing.preferred`）
