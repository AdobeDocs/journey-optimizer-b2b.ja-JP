---
title: メール設定
description: Marketo Engageで設定されたメール設定にアクセスして確認する方法を説明します。
feature: Setup
source-git-commit: f097f535237fe6b27322e2c325e59daa8a54ee2f
workflow-type: tm+mt
source-wordcount: '1167'
ht-degree: 3%

---

# メール設定

Adobe Journey Optimizer B2B editionは、Market Engage のチャネル機能とイベントトラッキングを活用します。 管理者は、マーケターに対してチャネル配信を有効にするために、配信とトラッキングの設定が適切に行われていることを確認する必要があります。

## 配信設定

デフォルトのメール設定は、マーケターがアカウントジャーニーでメールを作成する際に使用されます。 メール配信設定を確認するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL メール]_ の下にある **[!UICONTROL 配信設定]** を選択します。

![ メール配信設定へのアクセス ](./assets/config-email-delivery-email-header.png){width="800" zoomable="yes"}

これらの設定は、Journey Optimizer B2B editionでは読み取り専用です。 右上の **[!UICONTROL 設定を編集]** をクリックして、接続されたMarketo Engageインスタンスの設定オプションにアクセスします。

>[!NOTE]
>
>Adobe Marketo Engageのこれらの設定にアクセスして編集するには、製品管理者権限が必要です。

現在の設定をレビューするには、次の各タブを選択します。

### [!UICONTROL  メールヘッダーパラメーター ] {#email-header}

メールヘッダーパラメーターでは、次のデフォルト値を定義します。

* **[!UICONTROL 送信元メール]** - メールヘッダーの _送信元_ フィールドにリストされているメールアドレス。

* **[!UICONTROL 送信者ラベル]** - メール送信者アドレスの表示名。

* **[!UICONTROL 登録解除HTML]** – 操作以外のメールに表示される、受信者に登録解除アクションを説明するHTML（サポートされているメールクライアント用）。 このテキストとリンクが下部に追加されます。

* **[!UICONTROL 登録解除テキスト]** – 受信者に登録解除アクションを説明するために、操作以外のメールに表示されるプレーンテキストです。 このテキストとリンクが下部に追加されます。

* **[!UICONTROL Web ページとして表示HTML]** - _Web ページとして表示_ に使用するHTMLで、ブラウザーにメールを表示するためのリンクを提供します（サポートされているメールクライアント用）。

* **[!UICONTROL Web ページテキストとして表示]** - _Web ページとして表示_ に使用されるプレーンテキスト。ブラウザーにメールを表示するためのリンクを提供します。

### [!UICONTROL  ブランディングドメイン ] {#branding-domains}

ブランディングドメインを確認するには、「**[!UICONTROL ブランディングドメイン]**」タブをクリックします。

![ ブランディングドメイン設定へのアクセス ](./assets/config-email-delivery-branding-domains.png){width="700" zoomable="yes"}

この設定は、1 つ以上のMarketo Engage ワークスペースのプライマリ ドメインを定義します。 新しいメールでは、デフォルトでこのドメインが使用されますが、マーケターはメールごとに上書きできます。 詳しくは、[Marketo Engageドキュメント ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/add-multiple-branding-domains/edit-your-default-branding-domain){target="_blank"} を参照してください。

>[!NOTE]
>
>Journey Optimizer B2B editionおよびコネクテッドMarketo Engageインスタンスから複数のブランドをマーケティングしており、それぞれに独自のブランドトラッキングリンクを設定する場合は、ブランディングドメインを追加できます。 詳しくは、[Marketo Engageドキュメント ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/add-multiple-branding-domains/add-an-additional-branding-domain){target="_blank"} を参照してください。


### [!UICONTROL  カスタムヘッダーオプション ] {#custom-header-options}

カスタムヘッダーオプションを確認するには、「**[!UICONTROL カスタムヘッダーオプション]**」タブをクリックします。

![ カスタムヘッダーオプションへのアクセス ](./assets/config-email-delivery-custom-header.png){width="700" zoomable="yes"}

_[!UICONTROL Strict Transport Security]_ が有効な場合は、トラッキングリンクが HTTPS 経由で提供されることが保証されます（SSL で保護されたトラッキングリンクを含むサブスクリプションの場合のみ）。

## 通信の制限

通信の制限は、組織が送信するメールの量を制御します。 組織からのメールが多すぎて受信者に圧倒されないように制限を設定することをお勧めします。

現在の設定を確認するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL メール]_ の下で **[!UICONTROL 通信の制限]** を選択します。

![ 通信制限設定へのアクセス ](./assets/config-email-communication-limits.png){width="700" zoomable="yes"}

これらの設定は、Journey Optimizer B2B editionでは読み取り専用です。 右上の **[!UICONTROL 設定を編集]** をクリックして、接続されたMarketo Engageインスタンスの設定オプションにアクセスします。

>[!NOTE]
>
>Adobe Marketo Engageのこれらの設定にアクセスして編集するには、製品管理者権限が必要です。

通信制限の設定について詳しくは、[Marketo Engageドキュメント ](https://experienceleague.adobe.com/ja/docs/marketo/using/product-docs/administration/email-setup/enable-communication-limits){target="_blank"} を参照してください。

## SPF/DKIM

SPF （Sender Policy Framework）と DKIM （Domain Keys Identified Mail）を DNS 設定に組み込むことで、メール配信率を向上させます。 これらのテクノロジーは、メールがスパムではないことを受信者に保証します。 受信者のスパムフィルターがメールを拒否しないようにするには、ドメインに SPF と DKIM が設定されていることを確認します。

現在の設定を確認するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL メール]_ の下で、「**[!UICONTROL SPF/DKIM]**」を選択します。

![SPF/DKIM 設定へのアクセス ](./assets/config-email-spf-dkim.png){width="700" zoomable="yes"}

これらの設定は、Journey Optimizer B2B editionでは読み取り専用です。 右上の **[!UICONTROL 設定を編集]** をクリックして、接続されたMarketo Engageインスタンスの設定オプションにアクセスします。

>[!NOTE]
>
>Adobe Marketo Engageのこれらの設定にアクセスして編集するには、製品管理者権限が必要です。

### SPF 設定

ネットワーク管理者は、DNS エントリに次の行を追加する必要があります。

`[domain] IN TXT v=spf1 mx ip4:[corpIP] include:mktomail.com ~all`

このエントリでは、`[domain]` を web サイトのプライマリドメイン（`company.com` など）に、`[corpIP]` を企業のメールサーバーの IP アドレス（`255.255.255.255` など）に置き換えます。 Marketo Engageを通じて複数のドメインからメールを送信する場合、ドメインごとにこのエントリを 1 行に追加します。

DNS エントリに既に SPF レコードが存在する場合は、次を追加します。

`include:mktomail.com`

### DKIM の設定

DKIM は、メール受信者がメールメッセージの送信者を検証するために使用する認証プロトコルです。 受信者はメッセージが偽造されたものではないと確信できるので、多くの場合、インボックスへのメールの配信品質が向上します。

DNS レコードの公開鍵と、接続されたMarketo Engageインスタンスで有効になった送信側ドメインを使用して、送信メッセージにカスタムの DKIM 署名を使用します。 カスタム DKIM 署名には、送信される各メールに暗号化されたデジタル署名が含まれます。 その後、受信者は、送信ドメインの DNS で _公開鍵_ を検索することで、デジタル署名を復号化できます。 メール内のキーが DNS レコード内のキーと一致する場合、受信側のメールサーバーはMarketo Engageを通じて送信されたメールを受け入れる可能性が高くなります。

メール配信用のカスタム DKIM 署名の設定について詳しくは、[Marketo Engageドキュメント ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"} を参照してください。

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

これらの設定は、Journey Optimizer B2B editionでは読み取り専用です。 右上の **[!UICONTROL 設定を編集]** をクリックして、接続されたMarketo Engageインスタンスの設定オプションにアクセスします。

>[!NOTE]
>
>Adobe Marketo Engageのこれらの設定にアクセスして編集するには、製品管理者権限が必要です。

ボットアクティビティオプションの設定について詳しくは、[Marketo Engageドキュメント ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/email-setup/filtering-email-bot-activity#select-filter-type){target="_blank"} を参照してください。

