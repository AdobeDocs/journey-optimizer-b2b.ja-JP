---
title: Experience Manager Assets の操作
description: Adobe Journey Optimizer B2B editionでコンテンツをオーサリングする際に、接続されたAEM Assets リポジトリの画像アセットを使用する方法について説明します。
feature: Assets, Content, Integrations
role: User
exl-id: c6864981-209c-4123-8d3f-24deb07026a0
source-git-commit: ea2093b03ba89f9e8d3f0db60b65cb143603c217
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 2%

---

# Experience Manager アセットの操作

[!DNL Adobe Experience Manager Assets as a Cloud Service] を [!DNL Adobe Journey Optimizer B2B Edition] と統合すると、マーケティングコンテンツで使用するデジタルアセットを簡単に見つけてアクセスできます。 コンテンツを作成する際には、左側のナビゲーションの _[!UICONTROL Experience Manager Assets]_ 項目から、またアカウントジャーニーのメールコンテンツを作成する際に、アセットにアクセスできます。

{{aem-assets-licensing-note}}

これらのデジタルアセットを使用すると、[!DNL Assets as a Cloud Service] の最新の変更が、リンクされた参照を通じてライブメールキャンペーンに自動的に反映されます。 [!DNL Adobe Experience Manager Assets as a Cloud Service] で画像を削除すると、メール内で画像の参照が壊れて表示されます。 現在アカウントジャーニー内で使用されているアセットが変更または削除されると、画像の変更とその画像を使用しているジャーニーのリストがジャーニー作成者に通知されます。 アセットに対するすべての変更は、[!DNL Adobe Experience Manager Assets] の中央リポジトリで行う必要があります。

環境に 1 つ以上の [Assets リポジトリ接続 ](../admin/configure-aem-repositories.md) がある場合、コンテンツ作成者は、メール、メールテンプレートまたはビジュアルフラグメントを作成するときに、[!DNL Experience Manager Assets] をアセットのソースとして使用できます。

>[!IMPORTANT]
>
>管理者は、Assetsへのアクセスを必要とするユーザーをAssets Consumer Users または/およびAssets Users 製品プロファイルに追加する必要があります。 [詳細情報](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/security/ims-support#managing-products-and-user-access-in-admin-console){target="_blank"}

## AEM Assets画像へのアクセス

コンテンツデザイン スペースで、左側のサイドバーにある _[!UICONTROL Experience Manager Assets]_ （![Experience Manager Assets アイコン ](../../assets/do-not-localize/icon-assets-aem.svg)）アイコンをクリックします。 これにより、ツールパネルが、選択したリポジトリで使用可能なアセットのリストに変更されます。

![Assets セレクターアイコンをクリックして、画像アセットにアクセスする ](./assets/content-assets-selector-aem-assets.png){width="700" zoomable="yes"}

>[!NOTE]
>
>現在、[!DNL Adobe Experience Manager Assets] では [!DNL Adobe Journey Optimizer B2B Edition] の画像アセットのみがサポートされています。 アセットに対する変更は、[!DNL Adobe Experience Manager Assets] central リポジトリから行う必要があります。 [詳細情報](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets){target="_blank"}

### 表示されるリポジトリの変更

複数のAEM リポジトリが接続されている場合は、「**[!UICONTROL リポジトリ]**」のメニュー矢印をクリックして、左側のパネルに表示するリポジトリを選択します。

![AEM Assets リポジトリを選択して画像アセットにアクセスする ](./assets/content-assets-selector-aem-repo.png){width="700" zoomable="yes"}

画像アセットをビジュアルキャンバスに追加するには、複数の方法があります。

### 画像をドラッグ＆ドロップ

1. 左側のパネルに表示されている画像のサムネールを参照します。

1. 画像のサムネールをドラッグし、キャンバス内の新しい画像コンポーネントの追加場所にドロップします。

   ![ 画像アセットをドラッグ&amp;ドロップ ](./assets/content-drag-drop-image-aem-assets.png){width="700" zoomable="yes"}

## 画像の検索と選択

1. 画像コンポーネントをカンバスに追加し、**[!UICONTROL Experience Manager Assets]** をクリックして _[!UICONTROL Assetsを選択]_ ダイアログを開きます。

   ![ 画像コンポーネントのアセットの選択 ](./assets/content-image-component-empty.png){width="600" zoomable="yes"}

1. ダイアログで、使用可能なツールを使用して必要なアセットを見つける画像を選択します。

   * 右上の **[!UICONTROL リポジトリ]** を変更します。

   * 右上の **[!UICONTROL アセットを管理]** をクリックして、別のブラウザータブでAssets リポジトリを開き、AEM Assets management tools を使用します。

   * 右上の _表示タイプ_ セレクターをクリックして、表示を **[!UICONTROL リスト表示]**、**[!UICONTROL グリッド表示]**、**[!UICONTROL ギャラリー表示]**、**[!UICONTROL ウォーターフォール表示]** に変更します。

   * _並べ替え順序_ アイコンをクリックして、並べ替え順序を昇順と降順の間で変更します。

     ![Assetsを選択ダイアログのツールを使用し、画像アセットを検索して選択します ](./assets/content-select-assets-dialog-aem.png){width="700" zoomable="yes"}

   * 「**[!UICONTROL 並べ替え基準]**」メニュー矢印をクリックして、並べ替え条件を **[!UICONTROL 名前]**、**[!UICONTROL サイズ]**、**[!UICONTROL 変更]** に変更します。

   * 左上の _フィルター_ アイコンをクリックし、条件に従って表示される項目をフィルタリングします。

   * 「検索」フィールドにテキストを入力して、表示される項目をアセット名と一致するようにフィルタリングします。

   ![ フィルターと検索フィールドを使用してアセットを検索します ](./assets/content-select-assets-dialog-aem-filter.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 選択]**」をクリックします。
<!-- 

## Upload assets

To import files to Assets as a Cloud Service, you first need to browse or create the folder to be used for storage. You can then import an asset and add it to your email content. After assets are uploaded, you can [use the image assets as you author content](./assets-overview.md#add-assets-to-your-content).

1. While authoring your content in the email designer, drag an image element into the canvas. 

   The properties on the right reflect the image element selection. 

1. Click **[!UICONTROL Import media]** to open the _[!UICONTROL Upload image]_ dialog.

1. If your file system is open to your image file, drag and drop the file on the box in the dialog.

   ![Upload image file to Assets repository](./assets/email-designer-image-upload.png){width="700" zoomable="yes"}

   You can also click the **[!UICONTROL Select a file from your computer]** link and use your file system to locate and select the image file. Click Open and the image file is displayed in the box.

1. Click **[!UICONTROL Import]**.
-->
