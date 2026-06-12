---
title: ランディングページ
description: アカウントジャーニー向けのランディングページを作成、デザイン、公開します。Journey Optimizer B2B editionでは、ゼロから作成したり、HTMLをインポートしたり、フォームを追加したり、コンテンツをパーソナライズしたり、メールからリンクしたりできます。
feature: Landing Pages, Content
role: User
exl-id: 1a3b4519-e1c0-418a-979a-7ba3e5972edd
autotag-review: '2026-05-27T16:16:24.088Z'
TQID: 'https://experienceleague.adobe.com/zAr9SwPBHxU50gD1ZRdJQo3M-qL-BEO6R1UYq7hSG-8'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2:
  - id: a96755d6-1f54-4f3f-a971-d31f83705ab7
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e9001ce2-5245-4a8e-8601-dd958009072f
source-git-commit: a2443f98ec7a8a5c1d4be2450042e2375f6150b7
workflow-type: tm+mt
source-wordcount: 1637
ht-degree: 2%

---

# ランディングページ

ランディングページとは、電子メール、SMS メッセージ、デジタル位置情報でリンクされたアイテムをクリックした後、連絡先や顧客を誘導できるスタンドアロンのweb ページです。 これらのページをアカウントジャーニーに組み込むことで、見込客や顧客にweb上でメッセージを表示させ、アカウントジャーニーを先に進んでもらうことができます。 ランディングページのビジュアルデザイン機能では、ランディングページを作成、パーソナライズ、プレビューできます。

ランディングページの一般的なユースケース：

* マーケティングコミュニケーションや特定のサービスに対するオプトインやオプトアウトの提供。 電子メールやその他のコミュニケーションで、ターゲットリストへのリンクを使用します。
* コミュニケーションを送信する前に同意を収集し、オプトインまたはオプトアウト時に確認メールを送信します。
* ランディングページでフォームを使用して、プロファイルデータ（プログレッシブプロファイリング、嗜好、登録、類似のシナリオ）を取得または更新します。
* ジャーニーオーケストレーションに合わせて設計された、キャンペーン固有の情報に人物を誘導します。
* Journey Optimizer B2B editionの外部ページを構築することなく、専用のweb フォームにオーディエンスをリダイレクトできます。

## ランディングページワークフロー

ジャーニーオーディエンスのメンバーが特定のリンクをクリックしたときに、定義されたweb ページに誘導するには、Journey Optimizer B2B editionでランディングページを作成します。

1. [&#x200B; ページを作成](./landing-pages-create-publish.md) - プリセットを選択し、プライマリページを設定し、必要なサブページを追加します。
1. [&#x200B; ランディングページのコンテンツをデザイン &#x200B;](./landing-page-design.md) - ドラッグ&amp;ドロップ操作のビジュアルデザインコンポーネントを使用してページコンテンツを作成します。
1. [&#x200B; ランディングページをテストして公開する](./landing-pages-create-publish.md) - ページをプレビューし、フォームの動作をテストしてから、公開して公開します。
1. [&#x200B; ジャーニーからページにリンク &#x200B;](#link-to-a-landing-page) – 受信者がアクセスできるように、ランディングページのURLをメール、SMS、またはジャーニーアクションに追加します。

例えば、ランディングページを作成およびデザインして、オーディエンスをオンライン情報に誘導できます。 このページには、コミュニケーションの受信をオプトインまたはオプトアウトできるフォームが含まれます。 また、ニュースレターなどの定期的なコミュニケーションに登録することもできます。

ビジュアルデザイン空間でランディングページを作成、パーソナライズ、プレビューできます。

## ランディングページへのアクセスと管理

Journey Optimizer B2B editionのランディングページにアクセスするには、左側のナビゲーションに移動し、**[!UICONTROL コンテンツ管理]**/**[!UICONTROL ランディングページ]**&#x200B;をクリックします。 このアクションは、インスタンスで作成されたすべてのランディングページのリストを表示します。

![&#x200B; ランディングページライブラリへのアクセス &#x200B;](./assets/landing-pages-list.png){width="800" zoomable="yes"}

リストは、_[!UICONTROL 変更済み]_&#x200B;列に従って並べ替えられ、最も最近更新された項目が上部に表示されます。 列のタイトルをクリックして、昇順と降順を変更します。

### ランディングページリストのフィルター

ランディングページを名前で検索するには、検索バーにテキスト文字列を入力して一致を検索します。 _フィルター_ アイコン （![&#x200B; フィルターの表示または非表示アイコン &#x200B;](../assets/do-not-localize/icon-filter.svg)）をクリックして、使用可能なフィルターオプションを表示し、設定を変更して、指定した条件に従って表示される項目をフィルタリングします。

![表示されるランディングページをフィルター](./assets/landing-pages-list-filtered.png){width="700" zoomable="yes"}

<!-- 
This is going away? ### Customize the column display

Customize the columns that you want to display in the table by clicking the _Customize table_ icon ( ![Customize table icon](../assets/do-not-localize/icon-column-settings.svg) ) at the top right. 

In the dialog, select the columns to display and click **[!UICONTROL Apply]**.

![Select the columns that you want to display](./assets/landing-pages-customize-table-dialog.png){width="300"} 
-->

### ランディングページのステータスとライフサイクル

ランディングページのステータスによって、電子メールおよびSMS コンテンツ内でのリンクの可用性と、それに対して実行できる変更が決まります。

| ステータス | 説明 |
| -------------------- | ----------- |
| 下書き | ランディングページを作成する場合、そのランディングページはドラフトステータスになります。 ビジュアルコンテンツを定義または編集し、ホストされたページとして公開するまで、このステータスのままになります。 使用可能なアクション：<br/><ul><li>名前または説明を編集<li>リンク URLを編集<li>ビジュアルデザイン空間での編集<li>公開<li>複製<li>削除 |
| 公開日 | ランディングページを公開すると、ランディングページはJourney Optimizer B2B edition インスタンスでホストされ、メールまたはSMS メッセージのコンテンツでリンクできるようになります。 使用可能なアクション：<br/><ul><li>名前または説明を編集<li>リンク URLを編集<li>メールまたはSMS メッセージのコンテンツにリンクを追加する<li>ドラフトバージョンを作成<li>複製<li>削除 |
| 公開済み下書きあり | 公開されたランディングページからドラフトを作成すると、公開されたバージョンは残り、ドラフトコンテンツはビジュアルデザイン空間で変更できます。 ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツはホストされているページで更新されます。 使用可能なアクション：<br/><ul><li>名前または説明を編集<li>リンク URLを編集<li>メールまたはSMS メッセージのコンテンツにリンクを追加する<li>ビジュアルデザインスペースでのドラフトバージョンの編集<li>ドラフトバージョンを公開<li>複製<li>削除（両方のバージョンを削除）<li>ドラフトを破棄（公開済みステータスに戻る） |

![&#x200B; ランディングページのステータスのライフサイクル &#x200B;](./assets/status-lifecycle-diagram.png){zoomable="yes"}

## ランディングページの編集

ランディングページの編集は、現在のステータスに応じて異なります。

* ランディングページのステータスが&#x200B;**_ドラフト_**&#x200B;の場合、その詳細、URL、ビジュアルコンテンツのいずれかを編集できます。
* ランディングページのステータスが&#x200B;**_公開済み_**&#x200B;の場合、説明は編集できますが、名前は編集できません。 ビジュアルコンテンツを変更するには、ページのドラフトバージョンを作成する必要があります。
* ランディングページが&#x200B;**_下書き_**&#x200B;状態で公開済みの場合、詳細の編集は説明に限定されます。 ドラフトバージョンのビジュアルコンテンツを編集することもできます。

>[!BEGINTABS]

>[!TAB ドラフト]

1. _[!UICONTROL ランディングページ]_&#x200B;のリストページで、ランディングページ名をクリックして開きます。

   ビジュアルコンテンツのプレビューが表示され、ランディングページの詳細が右側に表示されます。

1. 名前や説明などの詳細を変更します。

   ![&#x200B; ドラフトステータスを持つランディングページの詳細](./assets/landing-page-draft-details.png){width="700" zoomable="yes"}

1. ビジュアルデザインスペースのコンテンツを変更するには、**[!UICONTROL ランディングページを編集]**&#x200B;をクリックします。

   必要に応じて、ビジュアルデザインツールを使用します。

   * [構造とコンテンツの追加](./landing-page-design.md#structure-content-landing-page)
   * [Assetsを追加](./landing-page-design.md#add-assets)
   * [レイヤー、設定、スタイルの移動](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [コンテンツのパーソナライズ](./landing-page-design.md#personalize-content)
   * [リンクされたURL トラッキングを編集](./landing-page-design.md#edit-linked-url-tracking)

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ページが条件を満たしており、表示できるようにするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

>[!TAB パブリッシュ済み]

1. _[!UICONTROL ランディングページ]_&#x200B;のリストページで、ページ名をクリックして開きます。

   ビジュアルコンテンツのプレビューが表示され、ランディングページの詳細が右側に表示されます。

1. 必要に応じて、説明を変更します。

   公開したランディングページの場合、他のすべての詳細を変更することはできません。

1. コンテンツを更新する場合は、右側の「**[!UICONTROL ランディングページを編集]**」をクリックします。

   ダイアログで「**[!UICONTROL ドラフトバージョンを作成]**」をクリックして、ビジュアルデザインスペースでドラフトバージョンを開きます。

   ![下書きバージョンの作成ダイアログ &#x200B;](./assets/landing-page-create-draft-version.png){width="300"}

   必要に応じて、ビジュアルデザインツールを使用します。

   * [構造とコンテンツの追加](./landing-page-design.md#structure-content-landing-page)
   * [Assetsを追加](./landing-page-design.md#add-assets)
   * [レイヤー、設定、スタイルの移動](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [コンテンツのパーソナライズ](./landing-page-design.md#personalize-content)
   * [リンクされたURL トラッキングを編集](./landing-page-design.md#edit-linked-url-tracking)

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ドラフトのランディングページが条件を満たしており、公開ページで変更を利用できるようにするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

   ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツがページ URLに更新されます。

>[!TAB 下書きで公開]

ランディングページを開くと、ドラフトバージョンが表示されます。 プレビュースペースの上部にあるタブを使用すると、公開バージョンとドラフトバージョンの表示を切り替えることができます。 下書きのアクションと詳細が右側に表示されます。

![&#x200B; ランディングページのドラフトバージョンのプレビューと詳細](./assets/landing-page-published-draft-details.png){width="700" zoomable="yes"}

コンテンツを更新するには：

1. 右上の「**[!UICONTROL ランディングページを編集]**」をクリックします。 必要に応じて、ビジュアルデザインツールを使用します。

   * [構造とコンテンツの追加](./landing-page-design.md#structure-content-landing-page)
   * [Assetsを追加](./landing-page-design.md#add-assets)
   * [レイヤー、設定、スタイルの移動](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [コンテンツのパーソナライズ](./landing-page-design.md#personalize-content)
   * [リンクされたURL トラッキングを編集](./landing-page-design.md#edit-linked-url-tracking)

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ドラフトページが条件を満たしており、変更を使用可能にするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

   ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツはホストされているページで更新されます。

>[!ENDTABS]

## ランディングページの複製

次のいずれかの方法を使用して、ランディングページを複製できます。

* _[!UICONTROL ランディングページ]_&#x200B;のリスト ページで、_詳細_ アイコン （**...**）をクリックします ランディングページ名の横にある「**[!UICONTROL 複製]**」を選択します。
* ランディングページの詳細ページの右上にある「**[!UICONTROL 」をクリックします…詳細]**&#x200B;を選択し、**[!UICONTROL 複製]**&#x200B;を選択します。

![&#x200B; ランディングページを複製](./assets/landing-page-details-duplicate-delete.png){width="600" zoomable="yes"}

ダイアログで、便利な名前（一意）と説明（オプション）を入力します。 「**[!UICONTROL 複製]**」をクリックして、アクションを完了します。

![複製されたランディングページの名前と説明を入力](./assets/landing-page-duplicate-dialog.png){width="350"}

複製された（新しい）ページは、_ランディングページ_&#x200B;のリストに表示されます。

## ランディングページの削除

ランディングページを削除するには、次のいずれかの方法を使用します。

* _[!UICONTROL ランディングページ]_&#x200B;のリスト ページで、_詳細_ アイコン （**...**）をクリックします ランディングページ名の横にある「**[!UICONTROL 削除]**」を選択します。
* ランディングページの詳細ページの右上にある「**[!UICONTROL 」をクリックします…詳細]**&#x200B;を選択し、**[!UICONTROL 削除]**&#x200B;を選択します。

このアクションを実行すると、確認ダイアログが開きます。 「**[!UICONTROL キャンセル]**」をクリックするか、「**[!UICONTROL 削除]**」をクリックして削除を確認することで、プロセスを中止できます。

![&#x200B; ランディングページダイアログの削除](./assets/landing-page-delete-dialog.png){width="400"}

## ランディングページへのリンク

電子メール、フラグメント、ページコンテンツを作成するマーケターまたはDesignerは、Journey Optimizer B2B edition インスタンスで作成された公開（ライブ）ランディングページへのリンクを埋め込むことができます。

1. フラグメント、電子メール、ランディングページ、またはテンプレートのビジュアルデザインスペースで作業する際に、リンクのテキストの抜粋、ボタンコンポーネント、または画像コンポーネントを選択します。

   右側のパネルには、**[!UICONTROL リンク]**&#x200B;のオプションが表示されます。

1. **[!UICONTROL Type]** オプションで、**[!UICONTROL ランディングページ]**&#x200B;を選択します。

   ![&#x200B; ランディングページのリンクオプション &#x200B;](../../assets/content-design-shared/content-design-link-settings.png){width="700" zoomable="yes"}

1. **[!UICONTROL ランディングページ]** オプションで、_ページを選択_ アイコン （![&#x200B; リンクを表示アイコン &#x200B;](../assets/do-not-localize/icon-landing-page-select.svg)）をクリックします。

1. ランディングページを選択ダイアログで、**[!UICONTROL ランディングページソース]**&#x200B;を&#x200B;**[!UICONTROL Journey Optimizer B2B edition]**&#x200B;として設定し、公開されたページのリストからランディングページのチェックボックスをオンにして、**[!UICONTROL 選択]**&#x200B;をクリックします。

   ![&#x200B; ランディングページのリンクオプション &#x200B;](../../assets/content-design-shared/content-design-link-landing-page-select.png){width="600" zoomable="yes"}

1. 「**[!UICONTROL ターゲット]**」オプションで、リンクターゲットの動作を選択します。

   * **[!UICONTROL なし]** - ブラウザーの既定の動作を使用してリンクを開きます。
   * **[!UICONTROL 空白]** – 新しいウィンドウまたはタブでリンクを開きます。
   * **[!UICONTROL 自分]** – 同じフレームでリンクを開きます。
   * **[!UICONTROL 親]** – 親フレーム内のリンクを開きます。
   * **[!UICONTROL トップ]** - ウィンドウの本文のリンクを開きます。

1. （テキストリンクのみ）リンクされたテキストに下線を引く場合は、「**[!UICONTROL 下線リンク]**」チェックボックスを選択します。

   右側のパネルで「**[!UICONTROL スタイル]**」タブを選択すると、リンクカラーを含むリンクテキストに追加のスタイルを設定できます。
