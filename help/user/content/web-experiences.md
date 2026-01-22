---
title: Web エクスペリエンス
description: アカウントジャーニー用にパーソナライズされた web エクスペリエンスを作成、設計および公開し、Journey Optimizer B2B editionの web サイト訪問者にターゲットを設定したコンテンツ変更を提供します。
feature: Content, Channels
role: User
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
source-git-commit: e3c00ab4657c7bf05573e049bbcb4bb3628e751e
workflow-type: tm+mt
source-wordcount: '1497'
ht-degree: 4%

---

# Web エクスペリエンス

Adobe Journey Optimizer B2B editionの web チャネルを使用すると、パーソナライズされたエクスペリエンスを web サイト上で直接作成でき、顧客と有意義なつながりを持つことができるようになります。 この機能は、カスタマイズされたコンテンツとのエンゲージメントを強化し、メールや SMS などの他のチャネルとシームレスに統合するために使用できる柔軟なツールキットを提供します。

Web エクスペリエンスでは、次のことが可能です。

* ターゲットとなる web サイト訪問者にパーソナライズされたコンテンツの変更を配信する
* アカウント属性に基づいてバナー、テキスト、画像、ボタンなどの web サイト要素をカスタマイズ
* 特定のページをターゲットにするか、URL マッチングルールを使用して複数のページに変更を適用します。
* エンゲージメントの追跡と web パーソナライゼーションの取り組みの影響の監視

>[!BEGINSHADEBOX]

## 前提条件

Web エクスペリエンスを作成する前に、次の要件が満たされていることを確認してください。

* 製品管理者は、1 つ以上の web チャネルを設定して、web エクスペリエンスに含める URL （ページ）を定義しています。 詳しくは、「[Web チャネル設定 &#x200B;](../admin/configure-channels-web.md)」を参照してください。

* Web サイトには、訪問者の特定とコンテンツ配信のために [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/js-overview) （`alloy.js`）が実装されています。 Adobe Experience Platform Web SDKのバージョンが 2.16 以上であることを確認してください。

* ジャーニーで web エクスペリエンスを作成および管理するために必要な [&#x200B; 権限 &#x200B;](../admin/user-management.md#b2b-product-permissions) を持っている。
   * _[!UICONTROL キャンペーン]_/_[!UICONTROL キャンペーンの管理]_ - web パーソナライゼーションアクションノードを追加または更新するために必要です。
   * _[!UICONTROL キャンペーン]_/_[!UICONTROL キャンペーンを表示]_ - Web パーソナライゼーションアクションノードの詳細を表示するために必要です。
   * _[!UICONTROL キャンペーン]_/_[!UICONTROL キャンペーンを承認および公開]_ - 1 つ以上の web パーソナライゼーションアクションノードを持つジャーニーを公開する場合に必要です。

* Web ブラウザーにAdobe Experience Cloud [Visual Editing Helper ブラウザー拡張機能 &#x200B;](#install-the-visual-editing-helper-extension) がインストールされていること。 この拡張機能は、Journey Optimizer B2B editionのコンテンツデザイン領域で web ページを確実に開き、作成し、プレビューするために必要です。

  >[!NOTE]
  >
  >現在、Google ChromeとMicrosoft Edgeは、Journey Optimizer B2B editionでの web ページのオーサリングをサポートしている唯一のブラウザーです。

>[!ENDSHADEBOX]

## Visual Editing Helper 拡張機能のインストール

1. ブラウザー（[!DNL Google Chrome] または [!DNL Microsoft Edge]）で新しいタブを開きます。

1. [Google Chrome web ストア](https://chromewebstore.google.com/category/extensions)に移動します。

   [!DNL Microsoft Edge] を使用している場合は、上部のバナーで他のストアの _拡張機能を許可_ を選択します。 このオプションを有効にすると、[!DNL Chrome Web Store] から [!DNL Microsoft Edge] に拡張機能を追加できます。

1. _[!DNL Adobe Experience Cloud Visual Editing Helper]_&#x200B;ブラウザー拡張機能を検索して移動します。

   ![Google ChromeのAdobe Experience Cloud Visual Editing Helper 拡張機能 &#x200B;](./assets/web-experience-google-chrome-adobe-visual-editing-extension.png){width="800" zoomable="yes"}

1. **[!UICONTROL Chromeに追加]** をクリックしてから、確認ダイアログで **[!UICONTROL 拡張機能を追加]** をクリックします。

   [!DNL Microsoft Edge] を使用している場合は、このアクションによって [!DNL Edge] に拡張機能が追加されます。

1. ブラウザーツールバーで、[!DNL Visual Editing Helper] ブラウザー拡張機能が正しく有効になっていることを確認します。

   ![Google Chrome ツールバーのAdobe Experience Cloud Visual Editing Helper 拡張機能アイコン &#x200B;](./assets/web-experience-google-chrome-adobe-visual-editing-extension-icon.png){width="450"}

Web エクスペリエンス用のJourney Optimizer B2B edition ビジュアルエディターで web サイトを開くと、[!DNL Adobe Experience Cloud Visual Editing Helper] が自動的に有効になります。 この拡張機能には条件付きの設定はなく、SameSite Cookie の設定を含むすべての設定を自動処理します。

>[!NOTE]
>
>次のいずれかの理由により、Journey Optimizer B2B edition web エディターで一部の web サイトが正しく開けない場合があります。
>
>* Web サイトに厳格なセキュリティポリシーがある。
>* Web サイトが iframe 内にある。
>* 顧客 QA またはステージサイトが外部から利用できません（サイトは内部）。

## Web エクスペリエンスの作成

[&#x200B; アクションを実行 _[!UICONTROL ノードを追加]_ して以下を実行する &#x200B;](../journeys/action-nodes.md) ときに、ジャーニーで web エクスペリエンスを設定できます。

1. _[!UICONTROL アクションオン]_ ターゲットで、「**[!UICONTROL ユーザー]**」を選択します。

1. 「_[!UICONTROL ユーザーに対するアクション]_」で「**[!UICONTROL web エクスペリエンスをパーソナライズ]**」を選択します。

   ![&#x200B; アクションの実行 – web エクスペリエンスのパーソナライズ &#x200B;](./assets/web-experience-add-journey-node.png){width="500"}

1. **[!UICONTROL Web エクスペリエンスを作成]** をクリックします。

1. _[!UICONTROL Web エクスペリエンスを作成]_ ダイアログで、便利な **[!UICONTROL 名前]** と **[!UICONTROL 説明]** （オプション）を入力します。

   * 名前 – 最大 100 文字。一意である必要があります。大文字と小文字は区別されません

   * 説明 – 最大 300 文字

   >[!NOTE]
   >
   >名前および説明フィールドでは、英数字および特殊文字をサポートしています。 予約文字（`\ / : * ? " < > |`）は使用できません **_許可されていません_**。

   ![Web エクスペリエンスを作成ダイアログ &#x200B;](./assets/web-experience-create-dialog.png){width="400"}

<!-- What is this for? 1. Properties? -->

1. **[!UICONTROL プロパティ]** タブで、web エクスペリエンスの説明を入力します。

1. **[!UICONTROL アクション]** タブをクリックし、web エクスペリエンスに使用する **[!UICONTROL web チャネル]** を選択します。

   Web チャネルの設定は、設定されたページマッチングルールに基づいて、コンテンツの変更を適用する場所を決定します。 詳しくは、[web チャネル設定 &#x200B;](../admin/configure-channels-web.md) を参照してください。

   ![&#x200B; 選択された web チャネル設定 &#x200B;](./assets/web-experience-journey-node-actions-tab.png){width="700" zoomable="yes"}

1. Web の変更を定義するには、「**[!UICONTROL コンテンツを編集]**」をクリックします。

   エディターが「_[!UICONTROL コンテンツ]_」タブで開き、web エクスペリエンスの変更を定義できます。 デザインツールを使用して web エクスペリエンスコンテンツの変更を追加する方法について詳しくは、[web エクスペリエンスデザイン &#x200B;](./web-experience-design.md) を参照してください。

1. 右側のパネルで、定義および管理方法に応じて web エクスペリエンスのプロパティを設定します。

   * **[!UICONTROL ビジュアルエディター]** - web エクスペリエンス変更デザイン用に [&#x200B; ビジュアルエディターと非ビジュアルエディター &#x200B;](./web-experience-design.md#web-design-tools) を切り替えます。
   * **[!UICONTROL 訪問者リダイレクト]** – このオプションを有効にすると、「コンテンツ」タブで新しいバリエーションを作成する代わりに [&#x200B; 訪問者を別の既存の URL にリダイレクト &#x200B;](#redirect-to-url) できます。

   ![&#x200B; ビジュアルエディターとリダイレクト URL のプロパティの切り替え &#x200B;](./assets/web-experience-journey-node-content-properties.png){width="700" zoomable="yes"}

1. **[!UICONTROL Web ページを編集]** をクリックして [Web の変更をデザイン &#x200B;](./web-experience-design.md) します。

1. 変更が完了したら、エディターの上にある左矢印をクリックして、「コンテンツ」タブとパーソナライズされた web エクスペリエンスノードのプロパティに戻ります。

   上部の左矢印をクリックすると、ジャーニーキャンバスに戻ります。

## Web エクスペリエンスの編集

1. ジャーニーを開き、「**[!UICONTROL web エクスペリエンスをパーソナライズ]**」アクションノードを選択します。

1. Web チャネルの設定またはコンテンツを変更するには、「**[!UICONTROL web エクスペリエンスを編集]**」をクリックします。

1. 「**[!UICONTROL アクション]**」タブを選択し、必要に応じて web 設定を変更します。

1. 「**[!UICONTROL コンテンツ]**」タブを選択し、必要に応じてビジュアルデザインツールを使用します。

   * _ビジュアルエディター_ - 「**[!UICONTROL コンテンツを編集]**」をクリックします。
   * _非視覚的エディター_ - 「**[!UICONTROL 変更を追加]**」をクリックします。

   詳しくは、[web エクスペリエンスデザイン &#x200B;](./web-experience-design.md) を参照してください。

1. 変更の定義が完了したら、エディターの上にある左矢印をクリックして、「コンテンツ」タブと web エクスペリエンスのプロパティに戻ります。

   上部の左矢印をクリックすると、ジャーニーキャンバスに戻ります。

## URL にリダイレクト

Web エクスペリエンスを作成する際に、コンテンツエディターで新しいバリエーションを作成するのではなく、別の既存の URL に訪問者をリダイレクトできます。 このオプションは、ページ内のいくつかの要素を変更するだけで済むわけではなく、2 つの異なるエクスペリエンスを比較してコンテンツ実験を実行する場合に役立ちます。

例えば、次の 2 つの処理を含む web キャンペーンを作成します。

処理 A で、ターゲット母集団の半分のコンテンツエディターを使用して web エクスペリエンスを作成します。

処理 B で、ターゲット母集団の残りの半分に対して「_[!UICONTROL URL にリダイレクト]_」オプションを選択します。 Journey Optimizer B2B edition以外で作成した代替デザインを含むページの URL を入力します。

![&#x200B; 訪問者を特定の URL にリダイレクトするように訪問者リダイレクトを設定する &#x200B;](./assets/web-experience-journey-node-content-visitor-redirection.png){width="500" zoomable="yes"}

>[!NOTE]
>
>このオプションを選択すると、web サイトのプレビューは表示されず、「ビジュアルエディター _[!UICONTROL 切り替え]_ は無効になります。

Web キャンペーンがライブの場合、Journey Optimizer B2B editionで定義した web エクスペリエンスと、代替ページへのリダイレクトを使用した web エクスペリエンスのパフォーマンスをトラッキングできます。

## Web エクスペリエンスのテスト

Web エクスペリエンスのコンテンツデザインが完了したら、_コンテンツをシミュレート_ 機能を使用して、web ページの変更をプレビューできます。 パーソナライズされたコンテンツを挿入した場合は、テストプロファイルデータを使用して、コンテンツのレンダリング方法を確認できます。 シミュレーションツールは、web エクスペリエンスの「_[!UICONTROL コンテンツ]_」タブや、コンテンツビジュアルデザインエディターから使用できます。

1. 右上の **[!UICONTROL コンテンツをシミュレート]** をクリックします。

1. テストプロファイルを選択します。

1. テストプロファイルを追加し、テストプロファイルデータを使用して web ページを確認します。

<!-- This works differently than emails (rely on Marketo data), currently. Will expand when we figure it out -->

## Web エクスペリエンスのアクティベート

Web エクスペリエンスがアクティベートされ、（ジャーニーを公開 [&#x200B; する際にオーディエンスに表示さ &#x200B;](../journeys/create-publish-journey.md#publish-a-journey) ます。 ジャーニーを通じて web エクスペリエンスをアクティブ化する前に、次の点を考慮してください。

* 既に実行中の別のジャーニーと同じページに影響を与える web エクスペリエンスを持つジャーニーを公開すると、すべての変更が web ページに適用されます。

* 複数のジャーニーが web サイトの同じ要素を更新する場合は、最近適用された変更が優先されます。

### 配信要件

Web エクスペリエンス配信を有効にするには、次の設定を定義する必要があります。

* Adobe Experience Platform データ収集で、「Adobe Experience Platform B2B edition」オプションを有効にしたデータストリームがAdobe Journey Optimizer サービスで定義されていることを確認します。

  これにより、Adobe Experience Platform Edgeがインバウンドイベントを正しく処理できるようになります。 [詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/datastreams/configure)

* Adobe Experience Platformで、「_[!UICONTROL Active-On-Edge結合ポリシー]_ オプションが有効になっている結合ポリシーが 1 つあることを確認します。

  顧客/ プロファイル /結合ポリシーExperience Platformメニューでポリシーを選択します。 [詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/merge-policies/ui-guide#configure)

  この結合ポリシーは、Journey Optimizer B2B edition インバウンドチャネルで使用すると、エッジでインバウンド web エクスペリエンスを正しくアクティブ化して公開できます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/merge-policies/ui-guide)

### トラブルシューティング

Adobe Experience Platform Assurance内のEdge Delivery ビューを使用して、Journey Optimizer B2B edition web エクスペリエンスの配信のトラブルシューティングを行うことができます。 このプラグインを使用すると、リクエスト呼び出しを詳細に調べ、期待されるエッジ呼び出しを検証し、プロファイルデータを調べることができます。 このプロファイルデータには、ID マップ、セグメントメンバーシップおよび同意設定が含まれます。 リクエストに対して選定されたアクティビティと選定されていないアクティビティを確認することもできます。

AssuranceのEdge Delivery ビューについて詳しくは、[Experience Platform ドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/assurance/view/edge-delivery) を参照してください。
