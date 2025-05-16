---
title: インテントデータ
description: Journey Optimizer B2B editionのインテントデータを生成するためのキーワードを組み合わせて送信する方法を説明します。
feature: Setup, Intent, Account Insights
roles: Admin
exl-id: c7f9f6fe-2275-42a4-af80-b5c3d1a82837
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# インテントデータ

Journey Optimizer B2B editionでは、インテント検出モデルが、リードのアクティビティに基づいて、十分な信頼性を持つ関心のあるソリューション/製品を予測します。 また、他のアカウントの共同メンバーのアクティビティも、タグ付きコンテンツと共に活用します。 人の意図は、製品に興味を持つ確率として解釈することができます。

* インテントのレベル – 既知のリード、アカウント、購入グループレベルで使用できます。
* インテントシグナルのタイプ – キーワード、製品、ソリューション

![ インテントデータビジュアライゼーション ](../data/assets/intent-data-visualization.png){width="700" zoomable="yes"}

この機能を有効にするには、キーワードのリストをスプレッドシートでAdobe担当営業に送信します。 これらのキーワードは、コンテンツのタグ付けに使用されます。

製品には、一連のキーワード（最大 20）を関連付けることができます。 1 つのカテゴリに一連の製品（最大 20）を関連付けることができます。 最大 20 個のカテゴリを使用できます。 このモデル全体は、取り込まれた単純なスプレッドシートを通じて実現されます。 スプレッドシートには、製品名に関連付ける 1 つのタブを含めることができ、キーワードのリストに関連付ける 1 つの列を含めることができます。

![ インテントデータキーワード – 「単一の製品」タブ ](./assets/intent-data-keywords-single-product-tab.png){width="500" zoomable="yes"}

複数のタブを追加し、それぞれに製品名を指定して、スプレッドシート全体をカテゴリに関連付けることができます。

![ インテントデータキーワード – 複数の「製品」タブ ](./assets/intent-data-keywords-multiple-product-tabs.png){width="500" zoomable="yes"}
