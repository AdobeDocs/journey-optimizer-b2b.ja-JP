---
title: Forms設定
description: フォームプリセットの設定方法について説明します。
feature: Setup, Channels
role: Admin
autotag-review: '2026-05-27T16:06:59.553Z'
TQID: 'https://experienceleague.adobe.com/GFW5SZ5Z-phoEIE6jTVD7EgwcT1Vx647mjoLXJejbFg'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 955fac784a8f438ec2f9aaf66e9aaeefda58e2a7
workflow-type: tm+mt
source-wordcount: 542
ht-degree: 16%

---

# Forms設定

マーケターがランディングページで使用するフォームを[作成して公開する](../content/forms.md)前に、製品管理者が1つ以上の専用プリセットを作成する必要があります。 各プリセットは、フォーム送信データの送信に使用される接続エンドポイントと、キャプチャしたデータの保存に使用されるデータセットを定義します。

データがストリーミングエンドポイントに到達すると、データセット情報にリンクされます。 生成されたソース／ターゲット接続とソースフローを使用すると、データがデータセットにプッシュされます。

>[!BEGINSHADEBOX]

## 前提条件

Web フォームを使用するには、Adobe Experience Platformで1つ以上の&#x200B;_&#x200B;**HTTP API ストリーミング接続**&#x200B;_&#x200B;を定義する必要があります。 使用する各接続が次の要件を満たしていることを確認します。

* データ型はXDMに設定する必要があります（Raw データではありません）
* 認証は無効にする必要があります（認証されていない接続）

ストリーミングソース接続の作成について詳しくは、[_Experience Platform ドキュメント_](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/streaming/http)を参照してください。

Journey Optimizer B2B editionのForms チャネル設定には、次の[権限](../admin/user-management.md#b2b-product-permissions)が必要です。

* _[!UICONTROL B2B チャネル設定]_ > _[!UICONTROL Forms プリセットの表示]_ - フォーム プリセット設定の表示に必要です。
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Forms プリセットの管理]_ - フォームプリセット設定の作成、更新、削除に必要です。
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Forms プリセットの公開]_ - フォームプリセット設定の公開に必要です。

>[!ENDSHADEBOX]

## フォームプリセット設定のガイドライン

プリセットの作成時：

* データセットとストリーミング接続の異なる組み合わせを使用して、複数のプリセットを設定できます。

* 複数のプリセットで同じデータセットまたはストリーミング接続を再利用できます。

* 各ストリーミング接続は、次のようなリソースを自動的に生成します。

   * _ソース接続_ - データの発生元。
   * _ターゲット接続_ - データが保存または使用される場所。
   * _Source フロー_ - ソース接続からExperience Platformにデータを移動するパイプライン。 マッピング、変換、検証を処理します。

## フォームプリセットを作成

1. 左側のナビゲーションで、**[!UICONTROL 管理]** > **[!UICONTROL チャネル]**&#x200B;に移動します。

1. ナビゲーションパネルの&#x200B;_[!UICONTROL フォーム設定]_&#x200B;で、**[!UICONTROL フォームプリセット]**&#x200B;を選択します。

   ![&#x200B; フォーム設定にアクセス &#x200B;](./assets/config-channels-forms.png){width="800" zoomable="yes"}

1. 「**[!UICONTROL フォームプリセットを作成]**」をクリックします。

1. 設定に一意の&#x200B;**[!UICONTROL 名前]** （必須）と&#x200B;**[!UICONTROL 説明]** （オプション）を入力します。

   >[!NOTE]
   >
   >名前は文字（A ～ Z）で始める必要があり、英数字のみを含めることができます。 アンダースコア `_`、ドット `.`、ハイフン `-`文字も使用できます。

1. **[!UICONTROL ストリーミング接続]**&#x200B;を選択します。

   この接続は、web ビューアがフォームを送信するときにデータを送信するために使用されるストリーミングエンドポイントです。 必要なストリーミング接続がリストに表示されない場合は、要件が満たされていることを確認します。

1. _データセットを選択_ （![&#x200B; データセットを選択アイコン &#x200B;](../assets/do-not-localize/icon-select-data.svg)）アイコンをクリックして、データセットをフォームにリンクします。

   データセットは、フォームの応答が保存され、反映される場所です。 特定のデータセットを検索するためのテキスト文字列を入力するか、リストから選択できます。

   ![&#x200B; データセットを選択ダイアログ &#x200B;](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"}

   >[!NOTE]
   >
   >現在、選択できるのは、プロファイルが有効な[Adobe Experience Platform データセット &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview)とプロファイルが無効なデータセットのみです。 一度に 1 つのデータセットを選択できます。 フォームデータの保存にシステムデータセットを使用することはできません。

   データセットのチェックボックスを選択し、**[!UICONTROL 選択]**&#x200B;をクリックします。

1. 「**[!UICONTROL ドラフトとして保存]**」をクリックします。

## フォームプリセットの公開

1. フォームプリセット名をクリックして、設定ページを開きます。

   必要に応じて、ドラフトを調整できます。

1. 「**[!UICONTROL 公開]**」をクリックします。

   フォームプリセットが&#x200B;_公開済み_ ステータスで一覧表示されている場合、フォーム作成に使用できます。
