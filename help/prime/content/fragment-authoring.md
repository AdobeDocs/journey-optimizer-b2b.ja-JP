---
title: フラグメント作成
description: ビジュアルデザインツールで再利用可能なコンテンツフラグメントを作成します。Journey Optimizer B2B Primeでは、電子メールやテンプレートの構造、アセット、パーソナライゼーション、条件付きコンテンツ、リンクされたURL トラッキングを追加できます。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、限定的なベータ版リリースの一部です。"
autotag-review: '2026-07-13T16:38:09.506Z'
TQID: 'https://experienceleague.adobe.com/Zn5L6Bc3x8SuGyjOPDdTWI-oxrrhk06a2f8ZvX2SN4s'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2:
  - id: e1663313-7961-4100-bea9-fa9f4edf8493
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 5206ed7bc0ce24e65700da28b023d76c68cb6419
workflow-type: tm+mt
source-wordcount: 215
ht-degree: 4%

---

# フラグメントオーサリング

[&#x200B; フラグメントを作成した後](./fragments.md#create-fragments)、ビジュアルデザインスペースを使用して、フラグメント内の構造とコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#design-fragment}

{{$include /help/_includes/content-design-components-prime.md}}

## アセットの追加 {#add-assets}

ビジュアルデザイン領域で、左側のナビゲーションバーの&#x200B;_Assets_ （![Assetsアイコン &#x200B;](../../assets/do-not-localize/icon-assets-me.svg)）アイコンを選択し、[!DNL Journey Optimizer B2B Prime] アセットライブラリから画像アセットを参照して選択します。

画像アセットを選択、置換、またはアップロードする手順については、[&#x200B; コンテンツのオーサリングにアセットを使用](./digital-asset-management.md#assets-authoring)を参照してください。

## レイヤー、設定、スタイルの移動 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

## コンテンツのパーソナライズ {#personalize-content}

[!DNL Journey Optimizer B2B Prime]は、パーソナライゼーションにHandlebars構文を使用しています。 トークンは、送信時に各受信者のプロファイルデータの値に置き換えられます。

_パーソナライゼーションを追加するには&#x200B;:_

1. テキストコンポーネントを選択し、ツールバーの「_パーソナライゼーションを追加_」（![&#x200B; パーソナライズのアイコン &#x200B;](../../user/assets/do-not-localize/icon-personalize.svg)）アイコンをクリックします。
1. パーソナライゼーションダイアログで、左側のスキーマツリーを参照し、プロファイル属性を選択します。 エディターは、対応するHandlebars式（例：`{{profile.firstName}}`）を挿入します。
1. 必要に応じて、欠落しているデータを処理するフォールバック値（例：`{{profile.firstName | default: "there"}}`）を追加します。
1. **[!UICONTROL 確認]**&#x200B;または&#x200B;**[!UICONTROL 挿入]**&#x200B;をクリックします。 式がフィールド内にインラインで表示されます。

式エディターツールと構文について詳しくは、[Personalization エディター](./personalization-expressions.md)を参照してください。

## リンクされたURL トラッキングを編集 {#edit-linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}
