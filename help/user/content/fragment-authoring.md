---
title: フラグメントのオーサリング
description: 効率を高め、デザインとブランディングの標準を維持するために、メールやテンプレートデザインで再利用できるコンテンツフラグメントを作成する方法を説明します。
feature: Content
source-git-commit: 1f551b636ef347fd65aa39a809dedba8372c3ac4
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 14%

---

# フラグメントのオーサリング

[ フラグメントを作成 ](./fragments.md#create-fragments) した後、ビジュアルエディターを使用して、フラグメントの構造コンポーネントとコンテンツコンポーネントをオーサリングします。

## 構造とコンテンツの追加 {#design-fragment}

>[!CONTEXTUALHELP]
>id="ajo-b2b_structure_components_fragment"
>title="構造コンポーネントの追加"
>abstract="構造コンポーネントはフラグメントのレイアウトを定義します。 **構造**&#x200B;コンポーネントをキャンバスにドラッグ＆ドロップして、フラグメントのコンテンツのデザインを開始します。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_content_components_fragment"
>title="コンテンツコンポーネントについて"
>abstract="コンテンツコンポーネントは、フラグメントのレイアウトの作成に使用できる空のコンテンツプレースホルダーです。"

{{$include /help/_includes/content-design-components.md}}

## アセットの追加

{{$include /help/_includes/content-design-assets.md}}

## レイヤー、設定、スタイルの移動

{{$include /help/_includes/content-design-navigation.md}}

## コンテンツのパーソナライズ

{{$include /help/_includes/content-design-personalization.md}}

## カスタムフィールドの有効化

メールまたはメールテンプレートの作成者がフラグメントを追加すると、デフォルトでフラグメントコンテンツがロックされます。 公開されたフラグメントに対する変更は、そのフラグメントが使用されているすべてのコンテンツアセットに自動的に反映されます。 フラグメント内のコンポーネントのパラメーターを編集可能として指定する場合、メールまたはテンプレートの作成者は、必要に応じてカスタムフィールドの値を指定できます。 このカスタマイズフラグは、画像、テキスト、ボタンのビジュアルコンポーネントに限定されます。

例えば、クリック可能なボタンを含む再利用可能なバナーをデザインする場合、ボタンの URL パラメーターを編集可能として指定できます。 その後、メール作成者は、メールキャンペーンに特化した URL を使用できます。 これらのカスタマイズ可能なフィールドを使用すると、マーケターは、まったく新しいコンテンツブロックを作成したり、元のフラグメントから継承された更新を中断したりすることなく、コンテンツを管理およびパーソナライズできます。

1. ビジュアルコンテンツエディターで、カスタマイズを有効にする画像、テキスト、またはボタン要素を選択します。

1. 右側のコンポーネント詳細で、「**[!UICONTROL 編集可能フィールド]** タブを選択します。

1. **[!UICONTROL 編集を有効にする]** オプションの切り替えをクリックして、編集可能フィールドを設定します。

   ![ フラグメント画像コンポーネントに対して編集可能フィールドを有効にする ](./assets/fragment-editable-fields-image.png){width="700" zoomable="yes"}

   コンポーネントタイプとフラグメントで定義されたパラメーターに応じて、表示されるフィールドのカスタマイズを有効にすることができます。

   カスタマイズを許可する各フィールドの切替スイッチを有効な状態に変更します。

1. **[!UICONTROL 概要]** をクリックして、編集可能なすべてのフィールドとそのデフォルト値を確認します。

   ![ 編集可能フィールドとそのデフォルト値を確認する ](./assets/fragment-editable-fields-image-overview.png){width="700" zoomable="yes"}

1. 変更を保存します。

## リンクされた URL トラッキングを編集

{{$include /help/_includes/content-design-links.md}}
