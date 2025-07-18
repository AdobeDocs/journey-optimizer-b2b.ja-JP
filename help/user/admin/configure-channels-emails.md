---
title: メールチャネル設定
description: Marketo Engageで設定されたメール設定にアクセスして確認する方法を説明します。
feature: Setup, Channels
role: Admin
exl-id: fb16b5e5-f1a5-4e59-b8c6-56985f03225a
source-git-commit: 4bbe641305065888a59b3e77357e9b39fa6d402e
workflow-type: tm+mt
source-wordcount: '1195'
ht-degree: 3%

---

# メールチャネル設定

Adobe Journey Optimizer B2B editionは、Marketo Engageのチャネル関数とイベントトラッキングを活用します。 管理者は、マーケターに対してチャネル配信を有効にするために、配信とトラッキングの設定が適切に行われていることを確認する必要があります。 Marketo Engageを介したメール配信およびトラッキングに必要なプロトコルについては、[ トラッキングとメール配信のプロトコル ](../start/email-protocols.md) を参照してください。

## 配信設定

デフォルトのメール設定は、マーケターがアカウントジャーニーでメールを作成する際に使用されます。 メール配信設定を確認するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL メール]_ の下にある **[!UICONTROL 配信設定]** を選択します。

![ メール配信設定へのアクセス ](./assets/config-email-delivery-email-header.png){width="800" zoomable="yes"}

これらの設定は、Journey Optimizer B2B editionでは読み取り専用です。 右上の **[!UICONTROL 設定を編集]** をクリックして、接続されたMarketo Engage インスタンスの設定オプションにアクセスします。

>[!NOTE]
>
>Adobe Marketo Engageのこれらの設定にアクセスして編集するには、製品管理者権限が必要です。

現在の設定をレビューするには、次の各タブを選択します。

### [!UICONTROL &#x200B; メールヘッダーパラメーター &#x200B;] {#email-header}

メールヘッダーパラメーターでは、次のデフォルト値を定義します。

* **[!UICONTROL 送信元メール]** - メールヘッダーの _送信元_ フィールドにリストされているメールアドレス。

* **[!UICONTROL 送信者ラベル]** - メール送信者アドレスの表示名。

* **[!UICONTROL 登録解除HTML]** – 操作以外のメールに表示されるHTML（サポートされているメールクライアント用）で、受信者に登録解除アクションを説明します。 このテキストとリンクが下部に追加されます。

* **[!UICONTROL 登録解除テキスト]** – 受信者に登録解除アクションを説明するために、操作以外のメールに表示されるプレーンテキストです。 このテキストとリンクが下部に追加されます。

* **[!UICONTROL web ページとして表示HTML]** - _web ページとして表示_ に使用されるHTML（サポートされているメールクライアント用）。ブラウザーにメールを表示するためのリンクを提供します。

* **[!UICONTROL Web ページテキストとして表示]** - _Web ページとして表示_ に使用されるプレーンテキスト。ブラウザーにメールを表示するためのリンクを提供します。

### [!UICONTROL &#x200B; ブランディングドメイン &#x200B;] {#branding-domains}

ブランディングドメインを確認するには、「**[!UICONTROL ブランディングドメイン]**」タブをクリックします。

![ ブランディングドメイン設定へのアクセス ](./assets/config-email-delivery-branding-domains.png){width="700" zoomable="yes"}

この設定は、接続されたMarketo Engage インスタンス内の 1 つ以上のワークスペースのプライマリドメインを定義します。 新しいメールではデフォルトとしてこのドメインが使用されますが、マーケターは [ メールごとに上書き ](../content/add-email.md#define-the-email-settings) できます。 デフォルトのブランディングドメインの定義について詳しくは、[Marketo Engage ドキュメント ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/add-multiple-branding-domains/edit-your-default-branding-domain){target="_blank"} を参照してください。

>[!NOTE]
>
>複数のブランドをマーケティングし、それぞれに独自のブランドトラッキングリンクを設定する場合は、ブランディングドメインを追加できます。 複数のブランディングドメインの追加について詳しくは、[Marketo Engage ドキュメント ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/add-multiple-branding-domains/add-an-additional-branding-domain){target="_blank"} を参照してください。

### [!UICONTROL &#x200B; カスタムヘッダーオプション &#x200B;] {#custom-header-options}

カスタムヘッダーオプションを確認するには、「**[!UICONTROL カスタムヘッダーオプション]**」タブをクリックします。

![ カスタムヘッダーオプションへのアクセス ](./assets/config-email-delivery-custom-header.png){width="700" zoomable="yes"}

_[!UICONTROL Strict Transport Security]_ が有効な場合は、トラッキングリンクが HTTPS 経由で提供されることが保証されます（SSL で保護されたトラッキングリンクを含むサブスクリプションの場合のみ）。

## 通信の制限

通信の制限は、組織が送信するメールの量を制御します。 組織からのメールが多すぎて受信者に圧倒されないように制限を設定することをお勧めします。

現在の設定を確認するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL メール]_ の下で **[!UICONTROL 通信の制限]** を選択します。

![ 通信制限設定へのアクセス ](./assets/config-email-communication-limits.png){width="700" zoomable="yes"}

これらの設定は、Journey Optimizer B2B editionでは読み取り専用です。 右上の **[!UICONTROL 設定を編集]** をクリックして、接続されたMarketo Engage インスタンスの設定オプションにアクセスします。

>[!NOTE]
>
>Adobe Marketo Engageのこれらの設定にアクセスして編集するには、製品管理者権限が必要です。

通信制限の設定について詳しくは、[Marketo Engage ドキュメント ](https://experienceleague.adobe.com/ja/docs/marketo/using/product-docs/administration/email-setup/enable-communication-limits){target="_blank"} を参照してください。

## SPF/DKIM

SPF （Sender Policy Framework）とDKIM（Domain Keys Identified Mail）を DNS 設定に組み込むことで、メール配信率を向上させます。 これらのテクノロジーは、メールがスパムではないことを受信者に保証します。 受信者のスパムフィルターがメールを拒否しないようにするには、ドメインに SPF とDKIMが設定されていることを確認します。

現在の設定を確認するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL メール]_ の下で **[!UICONTROL SPF/DKIM]** を選択します。

![SPF/DKIM設定へのアクセス ](./assets/config-email-spf-dkim.png){width="700" zoomable="yes"}

これらの設定は、Journey Optimizer B2B editionでは読み取り専用です。 右上の **[!UICONTROL 設定を編集]** をクリックして、接続されたMarketo Engage インスタンスの設定オプションにアクセスします。

>[!NOTE]
>
>Adobe Marketo Engageのこれらの設定にアクセスして編集するには、製品管理者権限が必要です。

### SPF 設定

ネットワーク管理者は、DNS エントリに次の行を追加する必要があります。

`[domain] IN TXT v=spf1 mx ip4:[corpIP] include:mktomail.com ~all`

このエントリでは、`[domain]` を web サイトのプライマリドメイン（`company.com` など）に、`[corpIP]` を企業のメールサーバーの IP アドレス（`255.255.255.255` など）に置き換えます。 Marketo Engageを通じて複数のドメインからメールを送信する場合、ドメインごとにこのエントリを 1 行に追加します。

DNS エントリに既に SPF レコードが存在する場合は、次を追加します。

`include:mktomail.com`

### DKIM設定

DKIMは、メール受信者がメールメッセージの送信者を検証するために使用する認証プロトコルです。 受信者はメッセージが偽造されたものではないと確信できるので、多くの場合、インボックスへのメールの配信品質が向上します。

DNS レコードに公開鍵があり、接続されたMarketo Engage インスタンスで送信側ドメインが有効になっている場合は、送信メッセージにカスタムDKIM署名が使用されます。 カスタム DKIM署名には、送信される各メールに暗号化されたデジタル署名が含まれます。 その後、受信者は、送信ドメインの DNS で _公開鍵_ を検索することで、デジタル署名を復号化できます。 メール内のキーが DNS レコード内のキーと一致する場合、受信側のメールサーバーはMarketo Engageを通じて送信されたメールを受け入れる可能性が高くなります。

メール配信用のカスタム DKIM署名の設定について詳しくは、[Marketo Engage ドキュメント ](https://experienceleague.adobe.com/ja/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"} を参照してください。

## ボットアクティビティ

メールボットアクティビティが、誤ってメールの開封やクリックデータを水増ししてしまう可能性があります。

Marketo Engageでは、ボットアクティビティの確認に次の 2 つの方法を使用します。

* **インタラクティブ Advertising ビューロー（IAB）リストとの一致** - IAB UA/IP （ユーザーエージェント/IP アドレス）リストのいずれかと一致するアクティビティは、ボットとしてマークされます。

* **近接パターンと一致** - 2 つ以上のアクティビティが同時に（1 秒以内に）発生した場合、それらのアクティビティはボットとして識別されます。 このメソッドでは、比較のために次の属性を考慮します。

   * リード ID（同じであること）
   * メールアセット（同じであること）
   * リンククリックまたはメール開封
   * 時間差（1 秒未満であること）

メールリンクのクリックとメールの開封アクティビティの場合、新しい属性には次の値が入力されます。

* ボットとして識別されたアクティビティには、識別されたパターンやメソッドとして _ボットアクティビティ_ `True`、および _ボットアクティビティパターン_ があります。
* ボットでないと識別されたアクティビティには、_ボットアクティビティ_ が `False` として、_ボットアクティビティパターン_ が `N/A` として含まれます。
* 属性が導入される前に発生するアクティビティでは、_ボットアクティビティ_ が空（null）として、_ボットアクティビティパターン_ が空（null）として設定されています

現在の設定を確認するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL メール]_ の下にある **[!UICONTROL ボットアクティビティ]** を選択します。

![ メール配信用のボットアクティビティ設定へのアクセス ](./assets/config-email-bot-activity.png){width="700" zoomable="yes"}

これらの設定は、Journey Optimizer B2B editionでは読み取り専用です。 右上の **[!UICONTROL 設定を編集]** をクリックして、接続されたMarketo Engage インスタンスの設定オプションにアクセスします。

>[!NOTE]
>
>Adobe Marketo Engageのこれらの設定にアクセスして編集するには、製品管理者権限が必要です。

ボットアクティビティオプションの設定について詳しくは、[Marketo Engage ドキュメント ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/filtering-email-bot-activity#select-filter-type){target="_blank"} を参照してください。
