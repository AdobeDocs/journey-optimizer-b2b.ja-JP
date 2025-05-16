---
title: メールメッセージのオーサリング
description: Adobe Journey Optimizer B2B でメールコンテンツを作成する方法を説明します。 テンプレート、HTMLの読み込み、AI を利用したツールを使用して、メール通信をパーソナライズおよび最適化します。
feature: Email Authoring, Content Design Tools
role: User
exl-id: 0f4ae644-ade7-49a0-935c-7f4779c25ffb
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '949'
ht-degree: 20%

---

# メールメッセージのオーサリング

ジャーニーアクションノードに [ 新しい <!-- or duplicated --> メールアセットを追加 ](./add-email.md) した後、メールメッセージのコンテンツを定義できます。

**[!UICONTROL メール]** プレビューパネルの上部にある _[!UICONTROL メールコンテンツを追加]_ をクリックします。

![ 「メールコンテンツを追加」をクリックします ](./assets/add-email-content.png){width="700" zoomable="yes"}

このアクションは、メールデザインツールを起動し、次のオプションからメールのデザイン方法を選択できます。

* E メールDesignerインターフェイスを使用して ](#design-your-email-from-scratch) ゼロからメールをデザイン [ します。

* ファイルまたは .zip フォルダーから[既存の HTML コンテンツを読み込み](#import-existing-html-content)ます。

* [ 既存のテンプレートを選択 ](#select-a-template) – 組み込みまたはカスタムメールテンプレートのリストから行います。

式エディターで件名を設定およびパーソナライズするには、_Personalization_ アイコンをクリックし、任意のMarketo Engageトークンを追加します。

メールコンテンツを作成およびパーソナライズした後、コンテンツを書き出して、検証したり、後で使用したりできます。 「**[!UICONTROL HTMLを書き出し]**」をクリックして、HTMLとアセットを含む.zip ファイルとしてコンテンツを保存します。

>[!TIP]
>
>ジェネレーティブ AI を活用したAdobe Journey Optimizer B2B editionの AI アシスタントを使用して、コンテンツを次のレベルに引き上げます。 AI アシスタントは、メール全体の生成、ターゲット設定されたテキストコンテンツの生成、およびオーディエンスの共感を得られる画像に対する AI アシスタントのレコメンデーションの取得により、配信の影響を最適化するのに役立ちます。 [詳細情報](./ai-assistant-emails.md)

## メールをゼロからデザイン {#design-from-scratch}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_landing_page"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはランディングページのレイアウトを定義します。**構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップして、ランディングページのコンテンツのデザインを開始します。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_landing_page"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、ランディングページのレイアウトの作成に使用できる空のコンテンツプレースホルダーです。"

ビジュアルコンテンツエディターを使用して、メールコンテンツの構造を定義します。 簡単なドラッグ&amp;ドロップ操作で構造コンポーネントを追加して移動することで、再利用可能なメールコンテンツの形状を数秒でデザインできます。

1. _[!UICONTROL テンプレートをデザイン]_ ホームページで「**[!UICONTROL ゼロからデザイン]**」オプションを選択します。

1. メールメッセージに [ 構造とコンテンツを追加 ](#add-structure-and-content) します。
1. メールメッセージに [ 画像アセットを追加 ](#add-assets) します。
1. [ メールコンテンツをパーソナライズ ](#personalize-content)。
1. [ リンクを確認および更新 ](#preview-and-edit-linked-urls) します。

<!-- If needed, you can further personalize your email by clicking **[!UICONTROL Switch to code editor]** from the advanced menu. The code editor allows you to edit the email source code, such as adding tracking or custom HTML tags.

>[!CAUTION]
>
>You cannot revert back to the visual designer for this email after switching to the code editor. -->

コンテンツが完成したら、上部の **[!UICONTROL コンテンツをシミュレート]** をクリックしてレンダリングを確認します。 デスクトップまたはモバイル表示を選択できます。

内容に問題がなければ、「**[!UICONTROL 保存]**」をクリックします。

## 既存のHTML コンテンツの読み込み

{{$include /help/_includes/content-design-import.md}}

![html コンテンツを zip ファイルにインポート ](./assets/email-import-zip-file.png){width="500"}

>[!NOTE]
>
>`<table>` タグを HTML ファイルの最初のレイヤーとして使用すると、上部レイヤータグの背景や幅の設定などのスタイルが失われる可能性があります。

読み込んだコンテンツは、必要に応じて、視覚的なメールエディターツールを使用してパーソナライズできます。

## テンプレートを選択

{{$include /help/_includes/content-design-select-template.md}}

>[!NOTE]
>
> 保存済みのテンプレートには、1 つ以上のコンポーネントにガバナンス（コンテンツロック）設定を適用できます。 管理されたテンプレートからメールを作成する [ 場合、ビジュアルデザイナーには、ロックされたコンポーネントに関するガイドラインが表示さ ](./email-authoring-governance.md) ます。

## 構造とコンテンツの追加 {#structure-content}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_email"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはメールのレイアウトを定義します。 ドラッグ＆ドロップ&#x200B;**構造**&#x200B;コンポーネントをキャンバスに追加して、メールコンテンツのデザインを開始します。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_email"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、メールのレイアウト作成に使用できる空のコンテンツプレースホルダーです。"

{{$include /help/_includes/content-design-components.md}}

### フラグメントを追加

{{$include /help/_includes/content-design-use-fragments.md}}

メールを保存した後、概要の「_[!UICONTROL 使用者]_」タブを選択すると、フラグメントの詳細ページに表示されます。

### アセットの追加

{{$include /help/_includes/content-design-assets.md}}

### レイヤー、設定、スタイルの移動

{{$include /help/_includes/content-design-navigation.md}}

### コンテンツのパーソナライズ

{{$include /help/_includes/content-design-personalization.md}}

>[!NOTE]
>
>アカウントジャーニーに _[!UICONTROL マイトークン]_ が定義されている場合、メールコンテンツにこれらのジャーニー固有のトークンを使用することもできます。 詳しくは、[ メールのパーソナライゼーション用のカスタムトークン ](./personalization-my-tokens.md) を参照してください。

### リンクされた URL トラッキングを編集

{{$include /help/_includes/content-design-links.md}}

### オプションを表示

ビジュアルメールエディターで使用できる表示およびコンテンツの検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、テキストのみ/プレーンテキストのいずれかでコンテンツの表示を切り替えます。
   * _表示_ アイコンをクリックして、デバイス間でコンテンツをプレビューします。
   * 標準提供のデバイスの 1 つを選択するか、カスタムサイズを入力してコンテンツをプレビューします。

### 詳細オプション

メールデザインスペースの上部にある _[!UICONTROL その他…]_ メニューから、次のアクションを実行できます。

![ 「詳細」をクリックしてテンプレートアクションにアクセス ](./assets/email-designer-more-menu.png){width="500"}

* **[!UICONTROL メールをリセット]** – このオプションをクリックして、ビジュアルメールデザイナーキャンバスを空白のスレートにクリアし、コンテンツの作成を再開します。
* **[!UICONTROL フラグメントとして保存]** - メールのすべてまたは一部をフラグメントとして保存し、複数のメールまたはメールテンプレートで再利用します。 フラグメントの名前と説明を指定し、使用可能なフラグメントのリストに保存します。
* **[!UICONTROL デザインを変更]** - _メールのデザイン_ ページに戻ります。 ここから、別のテンプレートを選択してデザインプロセスを再開したり、黒いキャンバスでコンテンツをゼロからデザインしたりできます。
* **[!UICONTROL コンテンツテンプレートとして保存]** - メール本文をメールテンプレートとして保存し、複数のメールまたはメールテンプレートで再利用します。 テンプレートの名前と説明を指定し、保存済みのメールテンプレートのリストに保存します。
* **[!UICONTROL HTMLを書き出し]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式のローカルシステムにダウンロードします。

## メールを確認およびテスト {#preview-test}

>[!CONTEXTUALHELP]
>id="ajo-b2b_email_preview_simulate"
>title="コンテンツのレンダリング方法の確認"
>abstract="コンテンツを定義したら、プレビューし、使用しているチャネルのレンダリングが正しいかどうかを確認できます。"

メッセージコンテンツを定義したら、テストプロファイルを使用してプレビュー、配達確認の送信、一般的なデスクトップ、モバイルおよび web ベースのクライアントでのレンダリングの制御を行うことができます。 パーソナライズされたコンテンツを挿入した場合は、テストプロファイルデータを使用して、そのコンテンツがメッセージにどのように表示されるかをプレビューできます。

メールコンテンツをプレビューするには、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルを追加して、テストプロファイルデータを使用してメッセージを確認します。

![ メールコンテンツをシミュレートしてデザインを確認する ](./assets/email-designer-simulate-content.png){width="700" zoomable="yes"}
