---
title: Journey Optimizer B2B Edition リリースノート
description: Adobe Journey Optimizer B2B Edition の最新機能、機能強化、バグ修正について説明します。新機能や製品の改善点に関する最新情報を常に提供します。
role: User, Admin
exl-id: 7d3f1c26-d8a6-4065-a70f-5b30cb975dc8
source-git-commit: 4033d0eb711120d615851d614aa6abbcf07f6ea0
workflow-type: tm+mt
source-wordcount: '3778'
ht-degree: 92%

---

# Journey Optimizer B2B Edition リリースノート

Adobe Journey Optimizer B2B Edition では、新機能、既存機能の強化およびバグ修正が継続的に提供されます。

Journey Optimizer B2B Edition は、[!DNL Adobe Experience Platform] 上にネイティブに作成され、最新のイノベーションと改善点を継承しています。次の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/latest){target="_blank"}を参照してください。

使用権限、パフォーマンスガードレール、制限事項について詳しくは、[製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}を参照してください。

## エージェント型 AI 機能

AI アシスタントインターフェイス内の Journey Optimizer B2B Edition では、次のエージェント型 AI 機能が使用できるようになりました。

| エージェント | 更新 | 説明 |
| ----- | ------ | ----------- |
| Journey Build Agent | 新規 | Journey Build Agent は、ジャーニーの分析、考案、共同作成をリアルタイムで行うので、マーケターはより迅速にジャーニーを開始し、エンゲージメントを向上させ、コンバージョン率を高めることができます。[詳細情報](../agents/journey-agent.md) |
| Audience Agent | 新規 | Audience Agent は、構造化データと非構造化データを使用して、購買グループを自動的に特定および作成します。これは、マーケターが適切な人物をより迅速かつ正確にターゲットにするのに役立ちます。[詳細情報](../agents/audience-agent-b2b.md) |
| 販売修飾子 | 新規 | Sales Qualifier は、Account Qualification Agentを含むAdobe Journey Optimizer B2B editionの AI 駆動型アドオンアプリケーションで、事業開発担当者（BDR）のワークフローを合理化するように設計されています。 チャネルをまたいで、見込み客の選定、アウトリーチ、購入者のエンゲージメントワークフローを自動化します [ 詳細情報 ](../agents/sales-qualifier.md)。 |

## 2025.10 リリースノート

**デプロイメント日**：2025年10月31日（PT）

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | ジャーニーの宛先に対してアクティブ化 | 新しい&#x200B;_宛先に対してアクティブ化_&#x200B;会社アカウントアクションを使用して、個人ではなく会社に対して直接アクティブ化します（このリリースでは LinkedIn 会社に制限されます。）[詳細情報](../journeys/action-nodes.md#activate-to-a-linkedin-destination) |
| 機能 | ブランドテーマ | ブランドテーマを使用すれば、技術ユーザー以外でも、標準テンプレートの上にカスタムスタイルを追加して、特定のブランドやデザイン言語に適合する再利用可能なコンテンツを作成できるようになりました。[詳細情報](../content/brand-themes.md) |
| 機能 | メールテンプレート - 画像を HTML に変換 | JPG または PNG 画像ファイル形式で保存されたデザインファイルを使用して、メールテンプレートを自動的に生成できるようになりました。[詳細情報](../content/email-template-image-convert.md) |
| 機能 | ペルソナマッピング | 属性マッピングを使用して、アカウントメンバーと確立されたペルソナを結び付けます。[詳細情報](../admin/persona-mapping.md) |
| 機能 | Salesforce および Dynamics 向けセールスインサイト | セールスチームメンバーは、Salesforce または Dynamics の統合内で成熟した購買グループと関連インサイトを確認し、新しい機会を特定できるようになりました。購入グループの詳細（ステージ、スコア、関連メンバーなど）が含まれます。 [詳細情報](../buying-groups/incrm-insights.md) |
| 機能 | [!DNL Adobe Target] へのオーディエンスの有効化 | アカウントジャーニーから外部の顧客オーディエンスにオーディエンスをアクティベートし、プッシュで [!DNL Adobe Target] るようになりました。 この統合を使用すると、[!DNL Target] で設計された web エクスペリエンスのジャーニーシーケンスを通じて認定されたオーディエンスを配信できます。 [詳細情報](../audiences/target-external-audience.md) |
| 機能強化 | 購買グループの完全性のスコアリングの改善 | 完全性のスコアリング用のカスタマイズ可能な役割メンバーしきい値を使用して、購買グループが実際の意思決定を反映していることを確認できるようになりました。[詳細情報](../buying-groups/completeness-scores.md) |
| 機能強化 | 購買グループメンテナンスジョブ | 購買グループメンテナンスジョブの頻度は、毎週から毎日に更新されます。 |
| 機能強化 | アカウントジャーニーの進行状況 | 公開済みのジャーニーのステータスが&#x200B;_ライブ_、_新規エントリに対してクローズ済み_、_中止_&#x200B;または&#x200B;_終了_&#x200B;である場合は、ジャーニーマップを開いて、各ジャーニーノードのアカウントのリストを確認できます。 |

>[!NOTE]
>
>以下のリリースの変更は、2025年10月31日（PT）にデプロイメントを開始し、各機能が段階的にロールアウトされます。機能および機能強化のリリース日は変更される場合があります。

### アーキテクチャを簡素化

Adobe Journey Optimizer B2B Edition が、簡素化されたアーキテクチャで使用できるようになりました。この更新されたアーキテクチャにより、同じシステムおよび同じデータストア上に Journey Optimizer B2B Edition と Marketo Engage が存在することはなくなりました。Journey Optimizer B2B Edition は、Adobe Experience Platform からのみデータを受信します。ただし、システムのプロビジョニングと設定には、引き続き Marketo Engage の使用権限と一部の設定機能に依存します。

この更新されたアーキテクチャには、次の複数のメリットがあります。

* **データを簡単に統合および拡大・縮小**：更新されたプラットフォームは、カスタムオブジェクト、購買グループ、アカウントイベントなどの複雑なデータモデルをサポートします。
* **複数の Adobe Marketo Engage インスタンスを接続**：複数の Adobe Marketo Engage 環境のデータを 1 か所で管理および統合します。
* **データを安全に保持**：高度なプライバシーとセキュリティ機能により、顧客情報を保護できます。
* **今後に向けて作成**：この更新により、組織は継続的な改善とイノベーションに取り組むことができます。

>[!NOTE]
>
>環境がこのアーキテクチャでプロビジョニングされている場合は、[ 設定のガイドライン ](../simplified-architecture.md) を確認してください。

シンプルなアーキテクチャにより、2025.10 リリースでは次の新機能と機能強化が提供されます。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | リレーショナルデータモデル | B2B アカウントにリンクされたリレーショナルデータを活用して、アカウントジャーニー内のアカウントをフィルタリングしたり、メールコンテンツをパーソナライズしたりします。 このリレーショナルデータは、購入記録、イベント登録、ソフトウェアライセンス、サービス購読、予約などの実際のビジネスエンティティを表すことができます。 [詳細情報](../admin/xdm-field-management.md#relational-schemas) |
| 機能 | 複数のMarketo Engage アクティベーション | リモート Marketo Engage インスタンスへの接続を設定し、それらの接続を使用して、ジャーニー用のMarketo Engage アクションを設定します。 リストへのユーザーの追加または削除やリクエストキャンペーンへのユーザーの追加など、これらのアクションは、指定されたMarketo Engage インスタンスに適用されます。 [詳細情報](../admin/marketo-actions-connect.md) |
| 機能 | メール疲労の重複排除 | メールの重複排除を有効にして、ジャーニー内で同じアドレスに同じメールが複数回送信されるのを防げるようになりました。重複するアドレスは、そのメールアドレスを持つ最初のレコードがジャーニーを完了するまでブロックされます。 |
| 機能強化 | 通信制限 | Marketo EngageとJourney Optimizer B2B editionの両方の通信制限の組み合わせが順守されるようになりました。 [詳細情報](../admin/configure-channels-emails.md#communication-limits) |

<!-- There are additional functional changes with the simplified architecture:

| Item | Description |
| ---- | ----------- |
| Asset management | The system supports an internal asset repository where you can organize folders, edit images, import images, and remove images. It does not support Marketo Engage Design Studio workspaces for asset management. |
| | | -->

<!-- hold for later release 

| Feature | Landing pages | You can now create and publish landing pages in Journey Optimizer B2B Edition to support your journeys and programs. _(Previously a Beta program feature.)_ [Learn more](../content/landing-pages.md) |
| Feature | Forms | You can now create and publish re-usable form components to enable data submission from landing pages that are created and published in Journey Optimizer B2B Edition. _(Previously a Beta program feature.)_ [Learn more](../content/forms.md) |

-->

## 2025.9 リリースノート

**デプロイメント日**：2025年9月30日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | メールコンテンツの共同作業 | メールアセットのコンテキストで Journey Optimizer B2B Edition ユーザにコメントしたり、Journey Optimizer B2B Edition ユーザと共同作業したりできるようになりました。チームメンバーにタグを付けると、コメントの詳細が記載されたメール通知を受信できます。通知は、パルス通知としても利用できます。[詳細情報](../content/email-collaboration-tools.md) |
| 機能 | メールデザインのダークモード | メールデザインスペースに、_ダークモード_&#x200B;に切り替える機能が追加されました。ダークモードでは、メールコンテンツをプレビューし、ダークモードでメールを表示する受信者専用にカスタム設定を定義できます。[詳細情報](../content/email-dark-mode.md) |
| 機能強化 | ジャーニー - ロールの人物数別にパスを分割 | アカウントノード別に分割パスを使用すると、1 つ以上の購買グループロールに属する人物数でアカウントをターゲットにできます。パスでは、役割の深度に基づいて、セールスアラートやその他のエンゲージメントに対する購買グループの準備を評価できます。[詳細情報](../journeys/split-merge-paths-nodes.md#buying-group-filtering-for-accounts) |
| 機能強化 | ジャーニー - イベントの顧客フィルター | 人物フィルターを使用して、人物イベントをリッスンします。これらのフィルターには、一致した購買グループの特定の役割をターゲットにする機能が含まれます。[詳細情報](../journeys/listen-for-event-nodes.md#add-filters-to-the-people-event) |

>[!NOTE]
>
>以下のリリースの変更は、2025年9月30日（PT）にデプロイメントを開始し、各機能が段階的にロールアウトされます。機能および機能強化のリリース日は変更される場合があります。

## 2025.8 リリースノート

**デプロイメント日**：2025年8月26日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | 役割テンプレートおよびジャーニーのユーザーエンゲージメントスコアフィルター | 購買グループの作成に使用される役割テンプレートと分割パスジャーニーノードで、_ユーザーエンゲージメントスコア_&#x200B;をフィルターとして使用できるようになりました。[詳細情報](../buying-groups/buying-groups-role-templates.md#add-the-template-roles) |
| 機能 | 購買グループのカスタムの役割の設定 | 購買グループのカスタムの役割を柔軟に設定できるようになりました。これにより、ユースケースに固有のロールを定義できます。[詳細情報](../buying-groups/default-custom-roles.md) |
| 機能 | エンゲージメントスコアの重み付けの設定 | 購買グループのエンゲージメントスコアに影響を与えるアクティビティに重み付けを割り当てることができるようになりました。この機能には、独自のカスタムスコアモデルの定義と、エンゲージメントスコアの計算に影響を与えるアクティブモデルの変更が含まれます。[詳細情報](../admin/engagement-score-weighting.md) |
| 機能強化 | フラグメントの条件付きコンテンツ | ビジュアルフラグメントデザインに条件付きコンテンツツールを使用できるようになりました。[詳細情報](../content/conditional-content.md) |
| 機能強化 | エンゲージメントスコアの更新 | 購買グループのエンゲージメントスコアロジックが更新され、スコアが正規化されました。さらに、メンバーレベルのエンゲージメントスコアだけでなく、購買グループ全体の総合的なエンゲージメントスコアも操作できるようになりました。[詳細情報](../buying-groups/engagement-scores.md) |
| 機能強化 | アクティブなジャーニーの監視 - 各ノードのアカウント | アクティブなアカウントジャーニーの場合は、ジャーニーの各アカウントノードに到達したアカウントのリストにアクセスできます。 |

## 2025.6 リリースノート

**デプロイメント日**：2025年7月15日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | GenStudio for Performance Marketing との統合 | （限定提供）GenStudio for Performance Marketing のメールエクスペリエンスを Journey Optimizer B2B Edition と統合して、マーケティング効率を高め、ブランドの一貫性を維持できるようになりました。この統合を利用すると、GenStudio AI を活用したコンテンツ作成と、Journey Optimizer B2B B2B Edition の高度なオーケストレーション機能を組み合わせることができます。[詳細情報](../content/genstudio-email-workflow.md) |
| 機能 | スパム検出レポート | スパムフィルターを回避し、メッセージがオーディエンスのインボックスに確実に配信されるようにするには、メールデザインスペースで&#x200B;_スパムレポート_&#x200B;を直接生成します。[詳細情報](../content/email-spam-report.md) |
| 機能 | ユーザーの詳細ページ | インテリジェントダッシュボード、購買グループの詳細ページ、アカウントの詳細ページでユーザーの名前が（ハイパーリンクとして）表示されている際に、その名前をクリックできるようになりました。このアクションにより、関連するユーザーの詳細ページが開き、連絡先、そのアクティビティ、上位の関与している購買グループに関する情報が表示されます。[詳細情報](../accounts/person-details.md) |
| 機能 | アカウントと購買グループのアクション | タイムリーで意図的なエンゲージメントを実現するために、アカウントの詳細ページと購買グループの詳細ページからアクションを直接実行します。 <li>_メールを送信_&#x200B;アクションを使用して、Marketo Engage の承認済みメールを、選択したアカウントの連絡先または購買グループのメンバーに送信します。[詳細情報](../accounts/account-details.md#send-emails) <li>購買グループの詳細からは、_新規メンバーを割り当て_、_メンバーを削除_、_役割を編集_&#x200B;などのアクションも実行できます。[詳細情報](../buying-groups/buying-group-details.md#members-tab) |
| 機能 | CRM 内から詳細ページへのアクセス | Salesforce や Microsoft Dynamics などの顧客関係管理（CRM）ツールで、アカウント、連絡先、リードの Journey Optimizer B2B Edition の詳細ページへのダイレクトリンクを設定できるようになりました。[詳細情報](../accounts/crm-linking.md) |
| 機能 | コンテンツデザインのカスタム CSS サポート | デザインスペースでメールやランディングページのコンテンツを作成する際に、独自のカスタム CSS を追加できるようになりました。[詳細情報](../content/design-custom-css.md) |
| 機能 | インテントキーワードマッピングの設定 | インテント検出モデルをアクティブ化および管理するために、スプレッドシートをアップロードしてインテントデータマッピングカテゴリを定義できるようになりました。[詳細情報](../admin/intent-data.md) |
| 機能強化 | メールの概要からのコンテンツのシミュレート | メールリストからメールを開く際に、メールの概要（詳細とプロパティ）から&#x200B;_コンテンツをシミュレート_&#x200B;ツールにアクセスできるようになりました。このアクセス権は、メールのデザインスペースに追加されます。[詳細情報](../content/email-simulate-content.md#display-the-email-preview) |
| 機能強化 | 役割テンプレートリストの合計数表示 | _[!UICONTROL アカウントジャーニー]_&#x200B;リストページが強化され、検索バーの横に合計数が表示されます。 |

<!-- The following capabilities are currently available only for a set of program participants (Beta):

**Brand Kit with AI Assistant** - Maintain brand consistency across email assets by storing and managing brand assets. Add assets, such as colors, fonts, logos, themes, visual content, and compliance guidelines, and use them for your generative AI content creation. -->

## 2025.5 リリースノート

**デプロイメント日**：2025年6月3日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | Litmus を使用したメールテスト | [Litmus Enterprise アカウント](https://www.litmus.com/email-testing){target="_blank"}を使用して、Journey Optimizer B2B Edition で選定した一般的なメールクライアントのメールのレンダリングをプレビューできるようになりました。この統合により、すべてのメールのインボックスで、メールコンテンツが適切に表示され、設計どおりに機能します。[詳細情報](../content/email-test-rendering.md) |
| 機能強化 | メールの複製 | ジャーニーノードにメールを追加する際に、既存のメールを複製できるようになりました。複製したメールの設定やコンテンツを変更するか、そのままにしておきます。[詳細情報](../content/add-email.md#add-an-email-to-your-journey) |
| 機能強化 | メールのハンドルバートークン形式 | メールコンテンツのパーソナライゼーショントークンで、ハンドルバースクリプトと完全に互換性のある更新済み形式が使用されるようになりました。この形式では、_キャメルケース_&#x200B;またはアンダースコアを使用し、スペースを排除します。[詳細情報](../content/email-authoring.md#content-authoring---personalization) |
| 機能強化 | リストの合計数の表示 | _[!UICONTROL ソリューションに対する関心]_&#x200B;および&#x200B;_[!UICONTROL アカウントジャーニー]_&#x200B;リストページが強化され、検索バーの横に合計数が表示されます。 |

## 2025.4 リリースノート

**デプロイメント日**：2025年4月29日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | アカウントリスト | 業界、場所、会社の規模など、定義した条件で重点顧客をターゲットにする静的または動的アカウントリストを作成できるようになりました。<a href="../accounts/account-lists.md">詳細情報</a> |
| 機能 | アカウントリストのジャーニーオーケストレーション | ジャーニーアクションノードを使用して、静的アカウントリストのアカウントを追加および削除します。<a href="../accounts/account-lists-journeys.md#take-an-action-node---add-to-account">詳細情報</a> |
| 機能強化 | Marketo Engage でジャーニーメンバーシップをフィルタリング | ジャーニーオーディエンスに Adobe Journey Optimizer B2B Edition アカウントリストを使用し、Marketo Engage スマートリストで&#x200B;_アカウントリストのメンバー_&#x200B;フィルターを使用します。<a href="../accounts/account-lists-journeys.md#marketo-engage-program---member-of-account-list">詳細情報</a> |
| 機能 | 非アクティブフィルター | メールの非アクティビティ、注目のアクション、データ値の変更、訪問済みの web ページなど、Marketo Engage キャンペーンとプログラム内の非アクティビティに基づいてジャーニーを調整します。<a href="../journeys/split-merge-paths-nodes.md#activity-filtering">詳細情報</a> |
| 機能強化 | 訪問済みの web ページフィルター | Marketo Engage キャンペーンとプログラムに関連付けられた訪問済みの web ページのアクティビティに基づいてジャーニーを調整します。<a href="../journeys/split-merge-paths-nodes.md#people-path-filters">詳細情報</a> |
| 機能強化 | メールリスト | アクティブなメールとドラフトのメールのグローバルリストを表示し、関連するアカウントジャーニー全体でメールを検索、確認、更新します。<a href="../content/emails-list.md">詳細情報</a> |

## 2025.3 リリースノート

**デプロイメント日**：2025年4月1日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | アカウントジャーニーを複製 | アカウントジャーニーで複製アクションが使用できるようになりました。アカウントジャーニーの詳細を複製するか、フローとパス構造のシンプルなスケルトンのみを複製できます。<a href="../journeys/journey-overview.md#duplicate-journey">詳細情報</a> |
| 機能 | アカウントジャーニーのマイトークン | アカウントジャーニーに固有の値を持つカスタムトークンのセットを定義できるようになりました。このカスタムトークンのセットは&#x200B;_マイトークン_&#x200B;と呼ばれ、これらのカスタムトークンはすべて、ジャーニーメールのオーサリング時にパーソナライゼーション用に使用されます。<a href="../content/personalization-my-tokens.md">詳細情報</a> |
| 機能 | 購買グループのステージを削除 | 購買グループステージモデルは、ドラフト状態または公開済みの状態の場合に削除できます。公開済み（ライブ）の場合は、ソリューションに対する関心に関連付けられていない場合にのみ削除できます。<a href="../buying-groups/buying-group-stages.md#delete-the-buying-group-stages-model">詳細情報</a> |
| 機能強化 | ジャーニーノードの数 | ノードレベルでの公開済みジャーニーメンバーシップの数に対する表示が向上しました。_ジャーニーマップ_&#x200B;では、ノードに&#x200B;_[!UICONTROL 入力済み合計アカウント数]_&#x200B;が表示されます。アクションノードを選択すると、右側の詳細には&#x200B;_[!UICONTROL まだアクションが実行されていないアカウント]_&#x200B;も含まれます。_イベントをリッスン_&#x200B;ノードの詳細には、_[!UICONTROL このステップのアカウント]_&#x200B;が含まれます。この情報を使用して、ライブ、完了、中止の各ジャーニーでのアカウントの進行状況を検証します。 |

## 2025.2 リリースノート

**デプロイメント日**：2025年3月11日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | カスタマイズ可能なフィールド - コンテンツフラグメント | ビジュアルフラグメントのデザイン中に、フラグメント内のコンポーネントのパラメーターを編集可能として指定できます。この機能により、メールまたはテンプレートの作成者は、必要に応じたカスタムフィールド値を指定できます。このカスタマイズフラグは、画像、テキストおよびボタンのビジュアルコンポーネントに制限されます。<a href="../content/fragment-authoring.md#enable-fragment-customization">詳細情報</a> |
| 機能 | ジャーニーの複製タイプ | アカウントジャーニーを複製する際に、Journey Optimizer B2B Edition で作成したメールと SMS メッセージを除く、ノードの詳細を含めることができます。代わりに、ノードの詳細と設定を除いた構造とパスフローのスケルトンコピーを作成できます。<a href="../journeys/journey-overview.md#duplicate-journey">詳細情報</a> |
| 機能強化 | 4 個の追加のサンプルメールテンプレート | サンプルメールテンプレートライブラリには、再エンゲージメント、通知、育成、フィードバックコンテンツの例として、4 個の SecurFinacial テンプレートが含まれるようになりました。 |

<!-- | Feature | B2B built-in roles and product permissions | Experience Platform now includes a set of built-in (default) roles that you can use to manage access to the B2B product capabilities. <a href="../admin/user-management.md#b2b-built-in-roles">Learn more</a> <br/>Administrators can now define custom roles in Adobe Experience Platform to include Journey Optimizer B2B Edition product permissions.  <a href="../admin/user-management.md#b2b-product-permissions">Learn more</a> | -->

## 2025.1 リリースノート {#Jan-2025}

**デプロイメント日**：2025年2月6日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | エクスペリエンスイベント転送 | 管理者は、Adobe Experience Platform（AEP）ベースのイベント定義を設定できます。これらの設定により、マーケターは、AEP エクスペリエンスイベントに反応するアカウントジャーニーを作成できます。<a href="../admin/configure-aep-events.md">詳細情報</a> |
| 機能 | 有料メディアの宛先 | アカウントジャーニーから有料メディアキャンペーンの対象となる既知の人物を選定し、LinkedIn などの広告プラットフォームでさらに関与できます。分割パスノードを使用して、特定の行動に基づいてアカウントオーディエンスをセグメント化し、追加のエンゲージメントを保証するアカウントを識別します。次に、Real-Time CDP を通じて、これらのアカウントの人物を、サポートされている有料メディアの宛先への外部顧客オーディエンスに追加します。<a href="../journeys/action-nodes.md#journey-optimizer-b2b-actions">詳細情報</a> |
| 機能 | インテリジェントダッシュボード | よりインテリジェントな分析と正確なアカウントの優先順位付けの AI 生成のインサイトなど、アカウントジャーニーを通じて購買グループの進行状況を表示します。<a href="../dashboards/intelligent-dashboard.md">詳細情報</a> |
| 機能 | 購買グループとアカウントの詳細 | 購買グループとアカウントレベルでインサイトを表示して、顧客との関与を開始する際に、より多くのコンテキストと履歴データを入手します。<p>購買グループの詳細には、検出されたファーストパーティのインテントが含まれます。<a href="../buying-groups/buying-group-details.md">詳細情報</a><p>アカウントの詳細アカウントでは、検出されたエンゲージメントの急増がハイライト表示されるので、カスタマイズされた販売に焦点を当てたエンゲージメントの準備が整ったアカウントに関して販売に警告できます。<a href="../accounts/account-details.md">詳細情報</a> |
| 機能 | ジャーニーの概要 | アカウントジャーニーにアクセスすると、「概要」タブにアクティブなアカウントジャーニーの包括的なスナップショットが表示され、完了とエンゲージメントアクティビティを分類および選定する円グラフと棒グラフを使用してアカウントの進行状況の詳細が表示されます。<a href="../dashboards/journeys-dashboard.md">詳細情報</a> |
| 機能 | Adobe Express の画像編集 | Adobe Express クイックアクションを使用すると、画像に簡単な編集（切り抜きやサイズ変更など）を加え、コンテンツの外観をより洗練されたものにすることができます。<a href="../content/image-edit-adobe-express.md#quick-actions-in-adobe-express">詳細情報</a>  <p>より包括的なデザインツールセットを実現することを目的に、この統合により、Journey Optimizer B2B Edition への完全な Adobe Express ライセンスが有効になります。この設定により、ローカルアセットワークスペース内で完全な Adobe Express ユーザーインターフェイスにアクセスできるようになります。<a href="../content/image-edit-adobe-express.md#adobe-express-enterprise-license">詳細情報</a> |
| 機能 | 購買グループの役割のインテントフィルター | インテントキーワードを送信すると、インテント検出モデルは、リードのアクティビティに基づいて、十分な信頼性を持つソリューション／製品に対する関心を予測します。<a href="../admin/intent-data.md">詳細情報</a> <p>このインテントデータは、購買グループの役割条件を定義するのに使用できます。<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">詳細情報</a> |
| 機能強化 | ジャーニーでの Marketo Engage イベントのサポート | _イベントをリッスン_&#x200B;ジャーニーノードは、人物レベルで _Web ページにアクセス_&#x200B;と&#x200B;_フォームを入力_&#x200B;という 2 つの Marketo Engage イベントをサポートするようになりました。<a href="../journeys/listen-for-event-nodes.md#listen-for-marketo-engage-event">詳細情報</a> |
| 機能強化 | Marketo Engage スマートリストの購買グループフィルター | Marketo Engage で購買グループフィルターを使用してスマートリストを表示および作成します。これらの追加されたフィルターを使用すると、Journey Optimizer B2B Edition 内のアカウントジャーニーから、Marketo Engage キャンペーンおよびプログラムをまたいで購買グループメンバーを抑制したり、含めたりすることができます。<a href="../buying-groups/marketo-engage-smart-list-buying-group-filters.md">詳細情報</a> |
| 機能強化 | ジャーニーと役割の Marketo Engage リストメンバーシップフィルター | Journey Optimizer B2B では、ジャーニーアクティビティの重複を排除することを目的に、_人物でパスを分割_&#x200B;ノードの条件として Marketo Engage リストのメンバーシップを確認します。<a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">詳細情報</a> <p> 購買グループの役割テンプレートの場合は、役割の条件としてリストメンバーシップを使用します。<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">詳細情報</a> |
| 機能強化 | エンゲージメントの概要ダッシュボード | このダッシュボードは、エンゲージメントの包括的なビューを表示するのに更新されています。スナップショットの円グラフと、時間の経過と共にトレンドを示す折れ線グラフを通じて、アカウントと個々のインタラクションのリアルタイムの指標が表示されます。<a href="../dashboards/engagement-dashboard.md">詳細情報</a> |

## 2024年リリース

2024年にリリースされた Journey Optimizer B2B Edition の機能と機能強化について詳しくは、以下のリストを展開してください。

+++2024年10月リリースノート

**デプロイメント日**：2024年10月29日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | メールの条件付きコンテンツ | アカウントレベルとリードレベルの両方での受信者の行動およびプロファイル特性に基づいて、メールコンテンツをパーソナライズします。 <p>メールのビジュアルデザインスペースでアカウントジャーニーのメールを作成する際に、条件付きルールを使用して、任意のコンテンツコンポーネントに複数のバリアントを定義します。<a href="../content/conditional-content.md">詳細情報</a> |
| 機能 | ジャーニーでの&#x200B;_リストに追加_&#x200B;および&#x200B;_リストから削除_&#x200B;の人物アクション | アカウントレベルとリードレベルの両方での受信者の行動およびプロファイル特性に基づいて、メールコンテンツをパーソナライズします。 <a href="../journeys/action-nodes.md">詳細情報</a> |
| 機能 | コンテンツガバナンスとコンポーネントのロック | 承認済みのコンテンツデザインに準拠するには、コンテンツガバナンス機能を使用して、メールテンプレートのコンテンツコンポーネントをロックします。メールテンプレートでコンテンツガバナンスをアクティベートすると、マーケターは、許可された要素のみを変更して、コンテンツ戦略に合わせた状態を維持できます。<a href="../content/template-content-governance.md">詳細情報</a> |
| 機能 | 購買グループステージ | カスタムの購買グループのステージングモデルを定義して公開すると、購買グループのライフサイクルステージを通じて購買グループの進行状況を追跡できます。これらのステージを使用して、購買グループのメンバーに対する次の最適なアクションを識別します。ステージの進行状況を判断し、変更に基づいてアクションをトリガーするトランジションルールとジャーニーノードを設定します。<a href="../buying-groups/buying-group-stages.md">詳細情報</a> |
| 機能強化 | 新しい標準メールテンプレート | サンプルテンプレートライブラリに、B2B マーケター向けに設計された追加のメールテンプレートが含まれるようになりました。これらのサンプルテンプレートを開始点として使用し、独自のブランドとメッセージを追加します。<a href="../content/email-templates.md#select-a-design-template">詳細情報</a> |
| 機能強化 | ユーザー属性としてのカスタムフィールド | Experience Platform のアカウントオーディエンススキーマでカスタムのユーザーフィールドが定義されている場合は、これらのフィールドを条件内のユーザー属性として使用することもできます。これらのカスタム属性は次で使用します。 <li>役割テンプレート<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">詳細情報</a></li><li>人物ジャーニーノード別にパスを分割<a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">詳細情報</a></li> |
| 機能強化 | メールチャネル設定 | Journey Optimizer B2B Edition インターフェイスにメール設定が表示されるようになりました。現在の設定をすばやく確認でき、管理者は「_[!UICONTROL 設定を編集]_」をクリックして Marketo Engage の設定に直接移動し、組織の要件に応じて設定を更新できます。<a href="../admin/configure-channels-emails.md">詳細情報</a> |

+++

+++2024年9月リリースノート

**デプロイメント日**：2024年10月7日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能強化 | 中央アセットライブラリ | 強化された&#x200B;_中央アセットライブラリ_&#x200B;を使用すると、Design Studio ワークスペースをまたいで Marketo Engage インスタンス内のすべての画像アセットを使用できます。Journey Optimizer B2B Edition からの Marketo Engage アセットの編集、削除、移動操作を防ぐ、ビルトインのガードレールが用意されています。これらの保護により、ソースアセット（Marketo Engage Design Studio）が維持され、Journey Optimizer B2B Edition でシームレスな読み取りと再利用が可能になります。<p>Journey Optimizer B2B Edition 専用アセットの場合、特定のワークスペースで完全なアセット管理機能が提供されます。<a href="../content/internal-image-assets.md">詳細情報</a> |
| 機能 | 最近アクセス済みのアセット | Journey Optimizer B2B Edition アプリのホームページに「_[!UICONTROL 最近アクセス済み]_」セクションが追加され、マーケターや管理者に対して最近アクセス済みのアセットのリストが表示されるようになりました。このリストを使用すると、一連のアセットページを移動して検索することなく、最近作業済みのアセットに直接移動できます。 <p>リストには、変更に関する追加情報が提供され、前回のセッションからさらに変更が必要なアセットを決定できます。メールアセットの場合、メールアセットを使用するアカウントジャーニーが表示されます。<a href="../home-page.md">詳細情報</a> |
| 機能強化 | ジャーニー分割ノード - パスを並べ替え | 分割パスノードでは、パスフィルタリングは上から下へ順に評価されます。各ユーザーまたはアカウントは、一致する最初のパスに沿って進行します。各パスカードの右上にある上向き矢印と下向き矢印をクリックして、定義済みのパスをリスト内で上下に移動することで、パスの順序を変更できます。<a href="../journeys/split-merge-paths-nodes.md#split-paths">詳細情報</a> |
| 機能強化 | ジャーニー分割ノード - 追加のアクティビティ履歴条件属性 | 条件を使用して、人物別に分割ノードのパスフィルタリングを定義する場合、_開封済みのメール_&#x200B;と&#x200B;_配信済みのメール_&#x200B;という 2 つの追加属性があります。これらの追加により、メールのアクティビティに基づいてジャーニー内の人物をフィルタリングする際の柔軟性が向上します。<a href="../journeys/journey-nodes.md#split-paths">詳細情報</a> |

+++

+++2024年8月リリースノート

**デプロイメント日**：2024年8月29日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | LinkedIn アカウントと一致するオーディエンス | Account Matched Audiences を通じて LinkedIn 広告オーディエンスを生成し、購買グループ内の空いている役割を埋めるのに役立ちます。一連の購買グループフィルターを定義することで、LinkedIn の一致するオーディエンスを維持し、購買グループのパラメーターに一致する見込み客をターゲットにすることができます。 <p>この機能は、Experience Platform の宛先を活用して統合のいくつかの側面を管理します。<a href="../data/linkedin-account-matched-audiences.md">詳細情報</a> |
| 機能強化 | ビジュアルコンテンツフラグメントのステータスライフサイクル | ビジュアルフラグメントは、ステータスライフサイクルを使用して管理されるようになりました。フラグメントのステータスによって、メールまたはメールテンプレートでの使用の可用性と、フラグメントに行われる変更が決定されます。 <p>この強化されたワークフローにより、プロモーションや通信のカレンダーに従って再利用コンテンツを簡単に管理できます。<a href="../content/fragments.md#fragment-status-and-lifecycle">詳細情報</a> |

+++
