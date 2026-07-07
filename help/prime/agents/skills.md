---
title: AI アシスタントのスキル
description: Journey Optimizer B2B PrimeのAI アシスタントのスキルを確認しましょう。プログラム、ジャーニー、オーディエンス、スコアリング、コンテンツ、送信時間の最適化用にパッケージ化されたワークフローです。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
autotag-review: '2026-06-24T23:55:36.649Z'
TQID: 'https://experienceleague.adobe.com/iIi07OBWKxxa-oW-A6VrlkoTS02kmCx8kfMaCe-C-4o'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: bef5003b-cad2-4f40-bdb2-a80426d52ef5id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: ff10f619-348f-47e3-99bf-3ce4c817cf2cid: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 4632a06ce5a17713fdcaecf6eac8c051bc984e28
workflow-type: tm+mt
source-wordcount: 582
ht-degree: 11%

---

# AI アシスタントのスキル

_スキル_&#x200B;は、エージェントが実行方法を把握しているパッケージ化されたワークフローです。`/` メニューと自然言語リクエストの両方の背後にある構成要素です。 各スキルには、ステップバイステップの指示と、1つのジョブに必要な特定のツール（例えば、「ジャーニーの公開」、「2人のリストの比較」、「スコアリングモデルの構築」）がバンドルされています。

>[!NOTE]
>
>各スキルは、スキルが[!DNL Journey Optimizer B2B Prime]または[!DNL Marketo Engage]状態（**Write**）、クエリ/分析/生成（**Read**）のみか、同等クエリ+変異関数（**Read+Write**）のどちらに基づいて分類されます。

## プログラムとプランニング {#programs-planning}

| スキル | 機能 | アクセス | 製品サーフェス | 影響/データフロー |
|---|---|---|---|---|
| `falco-program-creation` | エンドツーエンドの[!DNL Journey Optimizer B2B Prime] プログラム作成 – プログラム、サブフォルダー、トークン、リスト、ジャーニー。 | 書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime]。 _[概要からプログラムを作成](./program-from-brief.md)_&#x200B;を参照してください。 |
| `adapt-program` | [!DNL Journey Optimizer B2B Prime]適応のために[!DNL Marketo Engage] プログラムから移行ストーリーを生成します。 | 読み取り | [!DNL Journey Optimizer B2B Prime] | [!DNL Marketo Engage]を読み取り、[!DNL Journey Optimizer B2B Prime]を書き込みます |
| `folder-creation` | アセットツリーに組織フォルダーを作成します。 | 書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `program-creation` *（ビルド プログラム）* | キャンペーン概要からMarketoプログラムを作成します。 | 書き込み | [!DNL Marketo Engage] | 読み取り+書き込み[!DNL Marketo Engage] |
| `program-planning` *（プラン キャンペーン）* | ブリーフを設定/実装ドキュメントに変換。 | 読み取り | [!DNL Marketo Engage] | [!DNL Marketo Engage]を読み取ります |
| `program-qa` *（プログラムの検証）* | プログラムの検証/監査（ルールのみ、テスト計画、概要）。 | 読み取り | [!DNL Marketo Engage] | [!DNL Marketo Engage]を読み取ります |

## ジャーニー {#journeys}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `journey-creation` | 自然言語からカスタマージャーニーを作成、編集。 | 書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `journey-edit-dates` | 公開せずにジャーニーの開始日/終了日を変更します。 | 書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `journey-publish` | ユーザージャーニーの公開/立ち上げ/スケジュール： | 書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `journey-stop` | ジャーニーを中断、閉じる、停止、停止、または終了します。 | 書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `journey-reentry` | 再エントリを設定：許可/禁止、クールダウン、最大エントリ。 | 書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `journey-trafficcontrol` | プロファイルのルーティングを示すトラフィック制御シミュレーションを実行します。 | 読み取り | [!DNL Journey Optimizer B2B Prime] | [!DNL Journey Optimizer B2B Prime] （シミュレーション）を読み取ります |
| `journey-observability` | デバッグ/監視の進行状況 – パス、タイミング、分割、ストール、ドウェル。 | 読み取り | [!DNL Journey Optimizer B2B Prime] | [!DNL Journey Optimizer B2B Prime] + [!DNL Marketo Engage]を読み取ります（静的リスト チェック） |

## オーディエンスと人 {#audiences-people}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `audience-creation` | [!DNL Marketo Engage] スマートリストの適応、ユーザーリストの作成、ルールの追加/更新。 | 書き込み | [!DNL Journey Optimizer B2B Prime] | [!DNL Marketo Engage]を読み取り、[!DNL Journey Optimizer B2B Prime]を読み取り/書き込みます。  「_[プログラムのオーディエンスを作成](./audience-creation.md)_」を参照してください。 |
| `people-list-comparison` | 2つの人物リストを比較し、重複するメンバーを表示します。 | 読み取り | [!DNL Journey Optimizer B2B Prime] | [!DNL Journey Optimizer B2B Prime]を読み取ります |
| `import-leads` | CSV データ品質を検査し、[!DNL Marketo Engage]へのインポートをコミットします。 | 読み取り/書き込み | 両方 | 読み取り+書き込み[!DNL Marketo Engage] |
| `lead-investigation` *（リードの調査）* | リードのアクティビティ、スコアリング、クオリフィケーション、ライフサイクルを調査し、 | 読み取り | [!DNL Marketo Engage] | [!DNL Marketo Engage]を読み取ります |

## コンテンツとチャネル {#content-channels}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `content-personalization` | テンプレートの参照/プレビュー、コンテンツの編集/バリエーションの生成。 | 読み取り/書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `asset-tokens` | プログラム/フォルダー/ジャーニーでの完全なトークン CRUD。 | 読み取り/書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `fcs-channels` | チャネル検索とCRUD + パブリッシュ/停止/削除。 | 読み取り/書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |

## スコアリングとシグナル {#scoring-signals}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `scoring-studio` | スコアリングモデルのリスト作成/取得、構築/公開。 | 読み取り/書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] （スコアリングサービス）; [!DNL Marketo Engage]個のリードフィールド/アクティビティタイプを読み取ります。 _[カスタムスコアリングモデルの作成](./lead-scoring-model.md)_&#x200B;を参照してください。 |
| `engagementconfiguration` | エンゲージメント設定とウェイトの編集/更新を表示します。 | 読み取り/書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `intentconfiguration` | インテント設定とウェイトの設定/更新を表示します。 | 読み取り/書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `intent-query` | 人物/セグメント/リスト別のインテントスコアのクエリと説明。 | 読み取り | [!DNL Journey Optimizer B2B Prime] | [!DNL Journey Optimizer B2B Prime]を読み取ります |

## 送信時間の最適化 {#sto}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `send-time-optimization` | メールノードでSTO ステータスを確認し、有効/無効にします。 | 読み取り/書き込み | [!DNL Journey Optimizer B2B Prime] | 読み取り+書き込み[!DNL Journey Optimizer B2B Prime] |
| `send-time-report` | STO パフォーマンスレポートを取得/表示します。 | 読み取り | [!DNL Journey Optimizer B2B Prime] | [!DNL Journey Optimizer B2B Prime]を読み取ります |

## 知識 {#knowledge}

| スキル | 機能 | アクセス | 製品 | バックエンド（データフロー） |
|---|---|---|---|---|
| `product-knowledge` | Experience Leagueに関する[!DNL Journey Optimizer B2B Prime] ドキュメントのハウツー/コンセプトに関する質問に答えます。 | 読み取り | 両方 | 外部ドキュメントを読み取り – 製品データなし |

## クロスバックエンド {#cross-backend}

これらのスキルは、複数のバックエンドにまたがっています。

- **`adapt-program`** — `gather_program_assets`は[!DNL Marketo Engage] （`get_program`、`get_smart_campaign`、`list_emails`）を読み取り、次に`falcomcp_create_journey`経由で書き込みます。従来のクロスバックエンドです。
- **`audience-creation`** — [!DNL Marketo Engage] スマートリスト （`get_smart_list` / `get_smart_campaign`）を読み取り、[!DNL Journey Optimizer B2B Prime]人のユーザーリストを書き込みます。
- **`journey-observability`** — [!DNL Journey Optimizer B2B Prime]件の読み取りに加えて`check_lead_in_marketo_static_list` [!DNL Marketo Engage]件の読み取り。
- **`scoring-studio`** — [!DNL Journey Optimizer B2B Prime]個のスコアリングサービスと共に[!DNL Marketo Engage]個のリードフィールド/アクティビティタイプを読み取ります。

すべての`falco-mcp_*`およびジャーニー/トークン/スコアリング/STO/FCS ツールが[!DNL Journey Optimizer B2B Prime] サービスにヒットし、CSV/プログラム/リードツールが[!DNL Marketo Engage]にヒットしました。

