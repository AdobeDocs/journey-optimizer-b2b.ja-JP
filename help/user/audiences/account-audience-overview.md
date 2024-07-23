---
title: アカウントオーディエンス
description: アカウントオーディエンスと、そのアカウントベースのジャーニーを有効にする方法について説明します。
source-git-commit: 3d3f0e4d6e62aa7126e915cfd5b54151d1bf9186
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 0%

---


# アカウントオーディエンス

オーディエンスとは、類似の行動や特徴を共有する人々の集まりです。 Journey Optimizer B2B Edition は、Adobe Real-time Customer Data Platform B2B および B2P エディションにあるアカウントのセグメント化機能を使用します。 アカウントのセグメント化を使用すると、システム内の任意の B2B エンティティのデータを活用して、アカウントオーディエンスを生成できます。 これらのアカウントオーディエンスは、Journey Optimizer B2B Edition アカウントジャーニーの入力として機能し、シームレスなアクティベーションとパーソナライゼーション機能を促進します。

アカウントオーディエンスとその定義方法について詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/account-audiences) を参照してください。

## アカウントオーディエンスワークフロー

Journey Optimizer B2B Edition は、宛先カタログに表示されないExperience Platform（AEP）の宛先と考えることができます。 次の手順を使用して、アカウントオーディエンスをJourney Optimizer B2B Edition に対してアクティブ化します。

1. AEP でデータのスキーマを作成します。
1. データを AEP に取り込みます。
1. アカウントセグメントを作成してデータを評価します。
1. 評価済みのデータをJourney Optimizer B2B Edition に対してアクティブ化します。

Journey Optimizer B2B Edition では、アカウントオーディエンスをアカウントベースのジャーニーの入力として使用することで、これらのアカウント内の人物をターゲットにすることができます。 例えば、アカウントオーディエンスを使用して、最高執行責任者（COO）または最高マーケティング責任者（CMO）という肩書を持つ人物の連絡先情報を持たないすべてのアカウントのレコードを取得できます。

Journey Optimizer B2B Edition を使用すると、左側のナビゲーションから直接Adobe Experience Platform（AEP）アカウントオーディエンスを作成し、アカウントジャーニーに組み込むことができます。

![ アカウントオーディエンスへのアクセス ](./assets/account-audiences-browse.png){width="800" zoomable="yes"}

## アカウントオーディエンスの作成

アカウントのセグメント化を作成して、アカウントオーディエンスを定義します。 アカウントのセグメント化は、Journey Optimizer B2B Edition アプリケーション内で直接作成することも、[ セグメントビルダー UI](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/segment-builder) を使用することもできます。 Journey Optimizer B2B Edition でアカウントのセグメント化を作成する手順を以下に示します。

1. 左側のナビゲーションで **[!UICONTROL アカウント]**/**[!UICONTROL オーディエンス]** を選択します。

1. 右上の **[!UICONTROL オーディエンスを作成]** をクリックします。

1. セグメント定義を作成します。

   アカウント属性とオーディエンスが左側のナビゲーションバーに表示されます。 「_[!UICONTROL 属性]_」タブでは、Platform で作成した属性とカスタム属性の両方を追加できます。 各属性をドラッグして、セグメントのロジックを作成します。

   >[!TIP]
   >
   >アカウントオーディエンスを作成する場合、イベントは _[!UICONTROL 人物]_ の下に表示されることに注意してください。これらの属性は人物に関連付けられてい <br/> からです。
   >
   >「_[!UICONTROL オーディエンス]_」タブでは、以前に作成したユーザーベースのオーディエンスを追加して、独自のアカウントオーディエンスの作成時に構築できます。

   次の例では、`Country Code`、`Revenue Amount` および `Market segment` を使用して作成されたオーディエンスを定義します。 英語のクエリは、「I want all accounts in the US who are in the Finance Segment has overcome 100 万ドル。」となります。

   ![ アカウントオーディエンスセグメントビルダーの例 ](./assets/audience-segment-builder-US-finance-1M.png){width="700" zoomable="yes"}

1. 右上の **[!UICONTROL 保存して閉じる]** をクリックします。

Journey Optimizer B2B Edition のアカウントオーディエンスをアクティベートするには、[ アカウントジャーニーに追加 ](../journeys/journey-overview.md#add-the-account-audience-for-your-journey) してから [ ジャーニーを公開 ](../journeys/journey-overview.md) する必要があります。
