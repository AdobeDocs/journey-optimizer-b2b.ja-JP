---
title: 生成AI モデル
description: マーケターがメールやランディングページコンテンツの画像を生成するために選択できる生成AI画像モデルを作成、管理します。
topic: Artificial Intelligence
feature: Generative AI, Brand Identity, Content
role: User
level: Beginner, Intermediate
source-git-commit: 0612c3caa0673a7eb65a0aac0010edcf12c5d553
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 0%

---

# ブランド整合を実現する生成AI モデル

組み込みモデル、カスタム Firefly モデル、サードパーティの画像生成プロバイダーなど、AI画像作成機能を拡張して、特定のニーズに対応し、ブランドの整合性を向上させます。

- Firefly Image Model 4を搭載した&#x200B;**[!UICONTROL Adobe モデル]**&#x200B;は、標準装備で、追加設定なしで即座に画像を生成できます。
- Gemini 2.5 Flashを搭載した&#x200B;**[!UICONTROL パートナーモデル]**&#x200B;は、特定のユースケースに特化した機能を提供します。
- **[!UICONTROL カスタムモデル]**&#x200B;は、自社のアセットでトレーニングし、自社が追加したブランド固有のモデルです。

カスタムモデルについて詳しくは、[Adobe Firefly ドキュメント &#x200B;](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/custom-models-overview.html){target="_blank"}を参照してください。

マーケターは、メールやランディングページのコンテンツ用の画像を生成する際に、有効な生成モデルのいずれかを選択できます。

## 生成モデルの管理

一元的に、利用可能なあらゆるモデルを表示し、フィルタリングと検索によって特定のモデルを見つけ出し、ブランドのモデル設定を行うことができます。

1. 左側のナビゲーションで、**[!UICONTROL コンテンツ管理]** > **[!UICONTROL ブランド]**&#x200B;に移動します。

1. ページで、「**[!UICONTROL 生成モデル]**」タブを選択します。

![生成モデルリストにアクセス &#x200B;](./assets/brands-gen-models-list.png){width="800" zoomable="yes"}

### リストをフィルタリングして検索します

_フィルター_ ![&#x200B; フィルターアイコン &#x200B;](../../assets/do-not-localize/icon-react-filter.svg) アイコンをクリックして、フィルターメニューにアクセスします。 **[!UICONTROL Type]**&#x200B;または&#x200B;**[!UICONTROL Status]**&#x200B;でモデルをフィルタリングします。

![生成モデルリストのフィルター](./assets/brands-gen-models-filter.png){width="700" zoomable="yes"}

検索バーを使用して、特定の生成モデルを名前で検索することもできます。

### モデルのアクション

リスト内のカスタムモデルの場合は、_詳細メニュー_ ![詳細メニューアイコン &#x200B;](../../assets/do-not-localize/icon-more-menu.svg) アイコンをクリックします。 **[!UICONTROL 有効]**&#x200B;または&#x200B;**[!UICONTROL 無効]**&#x200B;を選択してモデルの可用性ステータスを変更するか、**[!UICONTROL 削除]**&#x200B;を選択してモデルをリストから削除できます。

![生成モデルリストのその他のメニュー](./assets/brands-gen-models-more-menu.png){width="450"}

組み込みモデルの場合、_有効_ （![有効にするアイコン &#x200B;](../../assets/do-not-localize/icon-enable.svg)）または&#x200B;_無効にする_ （![無効にするアイコン &#x200B;](../../assets/do-not-localize/icon-disable.svg)）アイコンをクリックして、画像生成のモデルの可用性を変更します。

>[!NOTE]
>
>削除できるのはカスタムモデルのみです。

## 生成モデルの追加

カスタムのFireflyモデルを作成するか、サードパーティの画像生成プロバイダーと連携して、生成AIの機能を拡張できます。

>[!NOTE]
>
>カスタム Firefly モデルを作成するには、Firefly ETLA契約書が必要です。

1. 「_[!UICONTROL 生成モデル]_」タブで、「**[!UICONTROL モデルを追加]**」をクリックします。

1. モデルの&#x200B;**[!UICONTROL 名前]**&#x200B;を入力します。

<!-- 1. Select a **[!UICONTROL Model provider]**. future development -->

1. **[!UICONTROL モデル ID]**&#x200B;を入力します。

   モデル IDを見つけるには、Firefly web サイトにアクセスし、トレーニング済みモデルに移動します。 一意のIDは、公開後にモデルの管理セクションで使用できます。 詳しくは、[Firefly カスタムモデルのドキュメント &#x200B;](https://helpx.adobe.com/firefly/web/work-with-enterprise-features/train-custom-models/custom-models-overview.html){target="_blank"}を参照してください。

1. オプションで、**[!UICONTROL 説明]**&#x200B;を入力して、モデルとその意図された使用状況を特定します。

   ![&#x200B; モデルを追加 – 生成モデル &#x200B;](./assets/brands-gen-models-add-model.png){width="550" zoomable="yes"}

1. 「**[!UICONTROL 接続をテスト]**」をクリックして、モデル設定を確認します。

1. 接続テストが成功したら、**[!UICONTROL 保存]**&#x200B;をクリックして、モデル設定を保存します。

   モデルを保存すると生成モデルリストに追加され、マーケターが使用できるようにします。 また、いつでも無効にしたり削除したりすることもできます。

   ![画像生成用の生成モデルの選択](./assets/gen-ai-model-selection.png){width="600" zoomable="yes"}
