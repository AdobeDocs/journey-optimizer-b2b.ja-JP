---
title: 購入グループのエンゲージメントスコア
description: Journey Optimizer B2B editionの重み付けアクティビティ、ロールベースの計算および 30 日間のスコアリングウィンドウを使用して、購入グループとユーザーのエンゲージメントスコアを計算します。
feature: Buying Groups, Engagement
role: User
exl-id: 424d9598-92dd-42de-8447-3c7cebc71a73
source-git-commit: 859e96ce0d450b52a8216f767c595938c23a9d50
workflow-type: tm+mt
source-wordcount: '1254'
ht-degree: 29%

---

# エンゲージメントスコア {#engagement-scores}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_engagement_score"
>title="エンゲージメントスコア"
>abstract="エンゲージメントスコアは、購買グループメンバーのエンゲージメントレベルを決定します。"

エンゲージメントスコアは、購入グループのメンバーのエンゲージメントレベルを示す数値です。 これらのスコアは、購入グループメンバーアクティビティ、重み付けアクション、重み付けロールに基づいています。 結果のスコアは、テナント（インスタンス）内で正規化され、一貫性のある比較が可能になり、実用的なインサイトが得られるようになります。 スコアの計算は、購入グループを作成するとすぐに開始されます。 Journey Optimizer B2B editionのデータハブシステムは、スコアを毎日計算し、取り込みサービスを使用してマルチレベルマーケティング（MLM） MySQL システムにアップロードします。

エンゲージメントスコアには、次の 2 種類があります。

* **購入グループエンゲージメントスコア** – 購入グループエンゲージメントスコアは、0 ～ 100 の間の正規化されたスコアで、人物レベルで計算されたエンゲージメントスコアに基づいています。

  購入グループエンゲージメントスコアは、[ 購入グループの詳細 ](./buying-group-details.md) ページに表示されます。 また、インテリジェントダッシュボードで、最もエンゲージメントの高い購入グループを表示することもできます。

  ![ 最も関与している購入グループ ](./assets/person-engagement-score-attribute-filtering.png){width="700" zoomable="yes"}

* **ユーザーエンゲージメントスコア** - ユーザーエンゲージメントスコアは、個々の購入グループメンバーのアクティビティに基づいています。

  購入グループメンバーごとのユーザーエンゲージメントスコアは、購入グループの詳細ページ [_[!UICONTROL  「メンバー ]_タブ ](./buying-group-details.md#buying-group-members) に表示されます。 これらのスコアは、上位のエンゲージメントメンバーや重複する連絡先情報を含むページやダッシュボードにも表示されます。

  ![ 最も関与している購入グループメンバー ](./assets/top-engaged-buying-group-members.png){width="550" zoomable="yes"}

>[!BEGINSHADEBOX]

ユーザーエンゲージメントスコアは、[ 役割テンプレート ](./buying-groups-role-templates.md#add-the-template-roles) および [ ジャーニーの人物によるパスのノード ](../journeys/split-merge-paths-nodes.md#people-path-filters) でのフィルタリングに使用できる属性です。

![ 設定済みのイベント定義へのアクセス ](./assets/most-engaged-buying-groups.png){width="550" zoomable="yes"}

>[!ENDSHADEBOX]

購入グループのメンバーが過去 30 日間に実行した、エンゲージメントの重み付けアクティビティは、スコアの計算に使用されます。 30 日間の期間を使用すると、アクティビティの発生件数が期限切れになり、スコアが下に移動する（スコアディケイ）ことがあります。 表示されるスコアは四捨五入されます（例えば、スコア 75.89999 は 76 と表示されます）。

## エンゲージメントスコアリングに使用するアクティビティ

購入グループのスコアリングは _トリガーベース_ ではありません。 これは、購買グループのすべてのメンバーのアクティビティを評価し、スコアを再計算する日別プロセスです。 アクティビティは _重み付け_ を使用して、アクティブな重み付けモデルに従って購買グループのスコアリングを通知します。このモデルは、各アクティビティの重み付け方法を決定します。

各アクティビティの 1 日あたりのフリークエンシーキャップは 20 です。購入グループのメンバーが 1 日に同じアクティビティを 20 回以上実行した場合、アクティビティのカウントは 20 に制限されます。

| アクティビティ名 | 説明 | エンゲージメントタイプ | 1 日あたりの最大頻度数 | 既定のモデル アクティビティの重み付け |
|---------------|-------------|-----------------|---------------------------|-------------------------------|
| イベントに出席 | メンバーがイベントに出席しました | イベント | 20 | 60 |
| 電子メールのクリック | メンバーがメール内のリンクをクリックします | メール | 20 | 30 |
| 電子メールの開封 | メンバーがメールを開きます | メール | 20 | 30 |
| フォームに入力済み | メンバーが web ページ上のフォームに入力して送信します | Web | 20 | 40 |
| 注目のアクション | メンバーに注目のアクションがあります | キュレート | 20 | 60 |
| リンククリック数 | メンバーが web ページ上のリンクをクリックします | Web | 20 | 40 |
| ページビュー | メンバーが web ページを閲覧した場合 | Web | 20 | 40 |
| イベントに登録 | イベントに登録されているメンバー | イベント | 20 | 60 |

<!-- old list

| Activity name | Description | Engagement type | Max daily frequency count | Activity weight |
| --- | --- | --- | --- | --- |
| [!UICONTROL Visit Webpage]| A member visits a web page | Web | 20 | 40 |
| [!UICONTROL Fill Out Form]| A member fills and submits a form on a web page | Web | 20 | 40 |
| [!UICONTROL Click Link] | A member clicks a link on a web page | Web | 20 | 40 |
| [!UICONTROL Open Email] | A member opens an email | Email | 20 | 30 |
| [!UICONTROL Click Email] | A member clicks a link in an email | Email | 20 | 30 |
| [!UICONTROL Open Sales Email] | A member opens a sales email | Email | 20 | 30 |
| [!UICONTROL Click Sales Email] | A member clicks a link in a sales email | Email | 20 | 30 |
| [!UICONTROL Interesting Moment] | A member has an interesting moment | Curated | 20 | 60 |
| [!UICONTROL Tap Push Notification] | A member receives a push notification | Mobile | 20 | 30 |
| [!UICONTROL Mobile App Activity] | A member performs an activity on a mobile app | Mobile | 20 | 30 |
| [!UICONTROL Mobile App Session] | A member is active on a mobile app session | Mobile | 20 | 30 |
| [!UICONTROL Fill Out Facebook Lead Ads Form] | A member fills and submits a Lead Ads form on a Facebook page | Social | 20 | 30 |
| [!UICONTROL Click RTP Call to Action] | A member clicks a personalized call to action | Web | 20 | 60 |
| [!UICONTROL View In-App Message] | A member views an in-app message | Mobile | 20 | 30 |
| [!UICONTROL Tap In-App Message] | A member taps an in-app message | Mobile | 20 | 30 |
| [!UICONTROL Subscribe SMS] | A member subscribes to SMS communications | SMS | 20 | 90 |
| [!UICONTROL Reply to Sales Email] | A member replies to a sales email | Email | 20 | 30 |
| [!UICONTROL Engaged with a Dialogue] | A member engages with a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Interacted with Document in Dialogue] | A member interacts with a document in a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Scheduled Meeting in Dialogue] | A member schedules an appointment in a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Reached Dialogue Goal] | A member reaches a goal in a Dynamic Chat dialogue |  |20 | 90 |
| [!UICONTROL Responded to a poll in webinar] | A member responds to a poll in a webinar event | Chat | 20 | 90 |
| [!UICONTROL Call to action clicked in webinar] | A member clicks a call-to-action link in a webinar event | Call | 20 | 30 |
| [!UICONTROL Asset downloads in webinar] | A member downloads a file/asset in a webinar event | Event | 20 | 60 |
| [!UICONTROL Asks questions in webinar] | A member asks questions in a webinar event | Event | 20 | 60 |
| [!UICONTROL Has attended event] | A member attended an event | Event | 20 | 60 |
| [!UICONTROL Engaged with an Agent in Dialogue] | A member engages with an agent in a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Clicked Link in Chat in Dialogue] | A member clicks a link in a Dynamic Chat dialogue | Chat | 20 | 90 |
| [!UICONTROL Engaged with a Conversational Flow] | A member engages with a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Scheduled Meeting in Conversational Flow] | A member schedules an appointment in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Reached Conversational Flow Goal] | A member reaches a goal in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Interacted with Document in Conversational Flow] | A member interacts with a document in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Engaged with an Agent in Conversational Flow] | A member engages with an Agent in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Clicked Link in Chat in Conversational Flow] | A member clicks a link in a Dynamic Chat conversational flow | Chat | 20 | 90 |
| [!UICONTROL Click Link in SMS V2] | A member clicks a link in an SMS message | SMS | 20 | 90 | -->

>[!NOTE]
>
>エンゲージメントスコアアクティビティは、ある人物のMarketo Engage アクティビティログに記録されます。 接続されたMarketo Engage インスタンスで、このログにアクセスできます。 詳しくは、Marketo Engage ドキュメントの [ ある人物のアクティビティログを見つける ](https://experienceleague.adobe.com/ja/docs/marketo/using/product-docs/core-marketo-concepts/smart-lists-and-static-lists/managing-people-in-smart-lists/locate-the-activity-log-for-a-person){target="_blank"} を参照してください。

## 役割テンプレートの重み付け {#engagement-score-weighting}

>[!CONTEXTUALHELP]
>id="ajo-b2b_buying_group_engagement_score_weighting"
>title="エンゲージメントスコアの役割別重み付け"
>abstract="役割別重み付けを使用して、エンゲージメントスコアの計算をカスタマイズします。"

ユーザーは _役割テンプレート_ 内の各役割に [ 重み付け ](./buying-groups-role-templates.md) を割り当てて、役割に異なる重み付けを割り当てることができます。

![役割テンプレートの各役割に重み付けを設定](./assets/roles-templates-weighting.png){width="700" zoomable="yes"}

各重み付けレベルは値に変換され、エンゲージメントスコアの計算に使用されます。

* [!UICONTROL 全く重要でない] = 20
* [!UICONTROL 重要ではない] = 40
* [!UICONTROL 標準] = 60
* [!UICONTROL 重要] = 80
* [!UICONTROL 非常に重要] = 100

_[!UICONTROL 非常に重要]_、_[!UICONTROL 重要]_、_[!UICONTROL 標準]_&#x200B;として重み付けされた 3 つの役割を持つ役割テンプレートは、次の重み付けパーセンテージに変換されます。

| 役割 | 重み付け | システム値 | 値の計算 | 割合 |
|-------------- |--------- |------------- |------------------ |---------- |
|               |          |              |                   |           |
| 意思決定者 | 非常に重要 | 100 | 100/240 | 41.67％ |
| インフルエンサー | 重要 | 80 | 80/240 | 33.33％ |
| 実務担当者 | 標準 | 60 | 60/240 | 25％ |
|               | 合計 | 240 |                   |           |

## スコア計算の例

次の例は、エンゲージメントスコアの計算を示しています。 説明されている役割の重み付けの割合、各購入グループメンバーのインバウンドアクティビティの数、各イベント発生の 1 日の上限 20 を使用します。

| 役割 | メンバー | アクティビティタイプ | 昨日のカウント | 今日のカウント | 計算 | 合計スコア |
|-------------- |--------- |-------------|-----------------|-------------|------|-----------|
|               |          |             |                 |             |      |           |
| 意思決定者 | Adam | 訪問済み web サイト | 37 | 15 | 20 + 15 | 35 |
|               |          | クリック済みメール | 1 | 1 | 1 + 1 | 2 |
|               |          |             |                 |             |      |           |
|               | Mark | 訪問済み web サイト | 5 | 3 | 5 + 3 | 8 |
|               |          | クリック済みメール | 1 | 1 | 1 + 1 | 2 |
|               |          | ダウンロード済みパブリッシャー | 3 | 2 | 3 + 2 | 5 |
| **意思決定者の合計スコア** |         |             |                 |             |      | **52** |
|               |          |             |                 |             |      |           |
| インフルエンサー | John | 訪問済み web サイト | 19 | 9 | 19 + 9 | 28 |
| **インフルエンサーの合計スコア** |         |             |                 |             |      | **28** |
|               |          |             |                 |             |      |           |
| 実務担当者 | Bob | クリック済みメール | 1 | 1 | 1 + 1 | 2 |
|               |          |             |                 |             |      |           |
|               | Paul | クリック済みメール | 1 | 1 | 1 + 1 | 2 |
|               |          |             |                 |             |      |           |
|               | Calvin | クリック済みメール | 1 | 1 | 1 + 1 | 2 |
|               |          | 訪問済み web サイト | 1 | 7 | 1 + 7 | 8 |
|               |          | ダウンロード済みパブリッシャー | 1 | 2 | 1 + 2 | 3 |
| **実務担当者の合計スコア** |         |             |                 |             |      | **17** |

最終的なエンゲージメントスコアは、各役割スコアの重み付けを適用して計算されます。

| 役割 | 役割の合計スコア | 役割の重み付け ％ | スコア X の重み付け ％ |
|-------------- |---------------- |------------- |---------------- |
| 意思決定者 | 52 | 41.67％ | 21.67 |
| 影響者 | 28 | 33.33％ | 9.33 |
| 実務担当者 | 17 | 25％ | 4.25 |
| **最終的なエンゲージメントスコア** |                |             | **35.25** |

## スコアリングロジック

計算の例で説明している計算ロジックに加えて、インスタンスのすべてのユーザー、購入グループおよびアカウントにわたって、システムで発生するスコアの正規化は非常に複雑です。 購入グループエンゲージメントスコアは、次の順序付きロジックに従って、ユーザーエンゲージメントスコアに依存します。

### 人物エンゲージメントスコアの計算ロジック

1. Web サイト訪問数、電子メールクリック数、ウェビナー出席など、重み付けと 1 日の割り当て量が関連付けられているすべての _エンゲージメントの重み付け_ アクティビティタイプを特定します。

1. 現在 30 日にハードコードされているアクティビティのルックバックウィンドウ内で実行されたすべてのユーザー _エンゲージメントの重み付け_ アクションを特定します。

1. 手順 1 で特定したすべての _エンゲージメントの重み付け_ アクティビティタイプの重み付けに対してアクティビティタイプの重み付けを正規化し、ルックバックウィンドウ内で発生しなかったものを無視します。

   この手順では _Min-Max 正規化_ を活用し、それらのほとんどを活用していないテナントのアクティビティタイプの重みの人為的な希釈を大幅に削減します。

1. ユーザーおよびアクティビティタイプごとに日別の割り当て量のフィルタリングを適用します。

   この手順は、スコアをゆがめる小さな値/大きなボリュームのアクティビティを回避することで、非常に大きな異常値を減らします。

1. アクティビティタイプごとの日別アクティビティの合計に関連する重みを掛け合わせ、ルックバックウィンドウのすべての日の結果を合計することで、生の人物エンゲージメントスコアを計算します。

1. _パワー変換_ （平方根）変換を使用すると、発生する可能性のある異常値を減らして分散を安定化できます。

   この変換により、歪度が低減され、データのパターンがより線形的になります。

1. 追加の _スケール正規化_ 変換を適用して、スコアが 0 から 100 の範囲全体を活用するようにします。

### 購入グループエンゲージメントスコアの計算ロジック

1. 役割テンプレートで設定された重み付けに従って、各購買グループ・メンバーにロール別に正規化された重み付けを適用します。

1. 各購買グループの購買グループ役割重量を標準化します。

   この正規化により、購買グループがすべてのロールを使用しない場合でも、ロールの重み付けの不必要な希薄化を回避できます。

1. 人物エンゲージメントスコアに人物の役割正規化された役割重みを乗算して、すべての購入グループメンバーの人物エンゲージメントスコアを集計し、それらを加算します。

1. _電力変換_ （平方根）変換を適用して、特に非常に大規模な購入グループの場合に、発生する可能性のある異常値を減らすことで分散を安定させます。

1. 追加の _スケール正規化_ 変換を適用して、スコアが 0 から 100 の範囲全体を活用するようにします。
