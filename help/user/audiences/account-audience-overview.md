---
title: アカウントオーディエンス
description: アカウントオーディエンスと、アカウントベースのジャーニーを有効にする方法について説明します。
feature: Audiences
role: User
exl-id: f9ba690f-bab2-4c31-9000-f0be1342c8b3
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 100%

---

# アカウントオーディエンス

オーディエンスとは、類似した行動や特性を共有する一連のユーザーです。Journey Optimizer B2B Edition では、Adobe Real-Time Customer Data Platform B2B および B2P Edition にあるアカウントのセグメント化機能を使用します。アカウントのセグメント化を使用すると、ユーザーはシステム内の任意の B2B エンティティのデータを活用してアカウントオーディエンスを生成できます。これらのアカウントオーディエンスは、Journey Optimizer B2B Edition アカウントジャーニーの入力として機能し、シームレスなアクティベーションとパーソナライゼーション機能を促進します。

アカウントオーディエンスとその定義方法について詳しくは、[Adobe Experience Platform セグメント化サービスのドキュメント](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/types/account-audiences){target="_blank"}を参照してください。

## アカウントオーディエンスワークフロー

Journey Optimizer B2B Edition は、宛先カタログに表示されない Experience Platform（AEP）の宛先と考えることができます。アカウントオーディエンスを Journey Optimizer B2B Edition にアクティベートするには、次の手順に従います。

1. AEP でデータのスキーマを作成します。
1. データを AEP に取り込みます。
1. データを評価するアカウントセグメントを作成します。
1. 評価したデータを Journey Optimizer B2B Edition にアクティベートします。

Journey Optimizer B2B Edition では、アカウントオーディエンスはアカウントベースのジャーニーの入力として使用され、これらのアカウント内の人物をターゲットにすることができます。例えば、アカウントオーディエンスを使用して、最高執行責任者（COO）または最高マーケティング責任者（CMO）という役職の人物に関する連絡先情報を持たないすべてのアカウントのレコードを取得できます。

Journey Optimizer B2B Edition を使用すると、左側のナビゲーションから直接 Adobe Experience Platform（AEP）アカウントオーディエンスを作成し、アカウントジャーニーに組み込むことができます。

![アカウントオーディエンスへのアクセス](./assets/account-audiences-browse.png){width="800" zoomable="yes"}

## オーディエンスの作成

アカウントのセグメント化を作成して、アカウントオーディエンスを定義します。Journey Optimizer B2B Edition アプリケーション内で直接アカウントのセグメント化を作成することも、[セグメントビルダー UI](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/segment-builder){target="_blank"} を使用することもできます。Journey Optimizer B2B Edition でアカウントのセグメント化を作成するために使用できる手順を以下に示します。

1. 左側のナビゲーションで、**[!UICONTROL アカウント]**／**[!UICONTROL オーディエンス]**&#x200B;を選択します。

1. 右上の「**[!UICONTROL オーディエンスを作成]**」をクリックします。

1. セグメント定義を作成します。

   アカウントの属性とオーディエンスは、左側のナビゲーションバーに表示されます。「_[!UICONTROL 属性]_」タブでは、Platform で作成された属性とカスタム属性の両方を追加できます。各属性をドラッグして、セグメントのロジックを作成します。

   >[!TIP]
   >
   >アカウントオーディエンスを作成する際は、イベントの属性が人物に関連付けられているので、イベントが&#x200B;_[!UICONTROL 人物]_&#x200B;の下にリストされます。<br/>
   >
   >「_[!UICONTROL オーディエンス]_」タブでは、独自のアカウントオーディエンスを作成する際に、以前に作成した人物ベースのオーディエンスを追加して作成できます。

   次の例では、`Country Code`、`Revenue Amount`、`Market segment` を使用して作成されたオーディエンスを定義します。英語でのクエリは、「I want all accounts in the US who are in the Finance Segment whose revenue exceeds $1M.」となります。

   ![アカウントオーディエンスセグメントビルダーの例](./assets/audience-segment-builder-US-finance-1M.png){width="700" zoomable="yes"}
   <br/>

   >[!IMPORTANT]
   >
   >アカウントレコードの `Account Name` 属性には、アカウントジャーニーに含める値が含まれている必要があります。この属性が空（null）の場合、アカウントレコードは除外されます。<br/>
   >空でないアカウント名を持つアカウントのみが含まれるようにするには、**[!UICONTROL アカウント名]**&#x200B;属性を追加し、一致条件として「_[!UICONTROL 存在する]_」を選択します。<br/>
   >![アカウント名属性が存在する](./assets/audience-segment-builder-account-name-exists.png){width="600"}
   ><br/>アカウント名にカスタム属性を使用している場合は、_[!UICONTROL アカウント名]_&#x200B;の代わりにカスタム属性名を使用します。

1. 右上の「**[!UICONTROL 保存して閉じる]**」をクリックします。

Journey Optimizer B2B Edition のアカウントオーディエンスをアクティベートするには、[アカウントジャーニーに追加](../journeys/journey-overview.md#add-the-account-audience-for-your-journey)して[ジャーニーを公開](../journeys/journey-overview.md)する必要があります。
