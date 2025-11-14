---
title: コンテンツのパーソナライゼーション
description: Journey Optimizer B2B editionでアカウント、ユーザー、システムトークンを使用して B2B メールをパーソナライズします。 パーソナライゼーションエディターと構文の使用方法を説明します。
feature: Personalization, Content Design Tools, Email Authoring
topic: Personalization
role: User, Developer
level: Intermediate
keywords: 式, エディター, 開始, パーソナライゼーション
source-git-commit: fee5bddcce11b3035da6ab93b18bcc7006b4b554
workflow-type: tm+mt
source-wordcount: '610'
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

* **マイトークン** （ジャーニー用に定義された場合） – メールが存在するジャーニー用に定義された [&#x200B; カスタムトークン &#x200B;](./personalization-my-tokens.md)。

>[!NOTE]
>
>XDM スキーマについて詳しくは、[Adobe Experience Platform データモデル（XDM）ドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home){target="_blank"} を参照してください。

## パーソナライゼーションエディター

パーソナライゼーションエディターは、メールコンテンツでパーソナライゼーションを定義する必要があるすべてのコンテキストで使用できます。 エディターでは、すべてのデータを選択、整理、カスタマイズおよび検証して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成できます。

>[!NOTE]
>
>パーソナライゼーションエディターの以下の情報は、[&#x200B; シンプルなアーキテクチャ &#x200B;](../simplified-architecture.md) でプロビジョニングされたJourney Optimizer B2B edition環境で使用できる変更内容を反映しています。

_パーソナライゼーションを追加_ （![&#x200B; パーソナライゼーションアイコンを追加 &#x200B;](../../assets/do-not-localize/icon-personalization-field.svg)）アイコンをクリックして、任意のフィールドまたはコンテンツコンポーネントでパーソナライゼーションを追加します。

![Personalization エディター &#x200B;](./assets/personalization-editor.png){width="800" zoomable="yes"}

パーソナライゼーショントークンまたはヘルパー関数を使用するには、左側のナビゲーションパネルでパーソナライゼーショントークンまたはヘルパー関数を見つけ、「**+**」をクリックして式に追加します。

_その他メニュー_ （**...**）アイコン（_追加_ （**+**）アイコンの横）をクリックすると、各属性の詳細が表示され、使用頻度の高い属性を _お気に入り_ に追加できます。 お気に入りに追加した属性には、エディターの左側のナビゲーションにある **[!UICONTROL お気に入り]** メニューからアクセスできます。

![Personalization エディター – トークンの詳細メニュー &#x200B;](./assets/personalization-editor-token-more-menu.png){width="800" zoomable="yes"}

<!-- >>[!NOTE]
>
>By default, the attributes list shows only populated attributes. To display all attributes, click the _Settings_ icon above the search field and toggle off the **[!UICONTROL Show only populated attributes]** option.
-->
また、文字列タイプのプロファイル属性が空の場合に表示されるデフォルトの代替テキスト文字列を定義することもできます。 属性の _詳細メニュー_ （**...**）アイコンをクリックし、「**[!UICONTROL 代替テキストで挿入]**」を選択します。 プロファイルの属性の値が空の場合に表示するテキストを入力し、[**[!UICONTROL 追加]**] をクリックします。

式は、コンテンツに挿入する前に検証することをお勧めします。 エディターの下部にある「**[!UICONTROL 検証]**」をクリックして構文を確認し、エラーがないことを確認します。

![Personalization エディターがコードを検証しました &#x200B;](./assets/personalization-editor-validated.png){width="500"}

式が完成し、エラーがなくなったら、「**[!UICONTROL 保存]**」をクリックします。

<!-- ## Personalization experimentation {#playground}

**[!DNL Adobe Journey Optimizer]** includes an interactive tool designed to help you learn and experiment with personalization capabilities.

This playground provides a simulated environment to write and test personalization code using sample data without requiring live datasets. You can leverage predefined code samples, edit dummy profile payloads, and preview the output of your personalization code in real-time. 

![personalization playground](assets/playground.png)

➡️ [Access the personalization playground](https://experienceleague.adobe.com/ja/apps/journey-optimizer/ajo-personalization){target="_blank"} 

## How-to videos{#video-perso}

Learn how to use contextual event information from a journey to personalize a message.

>[!VIDEO](https://video.tv.adobe.com/v/334165?quality=12)

Learn how to add profile-based personalization to a message and how to use audience membership as a pre-condition to a personalization block.

>[!VIDEO](https://video.tv.adobe.com/v/334078?quality=12)

Learn how to leverage the personalization editor playground to write and test personalization code using sample data.

>[!VIDEO](https://video.tv.adobe.com/v/3457868?quality=12) -->