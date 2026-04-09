---
title: メールコンテンツのダークモード
description: Journey Optimizer B2B editionのダークモードのメールデザインについて説明します。 レンダリングのプレビュー、設定のカスタマイズ、アクセシビリティの確保およびメールクライアント間のテスト。
feature: Email Authoring
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: ダークモード、メール、カラー、デザイン
exl-id: c9ffb883-d37f-48bc-b23d-6eccf7a04d9a
source-git-commit: 8073984ced07e86a3fa500c5bf0bd393abbe0990
workflow-type: tm+mt
source-wordcount: '1604'
ht-degree: 21%

---

# メールコンテンツのダークモード {#dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode"
>title="ダークモードに切り替え"
>abstract="ダークモードに切り替えると、レンダリング方法のプレビューや、特定のカスタム設定の定義ができます。 <br>最終的なレンダリングは、受信者のメールクライアントに応じて異なります。 すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_preview"
>title="ダークモードに切り替え"
>abstract="ダークモードに切り替えると、サポートされているメールクライアントでどのようにレンダリングされるかをプレビューできます。 <br>最終的なレンダリングは、受信者のメールクライアントに応じて異なります。 すべてのメールクライアントがダークモードをサポートしているわけではありません。"

_ダークモード_&#x200B;を使用すると、サポートメールクライアントまたはアプリで、テキスト、ボタン、その他のビジュアル要素の背景が暗く、色が明るいメールを表示できます。 このタイプのディスプレイは、目の疲れを軽減し、バッテリー寿命を節約し、低光量環境での読みやすさを向上させ、より快適な視聴体験を実現します。 主要なオペレーティングシステムやアプリでトレンドが高まる中、あらゆるユーザーに読みやすく視覚的に魅力的なコンテンツを提供することが、今日のメール設計における重要な検討事項となっています。

![明るいテーマと暗いテーマの両方でのコンテンツレンダリングを示す明るいモードと暗いモードのコンセプトダイアグラム &#x200B;](../assets/do-not-localize/light-dark-mode.svg){width="50%"}

[!DNL Journey Optimizer B2B Edition] ビジュアルデザイン空間で[電子メールコンテンツ &#x200B;](./email-authoring.md)を作成すると、_&#x200B;**[!UICONTROL ダークモード]**&#x200B;_&#x200B;表示に切り替えることができます。 このビューでは、ダークモードが有効になっているメールクライアントをサポートするための特定のカスタム設定を定義することもできます。

## メールクライアントの考慮事項

メールクライアントやアプリによって、ダークモードの適用方法には大きな違いがあります。 このため、ダークモードのレンダリングに対する期待は、慎重に考慮する必要があります。 メールデザイン分野でダークモードを使用する前に、次のメールクライアントのユースケースを検討してください。
<!--
* Check out the list of [email clients supporting dark mode](https://www.caniemail.com/search/?s=dark){target="_blank"}

* Learn more on Dark mode in this [Litmus blog post](https://www.litmus.com/blog/the-ultimate-guide-to-dark-mode-for-email-marketers){target="_blank"}
-->

+++ダークモードをサポートしていないクライアント

次のような一部のメールクライアントでは、この機能をまったくサポートしていません。

* [!DNL Yahoo! Mail]
* [!DNL AOL]

電子メールデザインでダークモードのカスタム設定を定義した場合、これらの電子メールクライアントはダークモードのレンダリングを表示できません。<!--Regardless of whether the interface is in light or dark mode, your email will render the same.-->

+++

+++独自のダークモード {#default-support}を適用しているクライアント

一部のメールクライアントでは、受信したすべてのメールに対して、独自のデフォルトのダークモードを体系的に適用しています。 ダークモードの設定や外部設定に応じて、色、背景、画像などの要素を自動的に調整します。 顧客は次の通りです。

* Gmail （デスクトップ web メール、iOS、Android™、モバイルウェブメール）
* Windows 版 Outlook
* Outlook Windows メール

<!--It is important to note that less than 25% of email clients offer customization options for dark mode. Clients such as Gmail implement their own dark mode rendering, which is not subject to external modification.-->
この場合、クライアントダークモード設定は、[!DNL Journey Optimizer B2B Edition]で定義したカスタムダークモード設定を上書きします

+++

+++カスタムダークモードをサポートするクライアント

最も人気のあるメールクライアントの多くは、`@media (prefers-color-scheme: dark)` クエリでカスタムダークモードをレンダリングするオプションを提供しています。これは、[!DNL Journey Optimizer B2B Edition]のメールスタイルで使用される方法です。 このクライアントのリストには、次のものが含まれます。

* Apple メール macOS
* Apple メール iOS
* Outlook macOS
* Outlook.com
* Outlook iOS
* Outlook Android™

この場合、[!DNL Journey Optimizer B2B Edition]で定義した特定の設定がレンダリングされます。 ただし、メールクライアントごとに制限が適用されることがあります。 例えば、一部のクライアント（Apple Mail 16 （macOS 13）など）では、画像がメールコンテンツに存在する場合、ダークモードが生成されません。

最適な結果を得るには、ターゲットとするメールクライアントでコンテンツをテストします。 各クライアントの最終結果にできるだけ近いシミュレーションを表示するには、メールデザイン領域で[Litmus メールテストレンダリング &#x200B;](./email-test-rendering.md)統合を使用します。

+++

## ダークモードのデザイン

[!DNL Journey Optimizer B2B Edition]でダークモード用にメールコンテンツのスタイルを設定すると、ビジュアルデザインスペースには2種類のツールが用意されます。

* [&#x200B; プレビュー関数](#preview-default-dark-mode)を使用して、ほとんどのサポート電子メールクライアントのデフォルトのダークモードのレンダリングを確認します。

* サポートするメールクライアントのデフォルト設定を上書きする場合は、メールコンテンツにカスタムダークモード設定を定義して適用します。 [詳細情報](#define-custom-dark-mode)

### デフォルトのダークモードのプレビュー {#preview-dark-mode}

<!--
 Should work with templates and themes, NOT for LP and fragments - but TBC with eng.
>[!NOTE]
>
>Currently you may not be able to switch to dark mode if you select an [email template](use-email-templates.md) or if you apply a [theme](apply-email-themes.md).
-->

1. 電子メールデザイン画面で電子メールコンテンツを開きます。

   キャンバスの右上には、明るい（デフォルト）と暗いモードの間でコンテンツ表示を切り替える明るい暗いセレクターがあります。

   ![右上隅にライトモードセレクターが表示されている電子メールデザインキャンバス &#x200B;](./assets/email-color-mode-light-selector.png){width="700" zoomable="yes"}

1. セレクターを&#x200B;_ダークモード_&#x200B;に変更します（![&#x200B; ダークモードアイコン &#x200B;](../assets/do-not-localize/icon-content-dark-mode.svg)）。

   キャンバスには、デフォルトのダークモード preview.xを使用してコンテンツが表示されます。

   デフォルトでは、ダークモードのプレビューでは、画像とアイコンを除くすべての要素に`full color invert`の配色が適用されます。 この配色は、明るい要素と暗い要素を持つ領域を検出し、それらを反転させます。 明るい背景が暗くなり、暗いテキストが明るくなり、暗い背景が明るくなり、明るいテキストが暗くなります。

   ![&#x200B; ダークモードのセレクターと、ダークモードで表示される電子メールコンテンツを示す電子メールデザインキャンバス &#x200B;](./assets/email-color-mode-dark-selector.png){width="700" zoomable="yes"}

>[!CAUTION]
>
>最終的なレンダリングは、受信者のメールクライアントによって異なる場合があります。 各メールクライアントの最終結果にできるだけ近いシミュレーションを表示するには、[Litmus テストメールレンダリング &#x200B;](./email-test-rendering.md)統合を使用します。

### カスタムダークモード設定の定義 {#custom-dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_image"
>title="特定の画像をダークモードで使用"
>abstract="ダークモードがオンの場合に表示する別の画像を選択できます。 <br> ダークモード用に特定の画像を追加しても、すべての電子メールクライアントで正しくレンダリングされるとは限りません。 すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。"

ダークモードに切り替えた後、受信者のメールクライアントでダークモードが有効になっている場合にのみ表示されるコンテンツの特定のスタイル要素を編集できます（この機能をサポートしている場合）。

>[!NOTE]
>
>ダークモードの最終的なレンダリングは、各メールクライアントに応じて異なるので、結果はクライアントごとに異なる場合があります。 詳しくは、[電子メールクライアントの考慮事項](#email-client-considerations)を参照してください。

メール デザイン スペースのカスタム ダークモードのスタイル設定では、<!-- `@media (prefers-color-scheme: dark)` method-->を使用します `@media (prefers-color-scheme: dark)` CSS クエリ。メールクライアントがダークモードに設定されているかどうかを検出し、メールで定義されているダークテーマのデザインを適用します。

_ダークモードのカスタム設定を定義するには&#x200B;:_

1. 必要に応じて、デザインキャンバスの右上にある&#x200B;_ダークモード_ （![&#x200B; ダークモードアイコン &#x200B;](../assets/do-not-localize/icon-content-dark-mode.svg)）にセレクターを移動します。

1. テキスト、背景、ボタンなど、スタイル設定カラー属性を編集できます。

   色とフォントのオプションを表示する![&#x200B; ダークモードのテキストスタイル設定パネル &#x200B;](./assets/email-color-mode-dark-text-settings.png){width="700" zoomable="yes"}

1. 画像とアイコンの場合は、ダークモード専用の特定のアセットを定義します。

   画像やアイコンの色は変更できませんが、ダークモードで使用する代替アセットを定義できます。 アイコンの様々な色の組み合わせを試したり、写真画像の色と彩度を調整したりできます。

   異なる色の組み合わせを持つ![&#x200B; アイコン &#x200B;](../assets/do-not-localize/color-contrast-images-diagram.svg){width="80%"}

   任意の画像を選択し、**[!UICONTROL 設定]** ペインの専用トグルを使用して&#x200B;**[!UICONTROL ダークモード]**&#x200B;に切り替えます。 次に、別の画像アセットを選択します。

   ![&#x200B; ダークモードの画像設定で、ダークモードに別の画像アセットを選択するオプションが表示されている](./assets/email-color-mode-dark-image-settings.png){width="700" zoomable="yes"}

   画像アセットの選択について詳しくは、[画像アセットの追加](./email-authoring.md#add-image-assets)を参照してください。

1. デザインの変更中の任意の時点で、**[!UICONTROL ライブビューに切り替え]**&#x200B;を選択して、様々なデバイスサイズでコンテンツがどのようにレンダリングされるかを確認します。

   このビューから、セレクターを&#x200B;_ダークモード_ （![&#x200B; ダークモードアイコン &#x200B;](../assets/do-not-localize/icon-content-dark-mode.svg)）に変更して、様々なデバイスでコンテンツのダークモードバージョンをプレビューします。

   ![異なるデバイスサイズでダークモードの電子メールコンテンツを表示するライブビューパネル &#x200B;](./assets/email-color-mode-dark-live-view.png){width="800" zoomable="yes"}

   >[!CAUTION]
   >
   >ライブビューは、様々なデバイスサイズをまたいでレンダリングがどのように表示される可能性があるかを比較するのにデザインされた汎用プレビューです。 最終的なレンダリングは、受信者のメールクライアントによって異なる場合があります。

1. ダークモードの変更が完了したら、「**[!UICONTROL コンテンツをシミュレート]**」をクリックします。

   ![&#x200B; ダークモードのテスト用に「コンテンツをシミュレート」ボタンがハイライト表示されたメールデザインキャンバス &#x200B;](./assets/email-color-mode-dark-simulate-content.png){width="700" zoomable="yes"}

   プレビューツールと校正ツールを使用して、メールデザインをテストします。 詳しくは、[電子メールコンテンツのプレビューとテスト &#x200B;](./email-simulate-content.md)を参照してください。

1. Litmus Enterprise アカウントをお持ちの場合は、「**[!UICONTROL メールをレンダリング]**」を選択して、Litmus内の様々なメールクライアントの最終的なダークモードのレンダリングを確認します。

   詳しくは、[Litmus](./email-test-rendering.md)を使用したメールのレンダリングのテストを参照してください。

   >[!CAUTION]
   >
   >シミュレーションでは、メールがダークモードでどのように表示されるかに非常に近いものの、実際のレンダリングは、メールサービスプロバイダーやデバイスレベルの設定の違いによって異なる場合があります。

## ベストプラクティス {#best-practices}

主要なメールクライアント間でダークモードの採用が増加するにつれて、[カスタムダークモード](#define-custom-dark-mode)を使用しているかどうかに関係なく、明るい環境と暗い環境の両方でメールがどのようにレンダリングされるかを考慮することが重要になります。

ダークモードでは、色、背景、画像が変更される可能性があり、場合によってはデザインの選択が上書きされることもあります。 視覚的な一貫性、アクセシビリティ、ブランドの整合性を確保するには、次のベストプラクティスに従います。

| 実践 |            |
| -------- | ---------- |
| 画像とロゴの最適化 | チェックリスト：<ul><li>ロゴやアイコンを、透明な背景のPNG ファイルとして保存して、暗いモードで白いボックスが表示されないようにします。 <li>白色の背景または明るい背景がハードコードされた画像は回避します。 <li>透明度がオプションでない場合は、不自然な色の反転を防ぐために、デザインでは単色の背景に画像を配置します。 |
| 背景を見る | チェックリスト：<ul><li>ライトモードとダークモードの両方で読みやすくするには、テキストと背景色の間に十分なコントラストを確保します。 <li>重要なコンテンツについては、背景色にのみ依存することは回避します。 一部のクライアントでは、ダークモードで背景色を上書きするので、重要な情報が表示されたままになります。 |
| ダークモードでアクセスしやすいコンテンツをデザイン | チェックリスト：<ul><li>色覚異常のある人物でも簡単に区別できる色の組み合わせを使用します。 <li>明るい背景と暗い背景の両方に対してコントラストを確保するのに、ミッドトーンパレットを使用します。 <li>高コントラストでアクセスしやすい色の組み合わせを使用して、読みやすさを向上させ、[!DNL Web Content Accessibility Guidelines (WCAG)]標準を満たします。 [!DNL WebAIM Contrast Checker]などのツールを使用して、色のコントラストを検証します。 <li>読みやすさに影響する場合があるので、細いフォントは回避します。 ブランドに細いフォントが必要な場合は、ダークモードで太字にします。 <li>純粋な黒の上で純粋な白をスキップすると、目の緊張を引き起こす可能性があり、一部のメールクライアントでは自動的に反転する可能性があります。 <li>ダークモードがサポートされていない場合は、アクセスできるフォールバックスタイル設定を指定します。 |
| ダークモード環境でのメールのテスト | チェックリスト：<ul><li>電子メールデザイン領域で[&#x200B; ダークモードのプレビュー](#preview-dark-mode)を使用します。このカラースキームは、反転したカラースキームを使用して問題を早期に検出します。 <li>「[[!UICONTROL &#x200B; メールをレンダリング &#x200B;]](./email-test-rendering.md)」オプションを使用してLitmus Enterprise アカウントを使用し、主要なメールクライアント（Apple Mail、Gmail、Outlookなど）でデザインをシミュレートし、ダークモードでカラーと画像がどのように動作するかを確認します。 |

<!--
KEEP dark mode accessibility best practices IN ONE SINGLE LOCATION - for now listed on this page.
If needed, it can be moved to the Design accessible content page:
The best practices for designing accesible content in dark mode are listed in [this section](accessible-content.md#dark-mode).
-->

<!--
**Inline critical styles**

Inline CSS helps maintain more control over styling, as some clients strip external styles in dark mode.
-->
