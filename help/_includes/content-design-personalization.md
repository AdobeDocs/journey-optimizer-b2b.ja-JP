---
title: コンテンツオーサリング – パーソナライゼーション
description: コンテンツオーサリングでのパーソナライゼーションの使用に関する再利用された節
source-git-commit: 3791beb98068a56882bb0a96fbc6b192e85130bb
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 2%

---

# コンテンツオーサリング – パーソナライゼーション

Journey Optimizer B2B editionでは、インラインのシンプルな構文を使用します。この構文を使用すると、パーソナライズされたコンテンツを二重の中括弧で囲んだ式を作 `{}` できます。 同じコンテンツまたはフィールドに、制限なく複数の式を追加できます。

例:

* `Hello {{profile.person.name.firstName}} {{profile.person.name.lastName}}`

* `Hello {{profile.person.name.fullName}}`

Journey Optimizer B2B editionは、コンテンツの処理時に、式をExperience Platformデータベースに含まれるデータで置き換えます。 最初の例は、_Hello John Doe_ となります。

次の例では、リード/アカウント属性とシステムトークンを使用してコンテンツをパーソナライズする手順の概要を説明します。

1. テキストコンポーネントを選択し、ツールバーの _パーソナライゼーションを追加_ アイコンをクリックします。

   ![ 「パーソナライズ」アイコンをクリック ](../assets/content-design-shared/visual-designer-personalize-icon.png){width="600"}

   これにより、「_Personalizationを編集_ ダイアログが開きます。

1. **+** または **...** をクリックして、空白スペースにトークンを追加します。

   ![ トークンを使用したパーソナライズされたテキストの作成 ](../assets/content-design-shared/visual-designer-personalize-dialog.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。
