---
title: ジャーニーへのメールの追加
description: Adobe Journey Optimizer B2B でメールアクションを追加、定義、最適化する方法を説明します。 ターゲットを絞ったメール通信でアカウントジャーニーを強化します。
feature: Email Authoring, Account Journeys
role: User
exl-id: 21a6ce0f-b59d-4be2-abc3-fda5c6a6334f
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 0%

---

# ジャーニーへのメールの追加

Adobe Journey Optimizer B2B editionを使用すると、アカウントジャーニーを通じてメールメッセージを顧客に送信できます。 メールデザインスペースで、メッセージの作成、パーソナライズ、プレビューを選択できます。 または、接続されたMarketo Engage インスタンスで既に定義されているメールを送信することもできます。

>[!NOTE]
>
>初めてメールを送信する場合は、Adobe Marketo Engage内でメールチャネルが設定されていることを確認してください。 詳しくは、[ トラッキングとメール配信のプロトコル ](../start/email-protocols.md) を参照してください。

## ジャーニーへのメールアクションノードの追加

「_[!UICONTROL アクションを実行]_」ノードを追加 [ して以下の操作を実行する ](../journeys/action-nodes.md) ときに、ジャーニーにメール配信を設定できます。

1. _[!UICONTROL アクションオン]_ ターゲットで、「**[!UICONTROL ユーザー]**」を選択します。

1. _[!UICONTROL ユーザーに対するアクション]_ については、「**[!UICONTROL メールを送信]**」を選択します。

1. 「_[!UICONTROL メールソース]_」で、送信するメールのソースを選択します。

   ![ アクションの実行 – メールの送信 ](assets/journey-node-send-email.png){width="700" zoomable="yes"}

   * **[!UICONTROL 新しいメールを作成]** を選択して、Journey Optimizer B2B editionでネイティブにメールを作成します。

     このオプションを使用すると、Journey Optimizer B2B editionでメールコンテンツをネイティブに管理できます。 **[!UICONTROL メールを作成]** をクリックして、_新しいメールを作成_ ダイアログを開きます。 新しいメールコンテンツアセット <!-- or duplicate an existing email content asset--> を作成できます。

     ダイアログで、メールの一意の **[!UICONTROL 名前]** と **[!UICONTROL 件名]** を入力し、「作成 **[!UICONTROL をクリックし]** す。

     ![ 新しいメールを作成ダイアログ – 新しいメール ](assets/create-new-email-no-duplicate.png){width="400"}

     メールコンテンツページの _[!UICONTROL メールのプロパティ]_ セクションで、_[!UICONTROL 送信者メール]_ および _[!UICONTROL 返信先アドレス]_ フィールドが既に設定されています。 「_[!UICONTROL 送信者名]_」フィールドと「_[!UICONTROL 説明]_ （オプション）」フィールドの値を入力できます。

     メール [ 設定 ](#define-the-email-settings) を定義し、「**[!UICONTROL メールコンテンツを編集]**」をクリックして [ コンテンツをデザイン ](./email-authoring.md) します。

     <!-- +++New email {#new-email}
     When you want to create an email using an empty canvas or an email template, use the _[!UICONTROL New email]_ option. 

     1. In the dialog, choose **[!UICONTROL New email]**.

     1. Enter a unique **[!UICONTROL Name]** for the email and a **[!UICONTROL Subject line]**.

        ![Create new email dialog - new email](assets/create-new-email.png){width="400"}

     1. Click **[!UICONTROL Create]**.

       In the _[!UICONTROL Email properties]_ section of the email content page, the _[!UICONTROL From email]_ and _[!UICONTROL Reply to address]_ fields are already configured. You can enter values for the _[!UICONTROL From name]_ and _[!UICONTROL Description]_ (optional) fields.

     1. Click **[!UICONTROL Edit email]** to define the email [settings](#define-the-email-settings) and design the [content](./email-authoring.md).

     +++

     +++Duplicate existing email {#duplicate-email}
     When you want to create an email using an existing email from the current journey or from another journey, use the Duplicate existing journey option. You can make changes to the duplicated email according to your objective for the journey node.

     1. In the dialog, choose **[!UICONTROL Duplicate existing email]**.

     1. For **[!UICONTROL Existing email to duplicate]**, click the _Select email_ icon and select the email you want to duplicate and use for the journey node.

      You can filter the list of emails by entering a text string in the search field to match the email name.

      ![Select email](assets/create-new-email-duplicate-select-email.png){width="600" zoomable="yes"}

      Select the checkbox for the email that you want to duplicate and click **[!UICONTROL Select]**. 

     1. Enter a unique **[!UICONTROL Name]** for the email and a **[!UICONTROL Subject line]**.

        ![Create new email dialog - duplciate existing email](assets/create-new-email.png){width="400"}

     1. Click **[!UICONTROL Create]**.

        In the _[!UICONTROL Email properties]_ section of the email content page, the _[!UICONTROL From email]_ and _[!UICONTROL Reply to address]_ fields are already configured. You can enter values for the _[!UICONTROL From name]_ and _[!UICONTROL Description]_ (optional) fields.

     1. If needed, click **[!UICONTROL Edit email]** to modify the email [settings](#define-the-email-settings) and [content](./email-authoring.md).

     +++
   —>
   * **[!UICONTROL Adobe Marketo Engageからメールを選択]** を選択すると、Marketo Engageで作成済みのメールの 1 つを使用して、ジャーニーの一部として送信できます。

     ![Marketo Engageのメールを選択 ](./assets/email-select-marketo.png){width="500" zoomable="yes"}

     このオプションを使用すると、ノードが設定され、メールコンテンツをジャーニーでさらに定義する必要がなくなります。

## メール設定の定義

**[!UICONTROL 概要]** パネルで選択した _詳細_ タブを使用して、下までスクロールし、メールオプションを表示して設定します。

![ メールの設定 ](./assets/email-summary-details-settings.png){width="600" zoomable="yes"}

| オプション | 説明 |
| ------ | ----------- |
| [!UICONTROL  送信者名 ] | E メールヘッダーで使用される送信者名。 受信者に表示する送信者の名前を入力します。 _パーソナライズ_ アイコン（![ パーソナライズアイコン ](../assets/do-not-localize/icon-personalize.svg)）をクリックして、フィールドのパーソナライゼーショントークンを使用します。 |
| [!UICONTROL  送信元メール ] | E メールヘッダーで使用される送信者のアドレス。 デフォルト値は [ メールチャネル配信設定 ](../admin/configure-channels-emails.md#delivery-settings) から入力されます。 _パーソナライズ_ アイコン（![ パーソナライズアイコン ](../assets/do-not-localize/icon-personalize.svg)）をクリックして、フィールドのパーソナライゼーショントークンを使用します。 |
| [!UICONTROL  返信先アドレス ] | E メールヘッダーで使用される送信者のアドレス。 デフォルト値は [ メールチャネル配信設定 ](../admin/configure-channels-emails.md#delivery-settings) （[!UICONTROL  ラベルから ]）から入力されます。 受信者が返信機能を使用している場合に入力するメールアドレスを入力します（送信者のアドレスと異なる場合も同じ場合もあります）。 _パーソナライズ_ アイコン（![ パーソナライズアイコン ](../assets/do-not-localize/icon-personalize.svg)）をクリックして、フィールドのパーソナライゼーショントークンを使用します。 |
| [!UICONTROL  件名 ] | E メールの件名フィールドに表示されるテキスト。 デフォルト値は、「_[!UICONTROL 新しいメールを作成]_ ダイアログで入力したテキストから入力されます。 必要に応じて、テキストを変更できます。 _パーソナライズ_ アイコン（![ パーソナライゼーションアイコン ](../assets/do-not-localize/icon-personalize.svg)）をクリックして、フィールドのパーソナライゼーショントークンを使用します。<!-- Click the AI Assistant button ( ![AI Assistant icon](../../assets/do-not-localize/icon-gen-ai.svg){width="30" zoomable="no"} ) to generate the subject line based on the current email content.--> |
| [!UICONTROL  運用上のメール ] | メールを操作可能として指定する場合は、チェックボックスを選択します。 運用中のメールは、オプトアウト/購読解除リストおよび通信の制限から除外されます。 受信者がメールメッセージを迷惑メールと見なさない商用メッセージ （SPAM）の場合にのみ、このオプションを選択します。 |
| [!UICONTROL Web ページとしてビューを含める ] | チェックボックスを選択して、メールメッセージコンテンツから生成される web ページへのリンクを含めます。 メールメッセージは web ページよりも機能が制限されるので、JavaScript、拡張 CSS およびフォームで役立ちます。 リンクの生成に使用するテキストは、[ メールチャネル配信の設定 ](../admin/configure-channels-emails.md#delivery-settings) （[!UICONTROL web ページのHTMLとして表示 ] および [!UICONTROL web ページテキストとして表示 ]）で設定します。 |
| [!UICONTROL  開封トラッキングを無効にする ] | メールの開封アクティビティを追跡しない場合は、チェックボックスを選択します。 機能を無効にした場合、一意のユーザーがメールを開いた場合にのみ、メールの開封アクティビティ数が増分されます。 メール本文コンテンツをデザインする際に [ メールコンテンツリンクのトラッキングを管理 ](./email-authoring.md#content-authoring---link-tracking) できます。 |
| [!UICONTROL  プリヘッダー ] | プリヘッダーを含めるチェックボックスを選択します。 プリヘッダーは、一部のメールクライアントの件名の後に表示される短い概要テキストです。 通常は、メールの短い概要を提供し、通常は 1 文です。 フィールドに概要テキストを入力し <!-- , or click the AI Assistant button ( ![AI Assistant icon](../../assets/do-not-localize/icon-gen-ai.svg){width="30" zoomable="no"} ) to generate summary text based on the current email content --> す。 |
| [!UICONTROL CC アドレスとして使用されるフィールド ] | 使用可能な場合は、`Email` タイプを使用して、Marketo Engageで設定された最大 25 の「リード」フィールドまたは「会社」フィールドを選択します。 |

## アラートの確認

メールメッセージコンテンツをデザインする際、重要な設定が見つからない場合は、インターフェイス（ページの右上）にアラートが表示されます。 このボタンが表示されない場合は、検出された問題はありません。

![ メールアラート ](./assets/email-alerts.png){width="600" zoomable="yes"}

次の 2 種類のアラートを検出できます。

* 推奨事項やベストプラクティスを参照する **_警告_**。例えば、次のようなものがあります。

   * `The opt-out link is not present in the email body`：メール本文に購読解除リンクを追加することがベストプラクティスです。

     >[!NOTE]
     >
     >マーケティングスタイルの電子メールメッセージには、オプトアウトリンクを含める必要があります。これはトランザクションメッセージには必要ありません。

   * `Text version of HTML is empty`：メール本文のテキストバージョンを必ず定義してください。このバージョンは、HTML コンテンツを表示できない場合に使用されます。

   * `Empty link is present in email body`: メール内のすべてのリンクが正しいことを確認してください。

   * `Email size has exceeded the limit of 100KB`：配信を最適化するには、メールのサイズが 100 KB を超えないようにしてください。

* **_エラー_** 解決されない限り、ジャーニー/キャンペーンのテストやアクティブ化はできません。例えば、次のエラーなどです。

   * `The subject line is missing`：メールの件名は必須です。

   * `The email version of the message is empty`：このエラーは、メールコンテンツが設定されていない場合に表示されます。
