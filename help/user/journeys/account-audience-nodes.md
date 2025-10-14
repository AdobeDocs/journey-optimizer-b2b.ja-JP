---
title: アカウントオーディエンスノード
description: アカウントオーディエンスノードをアカウントオーディエンスまたはアカウントリストで設定し、Journey Optimizer B2B editionでのターゲットオーケストレーションのジャーニーエントリポイントを定義します。
feature: Account Journeys, Audiences, Account Lists
role: User
exl-id: 288ac5a8-79ed-4654-8ac1-83da2af04f2c
source-git-commit: a8c2e8e96c5a70032ceba3f0630d1f6c5ae01726
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---


# アカウントオーディエンスジャーニーノード

アカウントオーディエンスノードは、ジャーニーにエントリするアカウントを指定します。 [&#x200B; アカウントジャーニーを作成 &#x200B;](./journey-overview.md#create-an-account-journey) すると、ジャーニーは常に、その入力を定義するアカウントオーディエンスノードで開始します。

このジャーニーノードには、次のいずれかの入力オプションを使用します。

* **[アカウントオーディエンス](../audiences/account-audience-overview.md)** - アカウントオーディエンスは、Experience Platform Segmentation Service から同期される基本的なオーディエンスを表します。
* **[アカウントリスト](../accounts/account-lists.md)** - アカウントリストは、ターゲットの Journey Orchestration に使用する名前付きアカウントのコレクションです。 アカウントリストは、定義済みの条件（業界、場所、会社の規模など）を使用して、名前付きのアカウントをターゲットにします。

## アカウントオーディエンスノードのオーディエンスを設定

1. **[!UICONTROL アカウントオーディエンス]** ノードをクリックします。 このアクションを実行すると、右側にノードのプロパティが表示されます。

   ![&#x200B; アカウントオーディエンスジャーニーノード &#x200B;](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. ジャーニーにエントリするアカウントの入力タイプを選択します。

   * **[!UICONTROL アカウントオーディエンス]**

     アカウントオーディエンスオプションを選択します。 次に、「**[!UICONTROL アカウントオーディエンスを追加]**」をクリックします。

     _[!UICONTROL オーディエンスを追加]_ ダイアログで、以前に作成したオーディエンスセグメントを選択します。 次に、「**[!UICONTROL オーディエンスを追加]** をクリックします。

     ![&#x200B; ノードのオーディエンスセグメントの選択 &#x200B;](./assets/node-audience-add-dialog.png){width="700" zoomable="yes"}

   * **[!UICONTROL アカウントリスト]**

     「アカウントリスト」オプションを選択します。 **[!UICONTROL アカウントリストを追加]** をクリックします。

     _[!UICONTROL ライブアカウントリストを選択]_ ダイアログで、公開済みのアカウントリストを選択します。 次に、「**[!UICONTROL 保存]**」をクリックします。

     ![&#x200B; ノードのライブアカウントリストの選択 &#x200B;](./assets/account-journey-account-audience-select-account-list.png){width="700" zoomable="yes"}

     アカウントリストの作成と公開について詳しくは、[&#x200B; アカウントリスト &#x200B;](../accounts/account-lists.md) を参照してください。

## オーディエンスセグメントの作成

1. 左側のナビゲーションで **[!UICONTROL アカウント]**/**[!UICONTROL オーディエンス]** を選択します。

1. 右上隅の **[!UICONTROL オーディエンスを作成]** をクリックします。

   ![&#x200B; オーディエンスセグメントの作成 &#x200B;](./assets/audiences-list-create.png){width="800" zoomable="yes"}

1. [&#x200B; セグメント化サービスガイド &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/types/account-audiences){target="_blank"} の手順に従います。
