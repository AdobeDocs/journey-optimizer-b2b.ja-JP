---
title: ランディングページ
description: 個人向けジャーニーのランディングページを作成、デザイン、公開します。Journey Optimizer B2B Primeでは、ゼロから作成、HTMLをインポートして、フォームを追加、コンテンツをパーソナライズし、メールからリンクできます。
autotag-review: '2026-06-12T22:53:39.337Z'
TQID: 'https://experienceleague.adobe.com/BvtB0i5CzlVutPA6HAzZy-Gfymw7ppZwthyBauyciLc'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: e666e996-b2cf-4c45-8fc2-1c625212ababid: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: a96755d6-1f54-4f3f-a971-d31f83705ab7id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 21f0ab524176df40128212fef920e10b06b5c317
workflow-type: tm+mt
source-wordcount: 2180
ht-degree: 6%

---

# ランディングページ

ランディングページとは、電子メール、SMS メッセージ、デジタル位置情報でリンクされたアイテムをクリックした後、連絡先や顧客を誘導できるスタンドアロンのweb ページです。 これらのページをジャーニーに組み込むことで、見込み客や顧客にweb上でメッセージを表示してもらい、ジャーニーを進めることができます。 ランディングページのビジュアルデザイン機能では、ランディングページを作成、パーソナライズ、プレビューできます。

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
1. [Test the landing page](./landing-pages-create.md) - Preview the page, test form behavior, and then publish to make it live.
1. [Link to the page from your journey](#link-to-a-landing-page) - Add the landing page URL to an email, SMS, or journey action so that recipients can reach it.


For example, you can create and design landing pages to direct your users to online information. The page could include a form where they can opt in or opt out from receiving your communications. Or it could be an opportunity to subscribe to a recurring communications, such as a newsletter. 

You can create, personalize, and preview landing pages in the visual design space.
-->

## ランディングページへのアクセスと管理 {#access-manage-landing-pages}

Journey Optimizer B2B Primeのランディングページにアクセスするには、左側のナビゲーションに移動し、**[!UICONTROL コンテンツ管理]**/**[!UICONTROL ランディングページ]**&#x200B;をクリックします。 このアクションは、インスタンスで作成されたすべてのランディングページのリストを表示します。

リストは、_[!UICONTROL 変更済み]_&#x200B;列に従って並べ替えられ、最も最近更新された項目が上部に表示されます。 列のタイトルをクリックして、昇順と降順を変更します。

### ランディングページリストのフィルター {#filter-list}

ランディングページを名前で検索するには、検索バーにテキスト文字列を入力して一致を検索します。 _フィルター_ アイコン （![ フィルターの表示または非表示アイコン ](../../user/assets/do-not-localize/icon-filter.svg)）をクリックして、使用可能なフィルターオプションを表示し、設定を変更して、指定した条件に従って表示される項目をフィルタリングします。

![表示されるランディングページをフィルター](./assets/landing-pages-list-filtered.png){width="800" zoomable="yes"}

<!-- 
This is going away? ### Customize the column display

Customize the columns that you want to display in the table by clicking the _Customize table_ icon ( ![Customize table icon](../assets/do-not-localize/icon-column-settings.svg) ) at the top right. 

In the dialog, select the columns to display and click **[!UICONTROL Apply]**.

![Select the columns that you want to display](./assets/landing-pages-customize-table-dialog.png){width="300"} 
-->

### ランディングページのステータスとライフサイクル {#landing-page-status}

ランディングページのステータスによって、電子メールおよびSMS コンテンツ内でのリンクの可用性と、それに対して実行できる変更が決まります。

| ステータス | 説明 |
| -------------------- | ----------- |
| 下書き | ランディングページを作成する場合、そのランディングページはドラフトステータスになります。 ビジュアルコンテンツを定義または編集し、ホストされたページとして公開するまで、このステータスのままになります。 使用可能なアクション：<br/><ul><li>名前または説明を編集</li><li>リンク URLを編集</li><li>ビジュアルデザイン空間での編集</li><li>公開</li><li>複製</li><li>削除</li></ul> |
| 公開日 | ランディングページを公開すると、ランディングページはJourney Optimizer B2B Prime インスタンスでホストされ、メールまたはSMS メッセージのコンテンツでリンクできるようになります。 使用可能なアクション：<br/><ul><li>名前または説明を編集</li><li>リンク URLを編集</li><li>メールまたはSMS メッセージのコンテンツにリンクを追加する</li><li>ドラフトバージョンを作成</li><li>複製</li><li>削除</li></ul> |
| 公開済み下書きあり | 公開されたランディングページからドラフトを作成すると、公開されたバージョンは残り、ドラフトコンテンツはビジュアルデザイン空間で変更できます。 ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツはホストされているページで更新されます。 使用可能なアクション：<br/><ul><li>名前または説明を編集</li><li>リンク URLを編集</li><li>メールまたはSMS メッセージのコンテンツにリンクを追加する</li><li>ビジュアルデザインスペースでのドラフトバージョンの編集</li><li>ドラフトバージョンを公開</li><li>複製</li><li>削除（両方のバージョンを削除）</li><li>ドラフトを破棄（公開済みステータスに戻る）</li></ul> |

<!-- ![Landing page status lifecycle](./assets/status-lifecycle-diagram.png){zoomable="yes"} -->

## ランディングページの作成 {#create-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_create"
>title="ランディングページの定義と設定"
>abstract="ランディングページを作成するには、プリセットを選択し、プライマリページとサブページを設定してから、公開する前にページをテストする必要があります。"

特定のリンクをクリックしたときに、定義されたweb ページにジャーニーオーディエンスのメンバーを誘導するには、[!DNL Journey Optimizer B2B Prime]にランディングページを作成します。 プリセットを選択し、プライマリページとサブページを設定し、[ ページをテスト ](#test-landing-page)して公開します。

>[!IMPORTANT]
>
>最初のランディングページを作成する前に、ランディングページの設定を完了します。 これには、ランディングページをホストするサブドメインを設定したり、サブドメインやその他のチャネル設定を指定する少なくとも1つのプリセットを定義したりすることが含まれます。 ランディングページの作成時にプリセットを選択します。 管理者の設定については、[ ランディングページ設定](../admin/configuration-presets-landing-pages.md)を参照してください。
>
>データキャプチャのユースケースの場合は、ランディングページに埋め込む前に[ フォーム ](./forms.md)を作成します。

ランディングページを作成するには、次の手順に従います。

1. 左側のナビゲーションに移動し、**[!UICONTROL コンテンツ管理]**/**[!UICONTROL ランディングページ]**&#x200B;を選択します。

1. ランディングページのリストから、「**[!UICONTROL ランディングページの作成]**」をクリックします。

1. **[!UICONTROL タイトル]** （必須）と&#x200B;**[!UICONTROL 説明]** （オプション）を入力します。

   タイトルと説明基準：

   * **タイトル** – 最大100文字。 一意である必要があります（大文字と小文字を区別しません）。
   * **説明** – 最大300文字。
   * Alpha、数値、特殊文字は使用できます。
   * 予約済みの文字は&#x200B;**_許可されていません_**: `\ / : * ? " < > |`

1. **[!UICONTROL プリセット]**&#x200B;を選択します。

   管理者[は、ランディングページに使用するサブドメインやその他の設定を定義するために、ランディングページプリセット ](../admin/configuration-presets-landing-pages.md#lp-presets)を作成します。 プリセットを選択し、**[!UICONTROL プリセットを表示]**&#x200B;をクリックして設定を確認し、ランディングページの要件に一致することを確認します。

1. 「**[!UICONTROL 作成]**」をクリックします。

   プライマリページとそのプロパティが表示されます。 プライマリページ設定を[設定する方法について説明します](#configure-primary-page)。

1. サブページ（例えば、感謝ページやエラーページ）を追加するには、**+** アイコンをクリックします。

   ランディングページごとに最大2つのサブページを追加できます。

プライマリページとサブページを設定およびデザインしたら、ランディングページを公開する前に[ テスト ](#test-landing-page)します。

>[!CAUTION]
>
>ランディングページが公開されている場合でも、定義されたURLをweb ブラウザーにコピー&amp;ペーストして、ランディングページにアクセスすることはできません。 [ ランディングページのテスト ](#test-landing-page)の説明に従って、プレビュー関数を使用してページをテストします。

## プライマリページの設定 {#configure-primary-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_primary_page"
>title="プライマリページ設定の定義"
>abstract="電子メールやweb サイトなどのランディングページのリンクを受信者がクリックするとすぐに表示されるプライマリページを定義します。"

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_lp_access_settings"
>title="ランディングページ URL の定義"
>abstract="このセクションでは、一意のランディングページ URL を定義します。 URLの最初の部分では、選択したプリセットの一部として、ランディングページサブドメインを以前に設定している必要があります。"

プライマリページとは、電子メールやweb サイトなどのランディングページのリンクを受信者がクリックすると、すぐに表示されるページのことです。

プライマリページの設定を定義するには、次の手順に従います。

1. ニーズに応じて&#x200B;**[!UICONTROL ページ名]**&#x200B;を変更します。デフォルトでは&#x200B;_プライマリページ_&#x200B;です。

1. ページ URLの終了部分を定義します。

   選択したプリセットによって、URLの最初の部分が決まります。 管理者は、プリセットの一部として[ ランディングページサブドメイン ](../admin/configuration-presets-landing-pages.md#lp-subdomains)を設定します。

   >[!CAUTION]
   >
   >ランディングページの URL は一意にする必要があります。
   >
   >ランディングページが公開されている場合でも、このURLをweb ブラウザーにコピー&amp;ペーストしてランディングページにアクセスすることはできません。 [ ランディングページのテスト ](#test-landing-page)の説明に従って、プレビュー関数を使用してテストします。

1. 匿名のランディングページが必要な場合は、**[!UICONTROL 特定のユーザーを要求]** オプションを無効にします。

1. _カレンダー_ アイコンをクリックして、**[!UICONTROL ページの有効期限]**&#x200B;を設定します。

   有効期限を選択したら、ページの有効期限に応じてアクションを選択します。

   * **[!UICONTROL リダイレクト URL]** - リダイレクトとして使用するページのURLを入力します。
   * **[!UICONTROL ブラウザーエラー]** - ページの代わりに表示するエラーテキストを入力します。

## ランディングページのテスト {#test-landing-page}

>[!CONTEXTUALHELP]
>id="ajo-b2b-prime_preview_lp_profiles"
>title="ランディングページのプレビューとテスト"
>abstract="ランディングページの設定とコンテンツを定義したら、テストプロファイルを使用してページをプレビューします。"

ランディングページの設定とコンテンツが定義されている場合は、テストプロファイルを使用してページをプレビューできます。 [ パーソナライズされたコンテンツ ](email-authoring.md#personalization)を挿入した場合、テストプロファイルデータを使用して、このコンテンツがランディングページにどのように表示されるかを確認できます。

>[!PREREQUISITES]
>
>ランディングページをプレビューしてテストするには、**[!UICONTROL メッセージを公開]**&#x200B;権限と、テストプロファイルを含む定義済みデータセットが必要です。

1. 「**[!UICONTROL プレビューとテスト]**」をクリックして、テストプロファイルの選択を開きます。

   >[!NOTE]
   >
   >ビジュアルデザイン空間にいる場合は、**[!UICONTROL コンテンツをシミュレート]**&#x200B;することもできます。

1. _[!UICONTROL Simulate]_&#x200B;画面から、テストプロファイルを選択します。

   必要なプロファイルがリストにない場合は、**[!UICONTROL テストプロファイルの管理]**&#x200B;をクリックして、既知のテストプロファイルのメールアドレスを使用し、リストに追加します。

   +++テストプロファイルの追加

   **[!UICONTROL ID名前空間]**&#x200B;の場合、_選択_ アイコン （![選択アイコン ](../../user/assets/do-not-localize/icon-select-data.svg)）をクリックし、プロファイルのテストに使用する`Email`名前空間を選択します。

   「**[!UICONTROL ID値]**」フィールドに、テストプロファイルを識別する電子メールアドレスを入力し、**[!UICONTROL プロファイルを追加]**&#x200B;をクリックします。 これを繰り返して複数のプロファイルを追加できます。

   左上の後向き矢印をクリックして、_[!UICONTROL シミュレーション]_ ページに戻ります。

   +++

1. 「**[!UICONTROL プレビューを開く]**」を選択してランディングページをテストします。

   ランディングページのプレビューが新しいタブで開きます。 選択したテストプロファイルデータは、パーソナライズされた要素に置き換わります。

1. ランディングページの各バリエーションに対してレンダリングをプレビューするには、別のテストプロファイルを選択します。

## ランディングページの編集 {#edit-landing-page}

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

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ページが条件を満たしており、表示できるようにするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

>[!TAB パブリッシュ済み]

1. _[!UICONTROL ランディングページ]_&#x200B;のリストページで、ページ名をクリックして開きます。

   ビジュアルコンテンツのプレビューが表示され、ランディングページの詳細が右側に表示されます。

1. 必要に応じて、説明を変更します。

   公開したランディングページの場合、他のすべての詳細を変更することはできません。

1. コンテンツを更新する場合は、右側の「**[!UICONTROL ランディングページを編集]**」をクリックします。

   ダイアログで「**[!UICONTROL ドラフトバージョンを作成]**」をクリックして、ビジュアルデザインスペースでドラフトバージョンを開きます。

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ドラフトのランディングページが条件を満たしており、公開ページで変更を利用できるようにするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

   ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツがページ URLに更新されます。

>[!TAB 下書きで公開]

ランディングページを開くと、ドラフトバージョンが表示されます。 プレビュースペースの上部にあるタブを使用すると、公開バージョンとドラフトバージョンの表示を切り替えることができます。 下書きのアクションと詳細が右側に表示されます。

<!-- ![Preview and details for the landing page draft version](./assets/landing-page-published-draft-details.png){width="700" zoomable="yes"} -->

コンテンツを更新するには：

1. 右上の「**[!UICONTROL ランディングページを編集]**」をクリックします。

1. 「**[!UICONTROL 保存]**」または「**[!UICONTROL 保存して閉じる]**」をクリックすると、ランディングページの詳細に戻ります。

1. ドラフトページが条件を満たしており、変更を使用可能にするには、**[!UICONTROL 公開]**&#x200B;をクリックします。

   ドラフトバージョンを公開すると、現在の公開済みバージョンが置き換えられ、コンテンツはホストされているページで更新されます。

>[!ENDTABS]

## ランディングページの複製 {#duplicate-landing-page}

次のいずれかの方法を使用して、ランディングページを複製できます。

* _[!UICONTROL ランディングページ]_&#x200B;のリスト ページで、_詳細_ アイコン （**...**）をクリックします ランディングページ名の横にある「**[!UICONTROL 複製]**」を選択します。
* ランディングページの詳細ページの右上にある「**[!UICONTROL 」をクリックします…詳細]**&#x200B;を選択し、**[!UICONTROL 複製]**&#x200B;を選択します。

<!-- ![Duplicate the landing page](./assets/landing-page-details-duplicate-delete.png){width="600" zoomable="yes"} -->

ダイアログで、便利な名前（一意）と説明（オプション）を入力します。 「**[!UICONTROL 複製]**」をクリックして、アクションを完了します。

<!-- ![Enter a name and description for the duplicated landing page](./assets/landing-page-duplicate-dialog.png){width="350"} -->

複製された（新しい）ページは、_ランディングページ_&#x200B;のリストに表示されます。

## ランディングページの削除 {#delete-landing-page}

ランディングページを削除するには、次のいずれかの方法を使用します。

* _[!UICONTROL ランディングページ]_&#x200B;のリスト ページで、_詳細_ アイコン （**...**）をクリックします ランディングページ名の横にある「**[!UICONTROL 削除]**」を選択します。
* ランディングページの詳細ページの右上にある「**[!UICONTROL 」をクリックします…詳細]**&#x200B;を選択し、**[!UICONTROL 削除]**&#x200B;を選択します。

このアクションを実行すると、確認ダイアログが開きます。 「**[!UICONTROL キャンセル]**」をクリックするか、「**[!UICONTROL 削除]**」をクリックして削除を確認することで、プロセスを中止できます。

<!-- ![Delete landing page dialog](./assets/landing-page-delete-dialog.png){width="400"} -->

## ランディングページへのリンク {#link-to-landing-page}

電子メール、フラグメント、ページコンテンツを制作するマーケターまたはクリエイターは、Journey Optimizer B2B Prime インスタンスで作成された公開（ライブ）ランディングページへのリンクを埋め込むことができます。

1. フラグメント、電子メール、ランディングページ、またはテンプレートのビジュアルデザインスペースで作業する際に、リンクのテキストの抜粋、ボタンコンポーネント、または画像コンポーネントを選択します。

   右側のパネルには、**[!UICONTROL リンク]**&#x200B;のオプションが表示されます。

1. **[!UICONTROL Type]** オプションで、**[!UICONTROL ランディングページ]**&#x200B;を選択します。

   <!-- ![Link options for a landing page](/help/assets/content-design-shared/content-design-link-settings.png){width="700" zoomable="yes"} -->

1. **[!UICONTROL ランディングページ]** オプションで、_ページを選択_ アイコン （![ リンクを表示アイコン ](../../user/assets/do-not-localize/icon-landing-page-select.svg)）をクリックします。

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
