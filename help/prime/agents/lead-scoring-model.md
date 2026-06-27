---
title: カスタムスコアリングモデルの作成
description: AI アシスタントのチャットインターフェイスにあるScoring Studio スキルを使用して、Journey Optimizer B2B Primeでカスタムリードスコアリングモデルを構築、プレビュー、公開します。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
autotag-review: '2026-06-25T21:20:26.754Z'
TQID: 'https://experienceleague.adobe.com/-D5EaJ-3GQ5iwaE6hChscZGEdflKmZ3tdp6VUNuPjWk'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: bef5003b-cad2-4f40-bdb2-a80426d52ef5id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: ff10f619-348f-47e3-99bf-3ce4c817cf2cid: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: d8f352c636ebd8980614922099701de8f755e8e4
workflow-type: tm+mt
source-wordcount: 489
ht-degree: 2%

---

# カスタムスコアリングモデルの作成

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_scoring_studio"
>title="Scoring Studio"
>abstract="Scoring Studioのスキルを使用して、AI アシスタントのチャットインターフェイスで独自のリードスコアリングモデルを作成、設定、公開できます。"

[!DNL Adobe Journey Optimizer B2B Prime]の&#x200B;[_Scoring Studio_ スキル ](./skills.md#scoring-signals)は、リードスコアリングモデルを作成、設定、公開できるAI ネイティブのリードスコアリングソリューションを提供します。 エージェント駆動型ワークフローとビジュアル UIを組み合わせたこのスタジオでは、[AI アシスタント チャット インターフェイス ](./chat-interface.md)の自然言語プロンプトを使用するか、UI コントロールと直接やり取りすることで、スコアリングモデルを構築できます。

* **スキル** - `scoring-studio`
* **Invocation** - スラッシュコマンドを使用してScoring Studioを開きます。 例：_&quot;open Scoring Studio.&quot;_
* **スコアリングサービスの読み取り/書き込み先** - [!DNL Journey Optimizer B2B Prime]、リードフィールドとアクティビティタイプの読み取り[!DNL Marketo Engage]

ローンチ時に、AI アシスタントは、アクティビティタイプ、リードフィールド、人物リスト、既存のスコアリストなどの関連コンテキストを自動的に取得し、データ内の提案を基盤にします。

AI アシスタント チャットインターフェイスで![Scoring Studioを開始](./assets/scoring-studio.png){width="700" zoomable="yes"}

## スコアリングモデルの作成 {#create-model}

Scoring Studioを開くと、AI Assistantは、静的リストと一連のスコアリングアクティビティを事前に入力した、関連性の高いサンプルスコアリングモデルを提案します。 この提案された開始点を受け入れるか、独自のプロンプトを指定してカスタムモデルを定義できます。

### モデルのプレビュー {#preview-model}

プロンプトを入力すると、AI アシスタントは変更を加える前にモデルのプレビューを生成します。 プレビューは次のように表示されます。

* 使用中のスコアリングディメンション
* 属性とアクティビティのスコアリング
* セグメントとして適用された静的リストまたはスマートリスト
* モデルの目標、ターゲットセグメント、主要シグナルの概要

プレビューを確認し、それに基づいてモデルを作成するか、チャットを通じて引き続き調整してから確定することができます。

### モデル構造 {#model-structure}

作成されたモデルは、_ディメンション_&#x200B;と&#x200B;_シグナル_&#x200B;に整理されています。 UIのプロパティパネルを使用して、各信号を設定できます。

* **信号タイプ** — アクティビティベースまたは属性ベース
* **アクティビティまたは属性** — スコアリングする特定の項目
* **信号パラメーター** – 信号の調整可能な設定

自然言語を使用してエージェント全体でモデルを構築および設定したり、UI コントロールと直接やり取りしたりできます。

## スコアリングモデルの公開 {#publish-model}

モデルが完成したら、それを公開するようにエージェントに指示します。 公開プロセスでは、次の処理が自動的に行われます。

| ステップ | 何が起こるか |
|---|---|
| **ルールのコンパイル** | すべてのスコアリングルールがコンパイルされ、検証されます |
| **スコアタスクの作成** | スケジュールされたスコアタスクが作成され、毎日実行するように設定されます |

公開後は、スコアを即座に処理する手動実行をトリガーすることもできます。

## スコアリング結果の表示 {#view-results}

スコアリング実行が完了すると、リード読み込みプロセスを介してスコアが[!DNL Marketo Engage]に書き戻されます。 読み込みが完了すると、更新されたスコアを[!DNL Marketo Engage]で直接確認できます。

各実行後、次のような結果の概要を表示できます。

* スコアリングされた人数
* 個人スコアは1人ごとに変化します

監査ログを使用して、追加の実行の詳細を確認できます。
