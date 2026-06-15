---
title: Formsの設定
description: プレースホルダー
autotag-review: '2026-06-12T22:44:42.084Z'
TQID: 'https://experienceleague.adobe.com/aJKRaYBEdieyIUsuszVy4g2LANEVLQP9aQfhhrKOhx0'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
  - id: d57c4909-c813-470d-ac87-cdd2d6b5f9dc
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ce49389601416e7acefb9f948c052a1d840d8854
workflow-type: tm+mt
source-wordcount: 541
ht-degree: 22%

---

# Forms設定

マーケターがランディングページで使用するフォームを作成して公開するには、事前に1つ以上の専用プリセットを作成する必要があります。 各プリセットは、フォーム送信データの送信に使用される接続エンドポイントと、キャプチャしたデータの保存に使用されるデータセットを定義します。

データがストリーミングエンドポイントに到達すると、データセット情報にリンクされます。 生成されたソース／ターゲット接続とソースフローを使用すると、データがデータセットにプッシュされます。

>[!BEGINSHADEBOX]

## 前提条件

Web フォームを使用するには、Adobe Experience Platformで1つ以上の&#x200B;_&#x200B;**HTTP API ストリーミング接続**&#x200B;_&#x200B;を定義する必要があります。 使用する各接続が次の要件を満たしていることを確認します。

* データ型はXDMに設定する必要があります（Raw データではありません）
* 認証は無効にする必要があります（認証されていない接続）

ストリーミングソース接続の作成について詳しくは、[_Experience Platform ドキュメント_](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/streaming/http)を参照してください。

<!-- 
permissions coming in GA

Forms channel configuration in Journey Optimizer B2B Edition requires the following permissions](../admin/user-management.md#b2b-product-permissions):

* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL View Forms Presets]_ - Required to view forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Manage Forms Presets]_ - Required to create, update, and delete forms preset configurations.
* _[!UICONTROL B2B Channel Configurations]_ > _[!UICONTROL Publish Forms Presets]_ - Required to publish forms preset configurations.
-->

>[!ENDSHADEBOX]

## フォームプリセット設定のガイドライン

プリセットの作成時：

* データセットとストリーミング接続の異なる組み合わせを使用して、複数のプリセットを設定できます。

* 複数のプリセットで同じデータセットまたはストリーミング接続を再利用できます。

* 各ストリーミング接続は、次のようなリソースを自動的に生成します。

   * _ソース接続_ - データの発生元。
   * _ターゲット接続_ - データが保存または使用される場所。
   * _Source フロー_ - ソース接続からExperience Platformにデータを移動するパイプライン。 マッピング、変換、検証を処理します。

## フォームプリセットを作成 {#create-preset}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_connection"
>title="使用するエンドポイントを選択"
>abstract="フォーム送信時にデータが送信されるストリーミングエンドポイントを定義します。"
>additional-url="https://experienceleague.adobe.com/ja/docs/experience-platform/sources/ui-tutorials/create/streaming/http" text="HTTP API ストリーミング接続を作成"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_form_dataset"
>title="データセットを選択"
>abstract="フォームの応答が保存され、反映されるデータセットを定義します。 テキストを入力して特定のデータセットを検索するか、リストから選択します。"

1. 左側のナビゲーションで、**[!UICONTROL 管理]** > **[!UICONTROL チャネル]**&#x200B;に移動します。

1. ナビゲーションパネルの&#x200B;_[!UICONTROL フォーム設定]_&#x200B;で、**[!UICONTROL フォームプリセット]**&#x200B;を選択します。

   <!-- ![Access the form configurations](./assets/config-channels-forms.png){width="800" zoomable="yes"} -->

1. 「**[!UICONTROL フォームプリセットを作成]**」をクリックします。

1. 設定に一意の&#x200B;**[!UICONTROL 名前]** （必須）と&#x200B;**[!UICONTROL 説明]** （オプション）を入力します。

   >[!NOTE]
   >
   >名前は文字（A ～ Z）で始める必要があり、英数字のみを含めることができます。 アンダースコア `_`、ドット `.`、ハイフン `-`文字も使用できます。

1. **[!UICONTROL ストリーミング接続]**&#x200B;を選択します。

   この接続は、web ビューアがフォームを送信するときにデータを送信するために使用されるストリーミングエンドポイントです。 必要なストリーミング接続がリストに表示されない場合は、要件が満たされていることを確認します。

1. _データセットを選択_ （![&#x200B; データセットを選択アイコン &#x200B;](../../user/assets/do-not-localize/icon-select-data.svg)）アイコンをクリックして、データセットをフォームにリンクします。

   データセットは、フォームの応答が保存され、反映される場所です。 特定のデータセットを検索するためのテキスト文字列を入力するか、リストから選択できます。

   <!-- ![Select datasets dialog](./assets/config-channel-forms-select-datasets.png){width="500" zoomable="yes"} -->

   >[!NOTE]
   >
   >現在、選択できるのは、プロファイルが有効な[Adobe Experience Platform データセット &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/catalog/datasets/overview)とプロファイルが無効なデータセットのみです。 一度に1つのデータセットを選択できます。 フォームデータの保存にシステムデータセットを使用することはできません。

   データセットのチェックボックスを選択し、**[!UICONTROL 選択]**&#x200B;をクリックします。

1. 「**[!UICONTROL ドラフトとして保存]**」をクリックします。

## フォームプリセットの公開

1. フォームプリセット名をクリックして、設定ページを開きます。

   必要に応じて、ドラフトを調整できます。

1. 「**[!UICONTROL 公開]**」をクリックします。

   フォームプリセットが&#x200B;_公開済み_ ステータスで一覧表示されている場合、フォーム作成に使用できます。
