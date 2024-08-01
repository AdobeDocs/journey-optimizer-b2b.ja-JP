---
title: ジャーニーの概要ダッシュボード
description: ジャーニーの概要ダッシュボードに表示される情報と、アカウントジャーニー戦略の監視と管理にどう役立つかを説明します。
feature: Dashboards, Account Journeys
exl-id: a3d4988e-5fa6-498b-828b-690095578db8
source-git-commit: 78d82aa8b3bb8b8d432eeb187d75e2354dbff3ee
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 1%

---

# ジャーニーの概要ダッシュボード

このダッシュボードは、選択したアカウントジャーニーの包括的な概要を提供し、完了、進行中のアクティビティ、中止の推移を分類および定量化するドーナツグラフと折れ線グラフを使用して、アカウントの進行状況の詳細を説明します。 これは、マーケターが、主要な配信とエンゲージメント指標を通じてメールおよび SMS チャネルの有効性を評価するのに役立ちます。

この概要は、公開済みアカウントジャーニーで使用でき、データがグラフとテーブルに入力され始めるまで約 4 時間かかります。

![ジャーニーの概要 ](./assets/journey-overview.png){width="700" zoomable="yes"}

## ジャーニーステータス

このドーナツグラフは、ジャーニーのステータスの分類を提供し、アカウントを `Completed`、`In Progress`、`Aborted` に分類します。 各セグメントには、グラフの外側の端に、対応する割合と口座番号がはっきりとラベル付けされます。

## ジャーニー完了の推移

この折れ線グラフは、ジャーニーを完了したアカウントの数を経時的に追跡します。 横軸はタイムラインをマッピングし、縦軸は勘定科目を定量化し、完了トレンドをわかりやすく表示します。

## ジャーニーパフォーマンスウィジェット

この節では、次の 2 つの重要な指標を示します。

* **[!UICONTROL ジャーニーの完了率]** - ジャーニーを正常に完了したアカウントの割合。
* **[!UICONTROL ジャーニー期間]** - アカウントがジャーニーを完了するまでにかかった平均時間。

## メールおよび SMS パフォーマンステーブル

パフォーマンステーブルは、メールと SMS チャネルの有効性を詳しく示します。 各表では、配信率やクリックスルー率などの指標を示し、各通信タッチポイントの影響を評価します。

**[!UICONTROL メールのパフォーマンス]** テーブル列：

* _[!UICONTROL アセット名]_ - アセットの名前
* _[!UICONTROL 送信済み]_ – 送信されたメールの数
* _[!UICONTROL 配信率]_ – 配信されたメール数を送信数で割った値
* _[!UICONTROL 開封率]_ – 開封されたメールの数を、配信された数で割った値
* _[!UICONTROL クリックスルー率]_ - クリックされたメールの数を、配信された数で割った値

**[!UICONTROL SMS パフォーマンス]** テーブル列：

* _[!UICONTROL アセット名]_ - アセットの名前
* _[!UICONTROL 送信済み]_ – 送信された SMS メッセージの数
* _[!UICONTROL 配信率]_ – 配信された SMS メッセージの数を送信数で割った値
* _[!UICONTROL クリックスルー率]_ - クリックされた SMS メッセージの数を、配信された数で割った値
<!-- 
To generate a shareable PDF of your current view, click **[!UICONTROL Export]** at the top right of the page. -->

## インタラクションの強化

各グラフまたはテーブルの右上にあるアクションアイコン（**...**）を使用して、データをさらにエンゲージします。

### ドリルスルー

_[!UICONTROL ジャーニーステータス]_ グラフで、個々のアカウントのステータスを詳しく分析するには、「**[!UICONTROL ドリルスルー]**」を選択します。

![ グラフデータのドリルスルー ](./assets/journey-status-drill-through.png){width="600" zoomable="yes"}
<!--
The applied global filters are carried over to the view and displayed at the top. Click the _Filter_ icon at the top left to filter the data display by journey.-->

### さらに表示

「**[!UICONTROL さらに表示]**」を選択すると、拡張されたデータとインサイトにアクセスできます。 表示されるポップアップには、データの分類が表示されます。

データをダウンロードするには、右上の **[!UICONTROL CSV をダウンロード]** をクリックします。

![ 拡張データの表示 ](./assets/journey-email-performance-view-more.png){width="600" zoomable="yes"}
