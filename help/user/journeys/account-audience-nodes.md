---
title: アカウントオーディエンスノード
description: Journey Optimizer B2B editionでアカウントジャーニーの入力を定義するために使用できる、アカウントオーディエンスノードタイプについて説明します。
feature: Account Journeys
exl-id: 288ac5a8-79ed-4654-8ac1-83da2af04f2c
source-git-commit: 5ed7e58b7a069c8b436d0d2f7b338072259768be
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 5%

---

# アカウントオーディエンスジャーニーノード

アカウントオーディエンスノードでは、ジャーニーの入力アカウントを定義します。 [ アカウントジャーニーを作成 ](./journey-overview.md#create-an-account-journey) すると、常に、ジャーニーの入力を定義する _アカウントオーディエンス_ ノードで開始します。

このノードに使用できる入力には、次の 2 種類があります。

* **[アカウントオーディエンス](../audiences/account-audience-overview.md)** - Experience Platform セグメント化サービスから同期される基本オーディエンスです。
* **[アカウントリスト](../accounts/account-lists.md)** - ターゲット設定された Journey Orchestration に使用できる名前付きアカウントのコレクションです。 アカウントリストは、定義済みの条件（業界、場所、会社の規模など）に基づいて名前付きアカウントをターゲットにします。

_ノードのオーディエンスを設定するには：_

1. **[!UICONTROL アカウントオーディエンス]** ノードをクリックして、右側にノードプロパティを表示します。

   ![ アカウントオーディエンスノード ](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. ジャーニーにエントリするアカウントの入力タイプを選択します。

   * **[!UICONTROL アカウントオーディエンス]**

     このタイプを選択し、「**[!UICONTROL アカウントオーディエンスを追加]**」をクリックします。

     _[!UICONTROL オーディエンスを追加]_ ダイアログで、以前に作成したオーディエンスセグメントを選択し、「**[!UICONTROL オーディエンスを追加]**」をクリックします。

     ![ ノードのオーディエンスセグメントの選択 ](./assets/node-audience-add-dialog.png){width="700" zoomable="yes"}

   * **[!UICONTROL アカウントリスト]**

     このタイプを選択し、「**[!UICONTROL アカウントリストを追加]**」をクリックします。

     _[!UICONTROL ライブアカウントリストを選択]_ ダイアログで、以前に公開したアカウントリストを選択し、「**[!UICONTROL 保存]**」をクリックします。

     ![ ノードのライブアカウントリストの選択 ](./assets/account-journey-account-audience-select-account-list.png){width="700" zoomable="yes"}

     アカウントリストの作成と公開について詳しくは、[ アカウントリスト ](../accounts/account-lists.md) を参照してください。

_オーディエンスセグメントを作成するには：_

1. 左側のナビゲーションで、**[!UICONTROL アカウント]**／**[!UICONTROL オーディエンス]**&#x200B;を選択します。

1. 右上の「**[!UICONTROL オーディエンスを作成]**」をクリックします。

   ![ オーディエンスセグメントの作成 ](./assets/audiences-list-create.png){width="800" zoomable="yes"}

1. [ セグメント化サービスガイド ](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/ui/account-audiences){target="_blank"} に記載されている手順に従います。
