---
title: Web エクスペリエンスデザイン
description: Journey Optimizer B2B editionで、視覚的なエディターと非視覚的なエディターを使用して web エクスペリエンスを設計します。変更を追加したり、コンテンツの更新を管理したり、クリック追跡を有効にしたり、コンテンツをパーソナライズしたりします。
feature: Content Design Tools, Channels
role: User
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
source-git-commit: d01f4c14f72ebf78b10e4fc6691df42707bedb47
workflow-type: tm+mt
source-wordcount: '2333'
ht-degree: 4%

---

# Web エクスペリエンスデザイン

[Web エクスペリエンスを作成 &#x200B;](./web-experiences.md#create-a-web-experience) した後で、コンテンツデザインスペースを使用して、Web ページに適用する変更を定義します。

>[!BEGINSHADEBOX]

**前提条件**

Web エクスペリエンスをデザインする前に、次の要件が満たされていることを確認します。

* 製品管理者は、1 つ以上の web チャネルを設定して、web エクスペリエンスに含める URL （ページ）を定義しています。 詳しくは、「[Web チャネル設定 &#x200B;](../admin/configure-channels-web.md)」を参照してください。

* Web サイトには、訪問者の特定とコンテンツ配信のために [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/js-overview) （`alloy.js`）が実装されています。 Adobe Experience Platform Web SDK バージョン 2.16 以降が必要です。

* ジャーニーで web エクスペリエンスを作成および管理するために必要な [&#x200B; 権限 &#x200B;](../admin/user-management.md#b2b-product-permissions) を持っている。
   * _[!UICONTROL キャンペーン]_/_[!UICONTROL キャンペーンの管理]_ - web パーソナライゼーションアクションノードを追加または更新するために必要です。
   * _[!UICONTROL キャンペーン]_/_[!UICONTROL キャンペーンを表示]_ - Web パーソナライゼーションアクションノードの詳細を表示するために必要です。

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>Web エクスペリエンスをデザインする前に、web ブラウザーにAdobe Experience Cloud Visual Editing Helper ブラウザー拡張機能がインストールされていることを確認します。 この拡張機能は、Journey Optimizer B2B editionの web エクスペリエンスデザイン領域で web ページを確実に開いて作成し、プレビューするために必要です。<br/>
>
>現在、Google ChromeとMicrosoft Edgeは、Journey Optimizer B2B editionでの web エクスペリエンスの拡張とオーサリングをサポートしている唯一のブラウザーです。 詳しくは、[Visual Editing Helper 拡張機能のインストール &#x200B;](./web-experiences.md#install-the-visual-editing-helper-extension) を参照してください。

## Web エクスペリエンスエディター

Journey Optimizer B2B editionには、web 変更を設計するための 2 種類のエディターが用意されています。

| エディタ | 説明 | に最適 |
| ------ | ----------- | -------- |
| [&#x200B; ビジュアルエディター &#x200B;](#visual-editor) | Web サイトを表示し、要素を直接選択および変更できるWYSIWYG （_What You See Is What You Get_） エディター。 Google ChromeまたはMicrosoft Edge web ブラウザーの [Visual Editing Helper 拡張機能 &#x200B;](./web-experiences.md#install-the-visual-editing-helper-extension) が必要です。 | テキスト、画像、ボタン、バナーなど、表示されるページ要素に視覚的な変更を加える。 |
| [&#x200B; 非視覚的エディター &#x200B;](#non-visual-editor) | ビジュアルエディターでは不可能な変更を適用するためのコードベースのエディター。 | 視覚的な選択が困難な要素のターゲティング、高度な CSS 変更の適用、非表示要素の変更。 |

Web エクスペリエンスのプロパティで、「**[!UICONTROL ビジュアルエディター]**」オプションを使用して、エディターのタイプを判断します。 ビジュアルエディターを使用する場合はオプションを有効にし、ビジュアルエディター以外の場合は無効にします。

![&#x200B; ビジュアルエディターオプションが有効 &#x200B;](./assets/web-experience-design-visual-editor-option.png){width="400"}

## ビジュアルエディター {#visual-editor}

>[!CONTEXTUALHELP]
>id="ajo-b2b_web_experience_browse"
>title="参照モードの使用"
>abstract="このモードでは、選択した web チャネル設定に対してパーソナライズするページに移動できます。"

ビジュアルエディターが、iframe 内の web ページを読み込み、ページプレビューで直接要素を選択して変更を適用できます。 Web エクスペリエンスのデザインにビジュアルエディターを使用するには、次の手順を実行します。

1. Web エクスペリエンスの詳細ページに表示された「_[!UICONTROL コンテンツ]_」タブを使用して、右側のパネルの **[!UICONTROL Web エクスペリエンスを編集]** をクリックします。

   ビジュアルエディターは、web チャネルの設定に基づいて web サイトを読み込みます。

   ![Web エクスペリエンスビジュアルエディター &#x200B;](./assets/web-experience-design-visual-editor.png){width="800" zoomable="yes"}

1. 必要に応じて、右上の **[!UICONTROL 参照]** をクリックし、サイトナビゲーションバーを使用して、変更する特定のページを読み込みます。

   また、上部のフィールドにページ URL を入力することもできます。

   >[!NOTE]
   >
   >読み込んだページが、web チャネル設定で定義された URL パターンと一致することを確認します。 右上の **[!UICONTROL 設定の詳細を表示]** をクリックすると、選択した web チャネル設定の URL またはページ一致ルールが表示されます。

   ![&#x200B; ビジュアルエディターでの参照モード &#x200B;](./assets/web-experience-design-visual-editor-browse.png){width="700" zoomable="yes"}

   <!-- If the web channel configuration is defined using page matching rules, use the left and right arrows to sequence through the matched pages -- right now these buttons don't do anything -->

   右上の **[!UICONTROL デザイン]** をクリックして、デザインスペースにページを読み込みます。

1. Web エクスペリエンスに合わせて表示されるページの変更方法を定義するには、次の操作を実行します。

   * Web エクスペリエンスのページに [&#x200B; 新しいコンポーネントを挿入 &#x200B;](#insert-new-components) ディバイダー、HTML、画像、見出し、段落、またはリンク）。

   * ページから既存の要素（画像、ボタン、段落、テキスト、コンテナ、見出し、リンクなど）を選択し、[web エクスペリエンス用に変更 &#x200B;](#modify-elements) します。

   * エンゲージメントを測定しインサイトを収集する要素の [&#x200B; クリックの追跡を追加 &#x200B;](#click-tracking-for-web-experiences) します。

1. 手順 2 を繰り返して、web エクスペリエンスに含める他のページを読み込み、手順 3 を繰り返して、ページの変更を定義します。

1. [&#x200B; 変更をレビューし &#x200B;](#manage-modifications) 必要な調整を行います。

1. 変更が完了したら、エディターの上にある左矢印をクリックして、web エクスペリエンスプロパティに戻ります。

### 要素の変更

表示されたページの要素をクリックして選択します。 青い境界線は選択した要素を示し、コンテキストツールバーに変更オプションが表示されます。

![&#x200B; 変更する要素を選択 &#x200B;](./assets/web-experience-design-select-element.png){width="700" zoomable="yes"}

ツールバーのオプションは、選択したコンポーネントタイプによって異なります。

| アクション | 説明 |
| ------ | ----------- |
| **[!UICONTROL テキストオプション]** | 選択した要素のテキスト要素クラスまたはテキストのスタイル設定を変更します。 |
| **[!UICONTROL 画像を選択]** | 画像のソースを置き換えるか、要素に画像を追加します。 |
| **[!UICONTROL リンクを編集/リンクを追加]** | リンク URL を変更または追加します。 |
| **[!UICONTROL 整列]** | 選択した要素をディスプレイ内で前後に移動します。 |
| **[!UICONTROL パーソナライゼーションの追加]** | パーソナライゼーションを挿入します。 |
| **[!UICONTROL クリック追跡要素]** | 要素のクリックの追跡を追加します。 |
| **[!UICONTROL 削除]** | 選択した要素をページから削除します。 |

選択した要素について、右側のパネルのプロパティが、使用可能なスタイル設定とアクションを反映して変更されます。 パネルの上部にあるアクションアイコンをクリックして、選択した要素を複製、クリック追跡、削除または非表示にします。

![&#x200B; 選択した要素のアクションアイコンをクリック &#x200B;](./assets/web-experience-design-visual-editor-element-properties-icons.png){width="300"}

+++テキスト要素

1. ページ上のテキスト要素を選択します。

1. 新しいテキストコンテンツを入力するか、テキスト文字列を選択して置換テキストを入力します。

1. （オプション）太字、斜体、配置など、[&#x200B; テキスト書式設定オプション &#x200B;](./content-components.md#text) を使用します。

1. テキスト要素の外側をクリックして、変更を適用します。

テキストコンポーネントのテキストスタイルオプションについて詳しくは、[&#x200B; コンテンツコンポーネント &#x200B;](./content-components.md#text) を参照してください。

+++

+++画像要素

1. ページ上の画像要素を選択します。

1. コンテキストツールバーまたは右側のパネルにある「_[!UICONTROL 画像を選択]_」アイコンをクリックします。

1. アセットライブラリから画像を参照して選択します。

1. 必要に応じて、右側のパネルの [&#x200B; 画像スタイル設定オプション &#x200B;](./content-components.md#image) を使用します。

+++

+++ボタンの要素

1. ページ上のボタン要素を選択します。

1. （オプション）ボタンの新しいテキストを入力するか、テキスト文字列を選択して置き換えるテキストを入力します。

   パーソナライゼーションを使用すると、アカウントプロファイルまたはユーザープロファイルのデータを使用してボタンテキストを変更できます。

1. 必要に応じて、右側のパネルの [&#x200B; ボタンのスタイルオプション &#x200B;](./content-components.md#button) を使用します。

+++

+++ コンテナ要素

1. ページ上でコンテナ要素を選択します。

1. 必要に応じて、右側のパネルの [&#x200B; コンテナのスタイルオプション &#x200B;](./content-components.md#container) を使用します。

+++

### 新しいコンポーネントの挿入

ビジュアルエディターのデザインの左側のナビゲーションで「**+**」アイコンを選択すると、次のコンポーネントタイプを web エクスペリエンスの変更としてページに追加できます。

* **[!UICONTROL ディバイダー]** – このコンポーネントを使用すると、分割線を挿入してメールのレイアウトと内容を整理できます。 線の色、スタイル、高さなどのスタイル属性は、右側のパネルのプロパティから調整できます。 詳しくは、[&#x200B; コンテンツコンポーネント &#x200B;](./content-components.md#divider) の _ディバイダー_ を参照してください。
* **[!UICONTROL HTML]** – このコンポーネントを使用して、既存の構造にHTML コードをコピーして貼り付けます。 これにより、無料のモジュラーHTML コンポーネントを作成して、一部の外部コンテンツを再利用できます。 詳しくは、{ コンテンツコンポーネント [&#x200B; の &#x200B;](./content-components.md#html)0}HTML _を参照してください。_
* **[!UICONTROL 画像]** – このコンポーネントを使用して、ページに画像ファイルを挿入します。 幅や高さなどのスタイル属性は、右側のパネルのプロパティから調整できます。 詳しくは、[&#x200B; コンテンツコンポーネント &#x200B;](./content-components.md#image) の _画像_ を参照してください。
* **[!UICONTROL 見出し]** – このコンポーネントを使用して、見出しクラステキストを挿入します。 テキストの色、スタイル、フォント、サイズなどのスタイル属性は、右側のパネルのプロパティから調整できます。 詳しくは、[&#x200B; コンテンツコンポーネント &#x200B;](./content-components.md#text) の _テキスト_ を参照してください。
* **[!UICONTROL 段落]** – このコンポーネントを使用して、標準テキスト要素を挿入します。 テキストの色、スタイル、フォント、サイズなどのスタイル属性は、右側のパネルのプロパティから調整できます。 詳しくは、[&#x200B; コンテンツコンポーネント &#x200B;](./content-components.md#text) の _テキスト_ を参照してください。
* **[!UICONTROL リンク]** – このコンポーネントを使用すると、指定した URL への独立したテキストリンクを挿入できます。 テキストの色、スタイル、配置、サイズなどのスタイル属性は、右側のパネルのプロパティから調整できます。

左側のコンポーネントタイプを選択し、追加先に隣接する要素の上にマウスポインターを置きます。

![&#x200B; ビジュアルエディターインターフェイス – 新しいコンポーネント &#x200B;](./assets/web-experience-design-visual-editor-insert-component.png){width="800" zoomable="yes"}

表示されたボタンの 1 つをクリックして、コンポーネントを配置します。

* ***[!UICONTROL 前に挿入]** – 選択した要素の前にコンポーネントを挿入します。
* ***[!UICONTROL 後ろに挿入]** – 選択した要素の後ろにコンポーネントを挿入します。

挿入するコンポーネントタイプの選択を解除するには、ページ上部に表示される青いコンテキストバナーの **[!UICONTROL ESC]** をクリックします。

## 非視覚的エディター {#non-visual-editor}

ビジュアルエディターでは簡単には実現できない変更を加える必要がある場合は、非ビジュアルエディターを使用します。 このコードベースのアプローチにより、要素のターゲティングと変更を正確に制御できます。 非視覚的なエディターを使用して web エクスペリエンスをデザインするには、次の手順を実行します。

1. Web エクスペリエンスの詳細ページに表示される _[!UICONTROL コンテンツ]_ タブを使用して、右側のパネルの **[!UICONTROL 変更を追加]** をクリックします。

   非視覚的なエディターは、web チャネル設定に基づいてページを読み込みます。

   ![&#x200B; 非視覚的エディターインターフェイス &#x200B;](./assets/web-experience-design-non-visual-editor.png){width="800" zoomable="yes"}

1. 最初に行う変更を定義します。

   左側のパネルには、既存の変更のリストが表示されます（存在する場合）。 **[!UICONTROL 追加]** をクリックして、新しい変更を定義します。 変更が定義されていない場合、パネルのデフォルトは _[!UICONTROL 変更を追加]_ オプションになります。

   * **[!UICONTROL 変更タイプ]** を選択します。

     | タイプ | 説明 |
     | ---- | ----------- |
     | [**[!UICONTROL CSS セレクター &#x200B;]**](#css-selector-modifications) | CSS セレクター文字列を使用して要素をターゲットに設定します。 |
     | [**[!UICONTROL &#x200B; ページ &#x200B;]**](#page-modifications) | カスタム HTML、CSS、JavaScriptを、`<head>` や `<body>` などのページレベルの要素に挿入する。 |

   * タイプに応じて変更パラメーターを設定します。

      * **[!UICONTROL CSS セレクター]** – 特定の要素をターゲットにする有効な CSS セレクターを入力します。
      * **[!UICONTROL アクションタイプ]** – 実行するアクション（編集、非表示、削除、挿入、置換）を選択します。
      * **[!UICONTROL コンテンツ]** – 適用するコンテンツまたはスタイルを指定します。

1. **[!UICONTROL 保存]** をクリックして、変更を適用します。

### CSS セレクターの変更

CSS セレクターの変更により、標準の CSS セレクター構文を使用して、要素を正確にターゲットにすることができます。

1. 変更のタイプとして **[!UICONTROL CSS セレクター]** を選択します。

1. 「**[!UICONTROL CSS 要素セレクター]**」フィールドにセレクターを入力します。

<!-- This field helps you find and select the HTML elements (or nodes in the DOM tree). -->

    **例セレクター：**
    
    | セレクター | ターゲット |
    | -------- | ------- |
    | &#39;#hero-banner&#39; | ID が「hero-banner」の要素 |
    | &#39;.cta-button&#39; | &#39;cta-button&#39; クラスを持つすべての要素 |
    | &#39;ヘッダーナビゲーション a&#39; | ナビゲーション内のリンク、ヘッダー内 |
    | &#39;[data-offer=&quot;premium&quot;]&#39; |特定のデータ属性を持つ要素 |

1. **[!UICONTROL アクションタイプ]** を選択し、必要な情報/コンテンツを指定します。

   * **[!UICONTROL コンテンツを設定]** - **[!UICONTROL CSS 要素セレクター]** 値によって識別される要素の「_[!UICONTROL コンテンツ]_」フィールドにテキストを入力します。

   * **[!UICONTROL 属性を設定]** – 現在の CSS セレクターに関連付ける属性を指定し、この属性によって要素を識別できるようにします。 **[!UICONTROL 属性名]** フィールドに名前を入力し、**[!UICONTROL コンテンツ]** フィールドに値を入力します。 属性が既に存在する場合は、値が更新されます。存在しない場合は、指定された名前と値で新しい属性が追加されます。

   ![&#x200B; 非ビジュアルエディターの css セレクターの変更 &#x200B;](./assets/web-experience-design-non-visual-editor-modification-css-selector.png){width="800" zoomable="yes"}

1. （任意）「**[!UICONTROL パーソナライゼーションを追加]**」をクリックし、[&#x200B; パーソナライゼーションエディター &#x200B;](./personalization.md#personalization-editor) を使用して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成します。

### ページの変更

ページコンテン `<head>` 変更タイプを使用して、カスタムコードを追加できます。 `<head>` 要素は、メタデータ（データに関するデータ）のコンテナで、`<html>` タグと `<body>` タグの間に配置されます。この場合、コードは本文やページの読み込みイベントを待たずに、ページの読み込みの開始時に実行されます。

`<head>` 要素は、通常、ページの上部に JavaScript または CSS コードを追加するために使用されます。後続のビジュアルアクションのセレクターは、このタブに追加される HTML 要素に応じて異なります。

>[!NOTE]
>
>カスタムコードは訪問者のブラウザーで実行されます。 コードが安全かつテスト済みで、ページのパフォーマンスやユーザーエクスペリエンスに悪影響を与えないことを確認します。

1. 変更のタイプとして「**[!UICONTROL ページ`<head>`]**」を選択します。

1. **[!UICONTROL コンテンツ]**&#x200B;ボックスでカスタムコードを追加します。

   >[!CAUTION]
   >
   >`<head>` セクションに `<script>` 要素および `<style>` 要素のみを追加できます。`<div>` タグやその他の要素を追加すると、残りの `<head>` 要素が `<body>` 内に入力される可能性があります。

   ![&#x200B; ビジュアルエディター以外のページヘッドの変更 &#x200B;](./assets/web-experience-design-non-visual-editor-modification-page-head.png){width="800" zoomable="yes"}

1. （任意）「**[!UICONTROL パーソナライゼーションを追加]**」をクリックし、[&#x200B; パーソナライゼーションエディター &#x200B;](./personalization.md#personalization-editor) を使用して、コンテンツ用にカスタマイズされたパーソナライゼーションを作成します。

## 変更の管理 {#manage-modifications}

>[!CONTEXTUALHELP]
>id="ajo-b2b_web_experience_modifications"
>title="すべての変更を簡単に管理"
>abstract="このパネルを使用すると、web ページに定義されたすべての調整と追加を移動して管理できます。"

作成したすべての変更は追跡され、ビジュアルエディターと非ビジュアルエディターの両方の **[!UICONTROL 変更]** パネルから管理できます。 左側のツールバーの _[!UICONTROL 変更]_<!-- ( ![Modifications icon](../assets/do-not-localize/icon-web-exp-modifications.svg) ) --> アイコンをクリックして、すべての変更を表示します。

各変更レコードには、以下が含まれます。

* ターゲット要素またはセレクター
* 変更の種類（編集、非表示、挿入など）
* 変更のプレビュー

![&#x200B; 変更パネル &#x200B;](./assets/web-experience-design-modifications-list.png){width="500" zoomable="yes"}

### 変更の編集

1. _[!UICONTROL 変更]_ リストで、編集する変更を見つけます。

1. _詳細メニュー_ （**...**）アイコンをクリックし、「**[!UICONTROL 編集]**」を選択します。

1. 必要に応じて、変更プロパティを更新します。

1. 「**[!UICONTROL 保存]**」をクリックして変更を保存します。

### 変更の削除

1. _[!UICONTROL 変更]_ リストで、削除する変更を見つけます。

1. _詳細メニュー_ （**...**）アイコンをクリックし、「**[!UICONTROL 変更を削除]**」を選択します。

1. プロンプトが表示されたら、削除を確認します。

<!-- ### Reorder modifications

Modifications are applied in the order that they appear in the list. If you have multiple modifications that affect the same element, the order may impact the final result.

Drag and drop modifications in the list to change the order. The preview updates to reflect the new modification order. -->

## 変更をプレビュー

公開する前に、訪問者に対する変更の表示をプレビューします。

ビジュアルエディターの上部にあるデバイスプレビューオプションを使用して、次の場所で変更を表示します。

* Desktop
* タブレット
* モバイル

![&#x200B; プレビュー用のデバイスのサイズの変更 &#x200B;](./assets/web-experience-design-device-view.png){width="550" zoomable="yes"}

プレビューが更新され、各デバイスサイズで変更がどのようにレンダリングされるかが表示されます。

URL バーを使用して、web チャネル設定内の別のページに移動します。 次に、URL マッチングルールに基づいて、変更がターゲットページに正しく適用されることを確認します。

## Web エクスペリエンスのクリックトラッキング {#web-click-tracking}

要素とのユーザーインタラクションを追跡して、エンゲージメントを測定し、インサイトを収集します。 クリック追跡データは、エンゲージメントレポートで使用でき、web エクスペリエンスの変更の有効性を測定するために使用できます。

Web エクスペリエンスがアクティベートされた（ライブ）場合、Adobe Customer Journey Analyticsを使用してレポートを作成することもできます（これには商品のサブスクリプションが必要です）。 Web エクスペリエンスの監視を向上させるために、web サイトの特定の要素に対するクリック数を追跡することもできます。 トラッキングを使用すると、web レポートにその要素のクリック数を表示できます。

Customer Journey Analyticsと web レポートの作成について詳しくは、[Customer Journey Analytics ドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-landing) を参照してください。

1. Web エクスペリエンスエディターで、画像やリンクなどの要素を選択します。

1. 要素プロパティまたはコンテキストツールバーで、「_[!UICONTROL クリック追跡要素]_」アイコンをクリックします。

   ![Web エクスペリエンス要素のクリックの追跡を有効にする &#x200B;](./assets/web-experience-design-visual-editor-click-tracking-icons.png){width="600" zoomable="yes"}

1. 左側のパネルでクリック追跡リストを開き、**[!UICONTROL 追跡されたアクション]** 値を変更して、レポートでこのインタラクションを識別します。

   ![Web エクスペリエンスのクリック追跡 ID の設定 &#x200B;](./assets/web-experience-design-visual-editor-click-tracking-identifier.png){width="600" zoomable="yes"}
