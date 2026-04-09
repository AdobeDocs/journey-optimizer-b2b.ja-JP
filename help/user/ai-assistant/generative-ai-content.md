---
title: コンテンツ用ジェネレーティブ AI
description: プロンプトのベストプラクティスなど、生成AIを活用して、パーソナライズされたメールやランディングページを [!DNL Journey Optimizer B2B Edition]で作成する方法を説明します。
feature: AI Assistant, Generative AI, Content
level: Beginner
topic: Artificial Intelligence
role: User
exl-id: 36baf7f9-2fff-4c33-bca0-7d43ec48e74a
source-git-commit: 8073984ced07e86a3fa500c5bf0bd393abbe0990
workflow-type: tm+mt
source-wordcount: '2506'
ht-degree: 32%

---

# コンテンツ用ジェネレーティブ AI {#generative-ai-content}

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-settings"
>title="AIによるコンテンツ生成"
>abstract="レイアウトを作成したら、[!DNL Journey Optimizer B2B Edition]の生成AI ツールを使用してコンテンツを強化できます。 この機能は、説明プロンプトに従ってコンテンツを微調整することで、パーソナライゼーションとコンテンツ改善のプロセスを簡素化します。"

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-reference-context"
>title="参照コンテンツ"
>abstract="_参照コンテンツ_&#x200B;を使用して、生成AIの追加のコンテキストを[!DNL Journey Optimizer B2B Edition]に提供するコンテンツを含むアセットファイルをアップロードするか、以前にアップロードしたファイルを選択します。 このオプションを選択すると、生成されたコンテンツの品質と関連性を高めるために必要なすべての素材が使用可能になります。"

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai-generation-start"
>title="Adobeの生成AIに関する用語"
>abstract="この機能へアクセスするには、Adobe Experience Cloud 生成 AI ユーザーガイドラインへの同意が必要です。 この機能の出力を確認して正確性を確認し、ユースケースに適していることを確認します。"
>additional-url="https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html" text="Adobe 生成 AI ユーザーガイドライン"

Microsoft Azure OpenAIとAdobe Fireflyを活用した[!DNL Adobe Journey Optimizer B2B Edition]のコンテンツ生成AIは、テキストや画像に対する先見的なコンテンツのバリエーション提案を提供します。 さまざまなメインタイトルや画像を試して、コンテンツの効果を最適化しましょう。

[!DNL Journey Optimizer B2B Edition]のコンテンツ作成に生成AI機能を使用して、Adobeの生成AI機能を活用します。 電子メール、SMS メッセージ、ランディングページ用にパーソナライズされたテキストやビジュアルを作成できます。 包括的なキャンペーンを構築する場合や、特定のアセットを改良するだけの場合など、これらの機能は、貴重な時間を節約しながら、コンテンツとブランドガイドラインの整合性を保つのに役立ちます。

<!--
Generate multiple variants and build an experiment to compare them. Leveraging Journey Optimizer Content Experiment, you can define multiple message treatments to measure which one performs best for your target audience. You can choose to vary the delivery content, or subject. The message audience is randomly allocated to each treatment to determine which one works best in terms of the specified metric. Learn more about Content Experiment in this section. 
-->

>[!IMPORTANT]
>
>[!DNL Journey Optimizer B2B Edition]でこれらの機能にアクセスするには、_[!UICONTROL AI アシスタント]_ > _[!UICONTROL コンテンツを生成]_&#x200B;権限が必要です。 製品管理者が機能の権限を付与する方法について詳しくは、[製品権限の役割を編集](../admin/user-management.md#edit-roles-for-product-permissions)を参照してください。

コンテンツ生成用のAI アシスタントツールは、次のアセットタイプでサポートされています。

* [メール](../content/ai-assistant-emails.md)
* [!BADGE Beta] [&#x200B; ランディングページ &#x200B;](../content/ai-assistant-landing-pages.md)

## 一般的なガイドラインと制限事項 {#general-guidelines-and-limitations}

生成AI機能の使用には、[Adobe Experience Cloud生成AI ユーザーガイドライン &#x200B;](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}が適用されます。 メディア作成に生成AI ツールを使用する際の透明性に対するAdobeの取り組みにより、Adobeは、[!DNL Firefly]生成されたアセットがダウンロードまたはエクスポートされたときに含まれるコンテンツまたはプロジェクトに[&#x200B; コンテンツ資格情報](https://helpx.adobe.com/firefly/web/get-started/learn-the-basics/content-credentials-overview.html){target="_blank"}を適用します。

[!DNL Journey Optimizer B2B Edition]のコンテンツに生成AIを使用する場合は、次の一般的なガイドラインを確認してください。

* 生成AI モデルに明確に定義されたプロンプトを使用し、正確に解釈。 提供するマーケティング目標やプロンプトは、生成されるコンテンツの品質に大きく影響します。

* コンテンツ参照ファイルをアップロードすることで、ブランドに即した正確なコンテンツを作成できます。 それ以外の場合は、公開されている情報に基づいてコンテンツが行われます。 アップロードされたコンテンツは、PDF、JPEG、PNG、またはZIP （サポートされているファイル形式を含む）のファイル形式にすることができます。 アップロードされたファイルの最大サイズは50 MBです。 大きなファイルや多数の画像は機能しますが、処理時間が長くなります。

* ブランド固有またはカスタムテンプレートを使用して、メールコンテンツを作成します。 最大8～10枚の画像を含むメールテンプレートをお勧めします。

* バリエーションを選択する際には、サムアップ、サムダウン、またはフラグアイコンを使用して、問題のある出力を必ず報告してください。

## 生成AIのベストプラクティスを確認 {#generative-ai-prompting-guide}

>[!CONTEXTUALHELP]
>id="ajo_b2b_ai_content_prompt"
>title="プロンプトガイダンス"
>abstract="コンバージョン率が高く、ブランドに即したマーケティングコンテンツを生成する効果的なプロンプトを作成する方法について、[!DNL Journey Optimizer B2B Edition]のドキュメントをご覧ください。"

このガイドは、リクエストの構成や意図の明確化を図り、AIがブランドガイドライン、オーディエンスのニーズ、キャンペーン目標に沿ったメッセージを生成することを支援します。

AI アシスタントが目標に合わせてカスタマイズされた高品質でブランドに即したマーケティングコンテンツを生成できるようにする効果的なプロンプトを書き込む方法について説明します。

### CO-STAR フレームワークの使用 {#costar-framework}

生成されたコンテンツで最高の結果を得るには、CO-STAR フレームワークを使用してプロンプトを整理します。 このような体系化されたアプローチにより、必要なものを正確に把握することができます。

| コンポーネント | 意味 | これが重要な理由 |
| --- | ---- | ------ |
| **C - コンテキスト** | キャンペーン、製品または状況に関する背景 | 全体像を把握する |
| **O - 目標** | 特定のマーケティング目標 | コンテンツが達成すべき目標を推進します |
| **S - スタイル** | コミュニケーション方法 | アプローチを設定します |
| **T - トーン** | 感情的なスタイルと声 | メッセージの雰囲気を形作ります |
| **A - オーディエンス** | ターゲットにしているオーディエンスは | 共感を呼ぶ適切なチャネルを通じて |
| **R - 要件** | 特定の制約または必須 | 境界と重要な要素を定義します |

{style="table-layout:fixed"}

### プロンプトの基本 {#key-takeaways}

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
<li>特定の抽出ガイダンスを使用して、ドキュメント使用に焦点を当てる
<li>トーン、戦略、ロケールの選択
<li>マーケティング目標とコンテンツタイプの機能を一致
<li>A/B テスト用に複数のバリアントを生成</ul>
</td>
<td>
<ul><li>プロンプトで構造の変更、スタイル設定、画像編集を依頼
<li>オプションでトーン/戦略をプロンプトに記載する
<li>_promote the product_のような曖昧な目的を使用する
<li>条件付き要素の選択をリクエスト
<li>プロンプトを通じてレイアウトの変更を想定</ul>
</td>
</tr>
</tbody>
</table>

### プロンプトでサポートされていないコンテンツ

>[!TIP]
>
>デザイン ツールまたは[!DNL Adobe Express]を使用して、ビジュアル/画像を修正します。

次のリクエストは&#x200B;**_サポートされていません_**。他のツールで処理する必要があります：

<table style="table-layout: fixed; border: 0;">
<thead style="border: 0; background-color: #FFFFFF">
<tr>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="赤十字アウト">  メール構造の変更</th>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="赤十字アウト">  視覚的なスタイルの変更</th>
<th><img src="../../assets/do-not-localize/check-box-red.svg" alt="赤十字アウト">  画像編集業務</th>
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
<li>画像のトリミングまたはサイズ変更</li>
<li>カラー調整</li>
<li>画像の置換</li>
</ul>
</td>
</tr>
</tbody>
</table>

### 品質チェックリスト {#quality-checklist}

コンテンツを生成する前に、次の点を確認します。

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} **目標をクリア**: アクション、製品/サービス、値、およびコンテキストを明確に示します。

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} **定義されたターゲットオーディエンス**：デモグラフィック、役割、またはセグメントを指定します。

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} **コンテンツの種類の調整**：目的は、選択したチャネルまたは形式と一致します。

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} **選択を確認**：トーン、戦略、ロケールが選択されています。プロンプトに含めないでください。

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} **ドキュメントの焦点が指定されています**：参照するコンテンツまたはセクションをハイライト表示します。

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} **ブランドが適用されました**：適切なブランドガイドラインが選択されています。

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} **現実的な範囲**: レイアウトの変更、スタイル設定、構造的な編集のリクエストを避けます。

### 効果的なマーケティング目標 {#marketing-objectives}

マーケティング目標を作成する際は、明確で実用的かつ測定可能であることを確認します。 あいまいなステートメントや汎用ステートメントは回避します。

**優れた目標の例：**

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「新しいAIを活用した分析ダッシュボードの30日間無料体験版のサインアップを促進する」

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「3月15日に予定されている「クラウドコストを40%削減」に関するB2B ウェビナーのリードを生成する」

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「プレミアム購読の期間限定25%割引を12月25日まで宣伝する」

**回避すべき例：**

![赤十字アウト &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「製品を宣伝する」（曖昧すぎる）

![赤十字アウト &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「人物を契約にサインさせる」 （値が不明確）

![赤十字アウト &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「新機能に関する電子メール」（目的に欠ける）

#### 目標の構造化

関連性の高いコンテンツを制作するために、コンテキストと価値提案を常に提供しましょう。 効果的な目標の作成に役立つ数式を使用します。**アクション +製品/サービス +価値/利点+緊急性/コンテキスト**

**優れた目標の例：**

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「新しいモバイルアプリをダウンロードして、ユーザーが環境に配慮したパーソナライズされたレコメンデーションを使用して、持続可能な生活習慣を追跡するのに役立ててください」

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「マーケター向けの高度なデータ視覚化技術に関する専用ワークショップへの登録を促進する」

![緑のチェックマーク &#x200B;](../../assets/do-not-localize/check-box-green.svg){width="20"} 「週に5時間以上節約できる革新的なAI ライティングアシスタントを紹介する製品発売イベントへの参加を促す」

**回避すべき例：**

![赤十字アウト &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「新しいアプリを発表」（値の提案とコンテキストが欠落）

![赤十字アウト &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「ワークショップへの登録を促す」（参加者とメリットに関する具体的な情報が不足している）

![赤十字アウト &#x200B;](../../assets/do-not-localize/check-box-red.svg){width="20"} 「プロモートイベント」（明確なアクション、値、または緊急性はありません）

#### チャネルタイプ別プロンプトの例 {#channel-type-practices}

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
<td>「詳細なROI指標により、3つの成功事例を紹介することで、企業の見込み顧客を育成します（Oracle:45%のコスト削減、Accenture:200%のリード増加、Microsoft:60%の時間短縮）。 従業員数が1,000人を超える企業のIT ディレクターをターゲットにする」</td>
</tr>
<tr>
<td><strong>ランディングページ</strong></td>
<td>「Fortune 500の顧客の声と無料のセキュリティ監査により、エンタープライズセキュリティソリューションがサイバー攻撃の99.9%を防ぐ方法を示すことで、B2B訪問者を適格リードに転換する」</td>
</tr>
</tbody>
</table>

<!--
 channels not yet supported
<tr>
<td><strong>SMS</strong></td>
<td>"Alert VIP customers about a 4-hour flash sale on premium electronics with 40% discount, limited to the first 100 customers"</td>
</tr>
<tr>
<td><strong>Push Notifications</strong></td>
<td>"Re-engage users who haven't opened the app in 7 days with personalized content recommendations based on their reading history"</td>
</tr> 
-->

<!--
 Wait on more B2B specific examples

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

### 新規コンテンツと既存コンテンツの変更の違い {#new-vs-modify}

リクエストに新しいコンテンツの生成が含まれるか、既存するコンテンツの更新が含まれるかを明確に示します。 この区別は、AI が適切なアプローチを選択する際のガイドとなり、より正確で有用な結果を確保するために重要です。

#### 新しいコンテンツの作成

この戦略は、マーケティング施策の立ち上げ、新しいソリューションの発表、コミュニケーションの更新/刷新を行う場合に適用します。 これにより、メッセージを強力なものにし、目標に沿ったものにできます。

**プロンプトの方法** ➤ 新しいコンテンツを作成する際は、既存のコンテンツを参照せずにマーケティング目標に焦点を当てます。

>[!BEGINSHADEBOX  「例」 ]

* **SaaS体験版**:「新しいCRM ソフトウェアをスモールビジネスのオーナー向けにローンチします。50%の時間短縮、90%のリード認定の迅速化、パーソナライズされたオンボーディングによる30日間の無料体験版の提供を強調します」
* **機能の発表**：「技術に関する意思決定者をターゲットに、エンタープライズ顧客の開発時間を 60％短縮する新しい API 統合機能を発表します」
* **イベントプロモーション**:「Google、Meta、Adobeの専門家による「Digital Marketing Trends 2024年版」ウェビナーの申し込み件数を増加させ、実用的なインサイトと限られた人数（最大500名）を重視」

>[!ENDSHADEBOX]

#### 既存のコンテンツの変更

>[!TIP]
>
>詳細、要約、簡略化などの標準的な変更の場合は、カスタムプロンプトを記述する代わりに&#x200B;**_調整_**&#x200B;を選択します。

現在のマーケティング施策を更新、更新、調整する必要がある場合は、変更プロンプトを使用できます。 この方法では、増分的な改善がサポートされるので、ゼロから開始することなく、メッセージの関連性を維持できます。

**プロンプトの方法** ➤ 既存のコンテンツを変更する際は、変更する内容と変更方法を明確に指定します。

>[!BEGINSHADEBOX  「例」 ]

* **キャンペーンの更新**:「一般的な生産性向上のメリットではなく、エンタープライズセキュリティ機能に焦点を当て、IT意思決定者をコンプライアンス認定の対象とするプログラム開始メールを変更する」
* **オーディエンスピボット**:「一般的な例をヘルスケアのユースケースとHIPAA コンプライアンスのメリットに置き換えて、特にヘルスケアをターゲットとするソフトウェアデモへの招待を適応させる」
* **季節のアップデート**:「第4四半期のホリデーショッピングの第3四半期のプロモーションキャンペーンを更新し、バック・トゥ・スクールからホリデーギフトへのフォーカスを迅速な配送に重点を置いて変更」

>[!ENDSHADEBOX]

## 詳細テキスト設定 {#text-settings}

明確で整形式のプロンプトを使用することに加えて、AI アシスタントコンテンツツールのテキスト設定には、生成された出力の最適化に使用できるテキスト設定が含まれています。

>[!TIP]
>
>プロンプトでこれらの特性に言及する代わりに、_[!UICONTROL テキスト設定]_&#x200B;で&#x200B;_[!UICONTROL コミュニケーション戦略]_&#x200B;および&#x200B;_[!UICONTROL トーン]_ オプションを使用します。

### コミュニケーション戦略のタイプ

コミュニケーション戦略では、メッセージの影響力を最大化するために、どのように伝えるかを決定します。 緊急性を構築する、信頼を確立する、迅速な行動を促すなど、目標によって効果的な戦略は異なります。 キャンペーンの目標とオーディエンスのマインドセットに最も一致する戦略を選択します。

| **戦略** | **最適な用途** | **メッセージングスタイル** | **例** |
| ------------ | ------------ | ------------------- | ------------ |
| **至急** | 時間的制約が厳しいオファー、期限、即時アクション | 時間ベースの言語で即座にプレッシャーを作成 | <li>「今すぐアクション：オファーは午前0時に期限切れになります」 <li>「スポットが埋まる前に今日登録」 <li>&quot;48時間フラッシュセールが今すぐ始まります&quot; |
| **FOMO（取り残されることへの恐れ）** | 制限付きのオファー、イベント、排他的アクセス | 緊急性、希少性、時間的プレッシャーの手がかりを使用 | <li>「残りわずか 24 時間。 40% オフの限定在庫&quot; <li>&quot;Last chance: Early bird pricing ends tomorrow&quot; <li>&quot;Only 100 beta spots remaining&quot; |
| **ソーシャルプルーフ** | 信頼構築、お客様の声、人気商品 | 他のユーザーのエクスペリエンスと検証を活用 | <li>&quot;50,000人以上の満足度の高い顧客に参加&quot; <li>&quot;業界の専門家によって評価される4.9/5つ星&quot; <li>「Fortune 500企業から信頼されています」 |
| **希少性** | 制限付きの在庫、排他的リリース、需要の高い商品 | 限定提供と排他性を強調 | <li>「在庫が5つしか残っていません」 <li>「限定版：100 ユニットが利用可能」 <li>&quot;Exclusive release: First come, first served&quot; |
| **インセンティブ** | プロモーション、報酬プログラム、特別オファー | 目に見えるメリットと報酬を強調 | <li>&quot;あなたの最初の注文の20% オフを取得&quot; <li>「今週末はダブルポイントを獲得」 <li>&quot;50 ドル以上のご注文で送料無料&quot; |
| **排他性** | プレミアム商品、VIP エクスペリエンス、メンバー限定オファー | プレミアムな位置付け言語と特別なアクセス言語を使用 | <li>「プライベートプレビューへの排他的な招待」 <li>「エリートメンバーシップで高度な分析を実現」 <li>「既に使用しているFortune 500企業に参加してください」 |
| **ゲーミフィケーション** | エンゲージメントキャンペーン、ロイヤルティプログラム、インタラクティブコンテンツ | ゲームの仕組みと達成言語を使用 | <li>&quot;あなたの次の報酬レベルのロックを解除&quot; <li>&quot;バッジを獲得するための完全な課題&quot; <li>&quot;排他的な賞品のためのリーダーボードを登る&quot; |
| **情報** | 教育、研究、複雑な製品、思想的リーダーシップ | 事実、データ、インサイト、説明を使用 | <li>「1万件以上のインタラクションを分析して得た5つのインサイト」 <li>&quot;新しい研究は、3つの画期的なアプローチを明らかにする&quot; <li>「マーケティングにおけるAIの導入方法」 |
| **教育とインサイト** | 学習コンテンツ、業界トレンド、ベストプラクティス | 貴重な知識と実用的なポイントを提供 | <li>「エキスパートガイドで高度なテクニックを学ぶ」 <li>「トップマーケターが活用する7つの戦略を見る」 <li>「ワークフローを最適化する方法を5つのステップで説明します」 |

### 適切なトーンの設定 {#tone}

トーンは、オーディエンスがメッセージをどのように認識し、応答するかを形作ります。 ブランドの声やプロファイルジャーニーのステージに一致するトーンを常に選択します。

各トーンの最も効果的なタイミングや、各スタイルに適したコンテンツの例など、利用可能なトーンオプションを確認しましょう。

| トーン性 | 最適な用途 | コンテンツの例 |
| ---- | ----- | ----- |
| プロフェッショナル | B2B コミュニケーション、正式発表 | 「戦略的パートナーシップを発表できることを嬉しく思います…」 |
| 共感的 | カスタマーサポート、機密性のあるトピック | 「私たちは、この問題があなたにとってどれほどイライラさせられなければならないかを理解しています…」 |
| ユーモラス | 魅力的なキャンペーン、わかりやすいコンテンツ | 「警告：生産性が大幅に向上する可能性があります。」 |
| 刺激的 | 製品ローンチ、イベントプロモーション | 「これこそ君が待ち望んでいた瞬間だ！」 |
| 感動的 | やる気を起こさせるキャンペーン、ブランドの目的 | 「力を合わせれば、世界を変えることができます…」 |
| 説得性 | セールスキャンペーン、コンバージョン率 | 「この期間限定のチャンスをお見逃しなく…」 |
| フレンドリー | 顧客エンゲージメント、ウェルカムメッセージ | 「君が我々と一緒にいてくれてよかった！」 |
| 正式 | 法的コミュニケーション、公式通知 | 「次の変更に関する通知です…」 |
| 謝罪 | サービスの復元、問題解決 | 「ボディアは、ご不便をおかけして心からお詫び申し上げます。」 |
| 断定的 | リーダーシップコンテンツ、権威あるメッセージ | 「今すぐ実行する必要があるのは次のとおりです…」 |
| ストーリーテリング | ブランドナラティブ、感情的なつながり | 「すべてはシンプルな疑問から始まりました…」 |
| 対話的 | 育成キャンペーン、関係の構築 | 「このプログラムがどのように役立つかについてお話ししましょう…」 |

## 最適化された参照コンテンツ {#reference-content}

>[!TIP]
>
>「**[!UICONTROL コンテンツを参照]**」メニューを通じてアセットを既にアップロードしている場合、プロンプトでアセットを参照する必要はありません。 選択したドキュメントが自動的に使用されます。

参照コンテンツファイルは、生成されたコンテンツを具体的かつ正確な詳細で強化する、事実にもとづく情報を提供します。 製品パンフレットやホワイトペーパーなどのドキュメントをアップロードする場合は、焦点が合っている部分を含めるようにプロンプトを変更します。

* **&#x200B;**&#x200B;_「製品パンフレットを使用します」_&#x200B;**の代わりに**&#x200B;_「高度なセキュリティ機能とコンプライアンス認定、特に SOC 2 コンプライアンスとデータ暗号化に焦点を当てます」を使用する必要があります_

* **&#x200B;**&#x200B;_「ケーススタディを参照します」_&#x200B;**の代わりに**&#x200B;_「医療クライアントの ROI 結果、特に地域医療センターにおける 40％のコスト削減を強調します」を使用する必要があります_

* **&#x200B;**&#x200B;_「技術的な詳細を含めます」_&#x200B;**の代わりに**&#x200B;_「REST API エンドポイントと 99.9％の稼働率 SLA に焦点を当て、API 統合機能と開発者のメリットを強調します」を使用する必要があります_

### コンテンツの改善

コンテンツを生成したら、**_[!UICONTROL 調整]_**&#x200B;機能を使用して繰り返し処理を行い、次のオプションで強化します。

* **[!UICONTROL 詳しく説明]** - AI アシスタントは、特定のトピックを拡大するのに役立ち、より深い理解とエンゲージメントのために追加の詳細を提供します。

* **[!UICONTROL 概要]** – 長い情報を使用すると、ページビューアが過負荷になる可能性があります。 AI アシスタントを使用して、重要なポイントを明確かつ簡潔な概要に要約し、注意を引いてさらに読むよう促します。

* **[!UICONTROL 言い換え]** - メッセージの意味を維持しながら、メッセージを書き換えます。 このオプションを使用すると、コアメッセージを変更せずに、代替表現を生成したり、フローを改善したり、フレーズを調整したりできます。

* **[!UICONTROL シンプルな言語を使用]** – 言語を簡略化して、より多くのユーザーに明確さとアクセシビリティを提供します。

* **[!UICONTROL 翻訳]** - テキストを別の言語に翻訳します。 （現在、サポートされている言語は英語のみです）。

* **[!UICONTROL トーンの変更]** - メッセージのトーンを、よりフレンドリーで、プロフェッショナルで、緊急で、インスピレーションを与えるなど、コミュニケーションスタイルに合わせて調整します。

* **[!UICONTROL コミュニケーション戦略の変更]** – 緊急性の作成や魅力的なアピールの強調など、目的に基づいてメッセージングアプローチを変更します。
