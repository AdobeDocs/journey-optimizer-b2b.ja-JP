---
title: SMS オーサリング
description: パーソナライゼーション、リンク、同意管理を使用して、アカウントジャーニー用のSMS メッセージを作成する – Journey Optimizer B2B editionでコンテンツをプレビューし、配信設定を行います。
feature: SMS Authoring, Content, Channels
role: User
exl-id: bd648253-74de-4083-a37a-ab7ceaea2746
autotag-review: '2026-05-27T16:18:50.732Z'
TQID: 'https://experienceleague.adobe.com/MEoL8Fm-drFPWzFZofvS7hMRTTpmRyThVxBUHUsS6Qs'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
subfeature_v2:
  - id: a22f05f6-0fcf-40c0-a70e-e13a3db185f7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: cad51180-f8ce-4cb7-aefc-437847b5d6d6
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 3ca6097c65a5a4c817239e0aa0979d1cc1a43836
workflow-type: tm+mt
source-wordcount: 1251
ht-degree: 4%

---

# SMS オーサリング

Adobe Journey Optimizer B2B editionを使用すると、モバイルデバイスを使用しているお客様にテキストメッセージ（SMS）を送信できます。 SMS エディターで、テキスト形式のメッセージの作成、パーソナライズおよびプレビューを行うことができます。

アカウントジャーニーのSMS メッセージを作成する前に、_[!UICONTROL 管理者]_&#x200B;設定から[SMS サービスプロバイダー](../admin/configure-channels-sms.md)が設定されていることを確認してください。

>[!IMPORTANT]
>
>**SMS同意管理**<br/>
>
>業界標準や規制に従って、すべてのSMS マーケティングメッセージには、受信者が簡単に購読を解除できる方法が含まれている必要があります。 SMS 受信者は、オプトインおよびオプトアウトのキーワードで返信ですることでこれを実行できます。 あらゆる標準的なオプトインキーワードとオプトアウトキーワードに対応しています。 さらに、SMS サービスプロバイダーアカウントに設定されたカスタムキーワードは、サポートされ、尊重されます。 配信時にSMSの同意設定がどのように評価されるかについて詳しくは、[同意設定](./channels-consent-preferences.md)を参照してください。

## アカウントジャーニーでのSMS アクションの追加 {#add-action}

_[!UICONTROL アクションを実行]_ ノードを追加し、次の操作を行うと、アカウントジャーニーでテキストメッセージ配信を設定できます。

1. ターゲット _の_ アクションで、**[!UICONTROL 人物]**&#x200B;を選択します。

1. _[!UICONTROL 人物に対するアクション]_&#x200B;で、**[!UICONTROL SMSを送信]**&#x200B;を選択します。

   ![&#x200B; アクションを実行 – SMSを送信](assets/journey-node-send-sms.png){width="800" zoomable="yes"}

1. _[!UICONTROL アクションを実行]_ パネルの下部にある「**[!UICONTROL SMSを作成]**」をクリックします。

1. ダイアログで、SMS メッセージの一意の&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

   ![新しいSMS ダイアログの作成](assets/create-new-sms.png){width="400"}

1. 「**[!UICONTROL 作成]**」をクリックします。

   _ジャーニーマップ_&#x200B;が開き、メッセージを作成し、メッセージを送信するためのSMS プロパティを設定できます。

### SMS メッセージの作成 {#create-message}

**[!UICONTROL メッセージ]** フィールドに送信するテキストを入力します。

最大1600文字のメッセージを作成でき、160文字ごとに1つのSMS メッセージと見なされます。

![SMS メッセージの作成](./assets/sms-message-compose.png){width="800" zoomable="yes"}

#### テキストメッセージのパーソナライズ {#personalize}

1. パーソナライゼーショントークンを追加するメッセージ内の場所にカーソルを置きます。

1. テキストメッセージボックスの右側にある「_パーソナライズ_」アイコン（![&#x200B; パーソナライズアイコン &#x200B;](../assets/do-not-localize/icon-personalize.svg)）をクリックします。

   このダイアログでは、アカウントトークン、人物トークン、システムトークンにアクセスできます。 標準トークンとカスタムトークンの両方が含まれています。 _検索_ バーを使用して必要なトークンを検索するか、フォルダーツリー内を移動してトークンのいずれかを検索して選択できます。

1. トークンの横にあるプラス（**+**）記号をクリックして、トークンを追加します。

   フォールバック付きのトークンを追加する場合は、_詳細_ アイコン （**...**）をクリックし、「**[!UICONTROL フォールバックテキスト付きの挿入]**」を選択します。 フォールバックは、そのフィールドがリードに使用できない場合に表示されるデフォルトです。

   ![省略記号をクリックして、トークンのフォールバックを使用します](./assets/sms-message-personalize-ellipsis-fallback.png){width="700" zoomable="yes"}

1. _[!UICONTROL フォールバック値を入力]_ ダイアログで、フォールバックとして表示されるテキストを入力し、**[!UICONTROL 追加]**&#x200B;をクリックします。

   ![&#x200B; トークンのフォールバックテキストを入力](./assets/sms-message-personalize-fallback-text.png){width="450"}

1. パーソナライゼーショントークンを配置したら、**[!UICONTROL 保存]**&#x200B;をクリックして変更を保存し、メインのSMS オーサリングワークスペースに戻ります。

   必要に応じて、トークンを使用してメッセージを引き続き編集できます。

#### テキストメッセージへのリンク（URL）の追加 {#add-links}

1. メッセージテキストを入力したら、テキストメッセージボックスの右側にある&#x200B;_リンク_ アイコン（![&#x200B; リンクアイコン &#x200B;](../assets/do-not-localize/icon-link.svg)）をクリックします。

1. ダイアログで、リンクするURLのタイプを選択します。

   * **[!UICONTROL ランディングページ]** – 公開されているランディングページのいずれかを選択するには、このオプションを選択します。

   * **[!UICONTROL 外部URL]** – 外部URLをリンクするには、このオプションを選択します。 リンクの&#x200B;**[!UICONTROL URL]**&#x200B;を入力してください。

     ![SMS メッセージのリンクを追加ダイアログ &#x200B;](./assets/sms-add-link-dialog.png){width="470"}

1. （オプション）トラッキングオプションを設定します。

   * **[!UICONTROL リンクトラッキングを有効にする]** – このチェックボックスを選択してトラッキングを有効にします。これには、_URLの短縮_&#x200B;が必要です。 短縮URL形式のサンプルが表示されます。 実際のURLは、SMSが受信者に送信されたときに作成されます。

   * **[!UICONTROL リードトラッキングを有効にする]** - ユーザーに対するアクティビティを追跡するには、このチェックボックスを選択します。</br>

<!--
      >[!NOTE] 
      >
      >When you allow tracking but disable _[!UICONTROL Enable Lead Tracking]_, the destination URL does not include the `mkt_tok` query string parameter after redirect. This parameter is used by Marketo Engage landing pages and Munchkin to ensure that tracking of person activities (such as when a person unsubscribes from an email). Do not disable this option unless the parameter is causing issues on your website.<br/>
      >For more information about using Munchkin tracking codes on your website, refer to the [Marketo Engage documentation](https://experienceleague.adobe.com/ja/docs/marketo/using/product-docs/administration/additional-integrations/add-munchkin-tracking-code-to-your-website){target="_blank"}.

-->

1. リンクオプションが完了したら、**[!UICONTROL 追加]**&#x200B;をクリックして、SMS メッセージにURL リンクを追加します。

### SMS プロパティの設定 {#sms-properties}

1. 「_[!UICONTROL SMS プロパティ]_」セクションに、メッセージの&#x200B;**[!UICONTROL 名前]** （必須、100文字の最大値）と&#x200B;**[!UICONTROL 説明]** （オプション、300文字の最大値）を入力します。

   これらのフィールドには、Alpha、数値、特殊文字を使用できます。 次の予約済み文字は&#x200B;**許可されていません**: `\`、`/`、`:`、`*`、`?`、`"`、`<`、`>`および`|`。

1. **[!UICONTROL SMSの種類]**&#x200B;を選択してください：

   * プロモーションテキストメッセージには`Marketing`を使用します。これにはユーザーの同意が必要です。
   * 注文確認、パスワードリセット通知、配信情報など、非商用メッセージには`Transactional`を使用します。

1. **[!UICONTROL SMS設定]**&#x200B;の場合は、事前定義済みの[SMS API設定](../admin/configure-channels-sms.md#create-new-api-credentials-for-an-sms-service-provider)のいずれかを選択します。

   この設定は、メッセージの配信に使用するSMS ゲートウェイサービスプロバイダーとアカウントを決定します。

1. 通信に使用する&#x200B;**[!UICONTROL 送信者番号]**&#x200B;を入力します。

   ![SMS メッセージのプロパティ &#x200B;](./assets/sms-properties.png){width="500" zoomable="yes"}

   受信者番号は、常にExperience Platformの`profile.mobilePhone.number` フィールドにマッピングされます。

### テキストメッセージのコンテンツをシミュレート {#preview-test}

>[!CONTEXTUALHELP]
>id="ajo-b2b_sms_preview_simulate"
>title="コンテンツのレンダリング方法の確認"
>abstract="コンテンツを定義したら、プレビューして、使用しているチャネルのレンダリングを確認できます。"

メッセージコンテンツを定義したら、テストプロファイルを使用して、そのコンテンツをシミュレート（プレビュー）できます。 パーソナライズされたコンテンツを挿入した場合は、テストプロファイルデータを使用して、このコンテンツがメッセージにどのように表示されるかを確認できます。

>[!IMPORTANT]
>
>テキストメッセージのシミュレーションを実行する前に、SMS メッセージを必ず保存してください。

1. SMS オーサリングワークスペースの上部にある「**[!UICONTROL コンテンツをシミュレート]**」をクリックします。

1. _[!UICONTROL コンテンツをシミュレート]_ ページで、**[!UICONTROL ユーザーを追加]**&#x200B;をクリックします。

1. _コンテンツをシミュレート_ ページを使用して、テストプロファイルに使用するリードを管理します。

   表示されたリストで、任意のリードを検索して追加できます（一度に最大10件のリード）。

   検索するには、電子メールアドレス全体を入力し、_Enter_&#x200B;を押します。 対応するリードプロファイルが選択用に表示されます。

   プレビューは、選択したプロファイルのパーソナライゼーションフィールドに更新されます。

   追加されたリードはすべて左側に表示されます。

   このリストを管理するには、さらにユーザーを追加し、プロファイルリストから個々のリードを削除します（データベースから削除されません）。

1. 選択したリードのコンテンツをシミュレート

   左側にリストされているリードのいずれかを選択します。 ページ上のSMS プレビューが、選択したリードを更新します。

   プレビュースペースの上にあるセレクターからリードを選択して、対応するリードのページ上のSMS プレビューを更新することもできます。

1. _[!UICONTROL コンテンツのシミュレート]_ ページを終了してSMS オーサリングワークスペースに戻るには、右上の&#x200B;**[!UICONTROL 閉じる]**&#x200B;をクリックします。

## SMS同意管理 {#consent-management}

受信者に、ブランドからのコミュニケーションの受信を登録解除する機能を提供し、この選択を尊重することが法的要件です。 これらの規制を遵守しないと、企業に法的リスクが生じます。 この機能は、受信者に未承諾のコミュニケーションを送信するのを避けるのに役立ちます。 これにより、迷惑メールとしてマークしたり、レピュテーションを損なったりすることを防ぐことができます。

このオプションを指定すると、SMS受信者はオプトインキーワードとオプトアウトキーワードで返信できます。 標準のオプトインキーワードとオプトアウトキーワードはすべて、SMS サービスプロバイダーで設定されているカスタムキーワードと同様に、サポートおよび尊重されます。 購読解除すると、プロファイルは今後のマーケティングメッセージのオーディエンスから自動的に削除されます。

Journey Optimizer B2B editionでは、次のロジックを使用してSMS メッセージのオプトアウトを管理できます。

* デフォルトでは、リードが自社からのコミュニケーションの受信をオプトアウトした場合、対応するプロファイルは後続のSMS配信から除外されます

* このリードの同意は、様々なソース（AEPやSMS サービスプロバイダーなど）から取得され、Journey Optimizer B2B editionに同期されます。 現在、インスタンスレベルでは、リードごとに1つの同意状態のみがサポートされています（リード「John Doe」は、インスタンス内のすべてのプロモーション SMSに購読または購読解除されています）。 現在、ブランドレベル/個人サブスクリプションリストレベルの同意に対するダブルオプトインはサポートしていません。
