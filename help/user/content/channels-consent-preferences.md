---
title: チャネルメッセージの同意
description: Journey Optimizer B2B editionがAEP XDM プロファイルの同意設定を読み取り、メール、SMS、WhatsApp チャネルのメッセージ配信時間にオプトインとオプトアウトを適用する方法について説明します。
feature: Setup, Channels
role: Admin, User
autotag-review: '2026-05-19T16:18:37.228Z'
TQID: 'https://experienceleague.adobe.com/-c0dJnpfiIcj0B5gViyEQ7E1Ws0BwP864OLF003rOjw'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
subfeature_v2:
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
  - id: a22f05f6-0fcf-40c0-a70e-e13a3db185f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: cba977f62f3d2a83bcf2487a8ec612b76a655954
workflow-type: tm+mt
source-wordcount: 412
ht-degree: 2%

---

# チャネルメッセージにおける同意

Adobe Journey Optimizer B2B editionは、Adobe Experience Platform XDM プロファイルに保存されている1人あたりの同意設定を読み取り、アプリの[&#x200B; ガバナンス管理](../admin/governance.md)の一環として、メッセージ配信時に適用します。 チャネルをオプトアウトしたユーザーは、コンテンツがチャネルまたは下流のメッセージプロバイダーから送信される前に、配信から除外されます。

次の節では、サポートされている各チャネルについて、Journey Optimizer B2B editionがメッセージ送信時の同意をどのように評価するかを説明します。

## メール {#email}

Journey Optimizer B2B editionは、[&#x200B; メールチャネル &#x200B;](../admin/configure-channels-emails.md)でメッセージを送信する際に、メール同意に対して次のXDM属性を評価します。

| XDM 属性 | `y` | `n` | 値なし |
| --- | --- | --- | --- |
| `consents.marketing.email.val` | オプトイン | オプトアウト | オプトイン |

メールの同意については、次の考慮事項を考慮してください。

* メールを世界中からオプトアウトした人は、業務用とマークされたメールを受け取ることができます。
* サブスクリプションレベルの環境設定はサポートされていません。

## SMS {#sms}

Journey Optimizer B2B editionは、[SMS チャネル &#x200B;](../admin/configure-channels-sms.md)を介してメッセージを送信する際に、SMS同意に対して次のXDM属性を評価します。

| XDM 属性 | `y` | `n` | 値なし |
| --- | --- | --- | --- |
| `consents.marketing.sms.val` | オプトイン | オプトアウト | オプトアウト |
| `consents.marketing.subscriptions.<senderID>` | オプトイン | オプトアウト | オプトアウト |
| `consents.marketing.sms.subscriptions.<senderId>.subscribers.<phoneNumber>` | オプトイン | オプトアウト | オプトアウト |

SMSの同意については、次の点に注意してください。

* リード（人物）レコードがSMSからオプトアウトされると、レコードは完全に除外され、ダウンストリーム SMS プロバイダーに渡されません。
* 可能な場合、購読レベルの同意が評価されます。 サブスクリプションレベルの同意が得られない場合、グローバルオプトアウトはフォールバックとして使用されます。
* SMSからオプトアウトしたユーザーは、引き続き運用中とマークされたメッセージを受信できます。
* 複数のリードレコードが同じ電話番号を共有している場合、同じオプトインまたはオプトアウトステータスを共有します。

## WhatsApp {#whatsapp}

Journey Optimizer B2B editionは、設定された[WhatsApp チャネル &#x200B;](../admin/configure-channels-whatsapp.md)を通じてメッセージを送信する際に、WhatsApp同意に対して次のXDM属性を評価します。

| XDM 属性 | `y` | `n` | 値なし |
| --- | --- | --- | --- |
| `consents.marketing.whatsApp.val` | オプトイン | オプトアウト | オプトアウト |
| `consents.idSpecific.Phone.<number>.marketing.whatsApp.val` | オプトイン | オプトアウト | オプトアウト |

WhatsAppの同意については、次の点を考慮してください。

* グローバル WhatsApp属性値（`consents.marketing.whatsApp.val`）が存在する場合、同意評価に使用されます。
* グローバル属性値が存在しないが、送信者固有のエントリが存在する場合、送信者固有のエントリが同意評価に使用されます。
* いずれかの属性に値が存在しない場合、その人物はオプトアウトとして扱われます。

## サポートなし {#not-supported}

次の同意関連の機能は、現在、Journey Optimizer B2B editionではサポートされていません。

* AEPの同意ポリシー
* マーケティング優先属性（`consents.marketing.preferred`）
