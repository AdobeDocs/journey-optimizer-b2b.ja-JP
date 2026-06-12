---
title: オーディエンス管理
description: オーディエンスのプレースホルダーページ。
autotag-review: '2026-06-12T22:47:10.727Z'
TQID: 'https://experienceleague.adobe.com/KWT9-Lr6358MQ0sLQyKAlb4SLERnBl-QQL7Cj1iXCZM'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: beb5f4be-cec3-471a-9db6-831a77dd3ac9id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: cb3217c9fd7beb712d0c61638d143b798010d2b7
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 4%

---

# オーディエンス管理

AJO B2B Primeでは、オーディエンスはどのように再生されますか？

マーケティング管理ハブで、右側のナビゲーションの&#x200B;**[!UICONTROL 人物リスト]**&#x200B;をクリックします。

![ ユーザーリストにアクセスしてオーディエンスを管理](./assets/people-lists.png){width="800" zoomable="yes"}

ページには2つのタブがあり、**[!UICONTROL 動的リスト]**&#x200B;と&#x200B;**[!UICONTROL 静的リスト]**&#x200B;を表示および管理できます。 タブをクリックして、各タイプ間でリストビューを切り替えます。

このページから、次のことができます。

* 新しい動的リストと静的リストの作成
* 既存リストの検索
* アセット情報を参照
* メンバーシップをレビューするためのアクセスリスト

<!--
## Audience Hub

The AI Audience Hub is a centralized, AI-driven starting point for all audience-related capabilities across AJO B2B. It is designed to accelerate first-time user success while progressively unlocking advanced intelligence, insights, and control for returning and power users.

The Hub acts as:

* A guided starting point for discovering, creating, and refining person lists, account lists, and buying groups

* A visibility layer for audience health, coverage, overlap, engagement patterns, and AI-driven insights

* A control center for audience governance, optimization, reuse, and readiness for activation across journeys and sales workflows

### High level structure

Prompt-based starting point - Quick Start prompts and freeform input to help users discover, create, or optimize audiences.

1. AI insights feed - Surfaces key audience signals such as overlap, gaps, saturation risk, and optimization opportunities.

1. Adaptive audience library - A personalized view of people lists, account lists, and buying groups that adapts based on usage, relevance, and activation.

1. Optimization and arbitration nudges - Guides users to refine, split, or reuse audiences before activation.

1. Audience visibility and reporting - High-level insight into audience health, engagement patterns, and usage across active journeys.


### Empty and Error States (High-Level)

No audiences / no data - Show Quick Start prompts to help first-time users create or import person lists

Low data or incomplete audience - Explain what's missing (e.g., insufficient contacts, missing persona coverage, or low engagement data) and suggest next steps.

AI insights unavailable - Provide a graceful fallback with a clear explanation, so users understand why insights aren't shown and what actions they can take manually.
-->

## ユーザーリストの作成


新しい動的リストまたは静的リストを作成するには：

1. _[!UICONTROL 人物リスト]_ ページの右上にある「**リストを作成**」をクリックします。
1. リストの&#x200B;**[!UICONTROL 親]**&#x200B;としてプログラムを選択します。
1. リストに&#x200B;**[!UICONTROL 名前]**&#x200B;と&#x200B;**[!UICONTROL 説明]** （オプション）を入力します。
1. 次にリスト **[!UICONTROL 種類]**&#x200B;を選択します。

   * **[!UICONTROL 静的]** - メンバーシップは、リストの作成時に評価された修飾フィルターによって決定されます。レコードを手動で選定または選定しない限り、リストメンバーシップは更新されません。
***[!UICONTROL Dynamic]** - メンバーシップは、適格なフィルターによって動的に決定されます。リストのメンバーシップが自動的に更新されます。

1. 「**[!UICONTROL 作成]**」をクリックします。

>[!NOTE]
>
>このBeta リリースのユーザーリストでは、現在、削除と重複はサポートされていません。

## 静的リスト

静的リストメンバーシップは、ユーザーの属性とアクティビティを参照するシンプルなフィルターによって定義されます。 メンバーシップは、手動でメンバーを選定または選定しない限り、変更されません。

### メンバーを追加

1. 静的リストを開き、右上の「**[!UICONTROL 人物を追加]**」をクリックします。

1. ダイアログで、左からフィルターをドラッグ&amp;ドロップして、リードのクオリフィケーションのルールを定義します。

   次のいずれかの組み合わせを使用して、人物をフィルタリングできます。

   * アクティビティ履歴
   * 会社属性
   * 顧客属性
   * ジャーニーメンバーシップなどの特殊フィルター

1. 変更を保存するには、**[!UICONTROL 完了]**&#x200B;をクリックします。

1. 「**[!UICONTROL メンバー]**」タブを選択します。

   短期間の後、適格なメンバーがリストに表示されます。

### メンバーを削除

1. 静的リストを開き、右上の「**[!UICONTROL 人を削除]**」をクリックします。

1. ダイアログで、除外するメンバーに一致するフィルターを追加します。

1. 変更を保存するには、**[!UICONTROL 完了]**&#x200B;をクリックします。

1. 「**[!UICONTROL メンバー]**」タブを選択します。

   一定期間が経過すると、失格となった会員はリストから除外されます。

## 動的リスト

動的リストメンバーシップは、ユーザーの属性とアクティビティを参照するシンプルなフィルターを使用して定義されます。 メンバーシップは、フィルターロジックに従ってリードのクオリフィケーションを行い、クオリフィケーションを行うことで自動的に維持されます。

### メンバーシップ ロジックの定義

1. 静的リストを開き、「ルール」タブを選択します。

1. 「ルールを編集」をクリックします。

1. ダイアログで、左からフィルターをドラッグ&amp;ドロップして、リードのクオリフィケーションのルールを定義します。

   次を任意に組み合わせることで、リストのリードを絞り込むことができます。

   * アクティビティ履歴
   * 会社属性
   * 顧客属性
   * ジャーニーメンバーシップなどの特殊フィルター

1. 変更を保存するには、**[!UICONTROL 完了]**&#x200B;をクリックします。

1. 「**[!UICONTROL メンバー]**」タブを選択します。

   短期間の後、適格なメンバーがリストに表示されます。

概要と最近のアクティビティを表示できるリードプロファイルの詳細ページを開くには、リスト内の人物の名前をクリックします。