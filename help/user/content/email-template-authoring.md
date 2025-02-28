---
title: メールテンプレートオーサリング
description: アカウントジャーニーメールに使用できるコンテンツメールテンプレートを作成して、デザインを簡単かつ効率的に再利用する方法を説明します。
feature: Email Authoring, Content
source-git-commit: 8315c760e573aa36819652798a400206e6268ccc
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 11%

---

# メールテンプレートオーサリング

[ メールテンプレートを作成 ](./email-templates.md#create-an-email-template) した後、ビジュアルデザイナーを使用して、メールテンプレートの構造コンポーネントとコンテンツコンポーネントを作成します。

## 構造とコンテンツを追加 {#structure-content}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_template"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはテンプレートのレイアウトを定義します。 テンプレートのコンテンツのデザインを開始するには、**構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップします。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_template"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、テンプレートのレイアウトの作成に使用できる空のコンテンツプレースホルダーです。"

{{$include /help/_includes/content-design-components.md}}

### フラグメントを追加

ビジュアルコンテンツエディターでは、「_フラグメント_」アイコンが左側に表示されます。 次の例では、フラグメントをテンプレートコンテンツに追加する手順の概要を説明します。

1. フラグメントリストを開くには、_フラグメント_ アイコン（![ フラグメントアイコン ](../assets/do-not-localize/icon-fragments.svg)）を選択します。

   次の操作が可能です。

   * リストを並べ替えます。
   * リストを参照、検索またはフィルターします。
   * サムネール表示とリスト表示を切り替えます。
   * 最近作成したフラグメントが反映されるように、リストを更新します。

   ![ リストからフラグメントを選択 ](./assets/visual-designer-fragments.png){width="700" zoomable="yes"}

1. 任意のフラグメントを構造コンポーネントプレースホルダーにドラッグ&amp;ドロップします。

   エディターは、メール構造のセクション/要素内でフラグメントをレンダリングします。

フラグメントのコンテンツは構造内で動的に更新され、コンテンツがメールにどのように表示されるかが表示されます。

>[!TIP]
>
>フラグメントをメール内の水平レイアウト全体に配置する場合は、1:1 列構造を追加してから、フラグメントをメール内にドラッグ&amp;ドロップします。

メールを保存した後、概要の「_[!UICONTROL 使用者]_」タブを選択すると、フラグメントの詳細ページに表示されます。 メールテンプレートに追加されたフラグメントは、テンプレート内では編集できません。ソースフラグメントがコンテンツを定義します。

### アセットの追加

{{$include /help/_includes/content-design-assets.md}}

### レイヤー、設定、スタイルの移動

{{$include /help/_includes/content-design-navigation.md}}

### コンテンツのパーソナライズ

{{$include /help/_includes/content-design-personalization.md}}

### リンクされた URL トラッキングを編集

{{$include /help/_includes/content-design-links.md}}

## オプションを表示

ビジュアルデザイナーで使用できる表示およびコンテンツの検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、テキストのみ/プレーンテキストのいずれかでコンテンツの表示を切り替えます。
   * _目_ アイコンをクリックすると、デバイス間でコンテンツをプレビューできます。
   * 標準提供のデバイスの 1 つを選択するか、カスタムサイズを入力してコンテンツをプレビューします。

### 詳細オプション

電子メールデザイナーの上部にある _[!UICONTROL その他…]_ メニューから、次のアクションを実行できます。

![ 「詳細」をクリックしてテンプレートアクションにアクセス ](./assets/visual-designer-more-menu.png){width="500"}

* **[!UICONTROL テンプレートをリセット]** – このオプションをクリックすると、ビジュアルデザイナーのキャンバスを空白のスレートに戻し、コンテンツの作成を再開できます。
* **[!UICONTROL フラグメントとして保存]** - テンプレートのすべてまたは一部をフラグメントとして保存し、複数のメールまたはメールテンプレートで再利用します。 フラグメントの名前と説明を指定し、使用可能なフラグメントのリストに保存します。
* **[!UICONTROL デザインを変更]** - _テンプレートのデザイン_ ページに戻ります。 ここから、テンプレートをゼロから設計するか、既存のテンプレートを使用して設計プロセスを再開するかを選択できます。
* **[!UICONTROL 書き出しHTML]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式でローカルシステムにダウンロードします。
