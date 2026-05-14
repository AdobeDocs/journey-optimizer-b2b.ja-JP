---
title: 顧客の詳細
description: Journey Optimizer B2B editionのAIによる概要、エンゲージメントスコア、アクティビティの追跡、購買グループメンバーの意図の検出により、人物のインサイトを表示できます。
feature: Account Insights
role: User
exl-id: 401d7107-fd20-471e-9adf-a64c590b0080
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: afadf741-c5fe-42cd-8013-23bb6ff2d1bc
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
autotag-review: 2026-03-27T22:21:27.328Z
TQID: https://experienceleague.adobe.com/EVVkq83oIwQy2BWI-0z0YA8uBCnvw6Wz2GI7O2c-jE0
source-git-commit: 9baf03a1ddc1733385b0398ffadde8f548c431cc
workflow-type: tm+mt
source-wordcount: 299
ht-degree: 7%

---

# 顧客の詳細

Journey Optimizer B2B editionの任意の場所から人物名をクリックすると、人物詳細ページが表示されます。 このページには、アカウントまたは購買グループに関連付けられた人物に関する有用な情報が含まれ、ハイライトデータとインテントデータ（設定されている場合）の生成AI概要が含まれます。<!-- There are also [actions](#person-actions) that you can execute for the person. -->

![人物の詳細ページ &#x200B;](./assets/person-details-page.png){width="800" zoomable="yes"}

このページにアクセスするには、[&#x200B; インテリジェントダッシュボード &#x200B;](../dashboards/intelligent-dashboard.md)、[購買グループの詳細ページ &#x200B;](../buying-groups/buying-group-details.md)、[&#x200B; アカウントの詳細ページ &#x200B;](./account-details.md)に表示されている名前をクリックします。

人物の詳細ページは、次の4つのセクションで構成されています。

## 人物の概要

![人物の概要](./assets/details-page-account-overview.png){zoomable="yes"}

ページ上部の「人物の概要」セクションには、次の情報が含まれています。

* 名前
* 職位
* メール
* 電話番号
* エンゲージメントスコア
* 概要

## アクティビティ

このセクションには、最新のメール、web、フォーム入力、および人物に関連する注目のアクション（最大20）のリストが表示されます。 項目は、日時を含むアクティビティタイプとしてリストされます。

![&#x200B; アクティビティ – 人物の詳細](./assets/person-details-activities.png){width="700" zoomable="yes"}

## エンゲージメントスコアにもとづく購買グループ

このセクションでは、その人物がメンバーである購買グループが含まれ、エンゲージメントスコアに従って並べ替えられます。 各カードには、次の購買グループ情報が含まれます。

* 名前 – 名前をクリックして、[購買グループの詳細](../buying-groups/buying-group-details.md)を開きます。
* エンゲージメントスコア
* 完全性スコア
* Stage
* メンバー

![&#x200B; エンゲージメントに基づく購買グループ – 人物の詳細](./assets/person-details-buying-groups-engagement.png){width="700" zoomable="yes"}

## インテントデータ

Journey Optimizer B2B editionでは、インテント検出モデルは、個人のアクティビティに基づいて、十分な信頼性で関心のあるソリューション/製品を予測します。 また、タグ付けされたコンテンツとともに、他のアカウントの共同メンバーのアクティビティも活用します。 人の意図は、製品に興味を持つ可能性として解釈できます。

{{intent-data-note}}

![&#x200B; インテントデータ – 人物の詳細](./assets/intent-data-panel.png){width="700" zoomable="yes"}

* 意図のレベル
* インテントシグナルの種類 – キーワード、製品、ソリューション

<!-- ## Person actions -->
