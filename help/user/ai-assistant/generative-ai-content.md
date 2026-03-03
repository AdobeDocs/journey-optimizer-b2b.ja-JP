---
title: コンテンツ用ジェネレーティブ AI
description: プロンプトのベストプラクティスなど、 [!DNL Journey Optimizer B2B Edition] で生成 AI を使用して、パーソナライズされたメールやランディングページを作成する方法を説明します。
feature: AI Assistant, Generative AI, Content
level: Beginner
topic: Artificial Intelligence
role: User
source-git-commit: d3238fa94f28c6d7e3fc0dce5b59fd70d8e74e34
workflow-type: tm+mt
source-wordcount: '2506'
ht-degree: 32%

---

# コンテンツ用ジェネレーティブ AI {#generative-ai-content}

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-settings"
>title="AI コンテンツ生成"
>abstract="レイアウトを作成したら、生成 AI ツールを使用してコンテンツ [!DNL Journey Optimizer B2B Edition] 強化できます。 この機能は、説明的なプロンプトに従ってコンテンツを微調整することで、パーソナライゼーションとコンテンツ改善のプロセスを簡素化します。"

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-reference-context"
>title="参照コンテンツ"
>abstract="_コンテンツを参照_ を使用して、[!DNL Journey Optimizer B2B Edition] での生成 AI に関する追加のコンテキストを提供するコンテンツを含むアセットファイルをアップロードしたり、以前にアップロードしたファイルを選択したりします。 このオプションにより、生成されるコンテンツの品質と関連性を高めるために必要なすべての資料が利用できるようになります。"

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-start"
>title="Adobe生成 AI 用語"
>abstract="この機能へアクセスするには、Adobe Experience Cloud 生成 AI ユーザーガイドラインへの同意が必要です。 この機能から出力される精度をレビューし、ユースケースに適していることを確認します。"
>additional-url="https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html" text="Adobe 生成 AI ユーザーガイドライン"

Microsoft Azure OpenAI とAdobe Fireflyを活用した [!DNL Adobe Journey Optimizer B2B Edition] コンテンツ用のジェネレーティブ AI は、テキストや画像に対するプロアクティブなコンテンツバリエーションの提案を提供します。 様々なメインタイトルや画像を試して、コンテンツへの影響を最適化します。

Adobeの生成 AI 機能を活用するには、コンテンツ作成 [!DNL Journey Optimizer B2B Edition] 生成 AI 機能を使用します。 メール、SMS メッセージ、ランディングページなどに対して、パーソナライズされたテキストやビジュアルを作成します。 完全なキャンペーンを作成する場合や、特定のアセットを単に絞り込む場合は、これらの機能を使用すると、貴重な時間を節約しながら、コンテンツをブランドガイドラインとシームレスに連携させることができます。

<!--
Generate multiple variants and build an experiment to compare them. Leveraging Journey Optimizer Content Experiment, you can define multiple message treatments to measure which one performs best for your target audience. You can choose to vary the delivery content, or subject. The message audience is randomly allocated to each treatment to determine which one works best in terms of the specified metric. Learn more about Content Experiment in this section. -->

>[!IMPORTANT]
>
>[!DNL Journey Optimizer B2B Edition] のこれらの機能にアクセスするには、_[!UICONTROL AI アシスタント]_/_[!UICONTROL コンテンツを生成]_ 権限が必要です。 製品管理者が機能に対する権限を付与する方法について詳しくは、「製品権限の役割の編集 [&#x200B; を参照してください &#x200B;](../admin/user-management.md#edit-roles-for-product-permissions)。

コンテンツ生成用の AI アシスタント ツールは、次のアセット タイプでサポートされています。

* [メール](../content/ai-assistant-emails.md)
* [!BADGE Beta][&#x200B; ランディングページ &#x200B;](../content/ai-assistant-landing-pages.md)

## 一般的なガイドラインと制限事項 {#general-guidelines-and-limitations}

ジェネレーティブ AI 機能を使用する際は、[Adobe Experience Cloud ジェネレーティブ AI ユーザーガイドライン &#x200B;](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"} に従ってください。 AdobeAdobeは、メディアの作成に生成 AI ツールを使用する際の透明性に取り組んでおり、ダウンロードまたは書き出し時に、[!DNL Firefly] 生成アセットを含むすべてのコンテンツまたはプロジェクトに [&#x200B; コンテンツ資格情報 &#x200B;](https://helpx.adobe.com/firefly/web/get-started/learn-the-basics/content-credentials-overview.html){target="_blank"} を適用します。

[!DNL Journey Optimizer B2B Edition] のコンテンツに生成 AI を使用するための一般的なガイドラインを確認します。

* 生成 AI モデルに対して明確に定義されたプロンプトを使用し、正確に解釈します。 指定するマーケティングの目的やプロンプトは、生成されるコンテンツの品質に強く影響します。

* コンテンツ参照ファイルをアップロードして、正確なオンブランドコンテンツを作成する。 それ以外の場合、コンテンツは、公開されている情報に基づいています。 アップロードされるコンテンツは、PDF、JPEG、PNG、ZIP （サポートされているファイル形式を含む）のいずれかのファイル形式になります。 アップロードできるファイルの最大サイズは 50 MB です。 ファイルのサイズが大きい場合や画像の数が多い場合でも動作しますが、処理時間が長くなります。

* ブランド固有またはカスタムテンプレートを使用して、メールコンテンツを作成します。 最大 8～10 個の画像を使用するメールテンプレートを推奨します。

* バリアントを選択する際は、サムアップ、サムダウンまたはフラグアイコンを使用して、問題のある出力を報告してください。

## ジェネレーティブ AI の迅速なベストプラクティス {#generative-ai-prompting-guide}

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai_content_prompt"
>title="迅速なガイダンス"
>abstract="コンバージョン [!DNL Journey Optimizer B2B Edition] 高いオンブランドのマーケティングコンテンツを生成する効果的なプロンプトを作成する方法については、このドキュメントを参照してください。"

このガイドは、リクエストを構造化し、明確に意図を伝え、ブランドガイドライン、オーディエンスのニーズ、キャンペーンの目標に沿ったメッセージを AI が確実に生成するのに役立ちます。

AI アシスタントが目標に合わせてカスタマイズされた高品質でブランドに即したマーケティングコンテンツを生成できるようにする効果的なプロンプトを書き込む方法について説明します。

### CO-STAR フレームワークの使用 {#costar-framework}

生成されるコンテンツを最適に活用するには、CO-STAR フレームワークを使用してプロンプトを整理します。 この構造化アプローチにより、必要なものをはっきりと示すことができます。

| コンポーネント | 意味 | これが重要な理由 |
| --- | ---- | ------ |
| **C - コンテキスト** | キャンペーン、製品または状況に関する背景 | 全体像を把握する |
| **O - 目標** | 特定のマーケティング目標 | コンテンツが達成すべき目標を推進します |
| **S - スタイル** | コミュニケーション方法 | アプローチを設定します |
| **T - トーン** | 感情的なスタイルと声 | メッセージの雰囲気を形作ります |
| **A - オーディエンス** | ターゲットとするオーディエンス | メッセージが適切な人物の共感を得られるようにします |
| **R - 要件** | 特定の制約または必須 | 境界と重要な要素を定義します |

{style="table-layout:fixed"}

### 必須メッセージ {#key-takeaways}

<table style="table-layout: fixed; width: 100%; border: 0;">
<thead style="border: 0; background-color: #FFFFFF;">
<tr>
<th>推奨</th>
<th>非推奨</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul><li>構造に CO-STAR フレームワークを使用
<li>新規コンテンツと既存のコンテンツを明確に区別
<li>特定の抽出ガイダンスでドキュメントの使用に焦点を当てる
<li>トーン、戦略、ロケールの選択
<li>マーケティング目標とコンテンツタイプの機能を一致
<li>A/B テスト用に複数のバリアントを生成</ul>
</td>
<td>
<ul><li>プロンプトで構造の変更、スタイル設定、画像編集を依頼
<li>オプションで使用可能な場合は、プロンプトでトーン/戦略に言及します
<li>_promote the product_（製品のプロモーション）など、あいまいな目標を使用する
<li>条件付き要素の選択をリクエスト
<li>プロンプトを通じてレイアウトの変更を想定</ul>
</td>
</tr>
</tbody>
</table>

### プロンプトでサポートされていないコンテンツ

>[!TIP]
>
>視覚的/画像的な変更には、デザインツールまたは [!DNL Adobe Express] を使用します。

次のリクエストはサポートされていません **_サポートされていません_**。他のツールを使用して処理する必要があります。

<table style="table-layout: fixed; border: 0;">
<thead style="border: 0; background-color: #FFFFFF">
<tr>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="赤十字">  メール構造の変更</th>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="赤十字">  視覚スタイルの変更</th>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="赤十字">  画像編集操作</th>
</tr>
</thead>
<tbody>
<tr style="border: 0;">
<td>
<ul>
<li>変更する特定のセクションの選択</li>
<li>要素の削除または複製</li>
<li>条件付き選択</li>
<li>レイアウトセクションの追加または削除</li>
</ul>
</td>
<td>
<ul>
<li>テキストの書式設定（太字、斜体、フォントサイズ）</li>
<li>カラーの変更</li>
<li>レイアウトのスタイル設定（境界線、パディング、余白）</li>
<li>視覚エフェクト（シャドウ）</li>
</ul>
</td>
<td>
<ul>
<li>背景の変更</li>
<li>テキストオーバーレイまたはロゴの追加</li>
<li>画像の切り抜きまたはサイズ変更</li>
<li>カラー調整</li>
<li>画像の置換</li>
</ul>
</td>
</tr>
</tbody>
</table>

### 品質チェックリスト {#quality-checklist}

コンテンツを生成する前に、次の点を確認します。

![&#x200B; 緑色のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"}**目的を明確**：アクション、製品/サービス、値およびコンテキストを明確に示します。

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"}**定義済みのターゲットオーディエンス**：人口統計、役割またはセグメントを指定します。

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"}**コンテンツタイプの位置揃え**：目的は、選択したチャネルまたは形式に一致します。

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"}**レビューの選択項目**：トーン、戦略、ロケールを選択する場合は、プロンプトに含めないでください。

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"}**ドキュメントフォーカスの指定**：参照するコンテンツまたはセクションをハイライト表示します。

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"}**ブランドが適用されています**：適切なブランドガイドラインが選択されています。

![&#x200B; 緑色のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"}**現実的な範囲**：レイアウトの変更、スタイル設定、構造の編集をリクエストしません。

### 効果的なマーケティングの目標 {#marketing-objectives}

マーケティング目標を作成する際は、明確で実用的かつ測定可能であることを確認します。 あいまいなステートメントや汎用ステートメントは回避します。

**優れた目標の例：**

![&#x200B; 緑色のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「新しい AI を利用した分析ダッシュボードの 30 日間無料トライアルのサインアップを促進」

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「3 月 15 日（PT）に開催される「クラウドコストを 40% 削減」に関する B2B ウェビナーのリードを生成」

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「12 月 25 日まで、プレミアム購読の 25% の期間限定ディスカウントを促進」

**回避すべき例：**

![&#x200B; 赤十字 &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「製品のプロモーション」（曖昧すぎる）

![&#x200B; 赤十字 &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「サインをさせる」（値は不明確）

![&#x200B; 赤十字 &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「新機能に関するメール」（目的がない）

#### 目標の構造化

関連するコンテンツを作成するためのコンテキストと価値提案を常に提供する。 次の式を使用して、効果的な目標を記述します。**行動+製品/サービス+価値/便益+緊急度/状況**

**優れた目標の例：**

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「パーソナライズされた環境に優しいお勧めで持続可能な生活習慣を追跡するのに役立つ、新しいモバイルアプリのダウンロードを促します」

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「マーケティング担当者向けの高度なデータビジュアライゼーション技術に関する排他的なワークショップの登録を促進」

![&#x200B; 緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「革新的な AI 書き込みアシスタントを紹介する製品ローンチイベントへの出席を増やし、週に 5 時間以上節約します」

**回避すべき例：**

![&#x200B; 赤十字 &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「新しいアプリを発表」（価値提案とコンテキストがありません）

![&#x200B; 赤十字 &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「ワークショップに登録してもらう」（参加者とメリットについての特異性がない）

![&#x200B; 赤十字 &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「イベントを促進」（明確なアクション、価値、緊急性がない）

#### チャネルタイプ別のプロンプトの例 {#channel-type-practices}

<table style="table-layout: auto; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>チャネル</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>メール</strong></td>
<td>「詳細な ROI 指標（Oracle:45% のコスト削減、アクセンチュア：200% のリード向上、Microsoft:60% の時間短縮）を提示することで、企業の見込み客を育成します。 従業員数 1000 人以上の企業の IT ディレクターをターゲットにする」</td>
</tr>
<tr>
<td><strong>ランディングページ</strong></td>
<td>「B2B の訪問者を見込み客に変換する。エンタープライズ・セキュリティ・ソリューションが、Fortune 500 の証言と無料のセキュリティ監査によって、サイバー攻撃の 99.9% を防ぐ仕組みを示す」</td>
</tr>
</tbody>
</table>

<!-- channels not yet supported
<tr>
<td><strong>SMS</strong></td>
<td>"Alert VIP customers about a 4-hour flash sale on premium electronics with 40% discount, limited to the first 100 customers"</td>
</tr>
<tr>
<td><strong>Push Notifications</strong></td>
<td>"Re-engage users who haven't opened the app in 7 days with personalized content recommendations based on their reading history"</td>
</tr> -->

<!-- Wait on more B2B specific examples

### Industry-specific approaches {#industry-approaches}

<table style="table-layout: fixed; border-collapse: collapse; border: 0;">
<thead>
<tr style="border: 0;background-color: #FFFFFF;">
<th>Industry</th>
<th>Example Prompt</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>B2B Technology</strong></td>
<td>"Demonstrate ROI and technical specifications while addressing security concerns for IT decision-makers evaluating our cloud infrastructure solution, emphasizing 99.9% uptime SLA, SOC 2 compliance, and 40% cost savings."</td>
</tr>
<tr>
<td><strong>E-commerce Retail</strong></td>
<td>"Create urgency around limited-stock holiday items while highlighting free shipping and easy returns for last-minute shoppers, emphasizing limited quantities (less than 50 remaining) and 24-hour shipping cutoff."</td>
</tr>
<tr>
<td><strong>Financial Services</strong></td>
<td>"Educate clients about investment portfolio diversification strategies while maintaining regulatory compliance, featuring certified financial advisor insights and risk disclaimers."</td>
</tr>
<tr>
<td><strong>Healthcare & Wellness</strong></td>
<td>"Promote preventive care benefits and annual health screenings while maintaining medical accuracy, featuring board-certified physician recommendations and patient privacy assurances."</td>
</tr>
<tr>
<td><strong>Education & Training</strong></td>
<td>"Emphasize career advancement outcomes and industry certifications while showcasing instructor expertise, highlighting 92% job placement rate and project-based curriculum."</td>
</tr>
<tr>
<td><strong>SaaS Platforms</strong></td>
<td>"Highlight time savings and automation benefits with specific metrics while addressing integration concerns, featuring average 25-hour weekly time savings and integration with 200+ popular tools."</td>
</tr>
</tbody>
</table>
 -->

### 新しいコンテンツと既存のコンテンツの変更 {#new-vs-modify}

リクエストに新しいコンテンツの生成が含まれるか、既存するコンテンツの更新が含まれるかを明確に示します。 この区別は、AI が適切なアプローチを選択する際のガイドとなり、より正確で有用な結果を確保するために重要です。

#### 新しいコンテンツの作成

マーケティングキャンペーンを開始する際、新しいソリューションを発表する際、または更新/更新された通信を開始する際に、この戦略を適用します。 これにより、メッセージの開始を強力に支援し、目標に合わせることができます。

**プロンプトの方法** ➤ 新しいコンテンツを作成する際は、既存のコンテンツを参照せずにマーケティング目標に焦点を当てます。

>[!BEGINSHADEBOX  「例」 ]

* **SaaS 体験版**:「中小規模企業のオーナー向けに新しい CRM ソフトウェアを発表しました。時間を 50% 節約し、リードの選定時間を 90% 短縮しました。パーソナライズされたオンボーディングで 30 日間の無料体験版を提供します」
* **機能の発表**：「技術に関する意思決定者をターゲットに、エンタープライズ顧客の開発時間を 60％短縮する新しい API 統合機能を発表します」
* **イベントのプロモーション**:「Google、Meta、Adobeのエキスパートが参加する「Digital Marketing Trends 2024」ウェビナーの登録を促進し、実用的なインサイトと限られた席（最大 500 席）を強調します」

>[!ENDSHADEBOX]

#### 既存のコンテンツの変更

>[!TIP]
>
>複雑な修正、要約、簡略化などの標準的な修正の場合、カスタム プロンプトを記述する代わりに **_リファイン_** を選択します。

現在のマーケティングキャンペーンを更新、更新、調整する必要がある場合は、変更プロンプトを使用します。 この方法では、増分的な改善がサポートされるので、ゼロから開始することなく、メッセージの関連性を維持できます。

**プロンプトの方法** ➤ 既存のコンテンツを変更する際は、変更する内容と変更方法を明確に指定します。

>[!BEGINSHADEBOX  「例」 ]

* **キャンペーンの更新**:「プログラム開始に関するメールを変更して、IT の意思決定者をコンプライアンス認定制度の対象にすることで、生産性向上のための一般的なメリットではなく、エンタープライズセキュリティの機能を重点的に取り上げるようにします」
* **オーディエンスのピボット**:「ソフトウェアデモの招待状を適応させて医療を具体的にターゲットにし、一般的な例を医療のユースケースと HIPAA コンプライアンスのメリットに置き換える」
* **季節的な最新情報**:「第 4 四半期のホリデーショッピングに関する第 3 四半期のプロモーションキャンペーンを更新して、送料を迅速に強調しながら、新学期からホリデーギフトへのフォーカスを変更します」

>[!ENDSHADEBOX]

## テキストの詳細設定 {#text-settings}

明確で適切な形式のプロンプトを使用することに加えて、AI アシスタント コンテンツ ツールのテキスト設定には、生成された出力を最適化するために使用できるテキスト設定が含まれています。

>[!TIP]
>
>プロンプトでこれらの特性に言及する代わりに、_[!UICONTROL テキスト設定]_ の _[!UICONTROL コミュニケーション方法]_ および _[!UICONTROL トーン]_ オプションを使用します。

### コミュニケーション戦略のタイプ

コミュニケーション戦略では、メッセージの影響力を最大化するために、どのように伝えるかを決定します。 緊急性を構築する、信頼を確立する、迅速な行動を促すなど、目標によって効果的な戦略は異なります。 キャンペーンの目標とオーディエンスのマインドセットに最も一致する戦略を選択します。

| **戦略** | **最適な用途** | **メッセージスタイル** | **例** |
| ------------ | ------------ | ------------------- | ------------ |
| **至急** | 時間的制約が厳しいオファー、期限、即時アクション | 時間ベースの言語で即座にプレッシャーを作成 | <li>「今すぐ行動：オファーは午前 0 時に有効期限が切れる」 <li>「今すぐ登録して、スポットがいっぱいになるようにしてください」 <li>「48 時間のフラッシュセールを今すぐ開始」 |
| **FOMO（取り残されることへの恐れ）** | 制限付きのオファー、イベント、排他的アクセス | 緊急性、希少性、時間的プレッシャーの手がかりを使用 | <li>「残りわずか 24 時間。 40% オフの限定在庫」 <li>「ラストチャンス：アーリーバードプライシングは明日終了だ」 <li>「ベータ版スポットが 100 個しか残っていない」 |
| **ソーシャルプルーフ** | 信頼構築、お客様の声、人気商品 | 他のユーザーのエクスペリエンスと検証を活用 | <li>「50,000 人以上の満足している顧客に参加」 <li>「業界のプロフェッショナルによる 4.9/5 つ星評価」 <li>「Fortune 500 企業に信頼」 |
| **希少性** | 制限付きの在庫、排他的リリース、需要の高い商品 | 限定提供と排他性を強調 | <li>「在庫が 5 件のみ残っています」 <li>「限定版：100 個」 <li>「独占的リリース：先着順」 |
| **インセンティブ** | プロモーション、報酬プログラム、特別オファー | 目に見えるメリットと報酬を強調 | <li>「最初の注文から 2 割引」 <li>「今週末にダブルポイントを獲得」 <li>「50 ドル以上のご注文は送料無料」 |
| **排他性** | プレミアム商品、VIP エクスペリエンス、メンバー限定オファー | プレミアムな位置付け言語と特別なアクセス言語を使用 | <li>「プライベートプレビューへの排他的な招待」 <li>「エリートメンバーシップで高度な分析を解き放つ」 <li>「Fortune 500 社の中から選ばれた企業が、すでに私たちを利用しています」 |
| **ゲーミフィケーション** | エンゲージメントキャンペーン、ロイヤルティプログラム、インタラクティブコンテンツ | ゲームの仕組みと達成言語を使用 | <li>「次の報酬レベルのロックを解除」 <li>「バッジを獲得するための完全な課題」 <li>「特別賞を獲得するにはリーダーボードに登ろう」 |
| **情報** | 教育、研究、複雑な製品、思想的リーダーシップ | 事実、データ、インサイト、説明を使用 | <li>「10,000 件以上のインタラクションの分析からの 5 つのインサイト」 <li>「新しい研究で 3 つの画期的なアプローチが明らかに」 <li>「マーケティングに AI を実装するための完全なガイド」 |
| **教育とインサイト** | 学習コンテンツ、業界トレンド、ベストプラクティス | 貴重な知識と実用的なポイントを提供 | <li>エキスパートガイドを使用して高度なテクニックを学ぶ <li>「マーケターが使用する 7 つの戦略を確認する」 <li>「ワークフローを 5 つの手順で最適化する方法を学ぶ」 |

### 適切なトーンの設定 {#tone}

トーンは、オーディエンスがメッセージをどのように認識し、応答するかを形作ります。 ブランドの声やプロファイルジャーニーのステージに一致するトーンを常に選択します。

それぞれが最適なタイミングや各スタイルに合ったコンテンツの例など、使用可能なトーンのオプションを確認します。

| トーン性 | 最適な用途 | コンテンツの例 |
| ---- | ----- | ----- |
| プロフェッショナル | B2B コミュニケーション、正式発表 | 「戦略的パートナーシップを発表できることを嬉しく思います…」 |
| 共感的 | カスタマーサポート、機密性のあるトピック | 「私たちはこの問題があなたにとってどれほどイライラするかを理解しています…」 |
| ユーモラス | 魅力的なキャンペーン、わかりやすいコンテンツ | 「警告：生産性が大幅に向上する可能性があります。」 |
| 刺激的 | 製品ローンチ、イベントプロモーション | 「今こそあなたが待っていた瞬間だ！」 |
| 感動的 | やる気を起こさせるキャンペーン、ブランドの目的 | 「力を合わせれば、世界を変えることができます…」 |
| 説得性 | セールスキャンペーン、コンバージョン率 | 「この期間限定のチャンスをお見逃しなく…」 |
| フレンドリー | 顧客エンゲージメント、ウェルカムメッセージ | 「私達と一緒にいてくれてうれしいわ！」 |
| 正式 | 法的コミュニケーション、公式通知 | 「これは、次の変更の通知です…」 |
| 謝罪 | サービスの復元、問題解決 | 「Bodea は引き起こされた不便について心からお詫びします。 |
| 断定的 | リーダーシップコンテンツ、権威あるメッセージ | 「今すぐ実行する必要があるのは次のとおりです…」 |
| ストーリーテリング | ブランドナラティブ、感情的なつながり | 「すべてはシンプルな疑問から始まりました…」 |
| 対話的 | 育成キャンペーン、関係の構築 | 「このプログラムがどのように役立つかについて説明しましょう…」 |

## 最適化された参照コンテンツ {#reference-content}

>[!TIP]
>
>**[!UICONTROL コンテンツを参照]** メニューを使用して既にアセットをアップロードしている場合は、プロンプトでアセットを参照する必要はありません。 選択したドキュメントが自動的に使用されます。

参照コンテンツファイルは、生成されたコンテンツを具体的で正確な詳細で充実させる事実に基づく情報を提供します。 製品カタログやホワイトペーパーなどのドキュメントをアップロードする際に、どのパーツにフォーカスがあるかを確認するようにプロンプトを変更します。

* **&#x200B;**&#x200B;_「製品パンフレットを使用します」_&#x200B;**の代わりに**&#x200B;_「高度なセキュリティ機能とコンプライアンス認定、特に SOC 2 コンプライアンスとデータ暗号化に焦点を当てます」を使用する必要があります_

* **&#x200B;**&#x200B;_「ケーススタディを参照します」_&#x200B;**の代わりに**&#x200B;_「医療クライアントの ROI 結果、特に地域医療センターにおける 40％のコスト削減を強調します」を使用する必要があります_

* **&#x200B;**&#x200B;_「技術的な詳細を含めます」_&#x200B;**の代わりに**&#x200B;_「REST API エンドポイントと 99.9％の稼働率 SLA に焦点を当て、API 統合機能と開発者のメリットを強調します」を使用する必要があります_

### コンテンツの絞り込み

コンテンツが生成されたら、**_[!UICONTROL 絞り込み]_** 機能を使用して、次のオプションでコンテンツを繰り返し拡張します。

* **[!UICONTROL 精巧]** - AI アシスタントは、特定のトピックを展開するのに役立ち、理解とエンゲージメントを深めるために追加の詳細を提供します。

* **[!UICONTROL 要約]** – 長い情報がページビューアを過負荷にする可能性があります。 AI アシスタントを使用して、重要なポイントを明確かつ簡潔な概要に要約し、注意を引いてさらに読むよう促します。

* **[!UICONTROL フレーズ変更]** - メッセージの意味を保持したまま書き換えます。 このオプションを使用すると、コアメッセージを変更せずに、代替表現を生成したり、フローを改善したり、フレーズを調整したりできます。

* **[!UICONTROL よりシンプルな言語の使用]** – 言語を簡素化し、より広いオーディエンスに対して明確でアクセシビリティを確保します。

* **[!UICONTROL 翻訳]** - テキストを別の言語に翻訳します。 （現在サポートされている言語は英語のみです。）

* **[!UICONTROL トーンを変更]** - メッセージのトーンを、よりフレンドリー、プロフェッショナル、緊急、またはインスピレーションを高めるなど、コミュニケーションスタイルに合わせて調整します。

* **[!UICONTROL コミュニケーション戦略の変更]** – 緊急性の創出や魅力的なアピールの強調など、目標に基づいてメッセージングアプローチを変更します。
