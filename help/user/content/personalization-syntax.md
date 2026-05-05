---
title: パーソナライゼーション構文
description: 式、ヘルパー、リテラルタイプ、フォーマットルールなど、Journey Optimizer B2B editionのHandlebars ベースのパーソナライゼーション構文について説明します。
feature: Personalization, Content Design Tools
topic: Personalization
role: Developer
level: Intermediate
keywords: 式, エディター, 構文, パーソナライゼーション
exl-id: 91bbead6-aca0-4f39-9ab5-798b26ab81ee
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: e7bdffdc-2950-4be5-8c23-84240a995090id: bd3c685c-6c92-4a4a-becb-535cc25215de
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
autotag-review: '2026-03-30T22:05:22.123Z'
source-git-commit: ee080e04cdc38327ef2367c0f55eee2ae606de51
workflow-type: tm+mt
source-wordcount: 361
ht-degree: 49%

---

# パーソナライゼーション構文 {#personalization-syntax}

[!DNL Journey Optimizer B2B Edition] [ パーソナライゼーションエディター](./personalization.md#personalization-editor)の式は、_ハンドルバー_&#x200B;のテンプレート構文に基づいています。 テンプレートと入力オブジェクトを使用して、HTML やその他のテキスト形式を生成します。 Handlebars テンプレートは、Handlebars 式が埋め込まれた標準のテキストのように見えます。

Handlebarsとその仕組みについて詳しくは、[HandlebarsJS ドキュメント ](https://handlebarsjs.com/){target="_blank"}を参照してください。

## 一般ルール

単純な式の例：

```
{{account.accountName}}
```

ここで：

* `account` は名前空間です。
* `accountName` は、属性で構成されるトークンです。

  >[!NOTE]
  >
  >属性構造は、[Adobe Experience Platform XDM スキーマ ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home){target="_blank"}で定義されています。

* 識別子は、次の場合を除き、任意のUnicode文字にすることができます。

  ```
  Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
  ```

* 構文では大文字と小文字が区別されます。

* **true**、**false**、**null** および **undefined**&#x200B;という語は、パス式の最初の部分でのみ使用できます。

* Handlebarsでは、{\{expression}\}によって返される値は&#x200B;_HTMLエスケープ_&#x200B;です。 式に`&`が含まれている場合、返されたHTML エスケープ出力は`&amp;`として生成されます。 Handlebarsに値をエスケープさせたくない場合は、+triple-stash_を使用します。

<!--
 For example:

    If the value of the field `profile.person.name` is _Mark & Mary_, the `{\{profile.person.name}\}` value generates as `Mark &amp; Mary` and `{\{\{profile.person.name}}}` renders as `Mark & Mary`. 
-->

* リテラル関数の引数の場合、テンプレート言語パーサーは単一のエスケープされていないバックスラッシュ （`\`）記号をサポートしません。 この文字は、バックスラッシュ（`\`）記号を追加してエスケープする必要があります。 例：

  ```
  {%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}
  ```

## ヘルパー {#helpers-all}

Handlebars ヘルパー関数は、パラメーターを追加できる簡単な識別子です。 各パラメーターは、Handlebars 式です。 これらのヘルパーには、メールテンプレート内の任意のコンテキストからアクセスできます。

```sql
{{#each account.accountOrganization.annualRevenue.amount}}
    <li>{{this.name}}</li>
{{/each }}
```

<!--
 These block helpers are identified with a `#` preceding the helper name and require a matching closing `/`, of the same name.

Blocks are expressions that have a block opening ( {\{# }\} ) and closing ( {\{/} } ). 
-->

これらの関数について詳しくは、[ ヘルパー関数](./personalization-helper-functions.md)を参照してください。

## リテラル型 {#literal-types}

[!DNL Adobe Journey Optimizer B2B Edition] では、次のリテラル型をサポートしています。

| リテラル | 定義 |
| ------- | ---------- |
| 文字列 | 文字で構成され、ダブルコーテーションで囲まれたデータタイプです。 <br>例：`"prospect"`、`"jobs"`、`"articles"` |
| ブール値 | true か false のいずれかであるデータタイプです。 |
| 整数 | 整数を表すデータタイプです。 正、負、ゼロのいずれかです。 <br>例：`-201`、`0`、`412` |
| 配列 | 他のリテラル値のグループとして構成されるデータタイプです。 複数の値を区切る場合は、角括弧で囲んでグループ化し、カンマで区切ります。<br> **メモ：**&#x200B;配列内の項目のプロパティに直接アクセスすることはできません。<br> 例：`[1, 4, 7]`、`["US", "FR"]` |

>[!CAUTION]
>
>**xEvent** 変数は、パーソナライズ式では使用できません。 xEventを参照すると、検証エラーが発生します。
