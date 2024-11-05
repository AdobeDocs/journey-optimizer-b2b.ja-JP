---
title: メールオーサリング
description: アカウントのジャーニーで使用される、パーソナライズされたメールコンテンツを作成する方法を説明します。
feature: Email Authoring, Content
exl-id: 0f4ae644-ade7-49a0-935c-7f4779c25ffb
source-git-commit: 8315c760e573aa36819652798a400206e6268ccc
workflow-type: tm+mt
source-wordcount: '1428'
ht-degree: 14%

---

# メールオーサリング

Adobe Journey Optimizer B2B editionを使用すると、メールメッセージを顧客に送信できます。 ビジュアルデザイナーで、メッセージの作成、パーソナライズ、プレビューを行えます。

## アカウントジャーニーへのメールアクションの追加

_[!UICONTROL 特定のアクションを実行]_ ノードを追加して以下の操作を実行すると、アカウントジャーニーでメール配信を設定できます。

1. _[!UICONTROL アクションオン]_ ターゲットで、「**[!UICONTROL ユーザー]**」を選択します。
1. _[!UICONTROL ユーザーに対するアクション]_ については、「**[!UICONTROL メールを送信]**」を選択します。
1. _[!UICONTROL メールソース]_ については、「**[!UICONTROL 新しいメールを作成]**」を選択します。

   または、「_[!UICONTROL Adobe Marketo Engageからメールを選択]_」オプションを使用して、Marketo Engageで作成済みのメールの 1 つを使用し、アカウントジャーニーの一部として送信することもできます。

   >[!NOTE]
   >
   >初めてメールを作成する場合は、Adobe Marketo Engage内でメールチャネルがから設定されていることを確認してください。 詳しくは、Marketo Engageドキュメントの [ メール配信品質の確認 ](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps#ensure-email-deliverability) を参照してください。

   ![ アクションの実行 – メールの送信 ](assets/journey-node-send-email.png){width="700" zoomable="yes"}

1. _[!UICONTROL アクションの実行]_ パネルの下部にある「**[!UICONTROL メールの作成]**」をクリックします。

1. ダイアログで、メールの一意の **[!UICONTROL 名前]** と **[!UICONTROL 件名]** を入力します。

   ![ 新しいメールを作成ダイアログ ](assets/create-new-email.png){width="400"}

1. 「**[!UICONTROL 作成]**」をクリックします。

   メールコンテンツページの _[!UICONTROL メールのプロパティ]_ セクションで、_[!UICONTROL 送信者メール]_ および _[!UICONTROL 返信先アドレス]_ フィールドが既に設定されています。 「_[!UICONTROL 送信者名]_」フィールドと「_[!UICONTROL 説明]_ （オプション）」フィールドの値を入力できます。

## メールコンテンツを作成

**[!UICONTROL メール]** プレビューパネルの上部にある _[!UICONTROL メールコンテンツを追加]_ をクリックします。

![ 「メールコンテンツを追加」をクリックします ](./assets/add-email-content.png){width="700" zoomable="yes"}

メールDesignerが起動し、以下のオプションからメールのデザイン方法を選択できます。

* E メールDesignerインターフェイスを使用して ](#design-your-email-from-scratch) ゼロからメールをデザイン [ します。

* ファイルまたは .zip フォルダーから[既存の HTML コンテンツを読み込み](#import-existing-html-content)ます。

* [ 既存のテンプレートを選択 ](#select-a-template) – 組み込みまたはカスタムメールテンプレートのリストから行います。

式エディターで件名を設定およびパーソナライズするには、_Personalization_ アイコンをクリックし、任意のMarketo Engageトークンを追加します。

メールコンテンツを作成およびパーソナライズした後、コンテンツを書き出して、検証したり、後で使用したりできます。 **[!UICONTROL 書き出しHTML]** をクリックして、HTMLとアセットを含む.zip ファイルとしてコンテンツを保存します。

>[!TIP]
>
>ジェネレーティブ AI を活用したAdobe Journey Optimizer B2B editionの AI アシスタントを使用して、コンテンツを次のレベルに引き上げます。 AI アシスタントは、メール全体の生成、ターゲット設定されたテキストコンテンツの生成、およびオーディエンスの共感を得られる画像に対する AI アシスタントのレコメンデーションの取得により、配信の影響を最適化するのに役立ちます。 [詳細情報](./ai-assistant-emails.md)

### メールをゼロからデザイン {#design-from-scratch}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_landing_page"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはランディングページのレイアウトを定義します。 **構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップして、ランディングページのコンテンツのデザインを開始します。"

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

### 既存のHTMLコンテンツの読み込み

{{$include /help/_includes/content-design-import.md}}

![html コンテンツを zip ファイルにインポート ](./assets/email-import-zip-file.png){width="500"}

>[!NOTE]
>
>`<table>` タグを HTML ファイルの最初のレイヤーとして使用すると、上部レイヤータグの背景や幅の設定などのスタイルが失われる可能性があります。

読み込んだコンテンツは、必要に応じて、視覚的なメールエディターツールを使用してパーソナライズできます。

### テンプレートを選択

{{$include /help/_includes/content-design-select-template.md}}

>[!NOTE]
>
> 保存済みのテンプレートには、1 つ以上のコンポーネントにガバナンス（コンテンツロック）設定を適用できます。 管理されたテンプレートからメールを作成する [ 場合、ビジュアルデザイナーには、ロックされたコンポーネントに関するガイドラインが表示さ ](./email-authoring-governance.md) ます。

## 構造とコンテンツを追加 {#structure-content}

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

ビジュアルコンテンツエディターでは、「_フラグメント_」アイコンが左側に表示されます。 次の例では、フラグメントをテンプレートコンテンツに追加する手順の概要を説明します。

1. フラグメントリストを開くには、「_フラグメント_」アイコンをクリックします。

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
>メール内の水平レイアウト全体を占めるようにフラグメントを追加するには、1:1 列構造を追加してから、フラグメントをドラッグ&amp;ドロップします。

メールを保存した後、概要の「_[!UICONTROL 使用者]_」タブを選択すると、フラグメントの詳細ページに表示されます。 メールテンプレートに追加されたフラグメントは、テンプレート内では編集できません。ソースフラグメントがコンテンツを定義します。

### アセットの追加

{{$include /help/_includes/content-design-assets.md}}

### レイヤー、設定、スタイルの移動

{{$include /help/_includes/content-design-navigation.md}}

### コンテンツのパーソナライズ

{{$include /help/_includes/content-design-personalization.md}}

### リンクされた URL トラッキングを編集

{{$include /help/_includes/content-design-links.md}}

### オプションを表示

ビジュアルメールエディターで使用できる表示およびコンテンツの検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、テキストのみ/プレーンテキストのいずれかでコンテンツの表示を切り替えます。
   * _表示_ アイコンをクリックして、デバイス間でコンテンツをプレビューします。
   * 標準提供のデバイスの 1 つを選択するか、カスタムサイズを入力してコンテンツをプレビューします。

### 詳細オプション

電子メールデザイナーの上部にある _[!UICONTROL その他…]_ メニューから、次のアクションを実行できます。

![ 「詳細」をクリックしてテンプレートアクションにアクセス ](./assets/email-designer-more-menu.png){width="500"}

* **[!UICONTROL メールをリセット]** – このオプションをクリックして、ビジュアルメールデザイナーキャンバスを空白のスレートにクリアし、コンテンツの作成を再開します。
* **[!UICONTROL フラグメントとして保存]** - メールのすべてまたは一部をフラグメントとして保存し、複数のメールまたはメールテンプレートで再利用します。 フラグメントの名前と説明を指定し、使用可能なフラグメントのリストに保存します。
* **[!UICONTROL デザインを変更]** - _メールのデザイン_ ページに戻ります。 ここから、別のテンプレートを選択してデザインプロセスを再開したり、黒いキャンバスでコンテンツをゼロからデザインしたりできます。
* **[!UICONTROL コンテンツテンプレートとして保存]** - メール本文をメールテンプレートとして保存し、複数のメールまたはメールテンプレートで再利用します。 テンプレートの名前と説明を指定し、保存済みのメールテンプレートのリストに保存します。
* **[!UICONTROL 書き出しHTML]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式でローカルシステムにダウンロードします。

## アラートの確認

メールメッセージコンテンツをデザインする際、重要な設定が見つからない場合は、インターフェイス（ページの右上）にアラートが表示されます。

このボタンが表示されない場合は、検出された問題はありません。

次の 2 種類のアラートを検出できます。

* 推奨事項やベストプラクティスを参照する **_警告_**。例えば、次のようなものがあります。

   * `The opt-out link is not present in the email body`：メール本文に購読解除リンクを追加することがベストプラクティスです。

     >[!NOTE]
     >
     >マーケティングスタイルの電子メールメッセージには、オプトアウトリンクを含める必要があります。これはトランザクションメッセージには必要ありません。

   * `Text version of HTML is empty`：メール本文のテキストバージョンを必ず定義してください。このバージョンは、HTMLコンテンツを表示できない場合に使用されます。

   * `Empty link is present in email body`: メール内のすべてのリンクが正しいことを確認してください。

   * `Email size has exceeded the limit of 100KB`：配信を最適化するには、メールのサイズが 100 KB を超えないようにしてください。

* **_エラー_** 解決されない限り、ジャーニー/キャンペーンのテストやアクティブ化はできません。例えば、次のエラーなどです。

   * `The subject line is missing`：メールの件名は必須です。

   * `The email version of the message is empty`：このエラーは、メールコンテンツが設定されていない場合に表示されます。

## メールを確認およびテスト {#preview-test}

>[!CONTEXTUALHELP]
>id="ajo-b2b_email_preview_simulate"
>title="コンテンツのレンダリング方法の確認"
>abstract="コンテンツを定義したら、プレビューし、使用しているチャネルのレンダリングが正しいかどうかを確認できます。"

メッセージコンテンツを定義したら、テストプロファイルを使用してプレビュー、配達確認の送信、一般的なデスクトップ、モバイルおよび web ベースのクライアントでのレンダリングの制御を行うことができます。 パーソナライズされたコンテンツを挿入した場合は、テストプロファイルデータを使用して、そのコンテンツがメッセージにどのように表示されるかをプレビューできます。

メールコンテンツをプレビューするには、「**[!UICONTROL コンテンツをシミュレート]**」をクリックし、テストプロファイルを追加して、テストプロファイルデータを使用してメッセージを確認します。

![ メールコンテンツをシミュレートしてデザインを確認する ](./assets/email-designer-simulate-content.png){width="700" zoomable="yes"}
