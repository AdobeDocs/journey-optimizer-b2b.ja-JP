---
title: AI アシスタントを使用する
description: Journey Optimizer B2B editionの機能を最大限に活用するために AI アシスタントがどのように役立つかを説明します。
feature: AI Assistant
level: Beginner
exl-id: 2d642c34-6f6d-4a0f-98c5-4b9ea1cdaa29
source-git-commit: d19ed2bbe850a14cb0563f6e3563cd8f1c8d3226
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%

---

# Journey Optimizer B2B editionでの AI アシスタントの使用

Journey Optimizer B2B editionで AI アシスタントを使用すると、製品のコンセプトを理解し、Journey Optimizer B2B editionの機能をすばやくナビゲートして学習し、特定の環境の運用に関するインサイトを取得できます。 また、Adobe Experience Cloud中のいくつかの製品で利用可能です。

>[!IMPORTANT]
>
>AI アシスタントを使用する前に、Adobe Experience Cloud 生成 AI ユーザー ガイドラインの同意が必要です。 本契約および使用ガイドラインの詳細については、 [Adobe Experience Cloud Generative AI ユーザーガイドライン](https://www.adobe.com/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html)を参照してください。

AI アシスタントにアクセスするには、ヘッダーのアイコンをクリックします。 AIアシスタントが右側のパネルで開きます。

![アイコンをクリックしてAIアシスタントにアクセスします](./assets/ai-assistant-icon-displayed.png){width="420" zoomable="yes"}

AIアシスタントインターフェイスが表示され、開始するための情報がすぐに提供されます。 _アイデア_&#x200B;の下にあるオプションを使用して、次のような質問とコマンド～に回答できます。

* アカウントジャーニーのどれが公開されましたか?
* どのようなソリューションの関心が生まれましたか?
* Journey Optimizer B2B editionの主なメリットを教えてください。

Adobe Journey Optimizer B2B editionでは、AI アシスタントは次のユースケースをサポートします。

## 製品に関する知識

製品に関する質問は、Adobe Systems Journey Manager の側面に関連する Journey Optimizer B2B Edition の概念に関するものです。 製品知識に関する質問の例をいくつか挙げます。

* SMSプロバイダーアカウントを設定するにはどうすればよいですか?
* アカウントジャーニーでメールを送信するにはどうすればよいですか?
* E メール内容をパーソナライズするにはどうすればよいですか?

製品に関する質問は、パネル下部のフィールドに入力し、Enter キーを押します。

![テキストボックスに質問を入力します](./assets/ai-assistant-ask-question.png){width="420" zoomable="yes"}

AI Assistant によって返された応答を確認するには、すべての製品ナレッジ ～に回答で利用可能な引用を確認します。

引用文献を表示し、AI Assistant の応答を検証するには、[ **[!UICONTROL 表示 ソース]**] を選択します。

![AI アシスタントのクエリの結果 ](./assets/ai-assistant-answer.png){width="420" zoomable="yes"}

AI アシスタントがインターフェイスを更新し、最初の応答を裏付けるドキュメントへのリンクを提供します。 さらに、引用が有効な場合、AI アシスタントは応答を更新して、提供されたドキュメントを参照する回答の特定の部分を示す脚注を含めます。

親指を上にするか、下に親指を立てて、～に回答の品質を評価します。

## 運用上の洞察

運用上のインサイトの質問は、組織のサンドボックス内のジャーニーオブジェクトに関するものです。運用上のインサイトの質問やプロンプトの例を次に示します。

* Adobe Systems Journey Optimizer B2B Edition にはいくつのライブジャーニーがありますか?
* スケジュールされたすべてのジャーニーのリストを提示してください。
* 過去 7 日間に作成されたジャーニーの数はいくつですか。

AI Assistant が運用上の分析情報に関する質問に十分な回答を提供するには、アクティブなサンドボックスにいる必要があります。

>[!NOTE]
>
>AI アシスタントのオペレーショナルインサイト質問でサポートされる唯一のAdobe Journey Optimizer B2B edition オブジェクトは、[ オペレーショナルインサイトドメインテーブル ](./ai-assistant-overview.md#operational-insights) に一覧表示されます。 現在アクセスしているサンドボックスのデータにのみアクセスできます。

<!-- Select to view an example of an operational insights question.

In the following example, AI Assistant receives the following query: _Show me dataflows that were created using the Amazon S3 source._

screen

AI Assistant responds with a table list of your dataflows and their corresponding IDs. Click the _Download_ icon ( Download icon ) to download the table as a CSV file. To view the entire table, click the _Expand_ icon ( Expand icon ).

screen

An expanded view of the table appears, providing you with a more comprehensive list of dataflows based on the parameters of your query.

screen

When prompted with an operational insights question, AI Assistant provides an explanation of how it computed the answer. In the following example, AI Assistant outlines the steps it took in order to identify the dataflows that were created using the Amazon S3 source.

screen

You can also provide filters and modifications to your questions, and you can instruct AI Assistant to render its findings based on the filters that you include. For example, you can ask AI Assistant to show you a trend of the count of segment definitions in the order of their created date, remove segment definitions with zero total profiles, and use month names instead of integers when displaying the data.

### Verify operational insights responses

You can verify each response related to operational insights questions using an SQL query that AI Assistant provides.

Select to view example of verifying operational insights responses

After receiving an answer for an operational insights question, click **[!UICONTROL Show sources]** and then select **[!UICONTROL View source query]**.

screen

When queried with an operational insights question, AI Assistant provides an SQL query that you can use to verify the process that it took to compute its answer. This source query is for verification purposes only and is not supported on Query Service.

screen  

 -->
