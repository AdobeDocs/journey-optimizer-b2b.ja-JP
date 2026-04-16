---
title: コンテンツ作成 – パーソナライゼーション
description: コンテンツオーサリングでのパーソナライゼーションの使用に関する節を再利用しました
source-git-commit: 944d2616fa21e7f8d2f8c439eaa2f5e529dacb84
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# コンテンツ作成 – パーソナライゼーション

Journey Optimizer B2B Editionでは、インラインのシンプルな構文を使用して、括弧`{{}}`で囲まれたパーソナライズされたコンテンツを使用して式を作成できます。 同じコンテンツまたはフィールドに複数の式を制限なく追加できます。

例えば、パーソナライゼーション式を`Hello {{lead.firstName}} {{lead.lastName}}`として追加できます。 コンテンツを処理する場合、Journey Optimizer B2B Editionは、エクスプレッションをExperience Platform データベースに含まれるデータに置き換えます。 最初の例は&#x200B;_Hello John Doe_&#x200B;です。

Journey Optimizer B2B Editionでのパーソナライゼーションツールの使用について詳しくは、[&#x200B; コンテンツパーソナライゼーション &#x200B;](../user/content/personalization.md)を参照してください。

>[!NOTE]
>
>Journey Optimizer B2B Editionは、メールのパーソナライゼーショントークンの&#x200B;_キャメルケース_&#x200B;構文に従って、他のAdobe Experience Platform アプリケーションと一致させ、一貫性のあるエクスペリエンスを実現します。 このトークン形式は、[Handlebars テンプレート言語](https://handlebarsjs.com/guide/#what-is-handlebars){target="_blank"}と完全に互換性があります。 この変更前に追加されたトークンは、自動的に更新されます。

次に、個人トークンとシステムトークンを使用してコンテンツをパーソナライズする手順の概要を示します。 これは、現在のJourney Optimizer B2B Edition リリースを反映しています。

1. テキストコンポーネントを選択し、ツールバーの「_パーソナライゼーションを追加_」（![&#x200B; パーソナライゼーションを追加アイコン &#x200B;](../assets/do-not-localize/icon-personalization-field.svg)）アイコンをクリックします。

   ![&#x200B; パーソナライズ アイコンをクリック &#x200B;](../assets/content-design-shared/visual-designer-personalize-icon.png){width="600"}

   この操作を実行すると、_Personalizationを編集_ ダイアログが開きます。

1. トークンの横にあるプラス（**+**）記号をクリックして、トークンを追加します。

   フォールバック付きのトークン（そのフィールドがリードに使用できない場合に表示されるデフォルトのテキスト）を追加する場合は、_詳細_ アイコン（**...**）をクリックし、**[!UICONTROL フォールバックテキスト付きの挿入]**&#x200B;を選択します。

   ![&#x200B; トークンを使用してパーソナライズされたテキストを作成](../assets/content-design-shared/visual-designer-personalize-dialog-handlebar.png){width="700" zoomable="yes"}

1. 含める追加のトークンやその他の静的テキストを追加します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   パーソナライゼーションスクリプトは、ビジュアルデザイン空間に表示されます。 これを選択して、必要なときに変更を加えることができます。

   ![&#x200B; パーソナライゼーションスクリプトを選択](../assets/content-design-shared/visual-designer-select-personalization-script.png){width="600"}
