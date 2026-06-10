---
title: フラグメント作成
description: ビジュアルデザインツールで再利用可能なコンテンツフラグメントを作成します。Journey Optimizer B2B editionでは、電子メールやテンプレートのコンポーネント、パーソナライゼーション、条件付きコンテンツ、カスタマイズ可能なフィールドを追加できます。
feature: Fragments, Content Design Tools
role: User
exl-id: d29754cf-6721-489c-bff8-cde034456db2
autotag-review: '2026-05-27T16:13:22.974Z'
TQID: 'https://experienceleague.adobe.com/WqMj4DVOmUd3s-r-n9bSyRjXSGS8sDWMFNh5wfOiE2Y'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2:
  - id: e1663313-7961-4100-bea9-fa9f4edf8493
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: a09a5a04-e30b-4d55-b031-38e6f5ec86db
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
source-git-commit: 955fac784a8f438ec2f9aaf66e9aaeefda58e2a7
workflow-type: tm+mt
source-wordcount: 391
ht-degree: 6%

---

# フラグメントオーサリング

[&#x200B; フラグメントを作成した後](./fragments.md#create-fragments)、ビジュアルデザインスペースを使用して、フラグメント内の構造とコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#design-fragment}

{{$include /help/_includes/content-design-components.md}}

## アセットの追加

{{$include /help/_includes/content-design-assets.md}}

## レイヤー、設定、スタイルの移動

{{$include /help/_includes/content-design-navigation.md}}

## コンテンツのパーソナライズ

{{$include /help/_includes/content-design-personalization.md}}

## 条件付きコンテンツ

ルールに基づいてコンテンツをターゲットプロファイルに適応させるコンディショナルコンテンツを追加するには、コンテンツコンポーネントを選択し、コンポーネントツールバーの「**[!UICONTROL コンディショナルコンテンツを有効にする]**」ボタンをクリックします。 公開されたフラグメントがメールメッセージに含まれると、条件付きルールによって、メールメッセージでレンダリングされる条件付きコンポーネントのバリエーションが決定されます。

詳しくは、[_条件付きコンテンツ_](./conditional-content.md)&#x200B;を参照してください。

## フラグメントのカスタマイズの有効化

作成者が[電子メール &#x200B;](./email-authoring.md#content-authoring---use-visual-fragments)または[電子メールテンプレート &#x200B;](./email-template-authoring.md#content-authoring---use-visual-fragments)にフラグメントを追加すると、フラグメントコンテンツはデフォルトでロックされます。 公開されたフラグメントに対する変更は、フラグメントが使用されるすべてのコンテンツアセットに自動的に反映されます。 フラグメント内のコンポーネントのパラメーターを編集可能として指定すると、メールまたはテンプレート作成者は、ニーズに固有のカスタムフィールド値を指定できます。 このカスタマイズフラグは、画像、テキストおよびボタンのビジュアルコンポーネントに制限されます。

例えば、クリック可能なボタンを含む再利用可能なバナーをデザインする場合、ボタンのURL パラメーターを編集可能として指定できます。 メール作成者は、メールキャンペーンに特化したURLを使用できます。 これらのカスタマイズ可能なフィールドを利用することで、マーケターは、まったく新しいコンテンツブロックを作成したり、継承された更新を元のフラグメントから中断したりすることなく、再利用可能なコンテンツを管理し、パーソナライズすることができます。

1. ビジュアルコンテンツエディターで、カスタマイズを有効にする画像、テキストまたはボタン要素を選択します。

1. 右側のコンポーネントの詳細で、「**[!UICONTROL 編集可能なフィールド]**」タブを選択します。

1. 「**[!UICONTROL 編集を有効にする]**」オプションの切替スイッチをクリックし、編集可能なフィールドを設定します。

   ![&#x200B; フラグメント画像コンポーネントの編集可能フィールドを有効にする](./assets/fragment-editable-fields-image.png){width="700" zoomable="yes"}

   表示されるフィールドのカスタマイズを有効にできます。これは、コンポーネントタイプとフラグメントで定義されたパラメーターに依存します。

   カスタマイズを許可するフィールドごとに、トグルを有効な状態に変更します。

1. **[!UICONTROL 概要]**&#x200B;をクリックして、編集可能なすべてのフィールドとそのデフォルト値を確認します。

   ![編集可能なフィールドとそのデフォルト値を確認](./assets/fragment-editable-fields-image-overview.png){width="700" zoomable="yes"}

1. 変更を保存します。

## リンクされたURL トラッキングを編集

{{$include /help/_includes/content-design-links.md}}
