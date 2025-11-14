---
title: パーソナライゼーション構文
description: 式、ヘルパー、リテラル型、書式設定ルールなど、Journey Optimizer B2B editionで Handlebars ベースのパーソナライゼーション構文について説明します。
feature: Personalization, Content Design Tools
topic: Personalization
role: Developer
level: Intermediate
keywords: 式, エディター, 構文, パーソナライゼーション
source-git-commit: fee5bddcce11b3035da6ab93b18bcc7006b4b554
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 44%

---

# パーソナライゼーション構文 {#personalization-syntax}

[!DNL Journey Optimizer B2B Edition] [&#x200B; パーソナライゼーションエディター &#x200B;](./personalization.md#personalization-editor) の式は、_Handlebars_ テンプレート構文に基づいています。 テンプレートと入力オブジェクトを使用して、HTML やその他のテキスト形式を生成します。Handlebars テンプレートは、Handlebars 式が埋め込まれた標準のテキストのように見えます。

Handlebars とその仕組みについて詳しくは、[HandlebarsJS ドキュメント &#x200B;](https://handlebarsjs.com/){target="_blank"} を参照してください。

## 一般規則

簡単な式の例：

```
{{account.accountName}}
```

次のとおりです。

* `account` は名前空間です。
* `accountName` は、属性で構成されるトークンです。

  >[!NOTE]
  >
  >属性構造は、[Adobe Experience Platform XDM スキーマ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/home){target="_blank"} で定義されます。

* 識別子には、以下を除く任意の Unicode 文字を使用できます。

  ```
  Whitespace ! " # % & ' ( ) * + , . / ; < = > @ [ \ ] ^ ` { | } ~
  ```

* 構文では大文字と小文字が区別されます。

* **true**、**false**、**null** および **undefined**&#x200B;という語は、パス式の最初の部分でのみ使用できます。

* Handlebars では、{\{expression}\} から返される値は _HTML エスケープ_ されています。 式に `&` が含まれている場合、返されるHTML エスケープ出力は `&amp;` として生成されます。 Handlebars の値をエスケープしない場合は、+triple-stash_を使用します。

<!-- For example:

    If the value of the field `profile.person.name` is _Mark & Mary_, the `{\{profile.person.name}\}` value generates as `Mark &amp; Mary` and `{\{\{profile.person.name}}}` renders as `Mark & Mary`. -->

* リテラル関数の引数の場合、テンプレート言語パーサーはエスケープされない単一のバックスラッシュ（`\`）記号をサポートしていません。 この文字は、バックスラッシュ（`\`）記号を追加してエスケープする必要があります。 例：

  ```
  {%= regexGroup("abc@xyz.com","@(\\w+)", 1)%}
  ```

## ヘルパー {#helpers-all}

Handlebars ヘルパー関数は、パラメーターを追加できる単純な識別子です。 各パラメーターは、Handlebars 式です。これらのヘルパーは、メールテンプレートの任意のコンテキストからアクセスできます。

```sql
{{#each account.accountOrganization.annualRevenue.amount}}
    <li>{{this.name}}</li>
{{/each }}
```

<!-- These block helpers are identified with a `#` preceding the helper name and require a matching closing `/`, of the same name. 

Blocks are expressions that have a block opening ( {\{# }\} ) and closing ( {\{/} } ). -->

これらの関数について詳しくは、「[&#x200B; ヘルパー関数 &#x200B;](./personalization-helper-functions.md)」を参照してください。

## リテラル型 {#literal-types}

[!DNL Adobe Journey Optimizer B2B Edition] では、次のリテラル型をサポートしています。

| リテラル | 定義 |
| ------- | ---------- |
| 文字列 | 文字で構成され、ダブルコーテーションで囲まれたデータタイプです。<br>例：`"prospect"`、`"jobs"`、`"articles"` |
| ブール値 | true か false のいずれかであるデータタイプです。 |
| 整数 | 整数を表すデータタイプです。正、負、ゼロのいずれかです。<br>例：`-201`、`0`、`412` |
| 配列 | 他のリテラル値のグループとして構成されるデータ型です。複数の値を区切る場合は、角括弧で囲んでグループ化し、カンマで区切ります。<br> **注意：** 配列内の項目のプロパティに直接アクセスすることはできません。 <br> 例：`[1, 4, 7]`、`["US", "FR"]` |

>[!CAUTION]
>
>**xEvent** 変数は、パーソナライズ式では使用できません。xEvent を参照すると、検証エラーが発生します。
