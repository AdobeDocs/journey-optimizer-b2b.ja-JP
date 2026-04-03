---
title: ブランド一致スコアリング
description: ブランドの整合性スコアリングでメールコンテンツを評価する – Journey Optimizer B2B editionで、ブランドガイドラインに照らし合わせて色、フォント、ロゴ、文章を検証します。
badge: label="ベータ版" type="Informative"
feature: Content, Brand Identity
hide: true
hidefromtoc: true
role: User
level: Beginner, Intermediate
exl-id: 686d5ce0-c597-48e1-a51f-e91e95a942d5
source-git-commit: 5824f311da00468b3e85c4e212f81c5d9657c5f7
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 26%

---

# ブランド整合性スコア付け {#brand-score}

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_score_overview"
>title="ブランドの選択"
>abstract="ブランドを選択して、一貫性とブランドの整合性を維持しながら、コンテンツが特定のガイドライン、標準、アイデンティティに合わせて作成されるようにします。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_score"
>title="ブランド整合性スコア"
>abstract="ブランド整合性スコアは、コンテンツがブランドのガイドラインにどの程度準拠しているかを測定し、色、フォント、ロゴ、画像、文体の一貫性を確保します。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_colors"
>title="色のスコア"
>abstract="色のスコア"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_fonts"
>title="フォントのスコア"
>abstract="フォントのスコア"

>[!CONTEXTUALHELP]
>id="ajo-b2b_brand_logos"
>title="ロゴのスコア"
>abstract="ロゴのスコア"

ブランドの整合性の評価とスコアは、選択したブランドで定義されたガイドライン [に準拠するコンテンツを作成、レビュー、管理するのに役立ちます](./brands-manage-create.md#brand-definitions)。 この機能を使用すると、メールキャンペーン全体のトーン、メッセージ、ビジュアルアイデンティティの一貫性を確保するだけでなく、コンテンツ公開前に品質チェックを行うことができます。

>[!AVAILABILITY]
>
>この機能は現在、パブリックベータ版として利用可能です。
>
>Adobe Journey Optimizer B2B editionでAIを活用した機能を使用するには、事前に[使用許諾契約書](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}が必要です。 詳しくは、アドビ担当者にお問い合わせください。
>
>製品管理者がこれらの機能を有効にする方法について詳しくは、[&#x200B; ブランド関連の権限](./brands-overview.md#brand-related-permissions)を参照してください。

## ブランド調整の検証

ブランドが明確に定義され、公開されたら、メールデザイン分野で直接ブランド調整スコアを評価して、コンテンツがブランドガイドラインに準拠していることを確認します。

1. メールコンテンツを作成したら、右側の&#x200B;_ブランド調整_ （![&#x200B; ブランド調整アイコン &#x200B;](../assets/do-not-localize/icon-brand-compliance.svg)）アイコンをクリックして、メールデザインスペースの&#x200B;_ブランド調整_&#x200B;右側のパネルを開きます。

   [&#x200B; デフォルトブランド &#x200B;](./brands-manage-create.md#default-brand)が自動的に選択されます。

   ![&#x200B; ブランド調整ツールにアクセス &#x200B;](./assets/brands-alignment-sidebar.png){width="600" zoomable="yes"}

   パネルの上部にある&#x200B;_フルスクリーン_ （![&#x200B; フルスクリーンアイコン &#x200B;](../assets/do-not-localize/icon-full-screen.svg)）アイコンをクリックすると、ブランドの整列ツールをフルスクリーンモードで表示できます。

1. 必要に応じて、**[!UICONTROL ブランド]** メニューの矢印（![下向き矢印](../assets/do-not-localize/icon-down-menu.svg)）をクリックして、別の公開済みブランドを選択します。

1. 「**[!UICONTROL スコアを評価]**」をクリックして、選択したブランドとのコンテンツの整合性をスコアリングします。

   選択したブランドのガイドラインに照らしてコンテンツが評価され、結果のスコアが表示されます。

   ![&#x200B; ブランド調整評価スコア &#x200B;](./assets/brands-alignment-evaluation.png){width="600" zoomable="yes"}

## 評価の確認

スコアは、評価されたメールコンテンツ内で特定された違反に従って計算されます。

* 100 = Perfect – 違反が見つかりません
* 80-99 =良好 – 軽微な違反のみ
* 60-79 =公正 – いくつかの重大な違反
* 60未満=不良 – 重大な違反には注意が必要

評価結果をより詳細に確認することで、違反を特定し、カテゴリの整合性スコア （_高_、_Medium_、_低_）を向上させ、詳細を確認することができます。 **[!UICONTROL 書き込みスタイル]**&#x200B;または&#x200B;**[!UICONTROL ビジュアルコンテンツ]**&#x200B;の場合は、_展開_ （![展開の矢印](../assets/do-not-localize/icon-expand-right.svg)）矢印をクリックして、評価の詳細を表示します。

![&#x200B; ブランドの整合性の評価の詳細](./assets/brands-alignment-evaluation-details.png){width="600" zoomable="yes"}

フラグ付けされたガイドラインを選択して、特定のフィードバックと提案を表示します。

コンテンツに変更を加え、「**[!UICONTROL スコアを再評価]**」をクリックして別の評価を実行し、改善された結果を確認できます。
