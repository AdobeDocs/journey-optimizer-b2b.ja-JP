---
title: Script Builder
description: 電子メールデザイン分野でのAI アシスタントであるScript Builderを使用して、Journey Optimizer B2B editionでHandlebars パーソナライゼーションスクリプトを生成し、Marketo Engage Velocity スクリプトを変換します。
feature: AI Assistant, Generative AI, Personalization, Email Authoring
role: User, Developer
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
autotag-review: '2026-07-27T16:18:02.498Z'
TQID: 'https://experienceleague.adobe.com/JWnXAAbCuZVLv4ZhWubpNsZ61xbYU7xtdOXkG9uoWis'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: bd3c685c-6c92-4a4a-becb-535cc25215de
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 0004f8fba0c3d4ae89063418e4d3ef8fea22b0c3
workflow-type: tm+mt
source-wordcount: 1074
ht-degree: 2%

---

# Script Builder

_Script Builder_&#x200B;は、[!DNL Adobe Journey Optimizer B2B Edition]電子メールデザインスペースで利用できるAIを活用したアシスタントです。 マーケターやメール開発者がパーソナライゼーションスクリプトをより迅速に作成でき、既存のパーソナライゼーションロジックを手動で書き換えることなく[!DNL Journey Optimizer B2B Edition]に変換することで、[!DNL Marketo Engage]からの移行に役立ちます。

>[!AVAILABILITY]
>
>Script Builderは現在、**_アカウントジャーニーのみ_**&#x200B;のメールに対する限定的なベータ版リリースとしてお客様を選択できます。 個人ジャーニーのサポートは、今後のリリースで予定されています。 アクセスするには、Adobe担当者にお問い合わせください。

ロケールによる言語ブロックの切り替え、地域またはペルソナによるコンテンツの入れ替え、動的なプロファイルまたはカスタムオブジェクト値の挿入など、条件付きメールのパーソナライゼーションを作成するには、_Handlebars_&#x200B;式のオーサリングが必要です。 [!DNL Marketo Engage]から移行する場合、_Velocity_ スクリプトを行ごとに書き換えるという課題が追加されました。 Script Builderは、単一の会話型インターフェイスから両方の課題に対応します。

* 平易な言語の説明から新しいHandlebars パーソナライゼーションスクリプトを生成します。
* [!DNL Marketo Engage] Velocity スクリプトを貼り付け、自動トークンマッピングを使用して同等のHandlebars スクリプトに変換します。
* ツール間でコピー&amp;ペーストすることなく、出力を直接メールにプレビュー、編集、検証、保存できます。

## ガイドラインと制限事項

>[!IMPORTANT]
>
>Script Builderへのユーザーのアクセスは、[!DNL Journey Optimizer B2B Edition]の他の生成AI機能と同じ権限で制御されます。 機能の権限の付与について詳しくは、[AI アシスタントへのアクセスの有効化](../ai-assistant/enable-ai-assistant-access.md)を参照してください。

Script Builderを使用する前に、[!DNL Journey Optimizer B2B Edition]の生成AI機能に適用される[ ガイドラインと制限事項](../ai-assistant/generative-ai-content.md#general-guidelines-and-limitations)を確認してください。 AI機能を使用する前に、[ ユーザー契約書](https://www.adobe.com/jp/legal/licenses-terms/adobe-gen-ai-user-guidelines.html){target="_blank"}への同意も必要です。

[!DNL Journey Optimizer B2B Edition]でサポートされている[Handlebars テンプレート言語](https://handlebarsjs.com/guide/){target="_blank"}、[ パーソナライゼーション構文](./personalization-syntax.md)、および[ ヘルパー関数](./personalization-helper-functions.md)を理解します。 Script Builderは有効なハンドルバーを生成しますが、構文を理解すると、出力を確実にレビューおよび編集できます。

## スクリプトビルダーを開く {#open-script-builder}

[ パーソナライゼーションエディター](./personalization.md)からScript Builderを利用できます。一方、[はアカウントジャーニーのメールコンテンツ ](./email-authoring.md)を作成します。

1. メールデザイン領域で、パーソナライゼーションスクリプトを追加または置換するコンポーネントを選択します。

1. パーソナライゼーションエディターを開くには、_パーソナライゼーションを追加_ （![ パーソナライゼーションを追加アイコン ](../../assets/do-not-localize/icon-personalization-field.svg)）アイコンをクリックします。

1. エディターで、**[!UICONTROL Script Builder]**&#x200B;を選択します。

   ![Personalization エディター – スクリプトビルダーを選択](./assets/personalization-script-builder-select.png){width="700" zoomable="yes"}

   >[!BEGINSHADEBOX]

   Script Builderに初めてアクセスする場合は、[_[!UICONTROL 生成AI利用条件&#x200B;]_](https://www.adobe.com/jp/legal/licenses-terms/adobe-gen-ai-user-guidelines.html){target="_blank"}を確認し、契約書を確認してください。

   ![Script Builderの生成AI利用条件の契約書ダイアログ ](./assets/personalization-script-builder-gen-ai-terms.png){width="400"}

   >[!ENDSHADEBOX]

   スクリプトビルダーパネルが開き、対話型チャットインターフェイスが表示されます。

   ![Personalization エディター – スクリプトビルダーパネル ](./assets/personalization-script-builder-welcome.png){width="700" zoomable="yes"}

1. 何をしたいかに応じてチャットを開始します。

   * [新しいスクリプトを生成](#generate-personalization-script)
   * [既存のVelocity スクリプトの変換](#convert-marketo-velocity-script)

## パーソナライゼーションスクリプトの生成 {#generate-personalization-script}

Script Builderを使用して、式を自分で記述することなく、平易な言語の説明から新しいHandlebars パーソナライゼーションスクリプトを作成します。

スクリプトビルダーには、[!DNL Marketo Engage]件のリードフィールドとアカウントフィールドを、組織に対して定義された[XDM フィールドマッピング ](../admin/xdm-field-management.md)に基づいて、同等の[!DNL Journey Optimizer B2B Edition]XDM プロファイル属性に解決するマッピングライブラリが含まれています。

1. Script Builder チャットインターフェイスで、必要なパーソナライゼーションロジックを記述します。

   例えば、表示するコンテンツバリアントを決定する属性、カスタムオブジェクト、条件を記述します。

1. プレビューペインで生成されたHandlebars スクリプトを確認します。

1. ロジックや文言を微調整する場合は、プレビューペインでスクリプトを直接編集します。

1. 「**[!UICONTROL 検証]**」をクリックして、[!DNL Journey Optimizer B2B Edition] スキーマに対するスクリプトを確認します。

   検証では、スクリプトを保存する前に構文エラーと未解決のトークン参照が検出されるため、壊れたパーソナライゼーションがライブメールに公開されることはありません。

1. 「**[!UICONTROL 保存]**」をクリックして、スクリプトをメール内の選択した場所に直接挿入します。

## Marketo Engage Velocity スクリプトの変換 {#convert-marketo-velocity-script}

Script Builderを使用して、既存の[!DNL Marketo Engage] Velocity スクリプトを[!DNL Journey Optimizer B2B Edition]の同等のHandlebars スクリプトに移行します。

1. Script Builder チャットで、`Convert this`と入力し、変換するVelocity スクリプトを貼り付けます。

   Script Builderは、Velocityの構成を解析し、トークン参照をXDM プロファイル属性と一致させ、同等のHandlebars スクリプトを生成します。

1. [ コンバージョンレポート ](#review-conversion-report)と[手動マッピングが必要なトークンを解決](#resolve-tokens-without-mapping)します。

1. [生成されたスクリプトをプレビューして検証](#preview-validate-script)し、電子メールに直接保存します。

### サポートされている速度の構成 {#supported-velocity-constructs}

Script Builderは、次の[!DNL Marketo Engage]個のVelocity control-flow構造を、同等のHandlebarsまたは条件付きコンテンツ式に変換します。

| 速度構造 | Handlebarsまたは条件付きコンテンツ同等 |
| ------------------- | --------------------------------------------- |
| `#if` / `#elseif` / `#else` | Handlebars `{{#if}}`、`{{else if}}`および`{{else}}` ブロックヘルパー、または[!DNL Journey Optimizer B2B Edition] [条件付きコンテンツ ](./conditional-content.md) ルール |
| `#set` | 生成されたスクリプト内のHandlebars変数割り当て |

セグメントベースの条件付きロジックを[条件付きコンテンツ ](./conditional-content.md) ルールに変換し、多くの言語バリアントブロックを含むメールを含む分岐動作をレプリケートします。

速度コンストラクトに直接ハンドルバーまたはコンディショナルコンテンツに相当するものがない場合、Script Builderは、不完全または誤った式を生成する代わりに[変換レポート ](#review-conversion-report)でフラグを付けます。

### コンバージョンレポートを見る {#review-conversion-report}

各コンバージョンの後、スクリプトビルダーは次のリストを含む構造化レポートを表示します。

* 正常にマッピングされたトークン。
* 手作業による解決が必要なトークン：
* 直接Handlebarsに相当するものがないVelocity構造。

残りのトークンを解決してスクリプトを保存する前に、レポートを使用して変換が完了したことを確認します。

### マッピングなしでトークンを解決 {#resolve-tokens-without-mapping}

カスタムリード属性やカスタム [!DNL Marketo Engage] オブジェクトなど、マッピングライブラリにないトークンの場合、Script Builderは次の順序でマッピングを解決しようとします。

1. 使用可能なXDM フィールドに基づくマッピングと、確実な一致が存在する場合に組織用に設定された[ モデルベースのクラス ](./personalization.md#custom-datasets)に対するカスタムオブジェクトに基づくマッピングが提案されます。

1. 自信をもって一致を提案できない場合は、チャットで正しいマッピングを求められます。

ライブラリ内にないトークンのマッピングを確認すると、Script Builderは決定を記憶するかどうかを尋ねます。 同意すると、マッピングはソース [!DNL Marketo Engage] インスタンスで記憶され、そのMunchkin IDによって識別されます。これにより、次回そのインスタンスからスクリプトを変換するときに、同じトークンが自動的に解決されます。

### スクリプトのプレビューと検証 {#preview-validate-script}

変換を確定する前に、Script Builderでは、元のVelocity スクリプトと生成されたHandlebars出力の横に並べてプレビューが表示され、インライン編集がサポートされます。 プレビューを使用して2つのバージョンを比較し、生成されたスクリプトで直接調整を行います。

「**[!UICONTROL 検証]**」をクリックして、生成されたハンドルバーを[!DNL Journey Optimizer B2B Edition] スキーマに照らし合わせて確認します。 保存すると検証が再度実行され、壊れたパーソナライゼーションがライブメールに公開されることはありません。

結果に満足したら、**[!UICONTROL 保存]**&#x200B;をクリックして、スクリプトをメール内の選択した場所に直接挿入します。

<!--
### Save reusable conversion profiles {#save-reusable-conversion-profiles}

Save your field mappings and segment mappings as a reusable conversion profile so that your token schema does not need to be re-entered for each script or migration batch. Select a saved profile at the start of a conversion to apply its mappings automatically.

### Audit logs {#conversion-audit-logs}

Script Builder records an audit log for every conversion event, including which scripts were processed, which tokens were remapped, which tokens required manual intervention, and who approved the final output. Use the audit log to review migration activity across your organization.

-->
