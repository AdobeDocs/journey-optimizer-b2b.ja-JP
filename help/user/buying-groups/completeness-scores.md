---
title: 購入グループの完全性スコア
description: Journey Optimizer B2B editionで、役割ベースのしきい値、カスタマイズ可能なメンバー要件、完了状況の設定を使用して、購入グループの完了状況スコアを計算します。
feature: Buying Groups
role: User
source-git-commit: 1ebc27a709e1b82029c22950897505f3945a507f
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 3%

---


# 完全性スコア {#completeness-scores}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_completeness_score"
>title="完全性スコア"
>abstract="完全性スコアは、購入グループのメンバーシップがセールス対応の購入グループにどの程度適合しているかを反映しています。"

完全性スコアは、定義された役割をまたいで必要なメンバーが購買グループにどの程度適合しているかを示すパーセンテージです。 これらのスコアは、役割テンプレートで設定した役割メンバーのしきい値と、購買グループ内の各役割に割り当てられたメンバーの実際の数に基づいています。 結果として得られるスコアは、マーケターが販売の準備状況を評価し、購入グループ構成のギャップを特定するのに役立ちます。 購入グループメンバーシップが変更されると、スコア計算が自動的に行われます。

![ 購入グループの完全性スコア ](./assets/buying-group-details-page-completeness-scores.png){width="800" zoomable="yes"}

完全性スコアには次の 2 種類があります。

* **購買グループ完全性スコア** – 購買グループ完全性スコアは、0% から 100% の間のパーセントで、ロール・レベルの完了度計算に基づく購買グループの全体的な完全性を表します。

  購入グループの完了度スコアは、「[ 購入グループの詳細 ](./buying-group-details.md) ページに表示されます。 このスコアは、購入グループがセールスエンゲージメントに必要な関係者を配置しているかどうかを一目で確認できます。

* **ロール完全性スコア** - ロール完全性スコアは、購買グループ内の個々のロールに対する比率で、そのロールに割り当てられたメンバー数に基づいています。

  各ロールの完了度スコアは、ロールを編集して完了度設定を調整する際に、購買グループの詳細ページに表示されます。 これらのスコアは、セールス対応のしきい値に達するために追加のメンバーが必要な特定の役割を特定するのに役立ちます。

  詳細ページには、追加の役割の最初の 2 つの役割の完全性スコアと n_+ リンクが表示されます。 リンクをクリックして、追加の役割完全性スコアを表示します。

完全性スコアは、購買グループ・メンバーシップの現在の状態を反映し、メンバーが追加または削除されると自動的に更新されます。 表示されたスコアは全体のパーセンテージとして表示されます（例えば、66.67% のスコアは 67% と表示されます）。

## セールスの準備の評価

Adobe Journey Optimizer B2B editionを利用することで、マーケターは購買グループが実際の意思決定プロセスに確実に合致するようツールを入手することができます。 カスタマイズ可能な役割メンバーしきい値を使用して、組織のセールス手法を反映した完全な購入グループを定義できます。 各役割に対して最小および最大のメンバー要件を設定することで、セールス対応購買グループの構成要素に関する明確な基準を確立できます。

購入グループの完全性スコアは、グループの販売準備の正確な尺度を提供します。 例えば、特定のソリューションのオポチュニティを完了するには、少なくとも 2 人の意思決定者、1 人の影響力者、1 人の実務担当者が必要な場合があります。 完全性スコアの計算は、これらの役割固有の各要件を考慮し、購入グループ全体の準備状況を示します。

## ジャーニーの有効性の測定

購入グループの完全性は、ジャーニーの有効性の主要業績評価指標（KPI）として機能します。 特定のジャーニーの目標は、購入グループの完全性を特定の割合で増やすか、販売対応アラートをトリガーする前に最小しきい値を達成することです。

大企業では、役割ごとに 1 人の人物を識別する場合があります。 ただし、その人物が販売の適切な連絡先ではない可能性があるか、重要な役割を果たすために複数の連絡先が必要になる場合があります。 例えば、大規模な組織では、複数の部門やビジネスユニットに分散した複数の情報技術（IT）意思決定者がいる場合があります。 1 人の意思決定者を特定するだけでは、複雑なエンタープライズ販売には不十分な場合があります。

現在の購買グループの完全性を分析した後、ロール・テンプレート内の各ロールに必要な連絡者数を調整できます。 これらの調整により、実際のパターンと販売成果に基づいて購買グループ戦略を調整できます。

<!-- ## Analyze audiences for journey optimization

Marketers can view the starting buying group completeness score of target account audiences to find the best performance indicators for a solution. This visibility enables marketers to:

* Determine if they need to adjust the completeness score requirements for each role to make journeys more effective.
* Identify which buying groups are closest to sales-ready status and prioritize them for acceleration campaigns.
* Segment buying groups by completeness score ranges and create tailored nurture strategies for different maturity levels.

>[!BEGINSHADEBOX]

The buying group completeness score is available to use for filtering in [journey split-path-by-account nodes](../journeys/split-merge-paths-nodes.md#account-path-filters) and for audience segmentation. Role completeness can be used to create personalized content that addresses specific gaps in buying group composition.

>[!ENDSHADEBOX] -->

## 役割の完了度の計算 {#role-completeness-calculation}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_role_completeness_calculation"
>title="役割の完了度の計算"
>abstract="役割の完全性スコアは、役割に割り当てられたメンバーの数に基づいてパーセンテージで計算されます。"

Journey Optimizer B2B editionは、個々の購入グループのロールに対する完了度スコアをパーセンテージで計算します。 このスコアは、完了までに役割に割り当てられているメンバーの数 [ 役割テンプレートに必要な数 ](./buying-groups-role-templates.md#change-the-completeness-score-settings) に基づきます。

ロール完全性の計算は、ゼロと指定されたしきい値の間の線形パーセンテージです（メンバーが必要です）。

* 割り当てられたメンバーの数が **ゼロ** の場合、役割の完了度は **0%** になります。
* 割り当てられたメンバーの数が **しきい値またはそれ以上** の場合、役割の完了度は **100%** になります。
* 割り当てられたメンバーの数が **1 からしきい値の間** である場合、完全性は比例的に計算されます。

### 役割の完了度の数式

役割の完了率は、次の式を使用して計算されます。

```text
Role Completeness % = ((Assigned Members - Threshold) / (Threshold)) × 100
```

次のとおりです。

* `Assigned Members` =現在の役割メンバー数
* `Threshold` = Members required roles template で設定された値

### 役割の完全性の例

次の例は、様々なしきい値設定を使用したロール完了度の計算を示しています。

| 役割 | メンバーが必要です | 割り当てられたメンバー | 計算 | 役割の完全性 |
|------|------------------|------------------|-------------|-------------------|
| 意思決定者 | 3 | 0 | None | 0% |
|  |  | 1 | 1/3×100 | 33% |
|  |  | 2 | 2/3 × 100 | 66% |
|  |  | 3 | しきい値 | 100% |
|  |  | 4 | しきい値を超える | 100% |
| インフルエンサー | 5 | 0 | None | 0% |
|  |   | 1 | 1/5×100 | 20% |
|  |   | 2 | 2/5 × 100 | 40% |
|  |   | 3 | 3/5 × 100 | 60% |
|  |   | 4 | 4/5 × 100 | 80% |
|  |   | 5 | しきい値 | 100% |
|  |   | 6 | しきい値を超える | 100% |

## 購買グループの完了度の計算 {#buying-group-completeness-calculation}

購入グループの完全性スコアは、個々のロールの完全性スコアを集計します。 この計算は、定義されたすべての役割をまたいで、購買グループの準備状況の全体像を提供します。

### 購買グループの完了度式

購買グループ完了率は、次の算式を使用して計算されます。

```text
Buying Group Completeness % = Σ(Role Completeness %) / Number of defined roles
```

次のとおりです。

* `Role Completeness %` =個々の役割の完了率（0 ～ 100%）
* `Σ` =購買グループ内のすべての役割の合計

<!--

## Use completeness scores in journeys

Use buying group completeness scores and role-level completeness scores to optimize your account journeys and personalize engagement strategies.

### Split paths by completeness

Use completeness thresholds in [journey split-path-by-account nodes](../journeys/split-merge-paths-nodes.md#account-path-filters) to route buying groups through different journey paths based on their readiness. For example:

* **High completeness path** (≥70%) - Buying groups that are nearly sales-ready can be routed to sales teams or receive call-to-action campaigns
* **Medium completeness path** (40-69%) - Buying groups in active development receive nurture campaigns focused on filling specific role gaps
* **Low completeness path** (<40%) - Newly formed buying groups receive awareness and education content to build initial engagement

### Trigger actions based on completeness milestones

Set up journey events that trigger specific actions when buying groups reach completeness milestones. FOr example:

* Alert sales teams when a buying group reaches 70% completeness.
* Send a _stakeholder alignment_ campaign when completeness increases by 20% or more within a defined timeframe.
* Trigger an automated assessment when a buying group stalls at the same completeness level for an extended period.

By leveraging completeness scores throughout the journey, you create more targeted, efficient campaigns that align with the actual composition and maturity of your buying groups.

-->