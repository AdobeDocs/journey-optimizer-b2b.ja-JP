---
title: スニペット
description: 特定のエディションに適用される機能またはページをメモするための再利用されたメモと視覚的要素
source-git-commit: 561a6fe3a99e93e93e176f63572b260e621a4298
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---

# スニペット

<!-- Content authoring steps for reuse -->

## インテントデータの設定 {#intent-data-note}

>[!NOTE]
>
>Journey Optimizer B2B edition インスタンス用に設定されたインテントデータは、ページに含まれます。 インテント検出モデルの詳細と、キーワード、製品、カテゴリの送信方法については、[ インテント データ ](../user/admin/intent-data.md) を参照してください。

## AEM assets ライセンスノート {#aem-assets-licensing-note}

>[!NOTE]
>
>AEM Assets as a Cloud Serviceのライセンスと Dynamic Media のライセンスは統合の前提条件です。 [Dynamic Media withOpen API](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/dynamicmedia/dynamic-media-open-apis/dynamic-media-open-apis-overview){target="_blank"} が有効になっていることを確認する必要があります。<br/>
>契約と設定に応じて、ビジュアルコンテンツのデザイン時にAdobe Experience Manager Assets as a Cloud ServiceにAdobe Journey Optimizer B2B editionから直接アクセスできます。

## コンテンツオーサリング – コンポーネント – 構造ステップ {#structures-step}

1. コンテンツデザインを開始するには、**[!UICONTROL 構造]** から項目をドラッグし、キャンバスにドロップします。

   必要に応じて _[!UICONTROL 構造]_ から項目を追加し、右側のパネルで各項目の設定を編集します。

   >[!TIP]
   >
   >_[!UICONTROL n:n 列]_ コンポーネントを選択して、列数（3～10）を任意に定義します。 また、列の下に矢印を移動して、各列の幅を定義することもできます。

   ![ 構造をキャンバスにドラッグして、設定を調整します ](../assets/content-design-shared/content-design-add-structure.png){width="800" zoomable="yes"}

   各列のサイズを構造コンポーネントの全幅の 10% 未満にすることはできません。 削除できるのは空の列のみです。

## コンテンツオーサリング – コンポーネント – コンテンツステップ {#contents-step}

1. 「**[!UICONTROL コンテンツ]**」セクションを展開し、必要な数の要素を 1 つ以上の構造コンポーネントに追加します。

   ![ コンテンツ要素をキャンバスにドラッグして、設定を調整します ](../assets/content-design-shared/content-design-add-content.png){width="800" zoomable="yes"}
   <!--
   reference to the contents elements--->

## コンテンツのオーサリング – コンポーネント – 設定手順 {#settings-step}

1. 必要に応じて、「設定」タブまたは _[!UICONTROL スタイル]_ タブで各コンポーネントに追加のカスタマイズを加えるこ _[!UICONTROL ができ]_ す。

   例えば、各コンポーネントのテキストスタイル、パディングまたは余白を変更できます。

## コンテンツオーサリング – アセットステップ {#assets-step}

1. _アセット_ ピッカーから、アセットライブラリに保存されたアセットを直接選択できます。

   アセットを含むフォルダーをダブルクリックします。 項目を構造コンポーネントにドラッグ&amp;ドロップします。

   ソースタイプのアセットの使用について詳しくは、[ コンテンツへのアセットの追加 ](../user/content/assets-overview.md#use-assets-for-content-authoring) を参照してください。

   ![Marketo Engage アセットをキャンバスにドラッグして、設定を調整します ](../assets/content-design-shared/content-design-add-asset.png){width="800" zoomable="yes"}

## コンテンツオーサリング – パーソナライゼーションステップ {#personalization-step}

1. パーソナライゼーションフィールドを挿入して、プロファイル属性、オーディエンスメンバーシップ、コンテキスト属性などからコンテンツをカスタマイズします。

## コンテンツオーサリング – 条件コンテンツステップの有効化 {#dynamic-content-step}

1. 「**[!UICONTROL 条件付きコンテンツを有効にする]**」をクリックし、動的コンテンツを追加して、条件付きルールに基づいてコンテンツをターゲットプロファイルに適応させます。

## コンテンツオーサリング – リンクトラッキング手順 {#links-tracking-step}

1. 左側のペインから「**[!UICONTROL リンク]**」タブを選択し、追跡するコンテンツのすべての URL を表示します。

   _トラッキングタイプ_ または _ラベル_ を変更し、必要に応じてタグを追加できます。
