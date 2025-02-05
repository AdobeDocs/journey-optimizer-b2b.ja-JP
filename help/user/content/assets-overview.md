---
title: アセット
description: Journey Optimizer B2B editionでのアセット管理について説明します。
feature: Assets, Content
exl-id: f3848e65-3196-4d1f-90cf-7aa6ceeafabb
source-git-commit: 728d5316cfdeee92bd4f67277d299bbec2773a4f
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 2%

---

# アセット

Adobe Journey Optimizer B2B editionでは、アセットは通常、アカウントジャーニーをサポートするコンテンツを設計する際に使用される画像です。 これらの画像をメール、メールテンプレートおよびフラグメント内で使用するには、アセットセレクターや、ビジュアルコンテンツエディター内のシンプルなドラッグ&amp;ドロップインターフェイスを使用します。

Adobe Journey Optimizer B2B editionを使用すると、マーケターはAdobe Marketo Engage Design Studio とAdobe Experience Manager Assetsas a Cloud Serviceの 2 種類のアセットライブラリにアクセスできます。 Adobe Marketo Engage Design Studio のみを使用するか、（お持ちのAEM Assets ライセンスに基づいて）同時に設定された両方のライブラリを使用することができます。

## アセット管理

Adobe Experience Manager as a のCloud Serviceをプロビジョニングしている場合、ユーザーアカウントに必要な権限があれば、Marketo Engage Design Studio とAdobe Experience Manager Assetsの両方のas a Cloud Serviceのリポジトリにアクセスできます。 これらのリポジトリは個別に存在し、同期していません。どちらのソースからも画像を使用できます。

### Adobe Marketo Engage assets

Adobe Marketo Engage Design Studio のアセットリポジトリは、Journey Optimizer B2B editionのすべてのサブスクリプションでデフォルトで提供されます。 つまり、Adobe Marketo Engage（[!UICONTROL Design Studio]/[!UICONTROL Images &amp; Files]）に保存されている任意の画像アセットにアクセスできます。 このリポジトリは、アセットのアップロード機能やダウンロード機能を含め、ローカルアセットライブラリとして使用できます。 また、これらのアセットをジャーニーコンテンツ内で使用することもできます。

Journey Optimizer B2B editionからMarketo Engageアセットに編集を加えたり、削除や移動を行ったりするのを防ぐ組み込みのガードレールがあります。 これらの保護機能により、ソースアセット（Marketo Engageデザインスタジオ）が維持されると同時に、Journey Optimizer B2B editionでシームレスな読み取りと再利用が可能になります。

サポートされているファイル形式：JPG、JPEG、GIF、PNG、EPS、SVG、RGB

### Adobe Experience Manager Assetsas a Cloud Service

Adobe Experience Manager Assetsを使用してマーケティングワークフローとクリエイティブワークフローを統合します。 Adobe Journey Optimizer B2B editionとネイティブに統合されているので、Assetsas a Cloud Serviceに簡単にアクセスして、デジタルアセットを検出して使用できます。 メッセージの入力に使用できるアセットのAssets リポジトリへのアクセスを提供します。

Adobe Journey Optimizer B2B editionはAdobe Experience Manager Assetsas a Cloud Serviceに接続して、クリエイティブシステムを拡張し、エクスペリエンス配信のためのデジタルアセットを統合する、一元的なアセット管理を行うことができます。 Adobe Experience Manager Assetsas a Cloud Serviceは、デジタルアセット管理およびDynamic Mediaの効率的な運用を実現する、使いやすいクラウドソリューションを提供します。 人工知能や機械学習などの高度な機能がシームレスに組み込まれています。

詳しくは、[Adobe Experience Manager as a Cloud Service ドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/overview) を参照してください。

{{aem-assets-licensing-note}}

コンテンツデザインの左側のナビゲーションの **[!UICONTROL Experience Manager Assets]** 項目から、Journey Optimizer B2B edition内のAdobe Experience Manager Assetsに直接アクセスします。 また、メール、メールテンプレートおよびビジュアルフラグメントコンテンツをデザインする際に、アセットやフォルダーにアクセスすることもできます。

現在、Adobe Journey Optimizer B2B editionで使用できるのは、Adobe Experience Manager Assets内の画像のみです。

## コンテンツオーサリングへのアセットの使用

アセットを使用して、メール、メールテンプレートおよびビジュアルフラグメントを作成します。 ビジュアルコンテンツエディターを使用すると、接続されたアセットリポジトリ内の画像にアクセスできます。 Experience Manager Assetsas a Cloud ServiceのサブスクリプションにデフォルトのAdobe Marketo Engage Design Studio が含まれている場合は、どちらのソースからも画像アセットを選択できます。 また、画像アセットをアップロードして、接続されたMarketo Engageの Design Studio リポジトリのJourney Optimizer B2B edition ワークスペースに配置することもできます。

画像コンポーネントの設定を編集するとき、またはキャンバス上で直接編集するとき、画像ソースを選択できます。

* **_画像コンポーネントの設定_** - ビジュアルデザイナーで画像コンポーネントを選択すると、右側のパネルで設定を表示して編集できます。 コンポーネントに表示される画像ファイルを追加または変更するには、ソースタイプを選択して画像ファイルを選択します。

  ![ 右側のパネルで画像コンポーネントの設定を編集します ](./assets/content-assets-image-settings.png){width="350"}

* **_空のコンポーネント_** - ビジュアルデザイナーで画像コンポーネントを追加すると、空になり、ソースを選択したり画像ファイルを選択したりするのに簡単にアクセスできます。

  ![ ソースを選択して、空の画像コンポーネント用の画像ファイルを選択する ](./assets/content-assets-image-component-empty.png){width="500"}

* **_画像コンポーネントツールバー_** - ビジュアルデザイナーで画像コンポーネントを選択すると、ツールバーを使用してソースを簡単に選択し、画像ファイルを選択できます。

  ![ ツールバーを使用して、画像コンポーネントの画像ファイルを選択するソースを選択 ](./assets/content-assets-image-toolbar-settings.png){width="500"}

画像アセットのソースに応じて、コンテンツの作成時に画像アセットを追加できます。

>[!BEGINTABS]

>[!TAB Marketo EngageAssets]

「**[!UICONTROL Marketo EngageAssets]**」をクリックしてアセットセレクターを開き、Marketo Engage ワークスペースまたはJourney Optimizer B2B edition ワークスペースから画像を選択できます。

![ ワークスペースからの画像アセットの選択 ](./assets/content-assets-image-me-selected.png){width="700" zoomable="yes"}

検索とフィルターを使用して、目的の画像アセットを見つけることができます。 アセットを選択し、「**[!UICONTROL 選択]** をクリックして、画像コンポーネントに使用します。

Marketo Engage画像アセットの使用について詳しくは、[ コンテンツでアセットを使用 ](./marketo-engage-design-studio.md#use-assets-in-your-content) を参照してください。

>[!TAB Experience Manager Assets]

**[!UICONTROL Experience Manager Assets]** をクリックして、アセットセレクターを開きます。ここで、Assetsを管理リポジトリーから画像を選択できます。

![AEM Assets リポジトリから画像アセットを選択 ](./assets/content-assets-image-aem-selected.png){width="700" zoomable="yes"}

検索とフィルターを使用して、目的の画像アセットを見つけることができます。 アセットを選択し、「**[!UICONTROL 選択]** をクリックして、画像コンポーネントに使用します。

AEM Assetsの画像ファイルの使用について詳しくは、「[Experience Manager Assets画像へのアクセス ](./aem-assets.md#access-aem-assets-images)」を参照してください。

>[!TAB  メディアのインポート ]

**[!UICONTROL メディアを読み込み]** をクリックして、画像ファイルを選択し、Journey Optimizer B2B editionのコンテンツに使用できるアセットとして読み込みます。

![ アセットとして読み込む独自の画像ファイルを選択する ](./assets/content-assets-image-import-file-selected.png){width="500" zoomable="yes"}

ファイルをドラッグ&amp;ドロップするか、ファイルシステムから選択した後、「**[!UICONTROL インポート]**」をクリックします。 読み込まれたアセットは、Adobe Marketo Engage Design Studio リポジトリのJourney Optimizer B2B edition Workspace に保存されます。

>[!ENDTABS]
