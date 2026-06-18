---
title: アセット
description: Journey Optimizer B2B editionで、電子メール、テンプレート、ビジュアルフラグメントの画像アセットを管理できます。
feature: Assets, Content
role: User
badge: label="ベータ版" type="Informative"
autotag-review: '2026-06-18T20:11:57.611Z'
TQID: 'https://experienceleague.adobe.com/Xsl4zqpk4xqXuOS85Z5U08tnbv8GWm3FXdqsegPCBI4'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: e666e996-b2cf-4c45-8fc2-1c625212ababid: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: c8402946-ff35-44c5-ab98-74c1bba0975fid: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 0e90250101eef0572af0382cc7d24bca727d2b75
workflow-type: tm+mt
source-wordcount: 495
ht-degree: 3%

---

# アセット

[!DNL Adobe Journey Optimizer B2B Prime]では、アセットは通常、ジャーニーをサポートするコンテンツを設計する際に使用される画像です。 これらの画像は、メール、メールテンプレート、アセットセレクターのビジュアルフラグメント、またはビジュアルデザイン空間でのシンプルなドラッグ&amp;ドロップインターフェイスで使用できます。

サポートされているファイル形式：JPG、JPEG、GIF、PNG、EPS、SVG、RGB


>>
Marketo Engage DAMなどの外部システムからのアセットの読み込みと、事前入力されたアセットライブラリへのアクセスはまだ利用できません。 今後のリリースには、既存システムからのアセットのインポート、フォルダーサポート、拡張されたアセット管理機能が含まれる予定です。

<!-- You can [edit these assets using Adobe Express](./image-edit-adobe-express.md), and move them into folders to organize them for use across your emails, templates, and fragments. -->

**Assets** ライブラリでは、画像やその他のクリエイティブアセットを保存および管理するための一元化されたリポジトリにアクセスできます。 また、メタデータを自動的に生成し、自然言語での検索を可能にするAIを利用した機能も搭載されています。

左側のナビゲーションで、**[!UICONTROL Content Management]**&#x200B;を展開し、**[!UICONTROL Assets]**&#x200B;を選択します。

>[!NOTE]
>
>このBeta リリースでは、Marketo Engage アセットライブラリの1回限りのコピーから、画像とアセットをメールキャンバス内で直接選択できます。 また、_[!UICONTROL Assets]_ ライブラリまたはコンテンツデザインスペースから追加の画像アセットをアップロードすることもできます。 これらのアップロードされたアセットは、[!DNL Adobe Journey Optimizer B2B Prime] インスタンスでのみ使用できます。

![Assets library](./assets/dam-asset-library-list-view.png){width="800" zoomable="yes"}

>[!BEGINSHADEBOX]

_[!UICONTROL Assets]_ ライブラリに初めてアクセスする場合は、_[!UICONTROL 生成AI利用条件]_&#x200B;を確認し、**[!UICONTROL 同意して続行]**&#x200B;をクリックします。

![Assets library](./assets/dam-asset-library-gen-ai-agree.png){width="500"}

>[!ENDSHADEBOX]

ライブラリでは、次の2つのレイアウトオプションをサポートしています。

* **[!UICONTROL リスト]** — _リストビュー_ （![ リストビューアイコン ](../../assets/do-not-localize/icon-falco-list-view.svg)）アイコンをクリックすると、メタデータ列を含む並べ替え可能なテーブルにアセットが表示されます。
* **[!UICONTROL ギャラリー]** — _ギャラリービュー_ （![ ギャラリービューアイコン ](../../assets/do-not-localize/icon-falco-gallery-view.svg)）アイコンをクリックすると、アセットが視覚的なサムネールグリッドとして表示されます。

## アセットの検索 {#find-assets}

_[!UICONTROL 検索]_ フィールドを使用して、必要なアセットを自然言語で記述してアセットを検索します。 検索結果は、AIが生成したメタデータにもとづいているため、ファイル名で検索する場合に限りません。

**例：**

* `team members`
* `nature`
* `exercise`

![Assets ライブラリの検索結果から選択した画像](./assets/dam-asset-library-select-image.png){width="700" zoomable="yes"}

## アセットの詳細を表示 {#view-details}

アセットを選択して詳細ビューを開きます。 詳細ビューには、AIが生成した説明、タグとキーワード、その他のメタデータフィールドが表示されます。 この情報は、アセットがアップロードされたときに自動的に生成されます。

リストまたはギャラリー表示でアセットを選択すると、右側の詳細ビューが開きます。 「AI メタデータ」タブを選択して、AIが生成した説明、タグ、メタデータを表示します。

![Assets ライブラリの検索結果から選択した画像](./assets/dam-asset-library-select-image-metadata.png){width="700" zoomable="yes"}

## アセットのアップロード {#upload}

1. 右上の「**[!UICONTROL アップロード]**」をクリックします。

1. ダイアログで、ローカルシステムからファイルをドラッグ&amp;ドロップします。

   ![画像アセットをアップロード ](./assets/dam-upload-assets-dialog.png){width="450"}

   または、**[!UICONTROL コンピューターからファイルを選択]**&#x200B;をクリックして、ローカルファイルシステムを使用してファイルを検索して選択することもできます。

1. 「**[!UICONTROL ファイルをアップロード]**」をクリックして、ファイルを確認し、リポジトリにアップロードします。

アップロードが完了すると、システムは自動的に説明を生成し、タグとキーワードを割り当て、被写体や設定などの視覚属性を抽出します。 手作業によるタグ付けは必要ありません。 このプロセスが完了するまで、新しい画像は&#x200B;_[!UICONTROL 処理中]_&#x200B;のステータスで表示されます。

![処理中の新しい画像アセット ](./assets/dam-asset-library-upload-processing.png){width="700" zoomable="yes"}
<!-- -->
