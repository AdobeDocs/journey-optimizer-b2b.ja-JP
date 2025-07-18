---
title: 顧客の詳細
description: Journey Optimizer B2B editionで、アカウントまたは購入グループに関連付けられたユーザーの詳細情報および生成 AI 概要へのアクセスについて説明します。
feature: Account Insights
role: User
source-git-commit: 5382bc89903a567268ee06648a8d6b0bf34695a6
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 7%

---

# 顧客の詳細

Journey Optimizer B2B editionのどこからでも名前をクリックすると、ユーザーの詳細ページが表示されます。 このページには、ハイライトとインテントデータ（設定されている場合）の生成 AI 概要など、アカウントまたは購入グループに関連付けられている人物に関する有用な情報が含まれています。<!-- There are also [actions](#person-actions) that you can execute for the person. -->

![ 人物の詳細ページ ](./assets/person-details-page.png){width="800" zoomable="yes"}

このページにアクセスするには、[ インテリジェントダッシュボード ](../dashboards/intelligent-dashboard.md)、[ 購入グループの詳細ページ ](../buying-groups/buying-group-details.md)、または [ アカウントの詳細ページ ](./account-details.md) に表示される名前をクリックします。

ユーザーの詳細ページは、次の 4 つのセクションで構成されます。

## 人物の概要

![ 人物の概要 ](./assets/details-page-account-overview.png){zoomable="yes"}

ページ上部の「ユーザーの概要」セクションには、次の情報が表示されます。

* 名前
* 職位
* メール
* 電話番号
* エンゲージメントスコア
* 概要

## アクティビティ

このセクションには、その人物に関連する最新のメール、web、フォーム入力、興味深い瞬間（最大 20）のリストが表示されます。 項目は、日付と時間を指定したアクティビティタイプとしてリストされます。

![ アクティビティ – 個人の詳細 ](./assets/person-details-activities.png){width="700" zoomable="yes"}

## エンゲージメントスコアに基づく購入グループ

このセクションには、人物がメンバーである購入グループが含まれ、エンゲージメントスコアに従って並べ替えられます。 各カードには、次の購入グループ情報が含まれます。

* 名前 – 名前をクリックして [ 購入グループの詳細 ](../buying-groups/buying-group-details.md) を開きます。
* エンゲージメントスコア
* 完全性スコア
* Stage
* メンバー

![ エンゲージメントに基づく購入グループ – 人物の詳細 ](./assets/person-details-buying-groups-engagement.png){width="700" zoomable="yes"}

## インテントデータ

Journey Optimizer B2B editionでは、インテント検出モデルが、ユーザーのアクティビティに基づいて、十分な信頼性を持つ関心のあるソリューション/製品を予測します。 また、他のアカウントの共同メンバーのアクティビティも、タグ付きコンテンツと共に活用します。 人の意図は、製品に興味を持つ確率として解釈することができます。

{{intent-data-note}}

![ インテントデータ – 個人の詳細 ](./assets/intent-data-panel.png){width="700" zoomable="yes"}

* インテントのレベル
* インテントシグナルのタイプ – キーワード、製品、ソリューション

<!-- ## Person actions -->
