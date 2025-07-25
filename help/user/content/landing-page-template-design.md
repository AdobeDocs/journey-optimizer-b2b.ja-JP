---
title: ランディングページのテンプレートデザイン
description: マーケターがランディングページの作成に再利用できるランディングページテンプレートのコンテンツをデザインおよび作成する方法について説明します。
feature: Templates, Landing Pages, Content Design Tools
role: User
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
exl-id: 3dc6a523-1a33-4560-8f3c-ce8d0bf9f064
source-git-commit: 9b053f81e3074f03740fe1f3b69f632219ad269a
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 18%

---

# ランディングページテンプレートのデザイン

[ ランディングページテンプレートの作成 ](./landing-page-templates.md#create-a-landing-page-template) 後、ビジュアルデザインスペースを使用して、ページテンプレートの構造コンポーネントとコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#structure-content-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_page_template_structure"
>title="ランディングページへの構造コンポーネントの追加"
>abstract="構造コンポーネントはランディングページのレイアウトを定義します。ページテンプレートのコンテンツのデザインを開始するには、**構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップします。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_page_template_content_components"
>title="ランディングページのコンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、ランディングページテンプレートのレイアウトの作成に使用できる空のコンテンツプレースホルダーです。"

{{$include /help/_includes/content-design-components.md}}

### カスタム CSS を追加

独自のカスタム CSS をランディングページデザインスペース内に直接追加できます。 カスタム CSS を使用して高度な特定のスタイル設定を適用し、コンテンツの外観をより柔軟に制御できます。 画像、ボタン、テキストなどのコンポーネントを含める前に、この最高レベルのスタイルを追加することをお勧めします。

キャンバスに 1 つ以上のコンテンツコンポーネントがある状態で、左側のナビゲーションツリーで **[!UICONTROL 本文]** コンポーネントを選択して、カスタム CSS エディターにアクセスします。

![ 本文スタイルへのアクセス ](./assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

{{$include /help/_includes/content-design-custom-css.md}}

### アセットの追加

{{$include /help/_includes/content-design-assets.md}}

### フォームを追加

{{$include /help/_includes/content-design-add-forms.md}}

### レイヤー、設定、スタイルの移動

{{$include /help/_includes/content-design-navigation.md}}

### コンテンツのパーソナライズ

{{$include /help/_includes/content-design-personalization.md}}

### リンクされた URL トラッキングを編集

{{$include /help/_includes/content-design-links.md}}

### 作業内容を保存します

**[!UICONTROL 保存]** をクリックすると、いつでもランディングページテンプレートを保存できます。
<!--
You can continue to make edits to the draft page template. When you are ready to make it available for using in page creation, you can [publish the template](./landing-page-templates.md#). -->

### オプションを表示

ビジュアルデザインスペースで使用できる表示およびコンテンツの検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、テキストのみ/プレーンテキストのいずれかでコンテンツの表示を切り替えます。
   * _表示_ アイコンをクリックして、デバイス間でコンテンツをプレビューします。
   * 標準提供のデバイスの 1 つを選択するか、カスタムサイズを入力してコンテンツをプレビューします。

### 詳細オプション

ビジュアルデザインスペースの上部にある _[!UICONTROL その他…]_ メニューから、次の操作を実行できます。

![ 「詳細」をクリックしてテンプレートアクションにアクセス ](./assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL ランディングページをリセット]** – このオプションをクリックして、ビジュアルデザインキャンバスを空白のスレートにクリアし、ページコンテンツの作成を再開します。
* **[!UICONTROL デザインを変更]** - _[!UICONTROL プライマリランディングページを作成]_ ホームページに戻ります。 ここから、別のテンプレートを選択してデザインプロセスを再開するか、空白のキャンバスでページをゼロからデザインするかを選択できます。
<!--- * **[!UICONTROL Save as content template]** - Save the page body as a landing page template to be reused across multiple landing pages. You provide a name and description for the template and save it to the list of saved  landing page templates. -->
* **[!UICONTROL HTMLを書き出し]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式のローカルシステムにダウンロードします。
