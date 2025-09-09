---
title: アセット
description: Journey Optimizer B2B editionで、メール、テンプレート、フラグメント用にMarketo Engage Design Studio とAEM Assetsの画像アセットを管理します。
feature: Assets, Content
role: User
exl-id: f3848e65-3196-4d1f-90cf-7aa6ceeafabb
source-git-commit: 79012352c3ae4e2f3d38b632b1f523d262f74f96
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 46%

---

# アセット

[!DNL Adobe Journey Optimizer B2B Edition] では、アセットは通常、アカウントジャーニーをサポートするためにコンテンツを設計する際に使用される画像です。 これらの画像をメール、メールテンプレートおよびフラグメント内でアセットセレクターから、またはビジュアルデザインスペース内のシンプルなドラッグ&amp;ドロップインターフェイスから使用できます。

[!DNL Journey Optimizer B2B Edition] では、マーケターは [!DNL Adobe Marketo Engage] [!DNL Design Studio] と [!DNL Adobe Experience Manager Assets as a Cloud Service] の 2 種類のアセットライブラリにアクセスできます。 Adobe Marketo Engage Design Studio のみを使用する場合や、（お持ちの [!DNL Experience Manager Assets] ライセンスに基づいて）同時に設定した両方のライブラリを使用する場合があります。

## アセット管理

[!DNL Adobe Experience Manager as a Cloud Services] のプロビジョニングが行われている場合、ユーザーアカウントに必要な権限があれば、[!DNL Marketo Engage Design Studio] と [!DNL Adobe Experience Manager Assets as a Cloud Service] の両方のリポジトリにアクセスできます。 これらのリポジトリは個別に存在し、同期していません。どちらのソースからも画像を使用できます。

### Adobe Marketo Engage アセット

[!DNL Adobe Marketo Engage Design Studio] Assets リポジトリは、[!DNL Journey Optimizer B2B Edition] サブスクリプションごとにデフォルトで提供されます。 つまり、[!DNL Adobe Marketo Engage] に保存されている任意の画像アセット（[!UICONTROL Design Studio]/[!UICONTROL  画像とファイル ]）にアクセスできます。 このリポジトリは、アセットのアップロードやダウンロード機能を含むローカルアセットライブラリとして使用できます。また、これらのアセットをジャーニーコンテンツ内で使用することもできます。

[!DNL Marketo Engage] アセットに対する編集、削除および移動操作を防ぐ組み込みのガードレールが [!DNL Journey Optimizer B2B Edition] ります。 これらの保護機能により、ソースアセット（Marketo Engage Design Studio）が維持されると同時に、[!DNL Journey Optimizer B2B Edition] でシームレスに読み取りと再利用が可能になります。

サポートされているファイル形式：JPG、JPEG、GIF、PNG、EPS、SVG、RGB

### Adobe Experience Manager Assets as a Cloud Service

[!DNL Adobe Experience Manager Assets] を使用してマーケティングワークフローとクリエイティブワークフローを統合します。[!DNL Journey Optimizer B2B Edition] とネイティブに統合されているので、Assets as a Cloud Serviceに簡単にアクセスして、デジタルアセットを検出して使用できます。 メッセージの入力に使用できるアセットの Assets リポジトリへのアクセスを提供します。

[!DNL Adobe Journey Optimizer B2B Edition] に接続 [!DNL Adobe Experience Manager Assets as a Cloud Service] ると、クリエイティブシステムを拡張してデジタルアセットをエクスペリエンス配信に統合し、一元的なアセット管理を行うことができます。 [!DNL Adobe Experience Manager Assets as a Cloud Service] は、デジタルアセット管理と Dynamic Media 操作を効率的に行うための使いやすいクラウドソリューションを提供します。 人工知能や機械学習などの高度な機能がシームレスに組み込まれています。

詳しくは、[Adobe Experience Manager Assets as a Cloud Service ドキュメント](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/overview){target="_blank"}を参照してください。

{{aem-assets-licensing-note}}

コンテンツデザインの左側のナビゲーションの [!DNL Adobe Experience Manager Assets]Experience Manager Assets[!DNL Journey Optimizer B2B Edition] 項目から、**[!UICONTROL 内の]** に直接アクセスします。 また、メール、メールテンプレート、ビジュアルフラグメントコンテンツを設計する際に、アセットとフォルダーにアクセスすることもできます。

現在、Adobe Journey Optimizer B2B Edition では、Adobe Experience Manager Assets の画像のみを使用できます。

## コンテンツオーサリングへのアセットの使用

メール、メールテンプレート、ビジュアルフラグメントを作成する際にアセットを使用します。ビジュアルコンテンツエディターを使用すると、接続されたアセットリポジトリ内の画像にアクセスできます。デフォルトの Adobe Marketo Engage Design Studio ト共に Experience Manager Assets as a Cloud Service のサブスクリプションを使用している場合は、どちらのソースからでも画像アセットを選択できます。また、画像アセットをアップロードして、接続された [!DNL Journey Optimizer B2B Edition] リポジトリの [!DNL Marketo Engage Design Studio] ワークスペースに配置することもできます。

画像コンポーネントの設定を編集するとき、またはキャンバス上で直接編集するとき、画像ソースを選択することができます。

* **_画像コンポーネント設定_** - ビジュアルデザインスペースで画像コンポーネントを選択すると、右側のパネルで設定を表示して編集できます。 コンポーネントに表示される画像ファイルを追加または変更するには、ソースタイプを選択し、画像ファイルを選択します。

  ![右側のパネルで画像コンポーネントの設定を編集](./assets/content-assets-image-settings.png){width="350"}

* **_空のコンポーネント_** - ビジュアルデザインスペースで画像コンポーネントを追加すると、コンポーネントは空になり、ソースを選択したり画像ファイルを選択したりするのに簡単にアクセスできます。

  ![ソースを選択して、空の画像コンポーネントの画像ファイルを選択](./assets/content-assets-image-component-empty.png){width="500"}

* **_画像コンポーネントツールバー_** - ビジュアルデザインスペースで画像コンポーネントを選択すると、ツールバーを使用してソースを選択し、画像ファイルを選択することができます。

  ![ツールバーを使用し、ソースを選択して、画像コンポーネントの画像ファイルを選択](./assets/content-assets-image-toolbar-settings.png){width="500"}

画像アセットのソースに応じて、コンテンツの作成時に画像アセットを追加できます。 構造コンポーネントのバックグラウンド設定で画像アセットを選択することもできます。

>[!BEGINTABS]

>[!TAB Marketo Engage アセット]

**[!UICONTROL Marketo Engage Assets]** をクリックして、アセットセレクターを開きます。ここで、[!DNL Marketo Engage] ワークスペースまたはJourney Optimizer B2B edition ワークスペースから画像を選択できます。

![ワークスペースから画像アセットを選択](./assets/content-assets-image-me-selected.png){width="700" zoomable="yes"}

検索とフィルターを使用して、目的の画像アセットを見つけることができます。アセットを選択し、「**[!UICONTROL 選択]**」をクリックして、画像コンポーネントに使用します。

画像アセットの使用について詳 [!DNL Marketo Engage] くは、[ コンテンツでアセットを使用 ](./marketo-engage-design-studio.md#use-assets-in-your-content) を参照してください。

>[!TAB Experience Manager Assets]

「**[!UICONTROL Experience Manager Assets]**」をクリックするとアセットセレクターが開き、Experience Manage Assets リポジトリから画像を選択できます。

![AEM Assets リポジトリから画像アセットを選択](./assets/content-assets-image-aem-selected.png){width="700" zoomable="yes"}

検索とフィルターを使用して、目的の画像アセットを見つけることができます。アセットを選択し、「**[!UICONTROL 選択]**」をクリックして、画像コンポーネントに使用します。

[!DNL Experience Manager Assets] の画像ファイルの使用について詳しくは、「[AEM Assets画像へのアクセス ](./aem-assets.md#access-aem-assets-images) を参照してください。

>[!TAB メディアを読み込み]

「**[!UICONTROL メディアを読み込み]**」をクリックして画像ファイルを選択し、Journey Optimizer B2B Edition コンテンツに使用できるアセットとして読み込みます。

![アセットとして読み込む独自の画像ファイルを選択](./assets/content-assets-image-import-file-selected.png){width="500" zoomable="yes"}

ファイルをドラッグ＆ドロップするか、ファイルシステムから選択したら、「**[!UICONTROL 読み込み]**」をクリックします。読み込まれたアセットは、[!DNL Journey Optimizer B2B Edition] リポジトリの [!DNL Adobe Marketo Engage Design Studio] ワークスペースに保存されます。

>[!ENDTABS]
