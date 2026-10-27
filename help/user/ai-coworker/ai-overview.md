---
title: JOURNEY OPTIMIZER B2B EDITIONのAI機能
description: AIを利用して、ワークフローを高速化 – Journey Optimizer B2B Editionの製品情報、トラブルシューティング、運用に関するインサイトを活用できます。
feature: AI Assistant
role: User, Admin
level: Beginner
exl-id: 52ff66d2-1969-4e2c-985a-c75e613368de
autotag-review: '2026-06-05T16:05:30.499Z'
TQID: 'https://experienceleague.adobe.com/4bXkOzwadjZVzhedVO6oQEEV1biaWMZFHEuqey74qek'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
    internal-label: AI Assistant
subfeature_v2:
  - id: eb7448d0-50e6-41cc-83e2-a84cd2413491
    internal-label: Operational Insights
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
    internal-label: Artificial intelligence
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: c2d3ba94927361f7695e901ef9071bdd4ded8f7d
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 8%
---
# JOURNEY OPTIMIZER B2B EDITIONのAI機能

[!DNL Adobe Journey Optimizer B2B Edition]のAI機能を使用して、コンテンツを生成し、製品知識を検索し、運用上のインサイトを得ます。

>[!IMPORTANT]
>
>[!DNL Journey Optimizer B2B Edition]でAI機能を使用するには、[ ユーザーガイドライン ](https://www.adobe.com/jp/legal/licenses-terms/adobe-gen-ai-user-guidelines.html){target="_blank"}への同意が必要です。 この契約書には、公開ベータ版の契約書も含まれているため、追加のAI対応機能をロールアウト時に使用できます。

+++ユーザー契約書インターフェイスの表示

![ ユーザー契約書の最初のページ。](./assets/user-agreement-1.png)

![ ユーザー契約書の最後のページ。](./assets/user-agreement-2.png)

+++

## [!DNL Coworker] アプリを使用 {#coworker-app}

コンテンツの生成以外のすべてのチャットワークフローに[!DNL CX Enterprise Coworker] アプリのインターフェイスを使用します。 製品に関する質問をしたり、業務上のインサイトを確認したり、B2B アカウントとユーザー向けに[ ジャーニースキル ](../agents/journey-agent.md)と[ オーディエンススキル ](../agents/audience-agent-b2b.md)を活用したりできます。 コンテンツの生成は、[!DNL Journey Optimizer B2B Edition]内で引き続き利用できます。

アプリを開く、会話を開始する、チャット機能を使用する方法については、[CX Coworker インターフェイスガイド ](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}を参照してください。

[!DNL Coworker]件のチャットクエリを送信する前に、必要な問い合わせタイプを検討してください。

### 製品知識

製品知識とは、[!DNL Adobe Experience League]に関する[!DNL Journey Optimizer B2B Edition] ドキュメントに基づいた概念とトピックを指します。 製品知識に関する質問は、さらに次のサブグループに指定できます。

| 製品知識 | 例 |
| --- | --- |
| ターゲットを絞った学習 | <li>購買グループとは？ <li> 購買グループの役割テンプレートの例を教えてください？ |
| オープン検出 | <li>購買グループを作成する手順？ <li>購買グループの役割テンプレートでカスタムフィールドを使用するにはどうすればよいですか？ |
| トラブルシューティング | <li>ジャーニーの購買グループが作成されなかったのはなぜですか？ <li>ジャーニーでリッスンするエクスペリエンスイベントが見つからないのはなぜですか？ |

### 運用上のインサイト

_運用上のインサイト_&#x200B;とは、[!DNL Coworker]がメタデータオブジェクト（属性、アカウントオーディエンス、データフロー、データセット、宛先、アカウントジャーニー、スキーマ、ソース、購買グループテンプレート、ソリューションの興味）について生成する回答を指します。 それらのインサイトには、カウント、ルックアップ、リネージへの影響などが含まれます。 サンドボックス内のデータは表示されません。

* オーディエンスサイズが最も大きいアカウントオーディエンスとそのサイズは何ですか？
* これまでジャーニーで使用されていないアカウントオーディエンスの数？
* ソリューションの関心&#x200B;_x_&#x200B;を使用するアクティブなジャーニーはどれですか？

次のドメインで、運用上のインサイトについて[!DNL Coworker]件の質問を行うことができます。

| ドメイン | サポートされているメタデータ | サポートされていないメタデータ |
| --- | --- | --- |
| 属性/フィールド | <li>属性名検索 <li>属性 – スキーマ関係 <li>属性 – データセットの関係 <li>属性 – オーディエンス関係 <li>属性 – 宛先関係 | <li>属性クラス <li>監査 <li>非推奨ステータス <li>ラベル <li>属性に保存された値 |
| アカウントオーディエンス <br><br>**_注:_** [!DNL Journey Optimizer B2B Edition]のコンテキストでは、[!DNL Coworker] チャットはアカウントオーディエンスに関するオーディエンスの質問にのみ回答できます。 [!DNL Adobe Experience Platform] コンテキストでは、[!DNL Coworker] チャットは個人オーディエンスに対してのみ質問に答えることができます。 | <li>オーディエンス数 <li>オーディエンスタイプ（ストリーミングまたはバッチ） <li>作成日/変更日 <li>アクティベーションステータス <li>メンバー数 <li>オーディエンスの重複 <li>名前とID検索 | <li>オーディエンスの重複 <li>オーディエンスアクティベーション <li>監査 <li>作成/修正 <li>ラベル <li>メンバーの選定のトレンド |
| データフロー | <li>データフロー数 <li>データフローステータス <li>データフロー – データセットの関係 <li>データフロー – ソース関係 | <li>制作/修正 <li>データフローとバッチの関係 <li>取り込みプロファイル数 |
| データセット | <li>データセット数 <li>プロファイル有効ステータス <li>作成/変更日 <li>データセット – スキーマ関係 <li>データセット – オーディエンスの関係 <li>データセット – 属性関係 <li>データセット – データフローの関係 <li>名前検索 <li>名前とID検索 | <li>監査 <li>作成者 <li>データセット – バッチ関係 <li>データセットの作成/修正 <li>データセットサイズ <li>プロファイル数 <li>行数 <li>値検索 |
| 宛先 | <li>設定済みの宛先数 <li>宛先 – オーディエンスの関係 <li>配信先属性の関係 | <li>アカウント設定 <li>アカウント資格情報 <li>一意のプロファイルがアクティブ化されました |
| ジャーニー（アカウントジャーニー） | <li>カウント <li>名前とID検索 <li>ジャーニーステータス <li>作成日/変更日 | <li>属性 – ジャーニーの関係 <li>監査 <li>制作/修正 <li>作成者 |
| スキーマ | <li>スキーマ数 <li>作成/変更日 <li>スキーマ – 属性関係 <li>スキーマ – データセットの関係 <li>スキーマ – オーディエンス関係 <li>プロファイル有効ステータス <li>名前検索 <li>名前とID検索 | <li>監査 <li>制作/修正 <li>作成者 <li>フィールドグループ <li>ID <li>ID 名前空間 <li>ラベル <li>プロファイル数 |
| ソース | <li>アカウント数 <li>アカウントステータス <li>各アカウントのアクティブ/非アクティブなデータフロー <li>Source コネクタ – データフローリレーションシップ <li>Source アカウント – データフローリレーションシップ | <li>アカウント資格情報 <li>アカウント設定データ取り込み指標 <li>プロファイルの数ソース – バッチ関係 |
| 購買グループテンプレート | <li>カウント <li>ステータス <li>ロール <li>名前とID検索 | <li>役割ルール |
| ソリューションへの関心 | <li>カウント <li>ステータス <li>ソリューションへの関心 – 購買グループテンプレートの関係 <li>名前とID検索 | <li>ソリューションへの関心 – 購買グループの関係 |

{style="table-layout:fixed"}

運用上のインサイトに関する質問の場合、回答がUIの現在の状態を反映しない場合があります。 これらの質問を裏付けるデータは、24時間ごとに更新されます。 例えば、ユーザーが日中に[!DNL Adobe Real-Time Customer Data Platform]に加えた変更は、夜間にデータストアと同期され、朝にユーザーからの質問に対応できるようになります。 オブジェクトに関連する特定のデータについて問い合わせるには、サンドボックスにサインインします。

### プライバシー、セキュリティ、ガバナンス

[!DNL Journey Optimizer B2B Edition]の[!DNL Coworker] チャットでは、プライバシー、セキュリティ、ガバナンスが優先されます。 次の情報を確認して、[!DNL Coworker] チャットから期待できる、顧客の信頼に焦点を当てた機能について確認します。

* [!DNL Coworker]は、トレーニング目的であっても、今日は個人データを使用しません。

* [!DNL Coworker] チャットでの以前のインタラクションの30日間のログを表示できます。

* [!DNL Coworker]は、プロンプトに応答する際に、サンドボックス固有のデータとパブリック Adobe ドキュメントに基づいています。 データはサンドボックス間で共有されません。

* [!DNL Coworker] チャットに入力したプロンプトは、他の顧客には共有されません。

## 次の手順

[!DNL Coworker] チャットの概要を理解したうえで、ワークフロー中にチャットを有効にして使用します。 詳しくは、次のドキュメントを参照してください。

* [AI機能へのアクセスを有効にする](./enable-ai-access.md)
* [質問ガイダンス](./question-guidance.md)
* [CX Coworker インターフェイスガイド](https://experienceleague.adobe.com/en/docs/coworker/content/chat/ui-guide){target="_blank"}
