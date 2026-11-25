---
title: B2B向けジャーニースキル
description: Workfront チャットを通じて、ジャーニーブリーフの準備、検証済みのドラフトグラフの確認、保存されたドラフトの設定、アカウントと個人のジャーニーの検査方法を説明します。
feature: Account Journeys, Person Journeys, Agentic AI
role: User
exl-id: 5d2945ab-4f6c-4d9c-b0a1-1a93dc1849f3
autotag-review: '2026-06-05T16:42:46.785Z'
TQID: 'https://experienceleague.adobe.com/SgjavYf2Tp5yO8s3f0DQexRCUILQRsD5bM6UwmbcgyE'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
subfeature_v2:
  - id: ff10f619-348f-47e3-99bf-3ce4c817cf2c
    internal-label: Agentic AI
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 876251dd1b69fc768c790daf0b9b1482015d69af
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%
---
# B2Bジャーニーのスキル

[!DNL Adobe CX Enterprise Coworker] チャットを使用して、[!DNL Adobe Journey Optimizer B2B Edition]でジャーニーを検索、作成、設定します。 概要から検証済みのドラフトを作成し、保存されたドラフトグラフと再入力設定を変更し、未設定のノードを設定します。 ジャーニーの変更は、アクティブなジャーニーではなく、保存されたドラフトに適用されます。

ルックアップ、作成、ルールのスキル識別子と、それらがサポートするアクションについては、[同僚ジャーニースキルリファレンス &#x200B;](./coworker-overview.md#skills)を参照してください。 この記事では、準備に関する簡単なガイダンスとジャーニーの観測可能性の例を提供します。

* [ジャーニー作成ガイダンス &#x200B;](#journey-creation-skills)：概要を作成し、作成する前にドラフトを確認します。
* [ジャーニーの可観測性に関するガイダンス &#x200B;](#journey-observability-skills)：アカウントとユーザーがアクティブなジャーニーをどのように移動するかについて質問します。

アプリを開いて会話を開始する方法については、[同僚インターフェイスガイド &#x200B;](https://experienceleague.adobe.com/ja/docs/coworker/content/chat/ui-guide){target="_blank"}を参照してください。

## ジャーニー制作のスキル {#journey-creation-skills}

ジャーニー作成スキルは、概要を検証済みのアカウントまたは個人のジャーニーグラフに変換します。 名前付きオーディエンスを[!DNL Adobe Experience Platform] オーディエンス IDに解決し、ドラフトを作成する前にグラフをプレビューします。

[!DNL Coworker]さんがドラフトを作成する前に、プレビューを明示的に承認する必要があります。 作成スキルでは、オーディエンスの検出、ノードルールの設定、メッセージのコピーの作成、ジャーニーの公開または削除は行われません。

### 概要の準備 {#basic-usage}

希望するジャーニーのドラフトを自然言語で記述します。 次の詳細を含めます。

* ジャーニーの種類：アカウントまたは人物。
* 既存オーディエンス：使用するオーディエンスの名前またはID。
* ジャーニーフロー：含めるアクション、待機、分岐。
* 再エントリの設定：アカウントまたはユーザーが再エントリできるかどうか、またはいつ入力できるか。

[!DNL Coworker]が目標を解釈できるように、キャンペーン概要から関連する詳細を含めます。 プレビューが意図したフローと一致しない場合は、リクエストを調整します。

![同僚チャットでのジャーニー作成プロンプト。](./assets/coworker-chat-b2b-journey-prompt.png){width="800" zoomable="yes"}

### ドラフトのレビューと作成 {#end-to-end-b2b-journey-creation}

検証済みのプレビューで、ジャーニーのタイプ、解決済みのオーディエンス、ノード、パスを確認します。 作成は、グラフがブリーフと一致する場合にのみ承認されます。

承認後、[!DNL Coworker]はドラフトを作成し、そのリンクを返します。 フォローアップリクエストを使用して、ルールスキルを使用して未設定のノードを設定します。 メッセージのコピーをアプリケーションに追加し、[&#x200B; ジャーニーのレビューと公開手順](../journeys/create-publish-journey.md)を完了します。

完全な例については、[&#x200B; アカウントジャーニーの構築](./coworker-overview.md#build-account-journey)を参照してください。

### 多段階のジャーニー

複数のステージがあるジャーニーの場合、各ステージのアクション、待機、分岐をブリーフに記述します。 グラフ構造を、ドラフト作成後に設定するルールとメッセージコピーと区別します。

保存したドラフトを修正するには、作成スキルを通じてグラフをリクエストするか、変更を再入力します。 未設定のノードの条件分割、アクション、イベント、動的リストオーディエンスにルールスキルを使用します。

## ジャーニーの観察能力 {#journey-observability-skills}

ジャーニーの可観測性に関するスキルでは、ジャーニーマップ、ログ、ダッシュボードなどを掘り下げることなく、アカウントや個人がB2B ジャーニーをどのように利用しているのかについて、自然言語で質問することができます。 主に、ジャーニーの進行とデータ同期のオブザーバビリティの2つの領域について説明します。

![ジャーニーの識別可能性に関するプロンプトと応答（[!DNL CX Coworker]](./assets/journey-observability-prompt-response.png){width="800" zoomable="yes"}）

### Account-level journey insight

特定のアカウントがジャーニーをどのように移動したのかを追跡し、次のような質問をすることで把握できます。

* 「Bodea Cloud アカウントに関する基本的な情報を教えてください」
* 「Northstar ServicesがABM ナーチャリング戦略において、どのように成功を収めたのかを教えてください。」
* 「このジャーニーは、いつContoso LLCが開始したのですか？」

### スプリットパスの推論とカウント

分岐が取得された理由と、各パスに続くユーザーまたはアカウントの数を理解します。

* 「なぜアカウント QiDemoAccount24はスプリットノード c764a9の小さな米国カリフォルニアのテクノロジーパスに行ったのですか？」
* 「スプリットノード node-459c7cの各パスの人数を教えてください。」
* 「アカウント 8のサンノゼ・パスにいる人を見せてください。」

ジャーニーの識別可能性のあるスキル分割ロジック、アカウント属性、アクティビティを分析して、ルーティングの意思決定を説明し、パスごとのカウントや人物リストを返します。

### 個人レベルのジャーニーの結果

アカウント内またはジャーニー全体の個々の結果を分析できます。特に、購買グループの分析や意思決定者とインフルエンサーの行動の比較に役立ちます。

* 「Bodea Next Web Engagement ジャーニーの分割パスごとに人数を指定してください。」
* 「隠れたスキップパスのユーザーをリストアップする」
* 「このアカウントのサンディエゴのロケーションパスにいる人を表示してください。」

### ジャーニーのライフサイクルとタイミング

ジャーニーまたは特定のアカウントのキータイムスタンプを取得します。

* 「この旅行はいつ公開されましたか？」
* 「最初のアカウントがこのジャーニーに入ったのはいつですか？」
* 「アカウント QiDemoAccount50がこのジャーニーを開始したのはいつですか？」

### 外部オーディエンスとアクティベーションの可視化

LinkedInなどの外部チャネルにプッシュするジャーニーの場合、アクティベーションステータスを確認できます。

* 「bsmith@acme.comは外部オーディエンスにありますか？」
* 「ObservabilityExtAudience01を通じてLinkedInにアクティベートされたすべてのユーザーを一覧表示します。」

### データ同期とパイプラインの可観測性

ジャーニーの識別可能性スキルは、データ同期の正常性情報を表示して、アカウントまたはリードがジャーニーに含まれていない理由をトラブルシューティングするのに役立ちます。

* 外部オーディエンス書き出しのジョブ指標とステータス
* バッチセグメント化スケジュールと完了時間
* 購買グループのメンテナンスのスケジュール
* ジョブマネージャーの統計（完了/失敗）