---
title: 購買グループ概要ダッシュボード
description: 購入グループの概要ダッシュボードと、マーケティングチームからの販売ハンドオフを有効にする方法について説明します。
feature: Dashboards, Buying Groups
exl-id: 26b1e7fd-2252-4782-8d0f-874720cc7d03
source-git-commit: 1713f3284bc030d44ae910015b24d4e5e099813f
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 3%

---

# 購買グループ概要ダッシュボード

購入グループの概要ダッシュボードは、B2B セールスのハンドオフプロセス用に設計されています。 これにより、マーケティングチームは、実行に必要なデータと共に、_準備完了_ の購入グループとそのメンバーをセールスチームに共有できます。 このプロセスにより、マーケティングから販売への効率的な移行が確実に行われます。

セールスのハンドオフは、次の要素で構成されます。

* **データのハンドオフ**：マーケティングによって _準備完了_ のターゲットデータが識別され、セールス部門から CSV 形式でアクセスできるようになります。 
* **営業承認**：営業は、手動でレビューし、_準備完了_ のターゲットをパイプラインに組み込みます。

このダッシュボードにアクセスするには、左側のナビゲーションで **[!UICONTROL アカウント]** を展開し、**[!UICONTROL 購入グループ]** を選択します。 「**[!UICONTROL 概要]**」タブがデフォルトで表示されていない場合は、選択します。

![ 購入グループの概要 ](./assets/buying-groups-overview.png){width="800" zoomable="yes"}
<!--
## Buying Group Status

Gain insights into your buying groups' progression with the Buying Group Status view. This visualization showcases the distribution of your buying groups categorized by their most recent status update within a specified time frame.

![Buying Groups overview](./assets/buying-groups-overview.png){width="800" zoomable="yes"}

**[!UICONTROL Status]** (y-axis): Track the journey of buying groups through various stages.
**[!UICONTROL Number of Buying Groups]** (x-axis): Quantify the number of buying groups at each status, providing a clear metric of your funnel's health and activity.

To generate a shareable PDF of your current view, click **[!UICONTROL Export]** at the top-right corner of the page. -->

## 購買グループの完了スコア分布

このビジュアライゼーションは、完了スコアに基づいて購入グループの分布を示し、4 つの異なるスコアバンドに分類されています。 中央の図は購入グループの合計数を表し、全体的な進行状況のスナップショットを簡単に提供します。 セグメント化された色は、各スコア範囲内の購入グループの割合を示し、完了のトレンドを一目で評価できます。

詳細情報を表示するには、右上の「**...**」メニューアイコンをクリックします。

![ 購入グループ完了スコアビジュアライゼーション ](./assets/buying-group-completion-score-chart.png){width="500"}

## 購買グループのエンゲージメントスコア分布

このビジュアライゼーションは、エンゲージメントスコアに基づく購入グループの分布を示し、4 つの異なるスコアバンドに分類されています。 中央の図は購入グループの合計数を表し、全体的な進行状況のスナップショットを簡単に提供します。 セグメント化された色は、各スコア範囲内の購入グループの割合を示し、完了のトレンドを一目で評価できます。

詳細情報を表示するには、右上の「**...**」メニューアイコンをクリックします。

![ 購入グループエンゲージメントスコアのビジュアライゼーション ](./assets/buying-group-completion-score-chart.png){width="500"}

## ソリューションに対する関心別の購買グループ

このビジュアライゼーションは、ソリューションの関心に基づいて購入グループの分布を示し、最も関心が高いソリューションを特定するのに役立ちます。 各棒グラフは特定のソリューションを表し、その長さは、その関心に関連付けられた購入グループの数を示します。 この棒グラフは、ソリューションの需要のトレンドを明確かつ迅速に把握します。

詳細情報を表示するには、右上の「**...**」メニューアイコンをクリックします。 **ドリルスルー** または **詳細の表示** を選択します。

![ 購入グループエンゲージメントスコアのビジュアライゼーション ](./assets/buying-group-by-solution-interest-chart.png){width="500"}

## データのフィルタリング

左上の _フィルター_ （![ フィルターアイコン ](../assets/do-not-localize/icon-filter.svg)）アイコンをクリックし、次の属性のいずれかを使用して表示データをフィルタリングします。

* 現在のステージ
* 業界
* 地域
* ソリューションに対する関心

![ 表示されたデータを属性でフィルタリング ](./assets/buying-group-overview-filters.png){width="500"}

データのフィルタリングに使用する各属性の値を選択し、「**[!UICONTROL 適用]**」をクリックします。

## データの操作

データを操作するには、各グラフの右上にある _その他_ （**...**）メニューを使用します。

### [!UICONTROL  ドリルスルー ]

個々のグループのスコアまたは分布を詳細に分析するには、「**[!UICONTROL ドリルスルー]**」を選択します。

![ ドリルスルーしてグラフデータにアクセス ](./assets/buying-group-completion-score-drill-through-view.png){width="700" zoomable="yes"}

ダッシュボードに適用されたグローバルフィルターは引き継がれます。 左上の _フィルター_ （![ フィルターアイコン ](../assets/do-not-localize/icon-filter.svg)）アイコンをクリックし、ドリルスルー表示の [ 属性フィルターの変更 ](#filter-the-data) をクリックします。

右上にある _その他_ （**...**）メニューをクリックし、**[!UICONTROL その他を表示]** を選択して [ 拡張データを表示 ](#view-more) することができます。

### [!UICONTROL  詳細を表示 ]

**[!UICONTROL さらに表示]** を選択すると、拡張されたデータとインサイトが表示されます。

![ 拡張データの表示 ](./assets/buying-group-engagement-score-view-more.png){width="700" zoomable="yes"}

表示されるポップアップには、購買グループ配分の内訳を示すチャートおよびテーブルが含まれる。

データをダウンロードするには、データテーブルの右上にある **[!UICONTROL CSV をダウンロード]** をクリックします。 概要ダッシュボードに戻るには、「**[!UICONTROL 閉じる]** をクリックします。
