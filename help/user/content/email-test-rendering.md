---
title: メールのレンダリングをテスト
description: Litmus アカウントを活用して、Journey Optimizer B2B editionでメールのレンダリングをテストする方法を説明します。
feature: Email Authoring, Integrations
level: Intermediate
role: User
source-git-commit: 23fe51dd0df0b958a61ada25521f35d8acd8bcc4
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 3%

---

# Litmus でのメールのレンダリングのテスト

メールをテストするには、[Litmus アカウント ](https://www.litmus.com/email-testing){target="_blank"} をJourney Optimizer B2B editionに使用します。 この統合を使用すると、一般的なメールクライアントでのメールのレンダリングをプレビューできます。 このツールを使用すると、メールコンテンツを適切に表示し、すべてのインボックスで設計どおりに動作させることができます。

1. メールデザインが完了し、テストする準備が整ったら、メールデザイン領域で **[!UICONTROL コンテンツをシミュレート]** をクリックします。

1. 右上の **[!UICONTROL メールをレンダリング]** をクリックします。

   ![ メールをレンダリングボタン ](./assets/email-simulate-render-button.png)

   Journey Optimizer B2B editionから Litmus アカウントにまだ接続していない場合は、表示されるページで体験版アカウントを開始するか、既存のアカウントに接続するかを選択できます。

1. 右上の **[!UICONTROL Litmus アカウントを接続]** をクリックするか、ページ内のリンクを使用します。

   ![Litmus アカウントを接続する ](./assets/email-simulate-render-litmus-connect.png)

1. 資格情報を入力し、「**[!UICONTROL ログイン]**」をクリックします。

   >[!IMPORTANT]
   >
   >Litmus アカウントをJourney Optimizer B2B editionに接続する場合、テストメッセージが Litmus に送信されることに同意する必要があります。 送信後は、これらのメールはAdobeで管理されなくなります。 その結果、テストメッセージに含まれる可能性のあるパーソナライゼーションデータも含め、Litmus データ保持メールポリシーがこれらのメールに適用されます。

1. 右上の **[!UICONTROL テストを実行]** をクリックして、メールのプレビューを生成します。

1. 一般的なデスクトップ、モバイル、Web ベースのクライアントでメールの内容を確認します。

   ![Litmus メールのプレビュー ](./assets/email-simulate-render-litmus-previews.png)

   表示されたサムネールをクリックして、レンダリングされたクライアントテストの詳細を表示します。

1. 確認が完了したら、左上の背面矢印（![ フィルターを表示または非表示のアイコン ](../../assets/do-not-localize/icon_back-arrow.svg)）をクリックして、コンテンツをシミュレート ページに戻ります。

   別のプロファイルを選択して別のレンダリングテストを行ったり、電子メールデザインスペースに戻ってレビューに基づいて必要な調整を行ったりできます。

