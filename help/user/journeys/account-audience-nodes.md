---
title: アカウントオーディエンスノード
description: Journey Optimizer B2B Edition でアカウントジャーニーの入力を定義するために使用できる アカウント オーディエンス ノードタイプについて説明します。
feature: Account Journeys
exl-id: 288ac5a8-79ed-4654-8ac1-83da2af04f2c
source-git-commit: ed75e0c9b0391c31034a1143ef58c20673eac328
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 0%

---

# アカウント オーディエンス ジャーニー ノード

アカウントオーディエンスノードでは、ジャーニーの入力アカウントオーディエンス(Adobe Experience Platform で作成および管理)が定義されます。 アカウントジャーニーを [作成する](./journey-overview.md#create-an-account-journey)場合、ジャーニーの入力を定義する _取引先オーディエンス_ ノードで必ず開始されます。

このノードに使用できる入力には、次の 2 種類があります。

* **[アカウント オーディエンス](../audiences/account-audience-overview.md)** - これは、Experience Platform セグメント化 サービスから同期される基本的なオーディエンスです。
* **[アカウント リスト](../accounts/account-lists.md)** - これは、ターゲットジャーニーオーケストレーションに使用できる名前付きアカウントのコレクションです。 アカウント リストは、業種、場所、会社の規模など、定義された条件によって名前付きアカウントをターゲットにします。

_ノードのオーディエンスを設定するには:_

1. **[!UICONTROL アカウントオーディエンス]**&#x200B;ノードをクリックして、右側にノードプロパティを表示します。

   ![アカウントオーディエンスノード](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. アカウントの入力タイプを選択して、ジャーニーを入力します。

   * **[!UICONTROL アカウントオーディエンス]**

     このタイプを選択して、「 **[!UICONTROL 追加 アカウント オーディエンス]**&#x200B;をクリックします。

     _[!UICONTROL オーディエンスを追加]_ ダイアログで、以前に作成したオーディエンスセグメントを選択し、「**[!UICONTROL オーディエンスを追加]**」をクリックします。

     ![ノードのオーディエンスセグメントを選択します。](./assets/node-audience-add-dialog.png){width="700" zoomable="yes"}

   * **[!UICONTROL アカウントリスト]**

     このタイプを選択して、「 **[!UICONTROL 追加 アカウント リスト]**&#x200B;をクリックします。

     _[!UICONTROL ライブアカウントリストを選択]_&#x200B;ダイアログで、以前に公開したアカウントリストを選択し、[**[!UICONTROL 保存]**] をクリックします。

     ![ノードのライブアカウントリストを選択する](./assets/account-journey-account-audience-select-account-list.png){width="700" zoomable="yes"}

     アカウントリストの作成と公開について詳しくは、 [アカウントリスト](../accounts/account-lists.md) を参照してください。

_オーディエンスセグメントを作成するには:_

1. 左側のナビゲーションで、「 **[!UICONTROL アカウント]** > **[!UICONTROL Audiences]**」を選択します。

1. 右上の [ **[!UICONTROL 作成オーディエンス]** をクリックします。

   ![オーディエンスセグメント作成](./assets/audiences-list-create.png){width="800" zoomable="yes"}

1. [ セグメント化サービスガイド ](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/ui/account-audiences){target="_blank"} に記載されている手順に従います。
