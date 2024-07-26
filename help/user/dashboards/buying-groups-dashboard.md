---
title: 購買グループ概要ダッシュボード
description: 購入グループの概要ダッシュボードと、マーケティングチームからの販売ハンドオフを有効にする方法について説明します。
feature: Dashboards, Buying Groups
exl-id: 26b1e7fd-2252-4782-8d0f-874720cc7d03
source-git-commit: ec72c46a57109814464542fd4a8e4a9828982136
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 2%

---

# 購買グループ概要ダッシュボード

購入グループの概要ダッシュボードは、B2B 販売ハンドオフ・プロセス用に設計されています。 これにより、マーケティングチームは、実行に必要なデータと共に、_準備完了_ の購入グループとそのメンバーをセールスチームに共有できます。 このプロセスにより、マーケティングから販売への効率的な移行が確実に行われます。

販売ハンドオフは、次の要素で構成されます。

* **データハンドオフ**：マーケティングは、_準備完了_ のターゲットデータを識別し、CSV 形式で営業部門からアクセスできるようにします。 
* **営業承認**：営業は、手動でレビューし、_準備完了_ のターゲットをパイプラインに組み込みます。

## 購入グループのステータス

購入グループステータス ビューを使用して、購入グループの進行状況に関するインサイトを取得します。 このビジュアライゼーションでは、指定した期間内の最新のステータス更新別に分類された購入グループの分布が表示されます。

![ 購入グループの概要 ](./assets/buying-groups-overview.png){width="800" zoomable="yes"}

**[!UICONTROL ステータス]** （Y 軸）：様々な段階を経て、購入グループのジャーニーを追跡します。
**[!UICONTROL 購入グループ数]** （x 軸）：各ステータスの購入グループ数を定量化し、ファネルの正常性とアクティビティを明確に指標します。
<!-- To generate a shareable PDF of your current view, click **[!UICONTROL Export]** at the top-right corner of the page. -->

### データのフィルター

* **データフィルター** - _[!UICONTROL 日付フィルター]_ を使用します。これは、購入グループの最後のステータス変更日を反映します。 開始日は調整可能です。 終了日はデフォルトで現在の日付になります。

  ![ 日付範囲別の購買グループ・ステータス・データのフィルタ処理 ](./assets//buying-group-status-filter-date.png){width="400"}

* **属性フィルター** – 左上の _フィルター_ アイコンをクリックすると、次の属性のいずれかを使用してデータ表示をフィルタリングできます。

   * ソリューションの関心
   * ステータス
   * 購入グループの状態
   * アカウント地域
   * アカウント業界
  <!-- * Account's Industry -->

  ![ 属性による購買グループ・ステータス・データのフィルタ処理 ](./assets/buying-group-status-drill-through-filters.png){width="500"}

## データの操作

データを操作するには、右上隅のアクションメニューを使用します。

![ アイコンをクリックしてアクションメニューにアクセスする ](./assets/buying-group-more-menu.png){width="300"}

### [!UICONTROL  ドリルスルー ]

個々のグループのステータスを詳細に分析するには、「**[!UICONTROL ドリルスルー]**」を選択します。

![ グラフデータのドリルスルー ](./assets/buying-group-status-drill-through-view.png){width="600" zoomable="yes"}

ダッシュボードに適用されたグローバルフィルターは引き継がれます。

右上のアクションメニューアイコンをクリックし、**[!UICONTROL さらに表示]** を選択して、[ 拡張データとインサイトを表示 ](#view-more) します。

### [!UICONTROL  詳細を表示 ]

拡張されたデータとインサイトについては、「**[!UICONTROL さらに表示]**」を選択します。 表示されるポップアップには、グラフと、購入グループのステータスの分類を示すテーブルが含まれます。

* [!UICONTROL  アカウント ID ]
* [!UICONTROL  アカウント名 ]
* [!UICONTROL  アカウント地域 ]
* [!UICONTROL  アカウント業界 ]
* [!UICONTROL  購買グループ名 ]
* [!UICONTROL  ソリューションの関心 ]
* [!UICONTROL ステータス]
* [!UICONTROL エンゲージメントスコア]
* [!UICONTROL  完全性スコア ]
* [!UICONTROL  メンバーの役割 ]
* [!UICONTROL  メンバーの登録/作成日 ]
* [!UICONTROL  ユーザー ID]
* [!UICONTROL 名前]
* [!UICONTROL メール]
* [!UICONTROL タイトル]
* [!UICONTROL  インバウンドエンゲージメントアクティビティの数 ]
* [!UICONTROL  最終エンゲージメント日 ]

![ 拡張データの表示 ](./assets/buying-group-status-view-more.png){width="600" zoomable="yes"}

データをダウンロードするには、右上の **[!UICONTROL CSV をダウンロード]** をクリックします。
