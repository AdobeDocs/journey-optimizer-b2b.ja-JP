---
title: ランディングページデザイン
description: ビジュアルツールを利用して、ランディングページをデザインできます。Journey Optimizer B2B editionなら、アカウントジャーニー用のコンテンツコンポーネントやフォーム、カスタム CSS、パーソナライゼーション、デバイスプレビューを追加できます。
feature: Landing Pages, Content Design Tools
role: User
exl-id: 9297cfb0-ec77-4b20-8f62-d50578bb4d59
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
  - id: a65c8aea-b21a-41ce-9ed7-6b517a69fd0b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
autotag-review: 2026-03-30T23:18:56.836Z
TQID: https://experienceleague.adobe.com/SXG2FrjpMlsGnofiUj1WeJ4NN3EVe1ZrcRpNdFfHwqA
source-git-commit: 508524bce6cdf1e5c4ad8c8916332666252472d1
workflow-type: tm+mt
source-wordcount: 411
ht-degree: 3%

---

# ランディングページのデザイン

[&#x200B; ランディングページを作成した後](./landing-pages-create-publish.md#create-landing-page)、ビジュアルデザインスペースを使用して、ページ内の構造コンポーネントとコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#structure-content-landing-page}

{{$include /help/_includes/content-design-components.md}}

### カスタム CSS を追加

ランディングページのデザインスペース内で、独自のカスタム CSSを直接追加できます。 カスタム CSSを使用して、高度で特定のスタイルを適用し、コンテンツの外観をより柔軟に制御できます。 画像、ボタン、テキストなどのコンポーネントを含める前に、この最高レベルのスタイル設定を追加することをお勧めします。

キャンバス内に少なくとも1つのコンテンツコンポーネントがある場合は、左側のナビゲーションツリーで&#x200B;**[!UICONTROL Body]** コンポーネントを選択して、カスタム CSS エディターにアクセスします。

![&#x200B; ボディスタイルにアクセス &#x200B;](./assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

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

![編集アイコンをクリックしてリンク追跡にアクセス &#x200B;](./assets/landing-page-link-tracking.png){width="400"}

**[!UICONTROL トラッキングタイプ]**&#x200B;を使用して、リンクのトラッキングを制御します。

* **[!UICONTROL トラッキング済み]** - リンク URLでトラッキングをアクティブ化します。
<!-- 
* External Opt-out - Considers the link URL as an opt-out or unsubscription URL.

* Mirror page - Considers the link URL as a mirror page URL.
-->
* **[!UICONTROL なし]** - リンク URLのトラッキングをアクティブ化しません。

### 作品を保存

いつでも&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックして、ドラフト ランディングページを保存します。

引き続きドラフトページを編集できます。 ページを表示し、電子メールまたはSMS メッセージでリンクできるようにする準備ができたら、ページを公開できます。

### 表示オプション

ビジュアルデザイン分野で利用可能な表示およびコンテンツ検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、またはテキストのみ/プレーンテキストのコンテンツ表示を切り替えます。
   * デバイス間でコンテンツをプレビューするには、_表示_ アイコンをクリックします。
   * すぐに使えるデバイスのいずれかを選択するか、カスタムディメンションを入力してコンテンツをプレビューします。

### 詳細オプション

ビジュアルデザインスペースの上部にある「_[!UICONTROL その他…]_」メニューから、次の操作を実行できます。

![詳細をクリックしてランディングページのアクションにアクセス &#x200B;](./assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL ランディングページをリセット]** – このオプションをクリックすると、ビジュアルデザインキャンバスが空白のスレートに消去され、ページコンテンツの作成が再開されます。
* **[!UICONTROL デザインを変更]** - _[!UICONTROL メインのランディングページの作成]_&#x200B;のホームページに戻ります。 そこから、別のテンプレートを選択してデザインプロセスを再開するか、空白のキャンバスでページをゼロからデザインするかを選択できます。
<!-- * **[!UICONTROL Save as content template]** - Save the page body as a landing page template to be reused across multiple landing pages. You provide a name and description for the template and save it to the list of saved  landing page templates. -->
* **[!UICONTROL HTMLを書き出し]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式でローカルシステムにダウンロードします。
