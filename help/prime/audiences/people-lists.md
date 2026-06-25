---
title: ユーザーリスト
description: Journey Optimizer B2B Primeでユーザーリストを作成および管理し、ジャーニーターゲティング、動的ルールベースのメンバーシップ、静的リストの宛先アクティベーションを実現します。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
autotag-review: '2026-06-12T22:47:10.727Z'
TQID: 'https://experienceleague.adobe.com/KWT9-Lr6358MQ0sLQyKAlb4SLERnBl-QQL7Cj1iXCZM'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: beb5f4be-cec3-471a-9db6-831a77dd3ac9id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 9433a1e86767e4504cb238ba8f3fae6e5c098a86
workflow-type: tm+mt
source-wordcount: 862
ht-degree: 3%

---

# ユーザーリスト

[!DNL Adobe Journey Optimizer B2B Prime]では、人物リストはターゲティングおよび人物ジャーニーのエントリ用の個人レベルのオーディエンスコンテナであり、ルールベースのライブ選定の動的リストと、固定またはジャーニーで管理されるメンバーシップの静的リストが含まれています。

## ユーザーリストへのアクセスと参照 {#access-and-browse}

1. 左側のナビゲーションで、**[!UICONTROL マーケティング管理]**&#x200B;を展開します。

1. **[!UICONTROL マーケティング]**&#x200B;のリソースリストの右側で、**[!UICONTROL 人物リスト]**&#x200B;を選択します。

   ![ ユーザーリストにアクセスしてオーディエンスを管理](./assets/people-lists.png){width="800" zoomable="yes"}

ページには2つのタブがあり、**[!UICONTROL 動的リスト]**&#x200B;と&#x200B;**[!UICONTROL 静的リスト]**&#x200B;を表示および管理できます。 タブをクリックして、各タイプ間でリストビューを切り替えます。

リストの上部にある&#x200B;_検索_ ツールにテキストを入力すると、表示されるリストを名前でフィルタリングできます。 リストツールを使用して、表示されるリストをカスタマイズします。

* 表示される列を制御するには、「_テーブルをカスタマイズ_」（「![ テーブルアイコン ](../../assets/do-not-localize/icon-falco-customize-table.svg)」）アイコンをクリックします。
* _列をリセット_ （![列幅をリセット アイコン ](../../assets/do-not-localize/icon-falco-reset-columns.svg)）アイコンをクリックして、列幅をリセットします。

このスペースから、次のこともできます。

* 新しい動的リストと静的リストの作成
* リストにアクセスして現在のメンバーシップを確認
* メンバーシップフィルターの適用

<!--
## Audience Hub

The AI Audience Hub is a centralized, AI-driven starting point for all audience-related capabilities across [!DNL Adobe Journey Optimizer B2B Prime]. It is designed to accelerate first-time user success while progressively unlocking advanced intelligence, insights, and control for returning and power users.

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

## ユーザーリストの作成 {#create-people-list}

1. _[!UICONTROL 人物リスト]_ ページの右上にある「**[!UICONTROL リストを作成]**」をクリックします。

1. ダイアログで、リストの&#x200B;**[!UICONTROL 親]**&#x200B;としてプログラムを選択します。

1. リストに&#x200B;**[!UICONTROL 名前]**&#x200B;と&#x200B;**[!UICONTROL 説明]** （オプション）を入力します。

1. 次にリスト **[!UICONTROL 種類]**&#x200B;を選択します。

   * **[!UICONTROL 静的]** - メンバーシップは、リストの作成時に評価された修飾フィルターによって決定されます。レコードを手動で選定または選定しない限り、リストメンバーシップは更新されません。
***[!UICONTROL Dynamic]** - メンバーシップは、適格なフィルターによって動的に決定されます。リストのメンバーシップが自動的に更新されます。

   ![人物リストの作成ダイアログ ](./assets/people-list-create-dialog.png){width="450"}

1. 「**[!UICONTROL 作成]**」をクリックします。

>[!NOTE]
>
>削除と複製は、現在、このBeta リリースのユーザーリストではサポートされていません。

## 静的リスト {#static-list}

静的リストメンバーシップは、ユーザーの属性とアクティビティを参照するシンプルなフィルターによって定義されます。 メンバーシップは、手動でメンバーを選定または選定しない限り、変更されません。

>[!NOTE]
>
>静的リストフィルター定義は、リストにメンバーを追加またはリストから削除する場合に1回だけ適用されます。 定義されたフィルターは、その後は使用できません。 フィルターを使用して一貫したオーディエンス定義を維持する場合は、代わりに動的リストを使用します。

<!--
What internet says about Marketo static lists -- which of these is also true in AJO B2B Prime?

* Manual Targeting: Storing fixed cohorts, such as attendees of a specific webinar, people who purchased a certain product, or a list of competitors.
* Third-Party Syncing: Allowing external platforms (like Amplitude or Twilio Segment) to automatically sync and export groups of users directly into Marketo as targeted audiences.
* Status Tracking: Helping marketers organize leads into specific categories or track multi-value interests without needing to create new, permanent database fields.List 
* Segmentation: Acting as a reliable, unchanging recipient or suppression list for email campaigns and engagement programs. Unlike a Smart List—which dynamically adds or removes people based on changing criteria or rules—a static list serves as a reliable snapshot. People remain on the list until explicitly added or removed by you or a backend flow.

So far, activating to a destination is the only thing that they are used for that I have found.
-->

### メンバーを追加 {#static-list-add-members}

1. 静的リストを開き、右上の「**[!UICONTROL 人物を追加]**」をクリックします。

1. ダイアログで、左からフィルターをドラッグ&amp;ドロップして、リードのクオリフィケーションのルールを定義します。

   次のいずれかの組み合わせを使用して、人物をフィルタリングできます。

   * アクティビティ履歴
   * 会社属性
   * 顧客属性
   * ジャーニーメンバーシップなどの特別なフィルター

1. 変更を保存するには、**[!UICONTROL 完了]**&#x200B;をクリックします。

1. 「**[!UICONTROL メンバー]**」タブを選択します。

   短期間の後、適格なメンバーがリストに表示されます。

### メンバーを削除 {#static-list-remove-members}

1. 静的リストを開き、右上の「**[!UICONTROL 人を削除]**」をクリックします。

1. ダイアログで、除外するメンバーに一致するフィルターを追加します。

1. 変更を保存するには、**[!UICONTROL 完了]**&#x200B;をクリックします。

1. 「**[!UICONTROL メンバー]**」タブを選択します。

   一定期間が経過すると、失格となった会員はリストから除外されます。

### 宛先に対してアクティブ化 {#static-list-activate}

静的リストをアクティブ化すると、ダウンストリームシステムで実行でき、手動エクスポートではなく継続的な同期が行われます。 これは、有料メディアのターゲティング、抑制、ダウンストリームのオーケストレーションに役立ちます。

* 静的リストは人物のコンテナとして機能します。
* アクティベーションは、そのメンバーシップを宛先に送信/同期します。
* その後、リンク先は、LinkedInでターゲティングしたり、外部オーディエンスから削除したりするなど、オーディエンスに対して何かをおこなうことができます。

アクティベーションモデルは、1回限りの書き出しではなく永続的なものであるため、

* 後でリストに追加された人物は、自動的に反映されます。
* 後で削除されたユーザーは、自動的に非アクティブ化されます。
* マーケターは、CSVを繰り返し書き出すことや手動でアップロードすることを避けます。
* ジャーニーは、継続的なオーケストレーションのために、オーディエンスを時間をかけて更新できます。

1. 「**[!UICONTROL 静的リスト]**」タブを選択します。

1. 宛先に対してアクティブ化する静的リストを探します。

1. 静的リスト名の横にある「_アクティブ化_」（「![ テーブルアイコンをカスタマイズ ](../../assets/do-not-localize/icon-falco-activate-dest.svg)」）アイコンをクリックします。

1. 設定済みの宛先接続のチェックボックスをオンにします。

   ![ アクティブ化に使用できる設定済みの宛先](./assets/static-list-activate-destination-select.png){width="600" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。

## 動的リスト {#dynamic-lists}

動的リストメンバーシップは、ユーザーの属性とアクティビティを参照するシンプルなフィルターを使用して定義されます。 メンバーシップは、フィルターロジックに従ってリードのクオリフィケーションを行い、クオリフィケーションを行うことで自動的に維持されます。

### メンバーシップルールの設定

1. 動的リストを開き、「**[!UICONTROL ルール]**」タブを選択します。

1. 「**[!UICONTROL ルールを編集]**」をクリックします。

1. ダイアログで、左からフィルターをドラッグ&amp;ドロップして、リードのクオリフィケーションのルールを定義します。

   次を任意に組み合わせることで、リストのリードを絞り込むことができます。

   * アクティビティ履歴
   * 会社属性
   * 顧客属性
   * ジャーニーメンバーシップなどの特別なフィルター

1. 変更を保存するには、**[!UICONTROL 完了]**&#x200B;をクリックします。

1. 「**[!UICONTROL メンバー]**」タブを選択します。

   短期間の後、適格なメンバーがリストに表示されます。

概要と最近のアクティビティを表示できるリードプロファイルの詳細ページを開くには、リスト内の人物の名前をクリックします。

### 動的リストの複製

動的リストの場合、重複アクションはクローン関数に似ています。 この関数を使用して、メンバーシップフィルターを複製し、別のプログラムに追加します。

1. _[!UICONTROL 動的リスト]_ タブで、複製するリストの横にある&#x200B;_複製_ （**...**）アイコンをクリックします。

1. ダイアログで、複製されたジャーニーの&#x200B;**[!UICONTROL 親]** プログラムを選択します。

1. 一意の&#x200B;**[!UICONTROL 名前]** （必須）と&#x200B;**[!UICONTROL 説明]** （オプション）を入力してください。

   デフォルトでは、ダイアログには元のリストの名前に`_copy`が追加されて使用されます。 必要に応じて、リストに別の一意の名前を入力します。

   ![ リストを複製ダイアログ ](./assets/people-list-duplicate-dialog.png){width="375"}

1. 「**[!UICONTROL 複製]**」をクリックします。
