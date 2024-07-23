---
title: SMS オーサリング
description: 顧客のモバイルデバイスにテキストメッセージ（SMS）を送信する方法、および SMS エディターでテキスト形式のメッセージをパーソナライズおよびプレビューする方法について説明します。
feature: SMS Authoring, Content
exl-id: bd648253-74de-4083-a37a-ab7ceaea2746
source-git-commit: e0d9359560f31b3e66f593426c66e64d31044d54
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 0%

---

# SMS オーサリング

Adobe Journey Optimizer B2B Edition を使用すると、モバイルデバイスの顧客にテキストメッセージ（SMS）を送信できます。 SMS エディターで、テキスト形式のメッセージの作成、パーソナライズおよびプレビューを行うことができます。

## SMS 設定

Adobe Journey Optimizer B2B Edition は、SMS サービスプロバイダー（または SMS ゲートウェイプロバイダー）を通じてテキストメッセージを送信します。 SMS メッセージを作成する前に、管理者設定からサービスプロバイダーを設定します。

### SMS ゲートウェイサービスプロバイダー

Adobe Journey Optimizer B2B Edition は現在、独立してテキストメッセージサービスを提供するサードパーティプロバイダーと統合されています。 テキストメッセージのサポートされているプロバイダーは、Sinch、Twilio および Infobip です。

Adobe Journey Optimizer B2B Edition で SMS チャネルを設定する前に、これらのプロバイダーのいずれかでアカウントを作成して、API トークンとサービス ID を取得する必要があります。 これらの資格情報は、Adobe Journey Optimizer B2B Edition と該当するプロバイダーとの接続を設定するために必要です。

>[!IMPORTANT]
>
>テキストメッセージサービスの使用には、該当するプロバイダーによる追加の利用条件が適用されます。 サードパーティのソリューションとして、Sinch、Twilio、Infobip は、Adobe Journey Optimizer B2B Edition のユーザーが統合を通じて利用できます。 Adobeは、サードパーティの製品を管理しておらず、責任も負いません。 テキストメッセージサービス（SMS）に関する問題やサポートのリクエストについては、プロバイダーにお問い合わせください。

### 既存の SMS API 設定の検証

>[!NOTE]
>
>説明された設定は、SMS 管理者権限を持つユーザーのみがアクセスできます。

左側のナビゲーションで、「**[!UICONTROL 管理者]**」セクションを展開し、「**[!UICONTROL 設定]**」をクリックします。

![AMA API 認証情報の設定へのアクセス ](./assets/config-sms-api.png){width="800" zoomable="yes"}

このページには、お使いのインスタンスで使用可能な API 設定が一覧表示されます。 表示される API 資格情報は、SMS サービスプロバイダーまたは作成者がフィルタリングできます。

![ フィルターアイコンをクリックして、API 資格情報のリストをフィルタリング ](./assets/config-sms-api-filter.png){width="500"}

### SMS サービスプロバイダーの新しい API 資格情報の作成

>[!BEGINTABS]

>[!TAB  シンチ ]

_Adobe Journey Optimizer B2B Edition で Sinch を SMS プロバイダーとして設定するには：_

1. 左側のナビゲーションで、「**[!UICONTROL 管理者]**」セクションを展開し、「**[!UICONTROL 設定]**」をクリックします。

1. **[!UICONTROL API 資格情報]** リストの右上にある「_[!UICONTROL 新しい API 資格情報の作成]_ をクリックします。

1. SMS API 資格情報を設定します。

   ![Sinch SMS API 資格情報の設定 ](./assets/config-sms-api-sinch.png){width="500"}

   * **[!UICONTROL SMS ベンダー]** - SMS プロバイダーとして「`Sinch`」を選択します。

   * **[!UICONTROL 名前]** - API 資格情報の名前を入力します。

   * **[!UICONTROL サービス ID]** および **[!UICONTROL API トークン]** - Sinch アカウントから API ページにアクセスします（資格情報は「SMS」タブで確認できます）。

   Sinch アカウントでこの情報を見つける方法について詳しくは、[Sinch 開発者向けドキュメント ](https://developers.sinch.com/docs/sms/getting-started/#2-get-credentials) を参照してください。

1. API 資格情報の設定の詳細が完了したら、「**[!UICONTROL 送信]**」をクリックします。

>[!TAB  ツイリオ ]

_Adobe Journey Optimizer B2B Edition で Twilio を SMS プロバイダーとして設定するには：_

1. 左側のナビゲーションで、「**[!UICONTROL 管理者]**」セクションを展開し、「**[!UICONTROL 設定]**」をクリックします。

1. **[!UICONTROL API 資格情報]** リストの右上にある「_[!UICONTROL 新しい API 資格情報の作成]_ をクリックします。

1. SMS API 資格情報を設定します。

   ![Twilio SMS API 資格情報の設定 ](./assets/config-sms-api-twilio.png){width="500"}

   * **[!UICONTROL SMS ベンダー]** - SMS プロバイダーとして「`Twilio`」を選択します。

   * **[!UICONTROL 名前]** - API 資格情報定義の名前を入力します。

   * **[!UICONTROL アカウント SID]** および **[!UICONTROL 認証トークン]** - Twilio コンソールダッシュボードページの _アカウント情報_ パネルにアクセスして、資格情報を検索します。

   Twilio アカウントでこの情報を見つける方法については、[Twilio ヘルプセンター ](https://help.twilio.com/articles/14726256820123-What-is-a-Twilio-Account-SID-and-where-can-I-find-it-) を参照してください。

1. API 資格情報の設定の詳細が完了したら、ページの右上にある「**[!UICONTROL 送信]**」をクリックします。

>[!TAB Infobip]

_Adobe Journey Optimizer B2B Edition で Infobip を SMS プロバイダーとして設定するには：_

1. 左側のナビゲーションで、「**[!UICONTROL 管理者]**」セクションを展開し、「**[!UICONTROL 設定]**」をクリックします。

1. **[!UICONTROL API 資格情報]** リストの右上にある「_[!UICONTROL 新しい API 資格情報の作成]_ をクリックします。

1. SMS API 資格情報を設定します。

   ![Infobip SMS API 資格情報の設定 ](./assets/config-sms-api-infobip.png){width="500"}

   * **[!UICONTROL SMS ベンダー]** - SMS プロバイダーとして「`Infobip`」を選択します。

   * **[!UICONTROL 名前]** - API 資格情報定義の名前を入力します。

   * **[!UICONTROL API ベース URL]** および **[!UICONTROL API キー]** - Infobip アカウントの web インターフェイスのホームページまたは API キー管理ページにアクセスして、資格情報を検索します。

   お使いの Infobip アカウントでこの情報を見つける方法の詳細については、[Infobip のドキュメント ](https://www.infobip.com/docs/api/_blank) を参照してください。

1. API 資格情報の設定の詳細が完了したら、ページの右上にある「**[!UICONTROL 送信]**」をクリックします。

>[!ENDTABS]

「_[!UICONTROL 送信]_」をクリックすると、資格情報が直ちに検証されて保存され、_[!UICONTROL API 資格情報]_ リストページにリダイレクトされます。 送信された資格情報が無効な場合は、リストページにエラーメッセージが表示されます。 この場合、設定をキャンセルするか、設定を更新して再度送信するかを選択できます。

## アカウントジャーニーへの SMS アクションの追加

「_[!UICONTROL 特定のアクションを実行]_」ノードを追加して以下の操作を実行すると、アカウントジャーニーでテキストメッセージ配信を設定できます。

1. _[!UICONTROL アクションオン]_ ターゲットで、「**[!UICONTROL ユーザー]**」を選択します。

1. _[!UICONTROL ユーザーに対するアクション]_ で、「**[!UICONTROL SMS を送信]**」を選択します。

   ![ アクションの実行 – SMS の送信 ](assets/journey-node-send-sms.png){width="800" zoomable="yes"}

1. _[!UICONTROL アクションの実行]_ パネルの下部にある「**[!UICONTROL SMS の作成]**」をクリックします。

1. ダイアログで、メールの一意の **[!UICONTROL 名前]** と **[!UICONTROL 件名]** を入力します。

   ![ 新しい SMS を作成ダイアログ ](assets/create-new-sms.png){width="500"}

## SMS メッセージの作成

>[!IMPORTANT]
>
>**SMS 同意管理**<br/>
><br/>
>業界標準と規制に従って、すべての SMS マーケティングメッセージには、受信者が簡単に登録解除できる方法を含める必要があります。 SMS 受信者は、オプトインおよびオプトアウトのキーワードで返信ですることでこれを実行できます。 すべての標準のオプトインおよびオプトアウトのキーワードがサポートされ、適用されます。 また、SMS サービスプロバイダーアカウントに設定されたカスタムキーワードもサポートされ、適用されます。

1. 送信するテキストを「**[!UICONTROL メッセージ]**」フィールドに入力します。

   160 文字ごとに 1 つの SMS メッセージと見なされる最大 1,600 文字のメッセージを作成できます。

1. **テキストメッセージをパーソナライズ**。

   テキストメッセージの作成時には、いつでもテキストメッセージボックスの右側にある _パーソナライズ_ アイコンをクリックします。

   ![ パーソナライズ アイコンをクリックして、メッセージにトークンを追加します ](./assets/sms-message-personalize-icon.png){width="800" zoomable="yes"}

   表示されたページから、Adobe Marketo Engage リードおよびシステムトークンにアクセスできます。 標準トークンとカスタムトークンの両方が含まれています。 検索バーを使用して必要なトークンを探すか、フォルダーツリーを移動して任意のリード/システムトークンを見つけて選択します。

   トークンを追加するメッセージ内の場所にカーソルを置きます。 トークンの横にあるプラス（**+**）記号をクリックして、トークンを追加します。 フォールバック（リードでフィールドが使用できない場合に表示されるデフォルト）を含むトークンを追加したい場合は、省略記号（**...**）をクリックし、「**[!UICONTROL フォールバックテキストで挿入]** を選択します。

   ![ 省略記号をクリックして、トークンのフォールバックを使用します ](./assets/sms-message-personalize-ellipsis-fallback.png){width="700" zoomable="yes"}

   _[!UICONTROL フォールバック値を入力]_ ダイアログで、フォールバックとして表示されるテキストを入力して、「**[!UICONTROL 追加]**」をクリックします。

   ![ トークンの代替テキストを入力します ](./assets/sms-message-personalize-fallback-text.png){width="400"}

   パーソナライゼーショントークンが配置されたら、「**[!UICONTROL 保存]**」をクリックして変更を保存し、メインの SMS オーサリングワークスペースに戻ります。 必要に応じて、トークンを使用してメッセージの編集を続行できます。

<!-- 1. **Add URLs to text message**.

   After defining your content, you can add URLs to your message by clicking the _Link_ icon.
   
   You can add two types of URLs: 

   External URLs - This is ANY external URL that can be directly typed into/ pasted into the input text box
   Adobe Marketo Engage Design Studio Landing Pages - Selecting this option, you will see a 'Landing Page picker' from which you can select any of the listed approved Landing Pages from Marketo Engage

   You can choose to 'shorten' either of these URLs by selecting the checkbox
   Note that the URL shortening function, uses the Marketo subdomain for shortening
   The shortened URL appears as a read-only field within the modal
   You can optionally track clicks on the URL
   You can also choose to include 'mkt_tok' for tracking activity against a user
   Click on Add to save changes & add the chosen URL to the SMS message
-->

## SMS プロパティの設定

1. 「_[!UICONTROL SMS プロパティ]_」セクションで、メッセージの **[!UICONTROL 名前]** （必須、100 個の cha\racter 最大）と **[!UICONTROL 説明]** （オプション、最大 300 文字）を入力します。

   Alpha、数字、特殊文字を使用できます。 次の予約文字は使用できません **許可されていません**:`\`、`/`、`:`、`*`、`?`、`"`、`<`、`>` および `|`。

1. **[!UICONTROL SMS タイプ]** を選択します。

   * ユーザーの同意が必要なプロモーションテキストメッセージには、`Marketing` を使用します。
   * 注文確認、パスワードリセット通知、配信情報など、非商用メッセージに `Transactional` を使用します。

1. **[!UICONTROL SMS 設定]** については、事前定義済みの API 設定の 1 つを選択します。

   この設定は、メッセージの配信に使用する SMS ゲートウェイ サービス プロバイダーおよびアカウントを決定します。

1. コミュニケーションに使用する **[!UICONTROL 送信者番号]**&#x200B;を入力します。

   ![ アクションの実行 – SMS の送信 ](./assets/sms-properties.png){width="700" zoomable="yes"}

   受信者番号は、常にMarketo Engageの `Lead.MainPhone` フィールドにマッピングされます。

<!-- ## Preview the text message content

When your message content is defined, you can use test profiles to preview its content. If you inserted personalized content, you can check how this content is displayed in the message, using test profile data.

1. Click **[!UICONTROL Simulate Content]** at the top of the SMS authoring workspace.

1. From the _[!UICONTROL Simulate Content]_ page, click **[!UICONTROL Add People]**.

1. Use the # page to manage the leads used for your test profile.

   In the displayed list, you can search for and add any of the leads (up to 10 leads at a time) from the Marketo Engage lead database.

   To search, enter the whole email address and click enter. The corresponding lead profile shows up for selection.

   The preview updated to the personalization fields for the selected profile.

   All the added leads appear on the left rail of the 'Simulate Content' page

   You can manage this list by adding more people and deleting individual leads from the profile listing (it does not remove them from the database).

1. Simulate content for a lead.

   Select any of the leads listed on the left rail of the Simulate Content page and the SMS preview on the page updates for the corresponding lead.

   You can also select a lead from the 'drop-down' box above the preview space and the SMS preview on the page updates for the corresponding lead

1. To exit the _[!UICONTROL Simulate Content]_ page and return back to the SMS authoring workspace, click Close. -->
