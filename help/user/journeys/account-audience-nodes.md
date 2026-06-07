---
title: アカウントオーディエンスノード
description: アカウントオーディエンスまたはアカウントリストを使用してアカウントオーディエンスノードを設定し、Journey Optimizer B2B editionでターゲットオーケストレーションのジャーニーエントリポイントを定義します。
feature: Account Journeys, Audiences, Account Lists
role: User
exl-id: 288ac5a8-79ed-4654-8ac1-83da2af04f2c
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
subfeature_v2:
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
autotag-review: '2026-04-29T23:21:59.633Z'
source-git-commit: 7cd6c4ecfbbd3a86b4f30d1b4fe6f06655a9c4f5
workflow-type: tm+mt
source-wordcount: 277
ht-degree: 4%

---


# アカウントオーディエンスジャーニーノード

アカウントオーディエンスノードは、ジャーニーにエントリするアカウントを指定します。 アカウント ジャーニーを[作成する場合](./create-publish-journey.md#create-a-journey)、ジャーニーは常に、入力を定義するアカウント オーディエンス ノードから始まります。

このジャーニーノードには、次のいずれかの入力オプションを使用します。

* **[アカウントオーディエンス](../audiences/account-audience-overview.md)** — アカウントオーディエンスは、Experience Platform Segmentation Serviceから同期する基本的なオーディエンスを表します。
* **[アカウントリスト](../accounts/account-lists.md)** — アカウントリストは、ターゲットジャーニーオーケストレーションに使用する名前付きアカウントのコレクションです。 アカウントリストは、業界、所在地、企業規模などの定義された基準を使用して、名前付きアカウントをターゲットにします。

## アカウントオーディエンスノードのオーディエンスの設定

1. 「**[!UICONTROL アカウントオーディエンス]**」ノードをクリックします。 このアクションは、右側のパネルにノードプロパティを表示します。

   ![&#x200B; アカウントオーディエンスジャーニーノード &#x200B;](./assets/account-journey-account-audience-node.png){width="700" zoomable="yes"}

1. ジャーニーに入力するアカウントの入力タイプを選択します。

   * **[!UICONTROL アカウントオーディエンス]**

     「アカウントオーディエンス」オプションを選択します。 次に、**[!UICONTROL アカウントオーディエンスを追加]**&#x200B;をクリックします。

     _[!UICONTROL オーディエンスを追加]_ ダイアログで、以前に作成したオーディエンスセグメントを選択します。 次に、**[!UICONTROL オーディエンスを追加]**&#x200B;をクリックします。

     ![&#x200B; ノードのオーディエンスセグメントを選択](./assets/node-audience-add-dialog.png){width="700" zoomable="yes"}

   * **[!UICONTROL アカウントリスト]**

     アカウントリストオプションを選択します。 「**[!UICONTROL アカウントリストを追加]**」をクリックします。

     _[!UICONTROL ライブアカウントリストを選択]_ ダイアログで、公開されたアカウントリストを選択します。 次に、「**[!UICONTROL 保存]**」をクリックします。

     ![&#x200B; ノードのライブアカウントリストを選択](./assets/account-journey-account-audience-select-account-list.png){width="700" zoomable="yes"}

     アカウントリストの作成と公開について詳しくは、[&#x200B; アカウントリスト &#x200B;](../accounts/account-lists.md)を参照してください。

## オーディエンスセグメントの作成

1. 左側のナビゲーションで、**[!UICONTROL アカウント]**/**[!UICONTROL オーディエンス]**&#x200B;を選択します。

1. 右上隅の「**[!UICONTROL オーディエンスを作成]**」をクリックします。

   ![&#x200B; オーディエンスセグメントを作成](./assets/audiences-list-create.png){width="800" zoomable="yes"}

1. [&#x200B; セグメント化サービスガイド &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/segmentation/types/account-audiences){target="_blank"}の手順に従います。
