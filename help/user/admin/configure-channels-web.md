---
title: Web チャネル設定
description: Journey Optimizer B2B editionで web チャネルを設定して、コンテンツ配信用の web プロパティとページマッチングルールを定義する方法について説明します。
feature: Setup, Channels
role: Admin
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
source-git-commit: 2f9b007df233cf8a233c3646bf691b7cff139f86
workflow-type: tm+mt
source-wordcount: '1064'
ht-degree: 3%

---

# Web チャネル設定

Web 設定は、コンテンツが配信される URL で識別される web プロパティです。 単一ページの URL または複数のページを一致させることができるので、web エクスペリエンスは、1 つまたは複数の web ページをまたいで変更を配信できます。 これらの設定は、マーケターがジャーニーで [web パーソナライゼーションアクションノードを追加 &#x200B;](../content/web-experiences.md#create-a-web-experience) キャンペーンの [&#x200B; エクスペリエンスの変更をデザイン &#x200B;](../content/web-experience-design.md) するために必要です。

>[!BEGINSHADEBOX]

**前提条件**

Web チャネルを使用するには、web サイトで訪問者の識別とコンテンツ配信のために [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/js-overview) （`alloy.js`）が実装されている必要があります。 Adobe Experience Platform Web SDKのバージョンが 2.16 以上であることを確認してください。

Journey Optimizer B2B editionの web チャネル設定には、次の権限が必要です [&#x200B; 権限 &#x200B;](../admin/user-management.md#b2b-product-permissions)。

* _[!UICONTROL チャネル設定]_/_[!UICONTROL メッセージプリセットの管理]_ - web チャネル設定の作成、更新、削除に必要です。
* _[!UICONTROL チャネル設定]_/_[!UICONTROL メッセージプリセットの表示]_ - web チャネル設定の表示に必要です。

>[!ENDSHADEBOX]

## Web チャネル設定の作成

1. 左側のナビゲーションで、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。

1. ナビゲーションパネルの _[!UICONTROL Web]_ の下にある **[!UICONTROL チャネル設定]** を選択します。

   ![Web チャネル設定へのアクセス &#x200B;](./assets/config-web-channels.png){width="800" zoomable="yes"}

1. 右上の **[!UICONTROL チャネル設定を作成]** をクリックします。

1. 設定の **[!UICONTROL 名前]** （必須）と **[!UICONTROL 説明]** （オプション）を入力します。

   >[!NOTE]
   >
   >名前は、文字（A ～ Z）で始まる必要があり、英数字のみを含めることができます。 アンダースコア `_`、ドット `.`、ハイフン `-` 文字も使用できます。

1. 「**[!UICONTROL Web 設定]**」セクションで、次のいずれかのオプションを選択します。

   * **[!UICONTROL 単一ページ]** – 変更を単一ページのみに適用する場合は、「**[!UICONTROL ページ URL]**」を入力または選択します。

     ![&#x200B; 単一ページ web チャネル設定のページ URL の選択 &#x200B;](./assets/config-web-channel-create-single-page.png){width="600" zoomable="yes"}

   * **[!UICONTROL ルールに一致するページ]** – 同じルールに一致する複数の URL をターゲットにするには、[&#x200B; ルールに一致するページ &#x200B;](#build-a-pages-matching-rule) を作成し、**[!UICONTROL デフォルトのオーサリングおよびプレビュー URL]** を入力します。

1. 「**[!UICONTROL 送信]**」をクリックして変更を保存します。

設定を保存すると、その設定は _ドラフト_ ステータスになり、マーケターがジャーニーで web チャネルを使用する際に使用できるようになります。 ドラフト状態である限り、設定の編集は続行できます。 名前の横にある _その他_ アイコン（**...**）をクリックし、「**[!UICONTROL 削除]**」を選択して、ドラフト web チャネル設定を削除することもできます。

Web チャネルは、ジャーニーで使用されるとすぐに _アクティブ_ ステータスになります。 この状態で、設定の名前と説明を編集できます。 Web 設定の変更や設定の削除はできません。

## ルールに一致するページ {#pages-matching-rule}

Web 設定を作成する際に、_[!UICONTROL ルールに一致するページ]_ を作成して、同じルールに一致する複数の URL をターゲットにすることができます。 これらのルールを使用すると、複数のページに同じコンテンツの変更を適用できます。

例えば、web サイト全体のヒーローバナーに変更を適用したり、すべての製品ページに表示されるトップ画像を追加したりできます。

### ルールの作成

1. [web チャネル設定を作成 &#x200B;](#create-a-web-channel-configuration) する場合は、「ページ一致ルール **[!UICONTROL を選択]** します。

1. 各セクションの異なる演算子を使用してルールを作成し、**[!UICONTROL ドメイン]** フィールドと **[!UICONTROL ページ]** フィールドの条件を定義します。

   +++ドメインオペレーター

   入力する文字列値に従ってドメインを照合するには、次の演算子を使用します。

   | 演算子 | 説明 | 例 |
   | --- | --- | --- |
   | [!UICONTROL &#x200B; 次に等しい &#x200B;] | ドメインの完全一致。 | |
   | [!UICONTROL &#x200B; 次で始まる &#x200B;] | 入力した文字列で始まるすべてのドメイン（サブドメインを含む）に一致します。 | `Starts with: dev` は、`dev`、`dev.example.com`、`dev.products.example.com` など、`developer.example.com` で始まるすべてのドメインとサブドメインに一致します |
   | [!UICONTROL Ends with （次の値で終わる） &#x200B;] | 入力された文字列で終わるすべてのドメイン（サブドメインを含む）に一致します。 | `Ends with: example.com` は、`example.com` で終わるすべてのドメインおよびサブドメイン（`stage.example.com`、`prod.example.com`、`myexample.com` など）に一致します |
   | [!UICONTROL &#x200B; ワイルドカード一致 &#x200B;] | 文字列の中央にワイルドカード一致を定義できます（例：`dev.*.example.com`）。 検証ルールでは、演算子が「ワイルドカード一致 _の場合、値に 1 つのワイルドカード（アスタリスク）が含まれている必要があり_ す。 | `Wildcard matching: dev.*.example.com` は `dev.products.example.com`、`dev.mytest.products.example.com`、`dev.blog.example.com` などのドメインと一致します |
   | [!UICONTROL &#x200B; すべて &#x200B;] | すべてのドメインに一致します。 これは、ドメインをまたいで特定のパスをテストする場合に役立ちます。 | |

   +++

   +++パス演算子

   入力する文字列値に従ってパスを照合するには、次の演算子を使用します。

   | 演算子 | 説明 | 例 |
   | --- | --- | --- |
   | [!UICONTROL &#x200B; 次に等しい &#x200B;] | パスの完全一致。 | |
   | [!UICONTROL &#x200B; 次で始まる &#x200B;] | 文字列で始まるすべてのパス（サブパスを含む）に一致します。 | |
   | [!UICONTROL Ends with （次の値で終わる） &#x200B;] | 文字列で終わるすべてのパス（サブパスを含む）に一致します。 | |
   | [!UICONTROL &#x200B; すべて &#x200B;] | すべてのパスに一致します。 これは、1 つまたは複数のドメインの下のすべてのパスをターゲットにする場合に便利です。 | |
   | [!UICONTROL &#x200B; ワイルドカード一致 &#x200B;] | パス内に内部ワイルドカード（`/products/*/detail` など）を定義できます。 パスコンポーネントのワイルドカード文字 `*` は、最初の `/` 文字まで任意の文字列に一致します。  および `/*/` 文字の任意のシーケンス（サブパスを含む）に一致します。 | `Wildcard matching: /products/*/detail` は、`example.com/products/yoga/detail`、`example.com/products/surf/detail`、`example.com/products/tennis/detail`、`example.com/products/yoga/pants/detail` などのパスと一致します |
   | [!UICONTROL Contains] | 値はワイルドカード（`*mystring*` など）に変換され、文字のシーケンスを含むすべてのパスに一致します。 | `Contains: product` は、文字列 `product` を含むすべてのパス（`example.com/products`、`example.com/yoga/perfproduct`、`example.com/surf/productdescription`、`example.com/home/product/page` など）に一致します |

   +++

   例えば、_Bodea_ Web サイトのすべての _LumaSecure_ ソリューションページでのコンテンツ変更をサポートするには、**[!UICONTROL ドメイン]**/**[!UICONTROL 次で始まる]**/`bodea` および **[!UICONTROL ページ]**/**[!UICONTROL 次を含む]**/`lumasecure` を選択します。

   ![Web チャネル設定に対するページ一致ルールの定義 &#x200B;](./assets/config-web-channel-pages-matching-rules.png){width="600" zoomable="yes"}

1. ユースケースに複数のルールが必要な場合は、「**[!UICONTROL 別のページルールを追加]**」をクリックし、前の手順を繰り返します。

   * 最大 10 のルールを定義できます。

   * 異なるルール間で **[!UICONTROL Or]** 演算子または **[!UICONTROL Exclude]** 演算子を使用します。

     _[!UICONTROL Or]_ は、複数のルールを定義するためのデフォルトの演算子で、一致させることができる複数の条件定義を追加する場合に役立ちます。

     _[!UICONTROL 除外]_ は、定義されたルールに一致するページの 1 つをターゲットにしない場合に便利です。 例えば、`bodea.com` を含み、ブログページ（`lumasecure` など）を除くすべての `bodea.com/blogs/lumasecure/latest-release` ページをターゲットにすることができます。

   ![&#x200B; ルールに一致するページと除外 &#x200B;](./assets/config-web-channel-pages-matching-rules-exclude.png){width="600" zoomable="yes"}

1. **[!UICONTROL デフォルトのオーサリングおよびプレビュー URL]** を入力します。

   この手順により、ルールで生成または照合されるページに、web エクスペリエンスのコンテンツデザインとプレビューの両方に使用する URL が指定されるようにします。

## Web チャネルの複製

既存の web チャネル設定を複製し、それを変更して、既存の設定に基づいて新しい web チャネルを作成できます。 ライブラリに保存されているアクティブな web チャネル設定は変更できません。

1. バリアントの _その他メニュー_ アイコン（**...**）をクリックし、「複製 **[!UICONTROL を選択し]** す。

   ![&#x200B; その他の nenu アイコンをクリックして、既存の web チャネル設定を複製 &#x200B;](./assets/config-web-channels-more-menu.png){width="450"}

   このアクションは、名前に `_Copy_nnn` が追加された複製された web チャネルを作成します。

1. 複製した web チャネルの名前をクリックして、パラメーターを編集します。

   * ルール内の目的または項目に一致するように、名前と説明を変更します。
   * 必要に応じて、単一ページの URL を変更します。
   * 必要に応じて、ルールに一致するページを要件に応じて変更します。

1. 設定が完了したら、「**[!UICONTROL 送信]**」をクリックします。
