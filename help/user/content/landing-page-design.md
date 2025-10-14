---
title: ランディングページのデザイン
description: ビジュアルツールを使用したランディングページの設計 – Journey Optimizer B2B editionで、アカウントジャーニー用のコンテンツコンポーネント、フォーム、カスタム CSS、パーソナライゼーションおよびデバイスプレビューを追加します。
feature: Landing Pages, Content Design Tools
role: User
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
exl-id: 9297cfb0-ec77-4b20-8f62-d50578bb4d59
source-git-commit: 79012352c3ae4e2f3d38b632b1f523d262f74f96
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 3%

---

# ランディングページのデザイン

[&#x200B; ランディングページを作成 &#x200B;](./landing-pages.md#create-a-landing-page) した後、ビジュアルデザインスペースを使用して、ページの構造コンポーネントとコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#structure-content-landing-page}

{{$include /help/_includes/content-design-components.md}}

### カスタム CSS を追加

独自のカスタム CSS をランディングページデザインスペース内に直接追加できます。 カスタム CSS を使用して高度な特定のスタイル設定を適用し、コンテンツの外観をより柔軟に制御できます。 画像、ボタン、テキストなどのコンポーネントを含める前に、この最高レベルのスタイルを追加することをお勧めします。

キャンバスに 1 つ以上のコンテンツコンポーネントがある状態で、左側のナビゲーションツリーで **[!UICONTROL 本文]** コンポーネントを選択して、カスタム CSS エディターにアクセスします。

![&#x200B; 本文スタイルへのアクセス &#x200B;](./assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

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

**[!UICONTROL 保存]** をクリックすれば、いつでもドラフトランディングページを保存できます。

引き続きドラフトページに編集を加えることができます。 ページを表示し、メールまたは SMS メッセージでのリンクに使用できるようにする準備ができたら、ページを公開できます。

### オプションを表示

ビジュアルデザインスペースで使用できる表示およびコンテンツの検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、テキストのみ/プレーンテキストのいずれかでコンテンツの表示を切り替えます。
   * _表示_ アイコンをクリックして、デバイス間でコンテンツをプレビューします。
   * 標準提供のデバイスの 1 つを選択するか、カスタムサイズを入力してコンテンツをプレビューします。

### 詳細オプション

ビジュアルデザインスペースの上部にある _[!UICONTROL その他…]_ メニューから、次の操作を実行できます。

![&#x200B; 「詳細」をクリックしてテンプレートアクションにアクセス &#x200B;](./assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL ランディングページをリセット]** – このオプションをクリックして、ビジュアルデザインキャンバスを空白のスレートにクリアし、ページコンテンツの作成を再開します。
* **[!UICONTROL デザインを変更]** - _[!UICONTROL プライマリランディングページを作成]_ ホームページに戻ります。 ここから、別のテンプレートを選択してデザインプロセスを再開するか、空白のキャンバスでページをゼロからデザインするかを選択できます。
<!--- * **[!UICONTROL Save as content template]** - Save the page body as a landing page template to be reused across multiple landing pages. You provide a name and description for the template and save it to the list of saved  landing page templates. -->
* **[!UICONTROL HTMLを書き出し]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式のローカルシステムにダウンロードします。
