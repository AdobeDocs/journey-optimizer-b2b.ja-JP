---
title: メールの重複排除
description: アカウントジャーニーでメールの重複排除を使用して、同じメールが同じメールアドレスに複数回送信されないようにする方法を説明します。
feature: Account Journeys, Channels
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: 電子メール、重複排除、ジャーニー、重複
exl-id: 93107acd-1cb2-4316-acfc-e32ab1e065ae
autotag-review: 2026-03-30T22:08:16.582Z
TQID: 'https://experienceleague.adobe.com/aWKXaC6x4Izeh81A6Fpy-Nrf18fHgnq6jUc-82ohErs'
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
subfeature_v2:
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 21fbce544faf291ad01a3301a9981add95442097
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 1%
---
# メールの重複排除

ジャーニー内で同じメールアドレスに同じメールが複数回送信されないようにするには、アカウントジャーニーでメールの重複排除を使用します。 この機能を有効にすると、そのメールアドレスを持つ最初のレコードがジャーニーを完了するまで、重複するメールアドレスがブロックされます。 アカウントがジャーニーを完了すると、新規アカウントがジャーニーにエントリする際に、メールを再度受信する資格を得ることができます。

## メールの重複排除の使用例

メールの重複排除を有効にするために考慮すべき重要なシナリオがいくつかあります。

* **電子メールは、Real-Time CDPのIDとして使用されていません** – 同じ電子メールアドレスが複数の人物プロファイルに表示される場合があります。 重複したプロファイルが同じジャーニーに該当し、メールの送信を複数回防ぐ場合は、この機能を有効にします。

* **複数のアカウントに関連付けられた単一の人物** - [!DNL Real-Time CDP] データモデルが1人の人物を複数のアカウントに関連付ける場合、同じメールアドレスを持つ複数のプロファイルが同じジャーニーに適格である場合に、同じメールを2回送信しないようにするには、この機能を有効にします。

>[!NOTE]
>
>メールの重複は、ジャーニーレベルで適用されます。 同じメールアドレスを持つ個人が異なるジャーニーに適格である場合でも、各ジャーニーからメールを受け取ることができます。

## ジャーニーのメール重複排除を有効にする

アカウントジャーニーのメール重複排除を有効にするには：

1. アカウントジャーニーを開きます。

1. **[!UICONTROL 詳細]** （**...**）をクリックします ジャーニーワークスペースの右上隅にあります。

   ![詳細メニューが展開されたジャーニーワークスペースにメールの重複排除オプションが表示されている](./assets/email-deduplication-more-menu.png){width="450"}

1. **[!UICONTROL メールの重複排除]**&#x200B;を選択します。

1. ダイアログで、「**[!UICONTROL 電子メールの重複排除]**」チェックボックスを選択します。

   ![切り替えが有効になっているメール重複排除ダイアログ &#x200B;](./assets/email-deduplication-dialog.png){width="400"}

1. 「**[!UICONTROL 保存]**」をクリックします。

メールの重複排除が有効になっている場合、ジャーニーはメールを送信する前に各メールアドレスを確認します。 同じメールアドレスのレコードがそのジャーニーノードに既に入力されている場合、最初のレコードがジャーニーを完了するまで、新しいエントリはブロックされます。
