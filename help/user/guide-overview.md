---
title: Adobe Journey Optimizer B2B Edition ドキュメント
description: Journey Optimizer B2B Edition の完全なドキュメント - オンボーディング、購買グループの作成、アカウントジャーニーの作成、コンテンツの管理に使用できるリソースを探索します。
exl-id: 3d7b6c82-95c3-4d89-b3dc-7fd5b0aef615
source-git-commit: 80716587f797d3009e6a57f8a20f72f2f982bb37
workflow-type: tm+mt
source-wordcount: '917'
ht-degree: 26%

---

# Adobe Journey Optimizer B2B Edition ドキュメント

[!DNL Adobe Journey Optimizer B2B Edition]は、マーケティング部門と営業部門がカスタマーライフサイクル全体にわたってアカウントベースのエクスペリエンスを調整し、特定製品の購買グループを選定できる初めてのアプリケーションです。 AIを活用して、ターゲットアカウント内の購買グループにエンゲージし、選定を行うことで、より質の高いパイプラインの生成や、より優れた獲得、拡大、維持戦略の策定に役立ちます。 また、営業部門とマーケティング部門のインサイトを共有することもできます。

このドキュメントでは、アプリケーションを習得するための情報を提供します。 マーケター、ビジネス開発担当者、データアナリスト、業務管理者向けに設計されています。

## 最新情報

[!DNL Journey Optimizer B2B Edition] アプリケーションとドキュメントの最新の追加と機能強化のサンプルをご覧ください。

>[!BEGINTABS]

>[!TAB AI エージェント ]

[Experience Platform Agent Orchestrator](https://experienceleague.adobe.com/ja/docs/experience-cloud-ai/experience-cloud-ai/home#agent-orchestrator){target="_blank"}では、AI アシスタントのインターフェイスにより、専門の担当者が自動的に呼び出され、適切な回答とインサイトを入手できます。 Agent Orchestratorは、会話履歴を記憶するため、コンテキストを繰り返すことなく自然に以前の質問を作成でき、複数の担当者からのインサイトを組み合わせて、明確で統一された回答を提供します。 [!DNL Journey Optimizer B2B Edition]のコンテキストでは、特定のB2B タスクとドメイン用に構築された3つのエージェントがあります。

* [Audience Agent B2B](./agents/audience-agent-b2b.md)
* [Journey Agent B2B](./agents/journey-agent.md)
* [Account Qualification Agent](./agents/sales-qualifier.md#account-qualification-agent)

>[!TAB WhatsApp チャネル ]

開発者や製品管理者がMeta Business Manager アカウントとの統合を設定する場合、マーケターはMeta APIを使用して、アカウントジャーニーにWhatsApp メッセージをコンテンツチャネルとして含めることができます。 WhatsAppは、アカウントメンバーにジャーニーコンテンツを直接配信するための利用可能なチャネルとして、メールとSMSを統合しています。

[!BADGE 詳細情報]{type=Informative url="/help/user/admin/configure-channels-whatsapp.md" tooltip="WhatsApp チャネルについて説明します"}

>[!TAB 生成AI モデル ]

メールデザイナーは、メールコンテンツ用の画像を生成する際に、標準[!DNL Firefly] モデル、ブランド固有のアセットでトレーニングされたカスタム [!DNL Firefly] モデル、承認済みのサードパーティ画像モデルから選択できるようになりました。 この選択範囲により、一般的なコンテンツのニーズから、ブランド化されたユースケースや特殊なユースケースまで、特定のデザインシナリオに適合するモデルをコントロールすることができます。

[!BADGE 詳細情報]{type=Informative url="/help/user/content/generative-ai-models.md" tooltip="生成AI モデルの選択方法について詳しく見る"}

>[!TAB 送信時間の最適化]

対面ジャーニーの&#x200B;_メール送信_ アクションノードの場合、送信時間の最適化を使用してメール配信のタイミングをパーソナライズできるようになりました。 これにより、あらゆる顧客に同時に配信するのではなく、各顧客がエンゲージメントする可能性が最も高いタイミングを予測し、それに応じて配信をスケジュール配信できます。

[!BADGE 詳細情報]{type=Informative url="/help/user/content/email-send-time-optimization.md" tooltip="送信時間の最適化について詳しく見る"}

>[!TAB ジャーニー再入力]

アカウントジャーニーワークフローを通じて、アカウント/人物を複数回送信できるようになりました。 再入力は、クオリフィケーション基準の再評価や再利用可能なナーチャリングワークフローなど、複数のシナリオに対応します。 再入力設定を使用して基準、制限、待機時間を設定し、アカウントが管理された方法でジャーニーに再評価されるようにします。

[!BADGE 詳細情報]{type=Informative url="/help/user/journeys/journey-re-entry.md" tooltip="ジャーニーの再入力について詳しく見る"}

>[!TAB  ブランドのテーマ ]

技術的な知識がなくても、特定のブランドやスタイルに合わせて、再利用可能なメールコンテンツのデザインガイドラインを作成できます。 マーケターは、テーマを活用することで、視覚的に魅力的でブランドに即した電子メールをより早く、より少ない労力で利用し、独自のデザインニーズに合わせた高度なカスタマイズオプションを利用できます。

[!BADGE 詳細情報]{type=Informative url="/help/user/content/brand-themes.md" tooltip="ブランドのテーマについて詳しく見る"}

>[!TAB  ペルソナマッピング ]

マーケターは、背景、責任、課題、好みのコミュニケーションチャネルなど、詳細なプロファイルを定義できます。 これらの定義を使用すると、管理者は[!DNL Journey Optimizer B2B Edition]のユーザー属性に従ってペルソナを設定できるため、ロールテンプレートはこれらのペルソナをキャプチャする合理化された一貫したロール条件を使用できます。

[!BADGE 詳細情報]{type=Informative url="/help/user/admin/persona-mapping.md" tooltip="ペルソナマッピングについて詳しく見る"}

>[!ENDTABS]

## さらに詳しく {#section-explore}

:::: landing-cards-container
:::
![icon](https://cdn.experienceleague.adobe.com/icons/list-check.svg?lang=ja)

最新のリリースノート

Adobe Journey Optimizer B2B editionの最新のリリースノート、新機能、改善点を常に把握できます。

[リリースノートを見る](./release-notes/release-notes.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/circle-play.svg?lang=ja)

基本を学ぶ

Journey Optimizer B2B editionのオンボーディングガイダンス（管理者およびマーケター向け）をご確認ください。

[基本を学ぶ](./start/get-started.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/gear.svg?lang=ja)

XDM フィールドの設定

Adobe Journey Optimizer B2B editionで使用するXDM スキーマとフィールドをアクティブ化するためのシステム設定を実装します。

[XDM フィールド管理の表示](./admin/xdm-field-management.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/envelope.svg?lang=ja)

通信チャネル

電子メール、SMS、WhatsAppなどのチャネルを設定、管理し、顧客とのパーソナライズされたインタラクションを実現します。

[電子メール チャネルの設定](./admin/configure-channels-emails.md)
[SMS チャネルの設定](./admin/configure-channels-sms.md)
[WhatsApp チャネルの設定](./admin/configure-channels-whatsapp.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/code-branch.svg?lang=ja)

アカウントジャーニーの作成

パーソナライズされたアカウントジャーニーを設計、編成、管理、最適化。

[ジャーニーを探索](./journeys/journeys-overview.md)
:::

:::
![icon](https://cdn.experienceleague.adobe.com/icons/users.svg?lang=ja)

購買グループについて

効果的なターゲティングのための購買グループの作成、管理、最適化に関する詳細なガイダンス。

[購買グループについてさらに詳しく](./buying-groups/buying-groups-overview.md)
:::

::::

<!--
:::
![icon](https://cdn.experienceleague.adobe.com/icons/image.svg?lang=ja)

Design Content

Learn how to author and manage content for personalized customer experiences orchestrated through journeys.

[Explore Content Components](./content/content-components.md)
::: 
-->

## 概要デモ

購買グループのコンポーネントと、アカウントジャーニーの作成の基本について説明します。

>[!VIDEO](https://video.tv.adobe.com/v/3432054?quality=12)

## ドキュメントを見る

<table style="table-layout:auto">
  <tr style="border: 0;">
    <td>
      <img src="../assets/do-not-localize/icon-quick-start.svg" width="35px" alt="基本を学ぶ"><br/>
      <strong>基本を学ぶ</strong><br/><a href="home-page.md">ログインとホームページ</a><br/><a href="./start/get-started.md">オンボーディングガイダンス</a><br/><a href="./ai-assistant/ai-assistant-overview.md">AI アシスタント</a>
    </td>
    <!--
    <td>
      <img src="../assets/do-not-localize/icon-configure.svg" width="35px"><br/>
      <strong>Configuration<br/>administration</strong><br/><a href="using/configuration/channel-surfaces.md">Channel surfaces</a> - <a href="using/configuration/about-data-sources-events-actions.md">Configure journeys</a>  - <a href="using/administration/permissions-overview.md">Access control</a> - <a href="using/administration/sandboxes.md">Sandboxes management</a>
    </td>
    -->
    <td>
      <img src="../assets/do-not-localize/icon_audience.svg" width="35px" alt="購買グループ"><br/>
      <strong>購買グループ</strong><br/><a href="./buying-groups/buying-groups-overview.md">購買グループの概要</a><br/><a href="./buying-groups/buying-groups-role-templates.md">役割テンプレート</a><br/><a href="./buying-groups/solution-interests.md">ソリューションに対する関心</a><br/><a href="./buying-groups/buying-groups-create.md">購買グループの作成</a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-paths.svg" width="35px" alt="アカウントジャーニー"><br/>
      <strong>アカウントジャーニー</strong><br/><a href="./journeys/journeys-overview.md">ジャーニーの概要</a><br/><a href="./journeys/create-publish-journey.md#create-a-journey">アカウントジャーニーの作成</a><br/><a href="./journeys/journey-nodes.md">ジャーニーノード</a>
    </td>
  </tr>
  <tr style="border: 0;">
    <td>
      <img src="../assets/do-not-localize/icon-campaign.svg" width="35px" alt="ジャーニーコンテンツ"><br/>
      <strong>ジャーニーコンテンツ</strong><br/><a href="./content/add-email.md">メールチャネル</a><br/><a href="./content/ai-assistant-emails.md">メール用 AI アシスタント</a><br/><a href="./content/genstudio-email-workflow.md">GenStudio のメールエクスペリエンス</a><br/><a href="./content/sales-alert-email.md">セールスアラートメール</a><br/><a href="./content/sms-authoring.md">SMS チャネル</a>
    </td>
        <td>
      <img src="../assets/do-not-localize/icon_assets.svg" width="35px" alt="コンテンツ管理"><br/>
      <strong> コンテンツ管理</strong><br/><a href="./content/assets-overview.md">Assetsの概要</a><br/><a href="./content/email-templates.md"> メールテンプレート </a><br/><a href="./content/fragments.md"> ビジュアルフラグメント </a><br/><a href="./content/conditional-content.md">条件付きコンテンツ </a><br/><a href="./content/brand-themes.md"> ブランドテーマ </a>
    </td>
    <td>
      <img src="../assets/do-not-localize/icon-offer.svg" width="35px" alt="インサイトとダッシュボード"><br/>
      <strong> インサイト </strong><br/><a href="./dashboards/intelligent-dashboard.md"> インテリジェントダッシュボード </a><br/><a href="./dashboards/engagement-dashboard.md"> エンゲージメントダッシュボード </a><br/><a href="./dashboards/buying-groups-dashboard.md">購買グループダッシュボード </a><br/><a href="./dashboards/journeys-dashboard.md">ジャーニーダッシュボード </a><br/><a href="./buying-groups/incrm-insights.md">CRM内インサイト </a>
    </td>

</tr>
</table>

## その他のリソース

<table style="table-layout:fixed">
<tr><td><strong>Adobe Journey Optimizer B2B edition</strong><br/>
<a href="https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b-learn/tutorials/overview" target="_blank"> ビデオとチュートリアル </a> - <a href="https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer-b2b.html" target="_blank">製品の説明</a> <!-- - <a href="https://www.adobe.com/content/dam/cc/en/security/pdfs/AJO_SecurityOverview.pdf" target="_blank">Security overview (PDF)</a> - <a href="https://developer.adobe.com/journey-optimizer-apis/" target="_blank">APIs reference</a> - <a href="https://experienceleague.adobe.com/tools/ajo-schemas/schema-dictionary.html?lang=ja" target="_blank">Journey Optimizer Schema Dictionary</a> -->
</td>
<td><strong>Adobe Experience Platform</strong><br/>
<a href="https://experienceleague.adobe.com/ja/docs/experience-platform/landing/home" target="_blank"> ドキュメント </a> - <a href="https://business.adobe.com/jp/products/experience-platform/documentation-and-developer-resources.html" target="_blank">開発者リソース </a>
</td></tr>
<tr><td><strong>Adobe Real-Time Customer Data Platform</strong><br/>
<a href="https://experienceleague.adobe.com/ja/docs/experience-platform/rtcdp/home" target="_blank"> ドキュメント </a> - <a href="https://experienceleague.adobe.com/ja/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/overview" target="_blank">開発者チュートリアル </a>
</td><td><strong>Adobe Marketo Engage</strong><br/>
<a href="https://experienceleague.adobe.com/ja/docs/marketo/using/home" target="_blank"> ユーザードキュメント </a> - <a href="https://experienceleague.adobe.com/ja/docs/marketo-developer/marketo/home" target="_blank">開発者ドキュメント </a>
</td>
</tr></table>

