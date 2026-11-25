---
title: Adobe Journey Optimizer B2B Editionの同僚
description: CX Enterprise Coworkerを使用して、アカウントと個人のジャーニーを検索、作成、設定し、ドラフトのプレビューを確認して、ジャーニー作成を承認する方法を説明します。
feature: Account Journeys, Person Journeys, Agentic AI
role: User
level: Beginner
autotag-review: '2026-11-24T23:47:29.469Z'
TQID: 'https://experienceleague.adobe.com/gkizS-MB6qEMoG1pMqD3tSCBtcEuv-m-GMD5H6Z4JsY'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: 9b63d357-750f-5558-9208-62fc8a356785
    internal-label: Approval
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: c2f21a5c-bae4-56c6-97e3-2fc9a0e6c120
    internal-label: Use Cases
subfeature_v2:
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 81b4844bc7b333baaa2218639a542fefd512102f
workflow-type: tm+mt
source-wordcount: '780'
ht-degree: 2%
---

# [!DNL Adobe Journey Optimizer B2B Edition] における [!DNL CX Enterprise Coworker] {#coworker-overview}

[!DNL Adobe CX Enterprise Coworker] チャットを使用して[!DNL Adobe Journey Optimizer B2B Edition]のタスクを完了します。 目標を分かりやすい言葉で説明する。 [!DNL Coworker]さんが作業を計画し、それを実行し、結果を検証し、承認のために作業を提示します。

既存のアカウントと人物のジャーニーを検索したり、新しいドラフトジャーニーを作成したり、保存されたドラフトを更新したりできます。 [!DNL Coworker]さんが概要を検証済みのジャーニーグラフに変換し、ドラフトを作成する前にプレビューします。 [!DNL Coworker]さんがジャーニーを作成する前に、プレビューを明示的に承認する必要があります。

[!DNL Coworker]は、組織の既存の[製品権限](../admin/user-management.md#b2b-product-permissions)を尊重します。 既に実行が許可されているアクションのみを実行できます。 書き込みアクセス権を持つ場合は、管理者が制御します。 アクセス要件については、[AI アクセスの有効化](../ai-coworker/enable-ai-access.md)を参照してください。

[!DNL Coworker]は、[!DNL Journey Optimizer B2B Edition]だけでなく、Adobe エコシステム全体で機能します。 その広範な機能については、[Adobe CX Enterprise Coworker チャットの概要](https://experienceleague.adobe.com/en/docs/coworker/content/chat/overview){target="_blank"}を参照してください。 アプリを開いて会話を開始する方法については、[同僚インターフェイスガイド &#x200B;](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}を参照してください。

## ジャーニー能力 {#skills}

3つのスキルを使用して、ジャーニーの検査、ジャーニーグラフの作成、ノードの設定を行います。 スキル識別子は正確な技術名です。

| スキル | お客様のビジネスにどのように役立つのか | スキルの範囲の外 |
| --- | --- | --- |
| `journey-lookup-ajob2b` | アカウントと個人のジャーニーをリスト、カウント、検索、説明できます。 ノード、再入力設定、ジャーニーが使用するアクティビティ、属性、イベントオーディエンスを調べます。 このスキルではジャーニーは変更されません。 | ジャーニーの作成または変更、ルールの設定、メッセージのコピーの作成、購買グループテンプレートの管理、公開、削除を行うことができます。 |
| `journey-creation-ajob2b` | ブリーフをジャーニーに変換。 ジャーニータイプを選択し、オーディエンスを[!DNL Adobe Experience Platform]のオーディエンス IDに解決し、グラフを検証してプレビューします。 明示的な承認後にドラフトを作成します。 保存したドラフトのグラフと再入力設定を編集します。 | 既存のジャーニーの検索、ルールの設定、メッセージのコピーの作成、購買グループテンプレートの管理、オーディエンスの発見、公開、削除を実行できます。 |
| `journey-rules-ajob2b` | 保存済みジャーニーの未設定ノードで、分割された条件、アクション、イベント、動的リストオーディエンスを設定します。 | グラフの変更、ジャーニーの検索、電子メールやSMSのコピーの作成、オーディエンスの発見、公開を行うことができます。 |

プロンプトガイダンスについて詳しくは、「[B2B向けジャーニースキル &#x200B;](./journey-skills.md)」を参照してください。 アカウントと個人のオーディエンスを操作するには、[B2B アカウントとユーザーのオーディエンススキル &#x200B;](./audience-skills-b2b.md)を参照してください。

## ユースケースの例 {#use-cases}

別のリクエストを使用して、ドラフトを作成し、そのノードを設定し、既存のジャーニーを検査します。

### アカウントジャーニーの構築 {#build-account-journey}

概要からアカウントナーチャリングジャーニーを作成し、そのノードを設定します。

プロンプトの例：_ようこそ電子メールを送信し、3日間待ってから、ケーススタディ電子メールを送信するエンタープライズターゲットアカウントのオーディエンスのアカウントジャーニーを作成します。_

1. [!DNL Coworker] チャットのオーディエンスとジャーニーのフローを説明します。
1. 検証済みのジャーニーグラフとプレビューを確認します。 [!DNL Coworker]は、名前付きオーディエンスを[!DNL Experience Platform]のオーディエンス IDに解決します。
1. プレビューを明示的に承認します。 [!DNL Coworker]がドラフトを作成し、そのリンクを返します。
1. ドラフトの未設定のノードを設定するように[!DNL Coworker]に依頼します。
1. [!DNL Journey Optimizer B2B Edition]でドラフトを開いて、メッセージのコピーを追加し、ジャーニーを確認します。

その結果は、公開されたジャーニーではなく、ドラフトジャーニーです。 アプリケーションで[&#x200B; ジャーニーのレビューと公開手順](../journeys/create-publish-journey.md)を完了します。

### ジャーニーの調査と更新 {#inspect-update-journeys}

ジャーニーのインベントリを確認し、保存したドラフトの分割条件と再入力設定を調整します。

参照プロンプトの例：_アカウントジャーニーはいくつありますか？ ジャーニー14251のアカウント待機中の場所を表示します。_

1. [!DNL Coworker]に州ごとのジャーニー数の確認を依頼するか、名前またはIDでジャーニーを検索します。
1. 各ノードのジャーニーの詳細とアカウント数を確認します。
1. 更新する保存済みのドラフトを特定します。
1. [!DNL Coworker]に分割条件の設定を依頼します。 例：_下書きジャーニーの14252ークフローの場合、高いインテントのブランチに価格ページへの訪問が必要になります。_
1. 再エントリの変更をリクエストします。 例：_下書きジャーニーの14252ークフローの場合、アカウントが30日間再入力されるのを防ぎます。_

変更は保存されたドラフトに適用されます。 公開は別のステップです。 設定の詳細については、[&#x200B; パスの分割と結合](../journeys/split-merge-paths-nodes.md)および[ジャーニーの再エントリ &#x200B;](../journeys/journey-re-entry.md)を参照してください。

## MCP ツール {#mcp-tools}

[!DNL Coworker]は、ジャーニータスクに次のモデル コンテキスト プロトコル （MCP） ツールを使用します。 読み取りツールは既存の情報を検査し、チェックツールはグラフを検証し、書き込みツールはジャーニー設定またはドラフトを変更します。

| ツール | サポートされているアクション | タイプ |
| --- | --- | --- |
| `list_account_journeys` | アカウントジャーニーのページ分割リストを返します。 | 読み取り |
| `list_person_journeys` | ページ分割された個人ジャーニーのリストを返します。 | 読み取り |
| `count_account_journeys` | 州別のアカウントジャーニーをカウントします。 | 読み取り |
| `count_person_journeys` | 州別の個人向けジャーニーの数。 | 読み取り |
| `get_journey` | ジャーニーノードの読み取りと再入力設定。 | 読み取り |
| `get_journey_rules` | ジャーニーの未設定ノードの設定ターゲットを読み取ります。 | 読み取り |
| `get_journey_node_catalog` | ルール データの有効な入力である`ruleset_types`を返します。 | 読み取り |
| `validate_journey_graph` | 作成したドラフトグラフを検証します。 | チェック |
| `create_journey` | `confirm=false`でジャーニーをプレビューします。 明示的な承認の後、ドラフトを作成し、そのリンクを返します。 | 書き込み |
| `update_journey` | 保存したドラフトジャーニーのグラフを変更します。 | 書き込み |
| `set_journey_reentry` | 再入力設定を変更します。 | 書き込み |
| `set_journey_split_conditions` | 分岐の条件を設定します。 | 書き込み |
| `apply_journey_rules` | 条件、アクション、イベント、動的リスト オーディエンスに`rule_data`をジャーニーに適用します。 | 書き込み |
