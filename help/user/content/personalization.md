---
title: コンテンツのパーソナライゼーション
description: Journey Optimizer B2B editionでアカウント、ユーザー、システムトークンを使用して B2B メールをパーソナライズします。 パーソナライゼーションエディターと構文の使用方法を説明します。
feature: Personalization, Content Design Tools, Email Authoring
topic: Personalization
role: User, Developer
level: Intermediate
keywords: 式, エディター, 開始, パーソナライゼーション
exl-id: 60bf2e06-8d6e-4cc4-8aff-5c5ca11f05ab
source-git-commit: 10e02b821609c48b82ea0248501daa60de6daa12
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 1%

---

# コンテンツのパーソナライゼーション {#add-personalization}

>[!CONTEXTUALHELP]
>id="aj-b2b_personalization"
>title="コンテンツエクスペリエンスのパーソナライズ"
>abstract="**Adobe Journey Optimizer B2B edition** を使用すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメッセージを作成できます。 名前、業界、役職などの情報を指定できます。"

パーソナライゼーション機能を使用すると、受信者に関するデータと情報を活用して、特定の受信者に合わせてメールメッセージを作成できます [!DNL Adobe Journey Optimizer B2B Edition] 名前、業界、役職などの情報を指定できます。

_パーソナライゼーションエディター_ を使用すると、すべてのデータを選択、整理、カスタマイズおよび検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。 ヘルパー関数などの様々なツールを使用して、メッセージをカスタマイズします。 エディターでは、_ハンドルバー_ に基づいたインラインパーソナライゼーション構文を使用します。式は、コンテンツを二重の中括弧 `{{}}` で囲んで構築されます。

Journey Optimizer B2B editionは、メッセージの処理時に、式をAdobe Experience Platform データセットとローカルシステム値に含まれるデータで置き換えます。 例えば、`Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}` は動的に `Hello John Doe` になります。

この構文を使用すると、メールの件名行、メッセージの本文、送信者情報など、複数のフィールドをまたいでメッセージをパーソナライズできます。

## Personalizationトークン

[!DNL Journey Optimizer B2B Edition] では、パーソナライゼーショントークンを使用して動的メールコンテンツを作成できます。

* **アカウントトークン** – これらのトークンは、_アカウント名_、_業界_、_従業員数_ などのアカウント属性に基づいています。 これらのトークンを使用して、Adobe Experience Platformで定義される **_XDM ビジネスアカウントの詳細_** スキーマによって管理される属性データを入力します。

* **人物トークン** – これらのトークンは、_名_、_役職_、_会社名_ などのビジネスユーザー属性に基づいています。 これらのトークンを使用して、Adobe Experience Platformで定義される **_XDM ビジネスユーザーの詳細_** スキーマによって管理される属性データを入力します。

* **システムトークン** – これらのトークンは、_日付_、_時間_、_購読解除リンク_ など、システムフィールドの値に基づいています。

* **マイトークン** （ジャーニー用に定義された場合） – メールが存在するジャーニー用に定義された [ カスタムトークン ](./personalization-my-tokens.md)。

>[!NOTE]
>
>XDM スキーマについて詳しくは、[Adobe Experience Platform データモデル（XDM）ドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home){target="_blank"} を参照してください。

## パーソナライゼーションエディター

パーソナライゼーションエディターは、メールコンテンツでパーソナライゼーションを定義する必要があるすべてのコンテキストで使用できます。 エディターでは、すべてのデータを選択、整理、カスタマイズおよび検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。

_パーソナライゼーションを追加_ （![ パーソナライゼーションアイコンを追加 ](../../assets/do-not-localize/icon-personalization-field.svg)）アイコンをクリックして、任意のフィールドまたはコンテンツコンポーネントでパーソナライゼーションを追加します。

![Personalization エディター ](./assets/personalization-editor.png){width="800" zoomable="yes"}

>[!NOTE]
>
>パーソナライゼーションエディターに関する以下の情報は、[!DNL Journey Optimizer B2B Edition] シンプルなアーキテクチャ [ でプロビジョニングされた ](../simplified-architecture.md) 環境で使用できる変更を反映しています。

### トークンおよびヘルパー関数

パーソナライゼーショントークンまたはヘルパー関数を使用するには、左側のナビゲーションパネルでパーソナライゼーショントークンまたはヘルパー関数を見つけ、「**+**」をクリックして式に追加します。

_その他メニュー_ （**...**）アイコン（_追加_ （**+**）アイコンの横）をクリックすると、各属性の詳細が表示され、使用頻度の高い属性を _お気に入り_ に追加できます。 お気に入りに追加した属性には、エディターの左側のナビゲーションにある **[!UICONTROL お気に入り]** メニューからアクセスできます。

![Personalization エディター – トークンの詳細メニュー ](./assets/personalization-editor-token-more-menu.png){width="800" zoomable="yes"}

<!-- >>[!NOTE]
>
>By default, the attributes list shows only populated attributes. To display all attributes, click the _Settings_ icon above the search field and toggle off the **[!UICONTROL Show only populated attributes]** option.
-->
また、文字列タイプのプロファイル属性が空の場合に表示されるデフォルトの代替テキスト文字列を定義することもできます。 属性の _詳細メニュー_ （**...**）アイコンをクリックし、「**[!UICONTROL 代替テキストで挿入]**」を選択します。 プロファイルの属性の値が空の場合に表示するテキストを入力し、[**[!UICONTROL 追加]**] をクリックします。

式は、コンテンツに挿入する前に検証することをお勧めします。 エディターの下部にある「**[!UICONTROL 検証]**」をクリックして構文を確認し、エラーがないことを確認します。

![Personalization エディターがコードを検証しました ](./assets/personalization-editor-validated.png){width="500"}

式が完成し、エラーがなくなったら、「**[!UICONTROL 保存]**」をクリックします。

### カスタムデータセット

[!BADGE Beta]{type=Informative tooltip="Beta機能"}

電子メールのパーソナライゼーションにリレーショナルスキーマを使用できます。 カスタムオブジェクトは _リレーショナルスキーマ_ 内で定義され、製品管理者は [ で ](../admin/xdm-field-management.md#relational-schemas) リレーショナルスキーマフィールドを設定 [!DNL Journey Optimizer B2B Edition] することができます。 これらのフィールドには、パーソナライゼーションエディターでアクセスできます。 人物またはアカウントと 1 対多（1:M）の関係を持つカスタムオブジェクトのみを使用できます。

>[!IMPORTANT]
>
>スクリプト化されたパーソナライゼーションにカスタムオブジェクトを使用する前に、[Handlebars テンプレート言語 ](https://handlebarsjs.com/guide/)、[ パーソナライゼーション構文 ](./personalization-syntax.md)、および組み込みの [ ヘルパー関数 ](./personalization-helper-functions.md) を確認して理解する必要があります。

カスタムオブジェクトを使用してパーソナライゼーションを定義すると、**[!UICONTROL Personalization トークン（ユーザー/リード、アカウント、システムおよびマイトークン]** と **[!UICONTROL カスタムオブジェクト]** （リレーショナルスキーマ）にわたって、スクリプトでアクセス可能なオブジェクトのすべての変数にアクセスできます。 カスタムオブジェクトを選択した状態で、カスタムオブジェクトフォルダーをクリックするとフィールドを表示できます。 式に追加するフィールドごとに「**+**」をクリックします。

![Personalization エディター – モデルベースのクラス – カスタム オブジェクト フィールドを追加 ](./assets/personalization-editor-custom-object-fields.png){width="700" zoomable="yes"}
