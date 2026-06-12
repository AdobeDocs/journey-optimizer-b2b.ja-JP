---
title: ランディングページ
description: 個人向けジャーニーのランディングページを作成、デザイン、公開します。Journey Optimizer B2B Primeでは、ゼロから作成、HTMLをインポートして、フォームを追加、コンテンツをパーソナライズし、メールからリンクできます。
source-git-commit: a2443f98ec7a8a5c1d4be2450042e2375f6150b7
workflow-type: tm+mt
source-wordcount: '1461'
ht-degree: 6%

---

# ランディングページ

ランディングページとは、電子メール、SMS メッセージ、デジタル位置情報でリンクされたアイテムをクリックした後、連絡先や顧客を誘導できるスタンドアロンのweb ページです。 これらのページをアカウントジャーニーに組み込むことで、見込客や顧客にweb上でメッセージを表示させ、アカウントジャーニーを先に進んでもらうことができます。 ランディングページのビジュアルデザイン機能では、ランディングページを作成、パーソナライズ、プレビューできます。

ランディングページの一般的なユースケース：

* マーケティングコミュニケーションや特定のサービスに対するオプトインやオプトアウトの提供。 電子メールやその他のコミュニケーションで、ターゲットリストへのリンクを使用します。
* コミュニケーションを送信する前に同意を収集し、オプトインまたはオプトアウト時に確認メールを送信します。
* ランディングページでフォームを使用して、プロファイルデータ（プログレッシブプロファイリング、嗜好、登録、類似のシナリオ）を取得または更新します。
* ジャーニーオーケストレーションに合わせて設計された、キャンペーン固有の情報に人物を誘導します。
* Journey Optimizer B2B Primeの外部ページを構築することなく、専用のweb フォームにオーディエンスをリダイレクトできます。

<!-- 
## Landing page workflow

To direct members of a journey audience to a defined web page when they click a specific link, create a landing page in Journey Optimizer B2B Edition: 


1. [Create the page](./landing-pages-create-publish.md) - Select a preset, set up the primary page, and add any required subpages.
1. [Design the landing page content](./landing-page-design.md) - Build the page content using drag-and-drop visual design components.
1. [Test and publish the landing page](./landing-pages-create-publish.md) - Preview the page, test form behavior, and then publish to make it live.
1. [Link to the page from your journey](#link-to-a-landing-page) - Add the landing page URL to an email, SMS, or journey action so that recipients can reach it.


For example, you can create and design landing pages to direct your users to online information. The page could include a form where they can opt in or opt out from receiving your communications. Or it could be an opportunity to subscribe to a recurring communications, such as a newsletter. 

You can create, personalize, and preview landing pages in the visual design space.
-->

## ランディングページへのアクセスと管理

Journey Optimizer B2B Primeのランディングページにアクセスするには、左側のナビゲーションに移動し、**[!UICONTROL コンテンツ管理]**/**[!UICONTROL ランディングページ]**&#x200B;をクリックします。 このアクションは、インスタンスで作成されたすべてのランディングページのリストを表示します。

リストは、_[!UICONTROL 変更済み]_&#x200B;列に従って並べ替えられ、最も最近更新された項目が上部に表示されます。 列のタイトルをクリックして、昇順と降順を変更します。

### ランディングページリストのフィルター

ランディングページを名前で検索するには、検索バーにテキスト文字列を入力して一致を検索します。 _フィルター_ アイコン <!-- ( ![Show or hide filters icon](../assets/do-not-localize/icon-filter.svg) ) -->をクリックして、使用可能なフィルターオプションを表示し、設定を変更して、指定した条件に従って表示される項目をフィルタリングします。

![表示されるランディングページをフィルター](./assets/landing-pages-list-filtered.png){width="800" zoomable="yes"}

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
| 公開日 | ランディングページを公開すると、ランディングページはJourney Optimizer B2B Prime インスタンスでホストされ、メールまたはSMS メッセージのコンテンツでリンクできるようになります。 使用可能なアクション：<br/><ul><li>名前または説明を編集<li>リンク URLを編集<li>メールまたはSMS メッセージのコンテンツにリンクを追加する<li>ドラフトバージョンを作成<li>複製<li>削除 |
| 公開済み下書きあり | 公開されたランディングページからドラフトを作成すると、公開されたバージョンは残り、ドラフトコンテンツはビジュアルデザイン空間で変更できます。 ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツはホストされているページで更新されます。 使用可能なアクション：<br/><ul><li>名前または説明を編集<li>リンク URLを編集<li>メールまたはSMS メッセージのコンテンツにリンクを追加する<li>ビジュアルデザインスペースでのドラフトバージョンの編集<li>ドラフトバージョンを公開<li>複製<li>削除（両方のバージョンを削除）<li>ドラフトを破棄（公開済みステータスに戻る） |

<!-- ![Landing page status lifecycle](./assets/status-lifecycle-diagram.png){zoomable="yes"} -->

## ランディングページの作成 {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_create"
>title="ランディングページの定義と設定"
>abstract="ランディングページを作成するには、プリセットを選択し、プライマリページとサブページを設定してから、公開する前にページをテストする必要があります。"

未定

## プライマリページの設定 {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_primary_page"
>title="プライマリページ設定の定義"
>abstract="電子メールやweb サイトなどのランディングページのリンクを受信者がクリックするとすぐに表示されるプライマリページを定義します。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_access_settings"
>title="ランディングページ URL の定義"
>abstract="このセクションでは、一意のランディングページ URL を定義します。 URLの最初の部分では、選択したプリセットの一部として、ランディングページサブドメインを以前に設定している必要があります。"

未定

## ランディングページのテスト {#test-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_preview_lp_profiles"
>title="ランディングページのプレビューとテスト"
>abstract="ランディングページの設定とコンテンツを定義したら、テストプロファイルを使用してページをプレビューします。"

未定

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

   <!-- ![Details for landing page with Draft status](./assets/landing-page-draft-details.png){width="700" zoomable="yes"} -->

1. ビジュアルデザインスペースのコンテンツを変更するには、**[!UICONTROL ランディングページを編集]**&#x200B;をクリックします。

   <!-- 
   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)
   -->

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ページが条件を満たしており、表示できるようにするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

>[!TAB パブリッシュ済み]

1. _[!UICONTROL ランディングページ]_&#x200B;のリストページで、ページ名をクリックして開きます。

   ビジュアルコンテンツのプレビューが表示され、ランディングページの詳細が右側に表示されます。

1. 必要に応じて、説明を変更します。

   公開したランディングページの場合、他のすべての詳細を変更することはできません。

1. コンテンツを更新する場合は、右側の「**[!UICONTROL ランディングページを編集]**」をクリックします。

   ダイアログで「**[!UICONTROL ドラフトバージョンを作成]**」をクリックして、ビジュアルデザインスペースでドラフトバージョンを開きます。

   <!-- 
   ![Create draft version dialog](./assets/landing-page-create-draft-version.png){width="300"} 

   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)
   -->

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ドラフトのランディングページが条件を満たしており、公開ページで変更を利用できるようにするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

   ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツがページ URLに更新されます。

>[!TAB 下書きで公開]

ランディングページを開くと、ドラフトバージョンが表示されます。 プレビュースペースの上部にあるタブを使用すると、公開バージョンとドラフトバージョンの表示を切り替えることができます。 下書きのアクションと詳細が右側に表示されます。

<!-- ![Preview and details for the landing page draft version](./assets/landing-page-published-draft-details.png){width="700" zoomable="yes"} -->

コンテンツを更新するには：

1. 右上の「**[!UICONTROL ランディングページを編集]**」をクリックします。

   <!--

   Use the visual design tools as needed:

   * [Add structure and content](./landing-page-design.md#structure-content-landing-page)
   * [Add Assets](./landing-page-design.md#add-assets)
   * [Navigate the layers, settings, and styles](./landing-page-design.md#navigate-the-layers-settings-and-styles)
   * [Personalize content](./landing-page-design.md#personalize-content)
   * [Edit linked URL tracking](./landing-page-design.md#edit-linked-url-tracking)

   -->

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ドラフトページが条件を満たしており、変更を使用可能にするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

   ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツはホストされているページで更新されます。

>[!ENDTABS]

## ランディングページの複製

次のいずれかの方法を使用して、ランディングページを複製できます。

* _[!UICONTROL ランディングページ]_&#x200B;のリスト ページで、_詳細_ アイコン （**...**）をクリックします ランディングページ名の横にある「**[!UICONTROL 複製]**」を選択します。
* ランディングページの詳細ページの右上にある「**[!UICONTROL 」をクリックします…詳細]**&#x200B;を選択し、**[!UICONTROL 複製]**&#x200B;を選択します。

<!-- ![Duplicate the landing page](./assets/landing-page-details-duplicate-delete.png){width="600" zoomable="yes"} -->

ダイアログで、便利な名前（一意）と説明（オプション）を入力します。 「**[!UICONTROL 複製]**」をクリックして、アクションを完了します。

<!-- ![Enter a name and description for the duplicated landing page](./assets/landing-page-duplicate-dialog.png){width="350"} -->

複製された（新しい）ページは、_ランディングページ_&#x200B;のリストに表示されます。

## ランディングページの削除

ランディングページを削除するには、次のいずれかの方法を使用します。

* _[!UICONTROL ランディングページ]_&#x200B;のリスト ページで、_詳細_ アイコン （**...**）をクリックします ランディングページ名の横にある「**[!UICONTROL 削除]**」を選択します。
* ランディングページの詳細ページの右上にある「**[!UICONTROL 」をクリックします…詳細]**&#x200B;を選択し、**[!UICONTROL 削除]**&#x200B;を選択します。

このアクションを実行すると、確認ダイアログが開きます。 「**[!UICONTROL キャンセル]**」をクリックするか、「**[!UICONTROL 削除]**」をクリックして削除を確認することで、プロセスを中止できます。

<!-- ![Delete landing page dialog](./assets/landing-page-delete-dialog.png){width="400"} -->

## ランディングページへのリンク

電子メール、フラグメント、ページコンテンツを制作するマーケターまたはクリエイターは、Journey Optimizer B2B Prime インスタンスで作成された公開（ライブ）ランディングページへのリンクを埋め込むことができます。

1. フラグメント、電子メール、ランディングページ、またはテンプレートのビジュアルデザインスペースで作業する際に、リンクのテキストの抜粋、ボタンコンポーネント、または画像コンポーネントを選択します。

   右側のパネルには、**[!UICONTROL リンク]**&#x200B;のオプションが表示されます。

1. **[!UICONTROL Type]** オプションで、**[!UICONTROL ランディングページ]**&#x200B;を選択します。

   <!-- ![Link options for a landing page](/help/assets/content-design-shared/content-design-link-settings.png){width="700" zoomable="yes"} -->

1. **[!UICONTROL ランディングページ]** オプションで、_ページを選択_ アイコン <!-- ( ![Show links icon](/help/assets/do-not-localize/icon-landing-page-select.svg) ) -->をクリックします。

1. ランディングページを選択ダイアログで、**[!UICONTROL ランディングページソース]**&#x200B;を&#x200B;**[!UICONTROL Journey Optimizer B2B edition]**&#x200B;として設定し、公開されたページのリストからランディングページのチェックボックスをオンにして、**[!UICONTROL 選択]**&#x200B;をクリックします。

   <!-- ![Link options for a landing page](/help/assets/content-design-shared/content-design-link-landing-page-select.png){width="600" zoomable="yes"} -->

1. 「**[!UICONTROL ターゲット]**」オプションで、リンクターゲットの動作を選択します。

   * **[!UICONTROL なし]** - ブラウザーの既定の動作を使用してリンクを開きます。
   * **[!UICONTROL 空白]** – 新しいウィンドウまたはタブでリンクを開きます。
   * **[!UICONTROL 自分]** – 同じフレームでリンクを開きます。
   * **[!UICONTROL 親]** – 親フレーム内のリンクを開きます。
   * **[!UICONTROL トップ]** - ウィンドウの本文のリンクを開きます。

1. （テキストリンクのみ）リンクされたテキストに下線を引く場合は、「**[!UICONTROL 下線リンク]**」チェックボックスを選択します。

   右側のパネルで「**[!UICONTROL スタイル]**」タブを選択すると、リンクカラーを含むリンクテキストに追加のスタイルを設定できます。
