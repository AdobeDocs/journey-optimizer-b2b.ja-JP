---
title: メールのレンダリングをテストする
description: Litmusとの統合により、デスクトップ、モバイル、web クライアントをまたいでメールのレンダリングをテストし、Journey Optimizer B2B editionで受信トレイの互換性を確認します。
feature: Email Authoring, Integrations
level: Intermediate
role: User
exl-id: 26d87a56-6bd1-4d4a-8090-71f5b0a7e9f8
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2:
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: cad51180-f8ce-4cb7-aefc-437847b5d6d6
autotag-review: '2026-03-30T22:28:13.343Z'
source-git-commit: 8fe8318d7e1c63cbaa2749fc3928eb0a12967bd9
workflow-type: tm+mt
source-wordcount: 376
ht-degree: 5%

---

# Litmus を使用したメールのレンダリングのテスト

メールをテストするには、Journey Optimizer B2B editionの[Litmus](https://www.litmus.com/email-testing){target="_blank"} Enterprise アカウントを活用します。 この統合により、一般的なメールクライアントでメールのレンダリングをプレビューできます。 このツールは、電子メールコンテンツが適切に表示され、あらゆる受信トレイに適切に表示されることを確認するのに役立ちます。

>[!AVAILABILITY]
>
>この統合は、Litmus Enterprise アカウントを持つJourney Optimizer B2B edition ユーザーのみが使用できます。 詳しくは、Litmus web サイト [&#128279;](https://www.litmus.com/solutions/esp/adobe-journey-optimizer){target="_blank"}の解決策ページを参照してください。

1. 電子メールデザインが完了し、テストの準備ができたら、電子メールデザインスペースの「**[!UICONTROL コンテンツをシミュレート]**」をクリックします。

1. 右上の「**[!UICONTROL メールをレンダリング]**」をクリックします。

   ![電子メールボタンをレンダリング &#x200B;](./assets/email-simulate-render-button.png){width="700" zoomable="yes"}

   Journey Optimizer B2B editionからLitmus アカウントにまだ接続していない場合、表示されたページには、体験版アカウントを開始するか、既存のアカウントに接続するためのオプションが表示されます。

1. 右上の&#x200B;**[!UICONTROL Litmus アカウントを接続]**&#x200B;するか、ページ内のリンクを使用します。

   ![Litmus アカウントを接続](./assets/email-simulate-render-litmus-connect.png){width="700" zoomable="yes"}

1. Litmus アカウントの資格情報を入力し、**[!UICONTROL ログイン]**&#x200B;をクリックします。

1. 「**[!UICONTROL Connect]**」をクリックして、LitmusとJourney Optimizer B2B editionの連携を確定し、レンダリング用にメールコンテンツを送信します。

   >[!IMPORTANT]
   >
   >Litmus アカウントをJourney Optimizer B2B editionに接続すると、テストメッセージがLitmusに送信されることに同意したことになります。 このコンテンツは、AdobeではなくLitmus内で管理されます。 そのため、Litmus データ保持メールポリシーは、テストメッセージに含まれる可能性のあるパーソナライゼーションデータを含む、これらのメールに適用されます。

1. 右上の「**[!UICONTROL テストを実行]**」をクリックして、メールのプレビューを生成します。

   ![Litmus レンダリングテストを実行](./assets/email-simulate-render-litmus-run-test.png){width="700" zoomable="yes"}

1. 一般的なデスクトップ、モバイル、Web ベースのクライアントでメールの内容を確認します。

   表示されたサムネールをクリックして、レンダリングされたクライアントテストの詳細を表示します。

   ![&#x200B; リトマス電子メールのプレビュー](./assets/email-simulate-render-litmus-previews.png){width="700" zoomable="yes"}

1. レビューが完了したら、左上の戻る矢印（![&#x200B; フィルターを表示または非表示にするアイコン &#x200B;](../../assets/do-not-localize/icon_back-arrow.svg)）をクリックして、コンテンツシミュレーションページに戻ります。

   別のプロファイルを選択して別のレンダリングテストを行うか、メールデザインスペースに戻ってレビューに基づいて必要な調整を行うことができます。
