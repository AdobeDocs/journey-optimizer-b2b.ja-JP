---
title: 顧客の詳細
description: Journey Optimizer B2B editionで、購買グループメンバー向けの AI 要約、エンゲージメントスコア、アクティビティトラッキング、インテント検出を使用して、人物インサイトを表示します。
feature: Account Insights
role: User
exl-id: 401d7107-fd20-471e-9adf-a64c590b0080
source-git-commit: 937101d6570a8217ff11037822c414350c6026ae
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 7%

---

# 顧客の詳細

Journey Optimizer B2B editionのどこからでも名前をクリックすると、ユーザーの詳細ページが表示されます。 このページには、ハイライトとインテントデータ（設定されている場合）の生成 AI 概要など、アカウントまたは購入グループに関連付けられている人物に関する有用な情報が含まれています。<!-- There are also [actions](#person-actions) that you can execute for the person. -->

![&#x200B; 人物の詳細ページ &#x200B;](./assets/person-details-page.png){width="800" zoomable="yes"}

このページにアクセスするには、[&#x200B; インテリジェントダッシュボード &#x200B;](../dashboards/intelligent-dashboard.md)、[&#x200B; 購入グループの詳細ページ &#x200B;](../buying-groups/buying-group-details.md)、または [&#x200B; アカウントの詳細ページ &#x200B;](./account-details.md) に表示される名前をクリックします。

ユーザーの詳細ページは、次の 4 つのセクションで構成されます。

## 人物の概要

![&#x200B; 人物の概要 &#x200B;](./assets/details-page-account-overview.png){zoomable="yes"}

ページ上部の「ユーザーの概要」セクションには、次の情報が表示されます。

* 名前
* 職位
* メール
* 電話番号
* エンゲージメントスコア
* 概要

## アクティビティ

このセクションには、その人物に関連する最新のメール、web、フォーム入力、興味深い瞬間（最大 20）のリストが表示されます。 項目は、日付と時間を指定したアクティビティタイプとしてリストされます。

![&#x200B; アクティビティ – 個人の詳細 &#x200B;](./assets/person-details-activities.png){width="700" zoomable="yes"}

## エンゲージメントスコアに基づく購入グループ

このセクションには、人物がメンバーである購入グループが含まれ、エンゲージメントスコアに従って並べ替えられます。 各カードには、次の購入グループ情報が含まれます。

* 名前 – 名前をクリックして [&#x200B; 購入グループの詳細 &#x200B;](../buying-groups/buying-group-details.md) を開きます。
* エンゲージメントスコア
* 完全性スコア
* Stage
* メンバー

![&#x200B; エンゲージメントに基づく購入グループ – 人物の詳細 &#x200B;](./assets/person-details-buying-groups-engagement.png){width="700" zoomable="yes"}

## インテントデータ

Journey Optimizer B2B editionでは、インテント検出モデルが、ユーザーのアクティビティに基づいて、十分な信頼性を持つ関心のあるソリューション/製品を予測します。 また、他のアカウントの共同メンバーのアクティビティも、タグ付きコンテンツと共に活用します。 人の意図は、製品に興味を持つ確率として解釈することができます。

{{intent-data-note}}

![&#x200B; インテントデータ – 個人の詳細 &#x200B;](./assets/intent-data-panel.png){width="700" zoomable="yes"}

* インテントのレベル
* インテントシグナルのタイプ – キーワード、製品、ソリューション

<!-- ## Person actions -->
