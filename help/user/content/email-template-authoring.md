---
title: メールテンプレートオーサリング
description: アカウントジャーニーメールに使用できるコンテンツメールテンプレートを作成して、デザインを簡単かつ効率的に再利用する方法を説明します。
feature: Templates, Email Authoring, Content
role: User
exl-id: 2d532f93-c452-400a-8a82-e1f0eb89b199
source-git-commit: 9b053f81e3074f03740fe1f3b69f632219ad269a
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 15%

---

# メールテンプレートオーサリング

[ メールテンプレートを作成 ](./email-templates.md#create-an-email-template) した後、ビジュアルデザインスペースを使用して、メールテンプレートの構造コンポーネントとコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#structure-content}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_template"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはテンプレートのレイアウトを定義します。 テンプレートのコンテンツのデザインを開始するには、**構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップします。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_template"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、テンプレートのレイアウトの作成に使用できる空のコンテンツプレースホルダーです。"

{{$include /help/_includes/content-design-components.md}}

### カスタム CSS を追加

独自のカスタム CSS をメールテンプレートデザインスペース内に直接追加できます。 カスタム CSS を使用して高度な特定のスタイル設定を適用し、コンテンツの外観をより柔軟に制御できます。 画像、ボタン、テキストなどのコンポーネントを含める前に、この最高レベルのスタイルを追加することをお勧めします。

キャンバスに 1 つ以上のコンテンツコンポーネントがある状態で、左側のナビゲーションツリーで **[!UICONTROL 本文]** コンポーネントを選択して、カスタム CSS エディターにアクセスします。

![ 本文スタイルへのアクセス ](./assets/email-template-body-styles.png){width="800" zoomable="yes"}

{{$include /help/_includes/content-design-custom-css.md}}

### フラグメントを追加

{{$include /help/_includes/content-design-use-fragments.md}}

テンプレートが保存されると、概要の「_[!UICONTROL 使用]_」タブを選択したときに、フラグメントの詳細ページに表示されます。

### アセットの追加

{{$include /help/_includes/content-design-assets.md}}

### レイヤー、設定、スタイルの移動

{{$include /help/_includes/content-design-navigation.md}}

### コンテンツのパーソナライズ

{{$include /help/_includes/content-design-personalization-email.md}}

### リンクされた URL トラッキングを編集

{{$include /help/_includes/content-design-links.md}}

## オプションを表示

ビジュアルデザインスペースで使用できる表示およびコンテンツの検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、テキストのみ/プレーンテキストのいずれかでコンテンツの表示を切り替えます。
   * _目_ アイコンをクリックすると、デバイス間でコンテンツをプレビューできます。
   * 標準提供のデバイスの 1 つを選択するか、カスタムサイズを入力してコンテンツをプレビューします。

### 詳細オプション

メールデザインスペースの上部にある _[!UICONTROL その他…]_ メニューから、次のアクションを実行できます。

![ 「詳細」をクリックしてテンプレートアクションにアクセス ](./assets/visual-designer-more-menu.png){width="500"}

* **[!UICONTROL テンプレートをリセット]** – このオプションをクリックすると、デザインキャンバスを空白のスレートにクリアして、コンテンツの作成を再開できます。
* **[!UICONTROL フラグメントとして保存]** - テンプレートのすべてまたは一部をフラグメントとして保存し、複数のメールまたはメールテンプレートで再利用します。 フラグメントの名前と説明を指定し、使用可能なフラグメントのリストに保存します。
* **[!UICONTROL デザインを変更]** - _テンプレートのデザイン_ ページに戻ります。 ここから、テンプレートをゼロから設計するか、既存のテンプレートを使用して設計プロセスを再開するかを選択できます。
* **[!UICONTROL HTMLを書き出し]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式のローカルシステムにダウンロードします。
