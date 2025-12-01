---
title: '[!DNL Adobe Target] 外部オーディエンス'
description: アカウントジャ  [!DNL Adobe Target]  ニーを通じて外部オーディエンスをアクティブ化。 B2B Web エクスペリエンスをパーソナライズし、クロスプラットフォームの一貫性を維持します。
feature: Integrations, Audiences, Account Journeys
role: User, Admin
source-git-commit: 598546c62cb2d567f19b26f7f760aa43e4dd0bc9
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 1%

---

# [!DNL Adobe Target] 外部オーディエンス

アカウントジャーニーを通じて、[!DNL Adobe Target] での外部オーディエンスのエクスペリエンスをアクティブ化およびパーソナライズできます。 この統合を使用すると、エンゲージメントを向上させる高度なパーソナライズとカスタマイズされたパーソナライゼーションを実現し、[!DNL Target] と [!DNL Journey Optimizer B2B Edition] 間でクロスプラットフォームの一貫性を維持できます。 この一貫性により、チームは B2B 購入者ジャーニー全体を通じて、購入グループの web チャネルを調整しパーソナライズすることができます。

Adobe Targetを通じて外部オーディエンスをアクティブ化するには、次の 2 つの手順があります。

1. ジャーニーから [&#x200B; 外部の顧客オーディエンスに追加 &#x200B;](#add-to-customer-external-audience-from-a-journey) します。
2. Experience Platformで宛先として [&#x200B; 用する &#x200B;](#activate-the-external-audience-to-target-as-a-destination) 外部オーディエンスをアクティベート [!DNL Target] します。

## ジャーニーから顧客外部オーディエンスに追加

ジャーニーで [_アクションを実行_ ノードを追加 &#x200B;](../journeys/action-nodes.md) して、_[!UICONTROL 外部顧客オーディエンスに追加]_ アクションを実行します。 アクションは、通常、イベントや以前のアクションなど、何らかのトリガーの結果として発生させるもので、 ジャーニーは、ユーザープロファイルを持つ資格のあるアカウントがノードに到達すると、アクションを実行します。

>[!NOTE]
>
>個人プロファイルを含む資格のあるアカウントが公開済みのジャーニーの _外部顧客オーディエンスに追加_ ノードに達した場合、これらのプロファイルが外部オーディエンスに入力されるまで最大 48 時間かかる場合があります。

1. ジャーニーキャンバスで _アクションを実行_ ノードを選択した状態で、「_[!UICONTROL アクション]_ **[!UICONTROL 人物]**」オプションを選択します。

1. _[!UICONTROL ユーザーに対するアクション]_ については、「**[!UICONTROL 外部顧客オーディエンスに追加]**」を選択します。

   ![ジャーニーノード – 担当者に対してアクションを実行 – 外部の顧客オーディエンスに追加 &#x200B;](./assets/node-add-external-audience.png){width="550" zoomable="yes"}

1. 右側のノードプロパティで、外部オーディエンスを設定します。

   * 作成済みの外部オーディエンスが 1 つ以上ある場合は、「既存を選択 **[!UICONTROL および]** 使用するオーディエンスを選択 [&#x200B; を選択でき &#x200B;](#choose-an-external-audience) す。

   * ノードに使用する [&#x200B; オーディエンスを作成する &#x200B;](#create-an-external-audience) 場合は、「新規作成 **[!UICONTROL を選択し]** す。

### 外部オーディエンスの作成

1. ノードプロパティで「**[!UICONTROL 新規作成]**」オプションを選択したら、「**[!UICONTROL 外部顧客オーディエンスを作成]**」をクリックします。

   ![&#x200B; ユーザーに対するアクションの実行 – 外部の顧客オーディエンスに追加 – 新しいオプションを作成 &#x200B;](./assets/node-add-external-audience-create-new-option.png){width="400"}

1. ダイアログで、新しいオーディエンスの **[!UICONTROL 名前]** （必須）と **[!UICONTROL 説明]** （オプション）を入力します。

   ![&#x200B; 外部顧客オーディエンスを作成ダイアログ &#x200B;](./assets/create-external-customer-audience-dialog.png){width="400"}

1. 「**[!UICONTROL 作成]**」をクリックします。

   新しいオーディエンスが作成され、確認メッセージが表示されます。 その後、ノードアクションの既存のオーディエンスとして使用に進むことができます。

### 外部オーディエンスを選択

1. ノードプロパティで「**[!UICONTROL 既存の顧客を選択]**」オプションを選択したら、「**[!UICONTROL 外部顧客オーディエンスを選択]**」をクリックします。

   ![&#x200B; ユーザーに対するアクションの実行 – 外部の顧客オーディエンスに追加 – 既存のオプションを選択 &#x200B;](./assets/node-add-external-audience-select-existing-option.png){width="300"}

1. _[!UICONTROL オーディエンスを追加]_ ダイアログで、使用するオーディエンスを選択します。

   「_検索_」フィールドにテキストを入力すると、表示される項目をフィルタリングしてオーディエンス名と一致させることができます。

   ![&#x200B; ユーザーに対するアクションの実行 – 外部の顧客オーディエンスに追加 – オーディエンスを追加ダイアログ &#x200B;](./assets/add-audience-dialog.png){width="700" zoomable="yes"}

1. **[!UICONTROL オーディエンスを追加]** をクリックします。

## Target を宛先として使用するための外部オーディエンスのアクティブ化

外部オーディエンスをAdobe Targetにアクティブ化するには、[!DNL Adobe Target] で [!DNL Real-time Customer Data Platform (RTCDP)] を宛先として設定している必要があります。 この設定について詳しくは、[RTCDP ドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/platform-learn/tutorials/destinations/target/configure-the-target-destination){target="_blank"} を参照してください。

>[!IMPORTANT]
>
>ジャーニーを通じてアクティベーションを使用するには、RTCDPを実装する際に、メールアドレスを ID として使用する必要があります。

アクティベーションプロセスでは、[!DNL Adobe Target] を外部オーディエンスまたは外部の宛先として追加する必要があります。 まず、オーディエンスビルダーで [!DNL Target] オーディエンスを作成します。 また、プレースホルダーオーディエンスを作成し、外部オーディエンス機能を追加することもできます。

>[!BEGINSHADEBOX]

![AEP権限アイコン &#x200B;](../../assets/do-not-localize/icon_permissions-outline.svg) これらの手順には、割り当てられたユーザーロールに対する次の権限が必要です。

* **[!UICONTROL Experience Platform]** - _[!UICONTROL 宛先]_ リソース：`Activate Destinations`、`Manage and Activate Dataset Destination` および `View Destination`
* **[!DNL Target]** - `Approver`

>[!ENDSHADEBOX]

1. Experience Platformで、左側のナビゲーションの **[!UICONTROL 接続]**/**[!UICONTROL 宛先]** に移動します。

1. 「**[!UICONTROL 参照]**」タブを選択します。

1. セグメントをアクティベートするために使用する宛先接続を見つけ、名前の横にある _詳細メニュー_ （**...**）アイコンをクリックして、「**[!UICONTROL オーディエンスをアクティベート]**」を選択します。

   「_[!UICONTROL 検索]_」フィールドにテキストを入力し、表示された宛先を名前でフィルタリングして、一致させる。

   ![Experience Platform – 宛先 – ターゲットの宛先を参照 – その他メニュー &#x200B;](./assets/aep-destinations-activate-target-audience.png){width="800" zoomable="yes"}

1. _[!UICONTROL 使用可能なオーディエンス]_ リストで、外部オーディエンスを選択し、「**[!UICONTROL 次へ]**」をクリックします。

   ![Experience Platform – 宛先 – ターゲットの宛先を参照 – その他メニュー &#x200B;](./assets/aep-destinations-activate-target-audience-available-audiences.png){width="700" zoomable="yes"}

1. 宛先に対して追加のフィールドマッピングを実行し（オプション）、「**[!UICONTROL 次へ]**」をクリックします。

1. 新しいオーディエンスパラメーターを確認し、「**[!UICONTROL 終了]**」をクリックします。

   ![Experience Platform – 宛先 – 宛先のアクティブ化 – レビュー &#x200B;](./assets/aep-destinations-activate-target-audience-review.png){width="700" zoomable="yes"}

アクティブ化すると、[Adobe Target オーディエンスでオーディエンスを表示し &#x200B;](https://experienceleague.adobe.com/en/docs/target/using/audiences/create-audiences/audiences#use-list){target="_blank"}Adobe Target アクティビティで使用できます。

