---
title: メールPersonalizationのカスタムトークン
description: 動的なメールパーソナライゼーション用のカスタムマイトークンを作成および管理する – Journey Optimizer B2B editionでアカウントジャーニーのテキスト変数と数変数を定義します。
feature: Personalization, Content, Email Authoring
role: User
exl-id: 05d4f446-6348-4555-9c46-316c2857f01d
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: bd3c685c-6c92-4a4a-becb-535cc25215de
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
autotag-review: '2026-03-30T22:21:17.156Z'
source-git-commit: 8fe8318d7e1c63cbaa2749fc3928eb0a12967bd9
workflow-type: tm+mt
source-wordcount: 605
ht-degree: 2%

---

# メールパーソナライゼーション用のカスタムトークン

コンテンツパーソナライゼーションでは、コンテンツアーティファクトが生成されたときに入力されるプレースホルダーまたは変数としてトークンを使用します。 標準のパーソナライズトークンは、メール、ランディングページ、フラグメント、テンプレートで利用できます。 また、アカウントジャーニーに固有の値を持つカスタムトークンのセットを定義することもできます。 このカスタムトークンのセットは&#x200B;_マイトークン_&#x200B;と呼ばれ、これらのカスタムトークンはすべて、[ ジャーニーメールのオーサリング ](./email-authoring.md#content-authoring---personalization)時にパーソナライゼーション用です。

アカウントジャーニーに固有の&#x200B;_マイトークン_&#x200B;に加えて、任意の標準（組み込み）トークンをメールのパーソナライゼーションに使用できます。

## 自分のトークンを管理 {#my-tokens}

_マイトークン_&#x200B;は、ドラフトステータスのアカウントジャーニーに対して作成または変更するカスタム変数です。 このカスタムトークンセットは、現在、テキストトークンと数値トークンの定義をサポートしています。

カスタムトークンをメールに追加すると、メールは`{{my.TokenName}}`と表示されます。 例えば、今後のウェビナーに関連するメールコンテンツを管理するために、`{{my.EventDate}}`または`{{my.WebinarSpeaker}}`個のトークンを作成できます。

_アカウントジャーニーのカスタムトークンにアクセスするには&#x200B;:_

1. ドラフトアカウントジャーニーを開きます。

1. 右上の&#x200B;**[!UICONTROL その他…]** メニューをクリックし、**[!UICONTROL マイトークン]**&#x200B;を選択します。

   ![右上の「詳細」をクリック](../journeys/assets/account-journey-draft-more-menu.png){width="450"}

   _マイトークン_ ページには、ジャーニーに定義されているすべてのカスタムトークンが一覧表示されます。

   ![自分のトークン ](./assets/my-tokens-list-page.png){width="700" zoomable="yes"}

### トークンの作成

1. _[!UICONTROL My Tokens]_ ページで、**[!UICONTROL Create]**&#x200B;をクリックし、定義するトークンタイプを選択します。

   * **[!UICONTROL テキスト]** – このタイプを使用して、基本的なテキスト文字列値を持つトークンを定義します。

   * **[!UICONTROL 数値]** – このタイプを使用して、数値を持つトークンを定義します。

1. ダイアログで、トークンの&#x200B;**[!UICONTROL Name]**&#x200B;と&#x200B;**[!UICONTROL Value]**&#x200B;を入力します。

   ![ テキストトークンの名前と値を入力](./assets/my-tokens-create-text-token-dialog.png){width="400"}

   トークン名にはスペースや特殊文字を使用できません。 `EventType`などの&#x200B;_キャメルケース_&#x200B;を使用して、簡単に識別できるマルチワード名を使用できます。

   _Number_ トークンを定義する場合、値には数字文字のみを含めることができます。 10進数を使用できます。

   ![番号トークンの名前と値を入力](./assets/my-tokens-create-number-token-dialog.png){width="400"}

1. 「**[!UICONTROL 追加]**」をクリックします。

### トークンの編集

アカウントジャーニーはドラフトステータスのままですが、定義済みのマイトークンのいずれかを編集できます。

1. _[!UICONTROL マイトークン]_ ページで、_詳細アクション_ アイコン （**...**）をクリックします トークン名の横にある「**[!UICONTROL 編集]**」を選択します。

   ![ トークンその他のアクションメニュー](./assets/my-tokens-more-actions.png){width="430"}

1. ダイアログで、ジャーニーの必要に応じて&#x200B;**[!UICONTROL Name]**&#x200B;と&#x200B;**[!UICONTROL Value]**&#x200B;を変更します。

   ![ トークンの名前と値を変更](./assets/my-tokens-edit-text-token-dialog.png){width="400"}

1. 「**[!UICONTROL 編集]**」をクリックします。

### トークンの削除

カスタムトークンは&#x200B;_マイトークン_ リストから削除できますが、現在ジャーニーのメールコンテンツで使用されていないことを確認する必要があります。

1. _[!UICONTROL マイトークン]_ ページで、_詳細アクション_ アイコン （**...**）をクリックします トークン名の横にある「**[!UICONTROL 削除]**」を選択します。

1. 確認ダイアログで、「**[!UICONTROL 削除]**」をクリックします。

## コンテンツでカスタムトークンを使用すると

アカウントジャーニーのメールコンテンツをオーサリングする場合、ビジュアルデザイン空間でパーソナライゼーションツールを使用する場合、_マイトークン_ リストのトークンのいずれかを使用できます。

1. テキストコンポーネントを選択し、ツールバーの「_パーソナライゼーションを追加_」（![ パーソナライゼーションを追加アイコン ](../../assets/do-not-localize/icon-personalization-field.svg)）アイコンをクリックします。

   ![ パーソナライゼーションを追加アイコンをクリック ](./assets/email-personalize-text.png){width="600"}

   この操作を実行すると、_Personalizationを編集_ ダイアログが開きます。 このダイアログには、アカウントジャーニーにカスタムトークンが定義されている場合、_[!UICONTROL Personalization トークン]_ ライブラリに&#x200B;_[!UICONTROL マイトークン]_ フォルダーが含まれます。

1. **[!UICONTROL My tokens]** フォルダーを展開し、**+**&#x200B;または&#x200B;**...**&#x200B;をクリックして、カスタムトークンのいずれかを空白スペースに追加します。

   必要に応じて、任意の静的テキストを追加できます。

   ![ マイトークンを使用してパーソナライズされたテキストを作成](./assets/personalization-edit-dialog-my-tokens.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。
