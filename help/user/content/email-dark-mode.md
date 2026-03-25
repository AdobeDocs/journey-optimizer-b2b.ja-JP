---
title: メールコンテンツのダークモード
description: Journey Optimizer B2B editionのダークモードのメールデザインについて説明します。 レンダリングのプレビュー、設定のカスタマイズ、アクセシビリティの確保およびメールクライアント間のテスト。
feature: Email Authoring
topic: Content Management
role: User
level: Beginner, Intermediate
keywords: ダークモード、メール、カラー、デザイン
exl-id: c9ffb883-d37f-48bc-b23d-6eccf7a04d9a
source-git-commit: b369ef39715f327fcff7237e827bebf4e82c27f6
workflow-type: tm+mt
source-wordcount: '1604'
ht-degree: 17%

---

# メールコンテンツのダークモード {#dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode"
>title="ダークモードに切り替え"
>abstract="ダークモードに切り替えて、レンダリング方法をプレビューしたり、特定のカスタム設定を定義したりできます。<br>最終的なレンダリングは、受信者のメールクライアントによって異なります。 すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_preview"
>title="ダークモードに切り替え"
>abstract="ダークモードに切り替えて、サポートメールクライアントでのレンダリング方法をプレビューします。<br>最終的なレンダリングは、受信者のメールクライアントによって異なります。 すべてのメールクライアントがダークモードをサポートしているわけではありません。"

_ダークモード_&#x200B;を使用すると、サポートメールクライアントまたはアプリで、テキスト、ボタン、その他のビジュアル要素の背景が暗く、色が明るいメールを表示できます。 このタイプのディスプレイは、目の疲れを軽減し、バッテリー寿命を節約し、低光量環境での読みやすさを向上させ、より快適な視聴体験を実現します。 主要なオペレーティングシステムやアプリでトレンドが高まる中、あらゆるユーザーに読みやすく視覚的に魅力的なコンテンツを提供することが、今日のメール設計における重要な検討事項となっています。

![明るいテーマと暗いテーマの両方でのコンテンツレンダリングを示す明るいモードと暗いモードのコンセプトダイアグラム &#x200B;](../assets/do-not-localize/light-dark-mode.svg){width="50%"}

ビジュアルデザイン空間で[!DNL Journey Optimizer B2B Edition]電子メールコンテンツ [&#128279;](./email-authoring.md)を作成すると、_&#x200B;**[!UICONTROL ダークモード]**&#x200B;_&#x200B;表示に切り替えることができます。 このビューでは、ダークモードが有効になっているメールクライアントをサポートするための特定のカスタム設定を定義することもできます。

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
In this case, the client dark mode settings override the custom dark mode settings that you define in [!DNL Journey Optimizer B2B Edition]

+++

+++Clients that support custom dark mode

Many of the most popular email clients offer the option to render custom dark mode with the `@media (prefers-color-scheme: dark)` query, which is the method used by the [!DNL Journey Optimizer B2B Edition] email styles. This list of clients includes:

* Apple メール macOS
* Apple メール iOS
* Outlook macOS
* Outlook.com
* Outlook iOS
* Outlook Android™

In this case, the specific settings you define in the [!DNL Journey Optimizer B2B Edition] are rendered. However, some restrictions could apply according to each email client. For example, some clients (such as Apple Mail 16 (macOS 13)) do not generate dark mode if images are present in the email content.

For optimal results, test your content with the email clients that you are targeting. To see a simulation that comes as close as possible to the final result for each client, use the [Litmus email test rendering](./email-test-rendering.md) integration in the email design space.

+++

## Design for dark mode

As you style your email content for dark mode in [!DNL Journey Optimizer B2B Edition], the visual design space provides two types of tools:

* Use the [preview function](#preview-default-dark-mode) to review the default dark mode rendering for most supporting email clients.

* If you want to override the default settings of supporting email clients, define and apply custom dark mode settings to your email content. [詳細情報 &#x200B;](#define-custom-dark-mode)

### デフォルトのダークモードのプレビュー {#preview-dark-mode}

<!-- Should work with templates and themes, NOT for LP and fragments - but TBC with eng. 
>[!NOTE]
>
>Currently you may not be able to switch to dark mode if you select an [email template](use-email-templates.md) or if you apply a [theme](apply-email-themes.md).-->

1. Open the email content in the email design space.

   At the top right of the canvas, there is a light-dark selector that toggles the content display between light (default) and dark mode.

   ![Email design canvas showing the light mode selector in the top right corner](./assets/email-color-mode-light-selector.png){width="700" zoomable="yes"}

1. Change the selector to _Dark mode_ ( ![Dark mode icon](../assets/do-not-localize/icon-content-dark-mode.svg) ).

   The canvas displays the content using the default dark mode preview.x

   By default, the dark mode preview applies the `full color invert` color scheme to all elements except images and icons. This color scheme detects areas with light and dark elements and inverts them. Light backgrounds become dark and dark text becomes light, or dark backgrounds become light and light text becomes dark.

   ![Email design canvas showing the dark mode selector and email content displayed in dark mode](./assets/email-color-mode-dark-selector.png){width="700" zoomable="yes"}

>[!CAUTION]
>
>The final rendering could vary according to the recipient&#39;s email client. To see a simulation that comes as close as possible to the final result for each email client, use the [Litmus test email rendering](./email-test-rendering.md) integration.

### ダークモードのカスタム設定の定義 {#custom-dark-mode}

>[!CONTEXTUALHELP]
>id="ajo-b2b_dark_mode_image"
>title="特定の画像をダークモードで使用"
>abstract="ダークモードがオンの場合に表示する別の画像を選択できます。<br>ダークモード用に特定の画像を追加しても、すべてのメールクライアントで正しくレンダリングされるとは限りません。 すべてのメールクライアントがカスタムダークモードをサポートしているわけではありません。"

After switching to dark mode, you can choose to edit specific styling elements of your content that are displayed only when dark mode is enabled in the recipient&#39;s email client (provided it supports that feature).

>[!NOTE]
>
>ダークモードの最終的なレンダリングは、各メールクライアントに応じて異なるので、結果はクライアントごとに異なる場合があります。 Review the [email client considerations](#email-client-considerations) for more information.

The custom dark mode styling in the email design space uses the<!-- `@media (prefers-color-scheme: dark)` method--> `@media (prefers-color-scheme: dark)` CSS query, which detects if the email client is set to dark mode and applies the dark-themed design that is defined in your email.

_To define custom dark mode settings :_

1. If needed, move the selector to _Dark mode_ ( ![Dark mode icon](../assets/do-not-localize/icon-content-dark-mode.svg) ) at the top right of the design canvas.

1. Edit any styling color attributes, such as text, backgrounds, or buttons.

   ![Dark mode text styling settings panel showing color and font options](./assets/email-color-mode-dark-text-settings.png){width="700" zoomable="yes"}

1. For the images and icons, define specific assets for dark mode only.

   You cannot change the colors of images and icons, but you can define alternative assets to be used for dark mode. You can experiment with different color combinations for your icons or make adjustments for color and saturation for photographic images.

   ![Icons with different color combinations](../assets/do-not-localize/color-contrast-images-diagram.svg){width="80%"}

   Select any image and switch to **[!UICONTROL Dark mode]** using the dedicated toggle in the **[!UICONTROL Settings]** pane. Then, select a different image asset.

   ![Dark mode image settings showing option to select different image asset for dark mode](./assets/email-color-mode-dark-image-settings.png){width="700" zoomable="yes"}

   See [Add image assets](./email-authoring.md#add-image-assets) for more information about selecting an image asset.

1. At any point during your design changes, select **[!UICONTROL Switch to live view]** to check how your content might render on various device sizes.

   From this view, change the selector to _Dark mode_ ( ![Dark mode icon](../assets/do-not-localize/icon-content-dark-mode.svg) ) to preview the dark mode version of your content across the different devices.

   ![Live view panel showing email content in dark mode across different device sizes](./assets/email-color-mode-dark-live-view.png){width="800" zoomable="yes"}

   >[!CAUTION]
   >
   >ライブビューは、様々なデバイスサイズをまたいでレンダリングがどのように表示される可能性があるかを比較するのにデザインされた汎用プレビューです。 最終的なレンダリングは、受信者のメールクライアントによって異なる場合があります。

1. ダークモードの変更が完了したら、「**[!UICONTROL コンテンツをシミュレート]**」をクリックします。

   ![&#x200B; ダークモードのテスト用に「コンテンツをシミュレート」ボタンが強調表示された電子メールデザインキャンバス &#x200B;](./assets/email-color-mode-dark-simulate-content.png){width="700" zoomable="yes"}

   プレビューツールと校正ツールを使用して、メールデザインをテストします。 詳しくは、[&#x200B; メールコンテンツのプレビューとテスト &#x200B;](./email-simulate-content.md)を参照してください。

1. Litmus Enterprise アカウントをお持ちの場合は、「**[!UICONTROL メールをレンダリング]**」を選択して、Litmus内の様々なメールクライアントの最終的なダークモードのレンダリングを確認します。

   詳しくは、[Litmusを使用したメールのレンダリングのテスト &#x200B;](./email-test-rendering.md)を参照してください。

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
| ダークモード環境でのメールのテスト | チェックリスト：<ul><li>電子メールデザイン領域では、[&#x200B; ダークモードのプレビュー](#preview-dark-mode)を使用します。このカラースキームを反転して、問題を早期に検出します。 <li>「[[!UICONTROL &#x200B; メールをレンダリング &#x200B;]](./email-test-rendering.md)」オプションを使用してLitmus Enterprise アカウントを使用し、主要なメールクライアント（Apple Mail、Gmail、Outlookなど）でデザインをシミュレートし、ダークモードでカラーや画像がどのように動作するかを確認します。 |

<!--KEEP dark mode accessibility best practices IN ONE SINGLE LOCATION - for now listed on this page.
If needed, it can be moved to the Design accessible content page:
The best practices for designing accesible content in dark mode are listed in [this section](accessible-content.md#dark-mode).-->

<!--**Inline critical styles**

Inline CSS helps maintain more control over styling, as some clients strip external styles in dark mode.-->
