---
title: ランディングページテンプレートデザイン
description: 再利用のためのランディングページテンプレートを設計 – Journey Optimizer B2B editionにコンテンツコンポーネント、フォーム、カスタム CSS、パーソナライゼーション、デバイスプレビューを追加します。
feature: Templates, Landing Pages, Content Design Tools
role: User
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
exl-id: 3dc6a523-1a33-4560-8f3c-ce8d0bf9f064
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: e666e996-b2cf-4c45-8fc2-1c625212abab
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
autotag-review: 2026-03-30T22:22:17.743Z
TQID: https://experienceleague.adobe.com/XlNcjTTWblzkxOISNEvzdI--xHz-sZiFUqsO3ferXTM
source-git-commit: 9baf03a1ddc1733385b0398ffadde8f548c431cc
workflow-type: tm+mt
source-wordcount: 353
ht-degree: 7%

---

# ランディングページテンプレートのデザイン

[ ランディングページテンプレートを作成した後](./landing-page-templates.md#create-a-landing-page-template)、ビジュアルデザインスペースを使用して、ページテンプレート内の構造コンポーネントとコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#structure-content-landing-page}

{{$include /help/_includes/content-design-components.md}}

### カスタム CSS を追加

ランディングページのデザインスペース内で、独自のカスタム CSSを直接追加できます。 カスタム CSSを使用して、高度で特定のスタイルを適用し、コンテンツの外観をより柔軟に制御できます。 画像、ボタン、テキストなどのコンポーネントを含める前に、この最高レベルのスタイル設定を追加することをお勧めします。

キャンバス内に少なくとも1つのコンテンツコンポーネントがある場合は、左側のナビゲーションツリーで&#x200B;**[!UICONTROL Body]** コンポーネントを選択して、カスタム CSS エディターにアクセスします。

![ ボディスタイルにアクセス ](./assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

{{$include /help/_includes/content-design-custom-css.md}}

### アセットの追加

{{$include /help/_includes/content-design-assets.md}}

### フォームを追加

{{$include /help/_includes/content-design-add-forms.md}}

### レイヤー、設定、スタイルの移動

{{$include /help/_includes/content-design-navigation.md}}

### コンテンツのパーソナライズ

{{$include /help/_includes/content-design-personalization.md}}

### リンクされたURL トラッキングを編集

{{$include /help/_includes/content-design-links.md}}

### 作品を保存

いつでも&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックして、ランディングページテンプレートを保存します。
<!--
You can continue to make edits to the draft page template. When you are ready to make it available for using in page creation, you can [publish the template](./landing-page-templates.md#). 
-->

### 表示オプション

ビジュアルデザイン分野で利用可能な表示およびコンテンツ検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、またはテキストのみ/プレーンテキストのコンテンツ表示を切り替えます。
   * デバイス間でコンテンツをプレビューするには、_表示_ アイコンをクリックします。
   * すぐに使えるデバイスのいずれかを選択するか、カスタムディメンションを入力してコンテンツをプレビューします。

### 詳細オプション

ビジュアルデザインスペースの上部にある「_[!UICONTROL その他…]_」メニューから、次の操作を実行できます。

![詳細をクリックしてテンプレートアクションにアクセス ](./assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL ランディングページをリセット]** – このオプションをクリックすると、ビジュアルデザインキャンバスが空白のスレートに消去され、ページコンテンツの作成が再開されます。
* **[!UICONTROL デザインを変更]** - _[!UICONTROL メインのランディングページの作成]_&#x200B;のホームページに戻ります。 そこから、別のテンプレートを選択してデザインプロセスを再開するか、空白のキャンバスでページをゼロからデザインするかを選択できます。
<!-- * **[!UICONTROL Save as content template]** - Save the page body as a landing page template to be reused across multiple landing pages. You provide a name and description for the template and save it to the list of saved  landing page templates. -->
* **[!UICONTROL HTMLを書き出し]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式でローカルシステムにダウンロードします。
