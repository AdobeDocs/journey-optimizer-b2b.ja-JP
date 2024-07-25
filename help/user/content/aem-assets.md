---
title: Experience Manager Assets の操作
description: Adobe Journey Optimizer B2B Edition でコンテンツをオーサリングする際に、接続されたAEM Assets リポジトリの画像アセットを使用する方法について説明します。
feature: Assets, Content
exl-id: c6864981-209c-4123-8d3f-24deb07026a0
source-git-commit: 7103e4f6666482a72511661dfaed1392d4eb16b1
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 1%

---

# Experience Managerアセットの操作

Adobe Experience Manager Assetsのas a Cloud ServiceをAdobe Journey Optimizer B2B Edition と統合すると、マーケティングコンテンツで使用するデジタルアセットを簡単に見つけてアクセスできます。 コンテンツを作成する際には、左側のナビゲーションの _[!UICONTROL Assets]_ 項目から、またアカウントジャーニーのメールコンテンツを作成する際に、アセットにアクセスできます。 また、Adobe Journey Optimizer B2B Edition から直接、Connected AEM Assetsのas a Cloud Serviceリポジトリにアセットをアップロードすることもできます。

>[!NOTE]
>
>現在、Adobe Journey Optimizer B2B Edition では、Adobe Experience Manager Assetsの画像アセットのみがサポートされています。 アセットに対する変更は、Adobe Experience Manager Assets中央リポジトリから行う必要があります。 [詳細情報](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets)

これらのデジタルアセットを使用すると、Assetsのas a Cloud Serviceの最新の変更が、リンクされた参照を通じてライブメールキャンペーンに自動的に反映されます。 Adobe Experience Manager Assetsのas a Cloud Serviceで画像を削除すると、メール内の参照が壊れて画像が表示されます。 現在アカウントジャーニー内で使用されているアセットが変更または削除されると、画像の変更とその画像を使用しているジャーニーのリストがジャーニー作成者に通知されます。 アセットに対するすべての変更は、Adobe Experience Manager Assets中央リポジトリで行う必要があります。

## AEM Assetsを画像ソースとして使用

お使いの環境に 1 つ以上の [Assets リポジトリ接続 ](../admin/configure-aem-repositories.md) がある場合、メール、メールテンプレートまたはビジュアルフラグメントの詳細を作成または表示する際に、AEM Assetsをアセットのソースとして指定できます。

* 新しいコンテンツを作成する場合は、ダイアログで `AEM Assets` を **[!UICONTROL Image Source]** 項目として選択します。

  ![ 作成ダイアログで画像のソースとしてAEM Assetsを選択する ](./assets/create-dialog-aem-assets.png){width="400"}

* 既存のコンテンツリソースを開く場合は、右側の _[!UICONTROL 本文]_ パネルで `AEM Assets` を選択します。

  ![ プロパティで画像のソースとしてAEM Assetsを選択する ](./assets/content-source-aem-assets.png){width="700" zoomable="yes"}

## オーサリング用アセットへのアクセス

>[!IMPORTANT]
>
>管理者は、Assetsへのアクセスを必要とするユーザーをAssets Consumer Users または/およびAssets Users 製品プロファイルに追加する必要があります。 [詳細情報](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/security/ims-support#managing-products-and-user-access-in-admin-console)

ビジュアルコンテンツエディターで、左側のサイドバーにある _アセットセレクター_ アイコンをクリックします。 これにより、ツールパネルが、選択したリポジトリで使用可能なアセットのリストに変更されます。

![Assets セレクターアイコンをクリックして、画像アセットにアクセスする ](./assets/content-assets-selector-aem-assets.png){width="700" zoomable="yes"}

複数のAEM リポジトリが接続されている場合は、「**[!UICONTROL リポジトリ]**」のメニュー矢印をクリックして、使用するリポジトリを選択します。

![AEM Assets リポジトリを選択して画像アセットにアクセスする ](./assets/content-assets-selector-aem-repo.png){width="700" zoomable="yes"}

画像アセットをビジュアルキャンバスに追加するには、複数の方法があります。

* 左側のナビゲーションから画像サムネールをドラッグ&amp;ドロップします。

  ![AEM Assets リポジトリを選択して画像アセットにアクセスする ](./assets/content-drag-drop-image-aem-assets.png){width="700" zoomable="yes"}

* キャンバスに画像コンポーネントを追加し、「参照 **[!UICONTROL をクリックして]** Assetsを選択 _[!UICONTROL ダイアログを開き]_ す。

  ダイアログで、選択したリポジトリから画像を選択できます。

  必要なアセットを見つけるのに役立つツールが複数あります。

  ![Assetsを選択ダイアログのツールを使用し、画像アセットを探して選択します ](./assets/content-select-assets-dialog-aem.png){width="700" zoomable="yes"}

   * 右上の **[!UICONTROL リポジトリ]** を変更します。

   * 右上の **[!UICONTROL アセットを管理]** をクリックして、別のブラウザータブでAssets リポジトリを開き、AEM Assets management tools を使用します。

   * 右上の _表示タイプ_ セレクターをクリックして、表示を **[!UICONTROL リスト表示]**、**[!UICONTROL グリッド表示]**、**[!UICONTROL ギャラリー表示]**、**[!UICONTROL ウォーターフォール表示]** に変更します。

   * _並べ替え順序_ アイコンをクリックして、並べ替え順序を昇順と降順の間で変更します。

   * 「**[!UICONTROL 並べ替え基準]**」メニュー矢印をクリックして、並べ替え条件を **[!UICONTROL 名前]**、**[!UICONTROL サイズ]**、**[!UICONTROL 変更]** に変更します。

   * 左上の _フィルター_ アイコンをクリックし、条件に従って表示される項目をフィルタリングします。

   * 「検索」フィールドにテキストを入力して、表示される項目をアセット名と一致するようにフィルタリングします。

  ![ フィルターと検索フィールドを使用してアセットを検索します ](./assets/content-select-assets-dialog-aem-filter.png){width="700" zoomable="yes"}

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
