---
title: Experience Manager Assets の操作
description: コンテンツ編集でAEM Assetsの画像にアクセスして利用 – Journey Optimizer B2B editionで変更内容をドラッグ&ドロップ、検索、フィルタリング、同期できます。
feature: Assets, Content, Integrations
role: User
exl-id: c6864981-209c-4123-8d3f-24deb07026a0
source-git-commit: 8073984ced07e86a3fa500c5bf0bd393abbe0990
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 2%

---

# Experience Manager アセットの操作

[!DNL Adobe Experience Manager Assets as a Cloud Service]が[!DNL Adobe Journey Optimizer B2B Edition]と統合されている場合、マーケティングコンテンツで使用するデジタルアセットを簡単に見つけてアクセスできます。 コンテンツを作成すると、左側のナビゲーションの&#x200B;_[!UICONTROL Experience Manager Assets]_&#x200B;項目からアセットにアクセスでき、アカウントジャーニーのメールコンテンツをオーサリングする場合にもアクセスできます。

{{aem-assets-licensing-note}}

これらのデジタルアセットを使用すると、リンクされた参照を通じて、[!DNL Assets as a Cloud Service]の最新の変更がライブメールキャンペーンに自動的に反映されます。 [!DNL Adobe Experience Manager Assets as a Cloud Service]で画像が削除された場合、画像は壊れた参照でメールに表示されます。 アカウントジャーニー内で現在使用されているアセットが変更または削除されると、ジャーニー作成者に対して、画像の変更と画像を使用したジャーニーのリストが通知されます。 アセットへのすべての変更は、[!DNL Adobe Experience Manager Assets]中央リポジトリで行う必要があります。

環境に1つ以上の[Assets repositories connections](../admin/configure-aem-repositories.md)がある場合、コンテンツ作成者は、メール、メールテンプレート、ビジュアルフラグメントを作成する際に、アセットのソースとして[!DNL Experience Manager Assets]を使用できます。

>[!IMPORTANT]
>
>管理者は、Assetsにアクセスする必要があるユーザーを、Assets コンシューマーユーザーまたはAssets ユーザーの製品プロファイルに追加する必要があります。 [詳細情報](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/security/ims-support#managing-products-and-user-access-in-admin-console){target="_blank"}

## AEM Assetsの画像へのアクセス

コンテンツデザイン領域で、左側のサイドバーにある&#x200B;_[!UICONTROL Experience Manager Assets]_ （![Experience Manager Assets アイコン ](../../assets/do-not-localize/icon-assets-aem.svg)）アイコンをクリックします。 これにより、ツールパネルが、選択したリポジトリ内の使用可能なアセットのリストに変更されます。

![Assets セレクターアイコンをクリックして、画像アセットにアクセスします](./assets/content-assets-selector-aem-assets.png){width="700" zoomable="yes"}

>[!NOTE]
>
>現在、[!DNL Adobe Experience Manager Assets]の画像アセットのみが[!DNL Adobe Journey Optimizer B2B Edition]でサポートされています。 アセットの変更は、[!DNL Adobe Experience Manager Assets]中央リポジトリから行う必要があります。 [詳細情報](https://experienceleague.adobe.com/en/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets){target="_blank"}

### 表示されたリポジトリを変更する

複数の接続されたAEM リポジトリがある場合は、**[!UICONTROL リポジトリ]**&#x200B;のメニュー矢印をクリックして、左側のパネルに表示するリポジトリを選択します。

![画像アセットにアクセスするには、AEM Assets リポジトリを選択してください](./assets/content-assets-selector-aem-repo.png){width="700" zoomable="yes"}

ビジュアルキャンバスに画像アセットを追加する方法は複数あります。

### 画像をドラッグ＆ドロップ

1. 左側のパネルに表示されている画像のサムネールを参照します。

1. 画像のサムネールをドラッグし、新しい画像コンポーネントを追加する場所にキャンバスにドロップします。

   ![画像アセットをドラッグ&amp;ドロップ ](./assets/content-drag-drop-image-aem-assets.png){width="700" zoomable="yes"}

## 画像の検索と選択

1. 画像コンポーネントをカンバスに追加し、**[!UICONTROL Experience Manager Assets]**&#x200B;をクリックして&#x200B;_[!UICONTROL Assetsを選択]_ ダイアログを開きます。

   ![画像コンポーネントのアセットを選択](./assets/content-image-component-empty.png){width="600" zoomable="yes"}

1. ダイアログから、使用可能なツールを使用して画像を選択し、必要なアセットを見つけます。

   * 右上の&#x200B;**[!UICONTROL リポジトリ]**&#x200B;を変更します。

   * 右上の&#x200B;**[!UICONTROL アセットの管理]**&#x200B;をクリックして、別のブラウザータブでAssets リポジトリを開き、AEM Assets管理ツールを使用します。

   * 右上の&#x200B;_表示タイプ_ セレクターをクリックして、表示を&#x200B;**[!UICONTROL リストビュー]**、**[!UICONTROL グリッドビュー]**、**[!UICONTROL ギャラリービュー]**、または&#x200B;**[!UICONTROL ウォーターフォールビュー]**&#x200B;に変更します。

   * 「_並べ替え順序_」アイコンをクリックして、並べ替え順序を昇順と降順で変更します。

     ![Assetsを選択ダイアログのツールを使用して、画像アセットを検索して選択する](./assets/content-select-assets-dialog-aem.png){width="700" zoomable="yes"}

   * 「**[!UICONTROL 並べ替え]**」メニューの矢印をクリックして、並べ替え条件を&#x200B;**[!UICONTROL 名前]**、**[!UICONTROL サイズ]**、または&#x200B;**[!UICONTROL 変更]**&#x200B;に変更します。

   * 左上の&#x200B;_フィルター_ アイコンをクリックして、条件に従って表示される項目をフィルタリングします。

   * 検索フィールドにテキストを入力して、アセット名に一致するアセットの表示アイテムをフィルタリングします。

   ![ フィルターと検索フィールドを使用してアセットを検索](./assets/content-select-assets-dialog-aem-filter.png){width="700" zoomable="yes"}

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
