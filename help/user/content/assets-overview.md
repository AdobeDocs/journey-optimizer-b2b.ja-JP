---
title: アセット
description: Journey Optimizer B2B editionでのアセット管理について説明します。
feature: Assets, Content
exl-id: f3848e65-3196-4d1f-90cf-7aa6ceeafabb
source-git-commit: 23fb478712f3c6df59e94432bdf16883e6acf70b
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 2%

---

# アセット

Adobe Journey Optimizer B2B editionでは、アセットは通常、ジャーニーコンテンツの作成に使用される画像です。 これらの画像は、アセットセレクターまたはビジュアルコンテンツエディター内のシンプルなドラッグ&amp;ドロップインターフェイスを使用して、Journey Optimizer B2B editionで作成されたメール、メールテンプレートおよびフラグメント内で使用できます。

Adobe Journey Optimizer B2B editionを使用すると、マーケターはAdobe Marketo Engage Design Studio とAdobe Experience Manager Assetsas a Cloud Serviceの 2 種類のアセットライブラリにアクセスできます。 Adobe Marketo Engage Design Studio のみを使用するか、（お持ちのAEM Assets ライセンスに基づいて）同時に設定された両方のライブラリを使用することができます。

## アセット管理

Marketo EngageアカウントとAdobe Experience Manager as aCloud Serviceがプロビジョニングされている場合、ユーザーアカウントに必要な権限があれば、Marketo Engage DAM とAdobe Experience Manager Assetsの両方のリポジトリにas a Cloud Service的にアクセスできます。 これらのリポジトリは個別に存在し、同期していません。どちらのソースの画像も使用できますが、コンテンツエディターで一度に有効にできる画像は 1 つだけです。 管理者は、Marketo EngageDAM からAdobe Experience Manager Assetsへの切り替えをas a Cloud Serviceにすることができます。 左側のナビゲーションの ]_0}Assets} 項目には、現在設定されているリポジトリーが表示されます。_[!UICONTROL 

### Adobe Marketo Engage assets

Adobe Marketo Engage Design Studio のアセットリポジトリは、Journey Optimizer B2B editionのすべてのサブスクリプションでデフォルトで提供されます。 つまり、Adobe Marketo Engage/[!UICONTROL Design Studio]/[!UICONTROL  画像とファイル ] に保存されている任意の画像アセットにアクセスできます。 このリポジトリは、アセットのアップロード機能やダウンロード機能を含め、ローカルアセットライブラリとして使用できます。 また、これらのアセットをジャーニーコンテンツ内で使用することもできます。

Journey Optimizer B2B editionからMarketo Engageアセットに編集を加えたり、削除や移動を行ったりするのを防ぐ組み込みのガードレールがあります。 これらの保護機能により、ソースアセット（Marketo Engageデザインスタジオ）が維持されると同時に、Journey Optimizer B2B editionでシームレスな読み取りと再利用が可能になります。

サポートされているファイル形式：JPG、JPEG、GIF、PNG、EPS、SVG、RGB

### Adobe Experience Manager Assetsas a Cloud Service

Adobe Experience Manager Assetsを使用してマーケティングワークフローとクリエイティブワークフローを統合します。 Adobe Journey Optimizer B2B editionとネイティブに統合されているので、Assetsas a Cloud Serviceに簡単にアクセスして、デジタルアセットを検出して使用できます。 メッセージの入力に使用できるアセットのAssets リポジトリへのアクセスを提供します。

Adobe Experience Manager AssetsはAdobe Experience Manager Assetsas a Cloud Serviceに接続して、クリエイティブシステムを拡張しエクスペリエンス配信のためにデジタルアセットを統合する、一元的なアセットワークスペースを実現できます。 Adobe Experience Manager Assetsas a Cloud Serviceは、デジタルアセット管理およびDynamic Mediaの効率的な運用を実現する、使いやすいクラウドソリューションを提供します。 人工知能や機械学習などの高度な機能がシームレスに組み込まれています。

詳しくは、[Adobe Experience Manager as a Cloud Service ドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-manager-cloud-service/content/assets/overview) を参照してください。

Adobe Experience Manager Assetsは、左側のナビゲーションの **[!UICONTROL Assets]** 項目から、Adobe Journey Optimizer B2B edition内で直接アクセスできます。 また、メールコンテンツをデザインする際に、アセットやフォルダーにアクセスすることもできます。

>[!NOTE]
>
>Cloud ServiceとしてのAEM AssetsとDynamic Media ライセンスは、この統合の前提条件です。<br/>
>契約と設定に応じて、Adobe Experience Manager Assetsのas a Cloud Serviceは、左メニューの「Assets」セクションを使用してAdobe Journey Optimizer B2B editionから直接アクセスできます。 また、メールコンテンツをデザインする際に、アセットやフォルダーにアクセスすることもできます。

現在、Adobe Journey Optimizer B2B editionで使用できるのは、Adobe Experience Manager Assets内の画像のみです。

## コンテンツオーサリングへのアセットの使用

アセットを使用して、メール、メールテンプレートおよびビジュアルフラグメントを作成します。 ビジュアルコンテンツエディター UI を使用すると、接続されたアセットリポジトリ内の画像にアクセスできます。

### アセットソースを選択

Experience Manager Assetsas a Cloud ServiceのサブスクリプションにデフォルトのAdobe Marketo Engage Design Studio が含まれている場合は、どちらのソースからも画像アセットを選択できます。 それには、新しいメール、メールテンプレートまたはビジュアルフラグメントの作成時に画像ソースを選択する必要があります。 または、コンテンツの編集時に画像のソースを選択できます。 この選択は、編集エクスペリエンスにのみ適用され、必要に応じて、別のライブラリからアセットにアクセスするように画像ソースを変更できます。

_**コンテンツリソースの作成**_ - メール、メールテンプレートまたはフラグメントの作成時に画像ソースを選択するには、ダイアログで **[!UICONTROL 画像ソース]** を設定します。

_**コンテンツリソースの編集**_ - ビジュアルプレビューで画像アセットソースを選択するには、右側のパネルにある **[!UICONTROL 画像ソース]** 設定を使用します。

### コンテンツへのアセットの追加

選択した画像アセットソースに応じて、コンテンツの作成時に画像アセットを追加できます。

>[!BEGINTABS]

>[!TAB Marketo Engage画像アセットの追加 ]

Marketo Engageアセットを追加するには、次のいずれかの方法を使用します。

* 構造要素を追加し、左のナビゲーションからビジュアルキャンバスにアセットをドラッグ&amp;ドロップします。
* 構造要素を追加し、_image_ コンテンツタイプを構造にドラッグ&amp;ドロップします。 右側のプロパティ設定では、画像を指定する方法が 2 つあります。
   * **[!UICONTROL 参照]** をクリックしてアセットセレクターを開くと、Adobe Marketo Engage Design Studio のアセットライブラリから画像を選択できます。
   * **[!UICONTROL メディアを読み込み]** をクリックして、ローカルシステムからアセットを読み込みます。 読み込まれたアセットは、Adobe Marketo Engage Design Studio ライブラリのAssets ルートフォルダー内に保存されます。

詳しくは [ コンテンツでのアセットの使用 ](./marketo-engage-design-studio.md#use-assets-in-your-content) を参照してください。

画像を変更するには、右側のプロパティで画像のソース URL を更新します。

>[!TAB Experience Manager Assets画像の追加 ]

1. メールデザイナーでメールコンテンツを作成する際に、画像要素をキャンバスにドラッグします。

   右側のプロパティには、画像要素の選択が反映されます。

1. **[!UICONTROL アセットを選択]** をクリックして、Experience Managerアセットセレクターを開きます。

   ここで、目的のコンテンツアセットを検索、フィルタリングおよびアクセスして、マーケティングアセットに追加できます。 セレクターの使用方法について詳しくは、このページを参照してください。

   >[!NOTE]
   >
   >複数のリポジトリが設定されている場合は、アセットセレクターのリポジトリスイッチャーを使用できます

1. メールに挿入するアセットを選択します。

>[!ENDTABS]
