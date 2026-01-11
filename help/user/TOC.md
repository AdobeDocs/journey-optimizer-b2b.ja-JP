---
user-guide-title: Journey Optimizer B2B エディションのドキュメント
user-guide-description: Adobe Journey Optimizer B2B Edition の概要と、ビルトインの生成 AI と業界最先端の自動化機能を使用して、アカウントと購買グループのジャーニーを調整する方法について説明します。
source-git-commit: ef3c33a769bf8f794bbc1a61f77feabc9db961e7
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 80%

---


# Journey Optimizer B2B Edition ユーザーガイド {#user}

+ [Adobe Journey Optimizer B2B Edition ドキュメント](guide-overview.md)
+ [リリースノート](./release-notes/release-notes.md)
+ 基本を学ぶ {#get-started}
   + [Journey Optimizer B2B Edition の概要](about-journey-optimizer-b2b-edition.md)
   + [ログインとホームページ](home-page.md)
   + [オンボーディングガイダンス](./start/get-started.md)
   + [トラッキングとメールプロトコル](./start/email-protocols.md)
+ AI アシスタント {#ai-assistant}
   + [概要](./ai-assistant/ai-assistant-overview.md)
   + [AI アシスタントへのアクセスを有効にする](./ai-assistant/enable-ai-assistant-access.md)
   + [質問ガイダンス](./ai-assistant/question-guidance.md)
   + [AI アシスタントを使用](./ai-assistant/use-ai-assistant.md)
   + エージェント {#ai-agents}
      + [Audience Agent](./agents/audience-agent-b2b.md)
      + [ジャーニー ビルド エージェント B2B](./agents/journey-agent.md)
      + [販売修飾子](./agents/sales-qualifier.md)
+ アカウントジャーニー {#account-journeys}
   + [概要](./journeys/journey-overview.md)
   + [ジャーニーの作成と公開](./journeys/create-publish-journey.md)
   + [ジャーニーノード](./journeys/journey-nodes.md)
   + ジャーニーノード {#journey-nodes}
      + [アカウントオーディエンス](./journeys/account-audience-nodes.md)
      + [アクションの実行](./journeys/action-nodes.md)
      + [イベントのリッスン](./journeys/listen-for-event-nodes.md)
      + [パスの分割と結合](./journeys/split-merge-paths-nodes.md)
      + [待機](./journeys/wait-nodes.md)
   + [ジャーニーの詳細](./journeys/journey-details.md)
+ ジャーニーコンテンツ {#journey-content}
   + [SMS チャネル](./content/sms-authoring.md)
   + メールチャネル {#email-channel}
      + [メールの追加](./content/add-email.md)
      + [メールオーサリング](./content/email-authoring.md)
      + [メールオーサリング用 AI アシスタント](./content/ai-assistant-emails.md)
      + [GenStudio ワークフロー](./content/genstudio-email-workflow.md)
      + [メールデザインのダークモード](./content/email-dark-mode.md)
      + [管理されたテンプレート](./content/email-authoring-governance.md)
      + [販売アラートメール](./content/sales-alert-email.md)
      + [メールの重複排除](./content/email-deduplication.md)
   + Web チャンネル（Beta） {#web-channel}
      + [概要](./content/web-experiences.md)
      + [Web エクスペリエンスデザイン](./content/web-experience-design.md)
      + [単一ページアプリケーション](./content/web-single-page-applications.md)
   + [カスタムパーソナライゼーショントークン](./content/personalization-my-tokens.md)
+ オーディエンス {#audiences}
   + [Experience Platform オーディエンス](./audiences/account-audience-overview.md)
   + [外部オーディエンスのターゲット設定](./audiences/target-external-audience.md)
   + [LinkedIn アカウントでマッチしたオーディエンス](./data/linkedin-account-matched-audiences.md)
+ アカウント {#accounts}
   + 購買グループ {#buying-groups}
      + [概要](./buying-groups/buying-groups-overview.md)
      + [ソリューションに対する関心](./buying-groups/solution-interests.md)
      + [役割テンプレート](./buying-groups/buying-groups-role-templates.md)
      + [デフォルトおよびカスタムの役割](./buying-groups/default-custom-roles.md)
      + [役割インサイト](./buying-groups/buying-group-role-insights.md)
      + 購買グループのスコアリング {#scoring}
         + [エンゲージメントスコア](./buying-groups/engagement-scores.md)
         + [完全性スコア](./buying-groups/completeness-scores.md)
      + [購買グループステージ](./buying-groups/buying-group-stages.md)
      + [購買グループの作成](./buying-groups/buying-groups-create.md)
      + [アカウントの書き出し](./audiences/account-list-export.md)
      + [Marketo Engage の購買グループフィルター](./buying-groups/marketo-engage-smart-list-buying-group-filters.md)
      + [CRM 内インサイト](./buying-groups/incrm-insights.md)
   + アカウントリスト {#account-lists}
      + [概要](./accounts/account-lists.md)
      + [ジャーニーとプログラムでの使用](./accounts/account-lists-journeys.md)
   + セールスエクスペリエンス {#sales-experience}
      + [アカウントの詳細](./accounts/account-details.md)
      + [購買グループの詳細](./buying-groups/buying-group-details.md)
      + [顧客の詳細](./accounts/person-details.md)
      + [CRM リンク](./accounts/crm-linking.md)
+ コンテンツ管理 {#content-management}
   + メール {#emails}
      + [メールコンテンツの操作](./content/emails-list.md)
      + [アクセシブルなコンテンツのデザイン](./content/email-accessible-content.md)
      + プレビューと検証 {#preview}
         + [コンテンツのシミュレート](./content/email-simulate-content.md)
         + [メールのレンダリングのテスト](./content/email-test-rendering.md)
         + [スパムレポート](./content/email-spam-report.md)
      + [メールでの共同作業](./content/email-collaboration-tools.md)
   + アセット {#assets}
      + [概要](./content/assets-overview.md)
      + 内部アセット {#internal-dam}
         + [内部アセットの操作](./content/internal-image-assets.md)
         + [Adobe Express を使用した画像の編集](./content/image-edit-adobe-express.md)
      + [Experience Manager 画像アセット](./content/aem-assets.md)
   + テンプレート {#templates}
      + [コンテンツガバナンス](./content/template-content-governance.md)
      + メールテンプレート {#email-templates}
         + [概要](./content/email-templates.md)
         + [メールテンプレートオーサリング](./content/email-template-authoring.md)
         + [画像をテンプレートに変換](./content/email-template-image-convert.md)
      + ランディングページテンプレート（ベータ版） {#landing-page-templates}
         + [概要](./content/landing-page-templates.md)
         + [ランディングページテンプレートのデザイン](./content/landing-page-template-design.md)
   + フラグメント {#visual-fragments}
      + [概要](./content/fragments.md)
      + [フラグメントオーサリング](./content/fragment-authoring.md)
   + フォーム（ベータ版） {#forms}
      + [概要](./content/forms.md)
      + [フォームのデザイン](./content/form-design.md)
   + ランディングページ（ベータ版） {#landing-pages}
      + [概要](./content/landing-pages.md)
      + [ランディングページのデザイン](./content/landing-page-design.md)
   + コンテンツデザインツール {#content-design}
      + [構造コンポーネント](./content/structure-components.md)
      + [コンテンツコンポーネント](./content/content-components.md)
      + [カスタム CSS](./content/design-custom-css.md)
   + ブランド（ベータ版） {#brands}
      + [概要](./content/brands-overview.md)
      + [管理と作成](./content/brands-manage-create.md)
      + [ブランド一致](./content/brand-alignment.md)
   + [ブランドテーマ](./content/brand-themes.md)
   + [条件付きコンテンツ](./content/conditional-content.md)
   + パーソナライゼーション {#personalization}
      + [概要](./content/personalization.md)
      + [パーソナライゼーション構文](./content/personalization-syntax.md)
      + [ヘルパー関数リスト](./content/personalization-helper-functions.md)
+ インテリジェントダッシュボード {#dashboards}
   + [Insights ダッシュボード](./dashboards/intelligent-dashboard.md)
   + [エンゲージメントダッシュボード](./dashboards/engagement-dashboard.md)
   + [Web エンゲージメントダッシュボード ](./dashboards/web-engagement-dashboard.md)
   + [購入グループダッシュボード](./dashboards/buying-groups-dashboard.md)
   + [アカウントジャーニーダッシュボード](./dashboards/journeys-dashboard.md)
+ 管理 {#admin}
   + [ガバナンス](./admin/governance.md)
   + [Marketo アクションの設定](./admin/marketo-actions-connect.md)
   + [ペルソナマッピング](./admin/persona-mapping.md)
   + [ユーザー管理](./admin/user-management.md)
   + XDM フィールド管理 {#xdm-field-management}
      + [XDM クラス](admin/xdm-field-management.md)
      + [エクスペリエンスイベントとフィールド](./admin/configure-aep-events.md)
      + [デフォルトの XDM フィールド](./admin/field-mapping.md)
   + チャネル {#channels}
      + [メール設定](./admin/configure-channels-emails.md)
      + [SMS 設定](./admin/configure-channels-sms.md)
      + [Web チャネル設定（Beta）](./admin/configure-channels-web.md)
      + [ランディングページの設定（Beta）](./admin/landing-page-settings.md)
      + [イベント収集用のデータストリーム設定](./data/aep-event-collection.md)
   + 設定 {#configurations}
      + [AEM Assets リポジトリ](./admin/configure-aem-repositories.md)
      + [インテントデータ](./admin/intent-data.md)
      + [エンゲージメントスコアの重み付け](./admin/engagement-score-weighting.md)
   + [アーキテクチャ設定の簡素化](simplified-architecture.md)
