---
title: ランディングページデザイン
description: ビジュアルツールを利用して、ランディングページをデザインしましょう。Journey Optimizer B2B Primeなら、コンテンツコンポーネント、フォーム、カスタム CSS、パーソナライゼーション、デバイスのプレビューを利用して、カスタマージャーニーを構築できます。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、限定的なベータ版リリースの一部です。"
feature: Landing Pages, Content Design Tools
role: User
autotag-review: '2026-07-08T20:36:05.221Z'
TQID: 'https://experienceleague.adobe.com/M8OA0CPihuuX5h9J-ZrGJOPHkHLwatX5VhBa8co4r4Y'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: aed878b8-11d0-487c-828b-d23b2051ec37id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: a96755d6-1f54-4f3f-a971-d31f83705ab7id: e7bdffdc-2950-4be5-8c23-84240a995090id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 75a4fec07c880f52ac1e8981b5f4416a2f69afe9
workflow-type: tm+mt
source-wordcount: 568
ht-degree: 2%

---

# ランディングページのデザイン

[ ランディングページを作成した後](./landing-pages-create-publish.md#create-landing-page)、ビジュアルデザインスペースを使用して、ページ内の構造コンポーネントとコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#structure-content-landing-page}

{{$include /help/_includes/content-design-components-prime.md}}

### カスタム CSS を追加 {#add-custom-css}

ランディングページのデザインスペース内で、独自のカスタム CSSを直接追加できます。 カスタム CSSを使用して、高度で特定のスタイルを適用し、コンテンツの外観をより柔軟に制御できます。 画像、ボタン、テキストなどのコンポーネントを含める前に、この最高レベルのスタイル設定を追加することをお勧めします。

キャンバス内に少なくとも1つのコンテンツコンポーネントがある場合は、左側のナビゲーションツリーで&#x200B;**[!UICONTROL Body]** コンポーネントを選択して、カスタム CSS エディターにアクセスします。

![ ボディスタイルにアクセス ](../../user/content/assets/landing-page-body-styles-css.png){width="800" zoomable="yes"}

手順、構文ルール、およびトラブルシューティングについては、[ コンテンツ用カスタム CSSの追加](./design-custom-css.md)を参照してください。

### アセットの追加 {#add-assets}

ビジュアルデザイン領域で、左側のナビゲーションバーの&#x200B;_Assets_ （![Assetsアイコン ](../../assets/do-not-localize/icon-assets-me.svg)）アイコンを選択し、[!DNL Journey Optimizer B2B Prime] アセットライブラリから画像アセットを参照して選択します。

画像アセットを選択、置換、またはアップロードする手順については、[ コンテンツのオーサリングにアセットを使用](./digital-asset-management.md#assets-authoring)を参照してください。

### フォームを追加 {#add-forms}

{{$include /help/_includes/content-design-add-forms.md}}

### レイヤー、設定、スタイルの移動 {#navigate-layers-settings-styles}

{{$include /help/_includes/content-design-navigation.md}}

### コンテンツのパーソナライズ {#personalize-content}

[!DNL Journey Optimizer B2B Prime]は、パーソナライゼーションにHandlebars構文を使用しています。 ランディングページが表示されると、トークンは各訪問者のプロファイルデータの値に置き換えられます。

_パーソナライゼーションを追加するには&#x200B;:_

1. テキストコンポーネントを選択し、ツールバーの「_パーソナライゼーションを追加_」（![ パーソナライズのアイコン ](../../user/assets/do-not-localize/icon-personalize.svg)）アイコンをクリックします。
1. パーソナライゼーションダイアログで、左側のスキーマツリーを参照し、属性を選択します。 対応するHandlebars式が挿入されます。
1. 必要に応じて、欠落しているデータを処理するフォールバック値を追加します。
1. **[!UICONTROL 確認]**&#x200B;または&#x200B;**[!UICONTROL 挿入]**&#x200B;をクリックします。 式がフィールド内にインラインで表示されます。

式エディターツールと構文について詳しくは、[Personalization エディター](./personalization-expressions.md)を参照してください。

### リンクされたURL トラッキングを編集 {#linked-url-tracking}

{{$include /help/_includes/content-design-links.md}}

![編集アイコンをクリックしてリンク追跡にアクセス ](../../user/content/assets/landing-page-link-tracking.png){width="400"}

**[!UICONTROL トラッキングタイプ]**&#x200B;を使用して、リンクのトラッキングを制御します。

* **[!UICONTROL トラッキング済み]** - リンク URLでトラッキングをアクティブ化します。
* **[!UICONTROL なし]** - リンク URLのトラッキングをアクティブ化しません。

### 作品を保存 {#save-your-work}

いつでも&#x200B;**[!UICONTROL 保存]**&#x200B;をクリックして、ドラフト ランディングページを保存します。

引き続きドラフトページを編集できます。 ページを表示し、電子メールまたはSMS メッセージでリンクできるようにする準備ができたら、ページを公開できます。

### 表示オプション {#view-options}

ビジュアルデザイン分野で利用可能な表示およびコンテンツ検証オプションを活用します。

* プリセットのズームオプション全体でコンテンツをズームイン/ズームアウトします。

* デスクトップ、モバイル、またはテキストのみ/プレーンテキストのコンテンツ表示を切り替えます。
   * デバイス間でコンテンツをプレビューするには、_表示_ アイコンをクリックします。
   * すぐに使えるデバイスのいずれかを選択するか、カスタムディメンションを入力してコンテンツをプレビューします。

### 詳細オプション {#more-options}

ビジュアルデザインスペースの上部にある「_[!UICONTROL その他…]_」メニューから、次の操作を実行できます。

![詳細をクリックしてランディングページのアクションにアクセス ](../../user/content/assets/landing-page-designer-more-menu.png){width="500"}

* **[!UICONTROL ランディングページをリセット]** – このオプションをクリックすると、ビジュアルデザインキャンバスが空白のスレートに消去され、ページコンテンツの作成が再開されます。
* **[!UICONTROL デザインを変更]** - _[!UICONTROL メインのランディングページの作成]_&#x200B;のホームページに戻ります。 そこから、別のテンプレートを選択してデザインプロセスを再開するか、空白のキャンバスでページをゼロからデザインするかを選択できます。
* **[!UICONTROL HTMLを書き出し]** - ビジュアルキャンバスのコンテンツを、zip ファイルとしてパッケージ化されたHTML形式でローカルシステムにダウンロードします。
