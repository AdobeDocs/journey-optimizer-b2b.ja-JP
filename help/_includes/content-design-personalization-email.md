---
title: コンテンツオーサリング – パーソナライゼーション
description: コンテンツオーサリングでのパーソナライゼーションの使用に関する再利用された節
source-git-commit: d67f44419e09693ec93fd4db7982ec59c672b633
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 1%

---

# コンテンツオーサリング – パーソナライゼーション

Journey Optimizer B2B editionでは、パーソナライズされたコンテンツを中括弧 `{}` で囲んだ式を作成できる、インラインのシンプルな構文を使用します。 同じコンテンツまたはフィールドに、制限なく複数の式を追加できます。

例:

* `Hello {{lead.firstName}} {{lead.lastName}}`
* `Hello {%= lead.mktoName ?: "Marketer" %}`

>[!NOTE]
>
>一貫したエクスペリエンスを実現するために、Journey Optimizer B2B editionはメール内のパーソナライゼーショントークンの _キャメルケース_ 構文に従って、他のAdobe Experience Platform アプリケーションと一致するようになりました。 このトークン形式は、[Handlebars テンプレート言語 ](https://handlebarsjs.com/guide/#what-is-handlebars){target="_blank"} と完全に互換性があります。 この変更の前に追加されたトークンは、自動的に更新されます。

Journey Optimizer B2B editionは、コンテンツの処理時に、式をExperience Platform データベースに含まれるデータで置き換えます。 最初の例は、_Hello John Doe_ となります。

次の例では、リード/アカウント属性とシステムトークンを使用してコンテンツをパーソナライズする手順の概要を説明します。

1. テキストコンポーネントを選択し、ツールバーの _パーソナライゼーションを追加_ アイコンをクリックします。

   ![ 「パーソナライズ」アイコンをクリック ](../assets/content-design-shared/visual-designer-personalize-icon.png){width="600"}

   これにより、「_Personalizationを編集_ ダイアログが開きます。

1. トークンの横にあるプラス（**+**）記号をクリックして、トークンを追加します。

   フォールバック（リードでそのフィールドが使用できない場合に表示されるデフォルトのテキスト）を含むトークンを追加したい場合は、_詳細_ アイコン（**...**）をクリックして **[!UICONTROL フォールバックテキストで挿入]** を選択します。

   ![ トークンを使用したパーソナライズされたテキストの作成 ](../assets/content-design-shared/visual-designer-personalize-dialog-handlebar.png){width="700" zoomable="yes"}

1. 含める追加のトークンやその他の静的テキストを追加します。

1. 「**[!UICONTROL 保存]**」をクリックします。

   パーソナライゼーションスクリプティングがビジュアルデザインスペースに表示されます。 必要に応じて、テンプレートを選択して変更を加えることができます。

   ![ パーソナライゼーションスクリプトを選択 ](../assets/content-design-shared/visual-designer-select-personalization-script.png){width="600"}
