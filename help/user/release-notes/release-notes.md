---
title: リリースノート
description: Adobe Journey Optimizer B2B エディションの最新のリリースノート
exl-id: 7d3f1c26-d8a6-4065-a70f-5b30cb975dc8
source-git-commit: 60bda27f2d7b6bb5b8dd07ec26e0b608b8858318
workflow-type: tm+mt
source-wordcount: '1650'
ht-degree: 9%

---

# Journey Optimizer B2B edition リリースノート

Adobe Journey Optimizer B2B editionは、新機能、既存機能の強化、およびバグ修正を継続的に提供します。

Journey Optimizer B2B editionは [!DNL Adobe Experience Platform] でネイティブに構築され、最新のイノベーションや改善点を引き継いでいます。 以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/latest){target="_blank"}を参照してください。

使用権限、パフォーマンスガードレール、制限について詳しくは、[ 製品説明 ](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} を参照してください。

## 2025.2 リリースノート

**リリース日**:2025 年 3 月 11 日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 新機能 | カスタマイズ可能なフィールド – コンテンツフラグメント | コンテンツフラグメントデザイナーは、フラグメント内のコンポーネントのパラメーターを編集可能として指定できます。 これにより、メールまたはテンプレートの作成者は、必要に応じてカスタムフィールド値を指定できます。 このカスタマイズフラグは、画像、テキスト、ボタンのビジュアルコンポーネントに限定されます。 <a href="../content/fragment-authoring.md#enable-custom-fields">詳細情報</a> |
| 新機能 | B2B の組み込みの役割と製品の権限 | Experience Platformには、B2B 製品の機能へのアクセスを管理するために使用できる、組み込みの（デフォルトの）一連のロールが含まれるようになりました。 <a href="../admin/user-management.md#b2b-built-in-roles">詳細情報</a> <br/> 管理者は、Adobe Experience Platformでカスタムの役割を定義して、Journey Optimizer B2B edition製品の権限を含めることができるようになりました。  <a href="../admin/user-management.md#b2b-product-permissions">詳細情報</a> |
| 新機能 | ジャーニーの複製タイプ | アカウントジャーニーを複製する際、Journey Optimizer B2B editionで作成されたメールと SMS メッセージを除く、ノードの詳細を含めることができます。 別の方法として、ノードの詳細や設定を行わずに、構造およびパス フローのスケルトン コピーを作成することもできます。 <a href="../journeys/journey-overview.md#duplicate-journey">詳細情報</a> |
| 機能強化 | 4 つの追加のサンプルメールテンプレート | サンプルのメール・テンプレート・ライブラリには、再エンゲージメント、通知、育成、フィードバックの各コンテンツの例として、4 つの SecurFinacial テンプレートが含まれるようになりました |

## 2025.1 リリースノート {#Jan-2025}

**リリース日**:2025 年 2 月 6 日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 新機能 | エクスペリエンスイベント転送 | 管理者は、Adobe Experience Platform（AEP）ベースのイベント定義を設定できます。 これらの設定により、マーケターは、AEP エクスペリエンスイベントに反応するアカウントジャーニーを作成できます。  <a href="../admin/configure-aep-events.md">詳細情報</a> |
| 新機能 | 有料メディアの宛先 | アカウントジャーニーから有料メディアキャンペーンの既知の人物を選定して、LinkedIn などの広告プラットフォームでさらにエンゲージできるようにします。 アカウントジャーニーの分割パスノードを使用して、特定の行動に基づいてアカウントオーディエンスをセグメント化し、追加のエンゲージメントが必要なアカウントを特定します。 次に、これらのアカウントの人物を、Real-time CDP を通じて、サポートされている有料メディアの宛先の外部の顧客オーディエンスに追加します。 <a href="../journeys/action-nodes.md#journey-optimizer-b2b-actions">詳細情報</a> |
| 新機能 | インテリジェントダッシュボード | よりインテリジェントな分析と正確なアカウントの優先順位付けのための AI で生成されたインサイトを含め、アカウントジャーニーを通じて購入グループの進行状況を表示します。 <a href="../dashboards/intelligent-dashboard.md">詳細情報</a> |
| 新機能 | 購入グループとアカウントの詳細 | 顧客とのエンゲージメントを開始する際に、購入グループおよびアカウントレベルでインサイトを表示して、より多くのコンテキストおよび履歴データを持つようにします。<p>購入グループの詳細には、検出されたファーストパーティインテントが含まれています。 <a href="../buying-groups/buying-group-details.md">詳細情報</a><p>アカウントの詳細アカウントは、検出されたエンゲージメントのインテントの急増を強調します。これにより、カスタマイズされたセールスに焦点を当てたエンゲージメントの準備が整ったアカウントに関してセールスにアラートを表示できます。  <a href="../accounts/account-details.md">詳細情報</a> |
| 新機能 | ジャーニーの概要 | アカウントジャーニーにアクセスすると、「概要」タブに、アクティブなアカウントジャーニーの包括的なスナップショットが表示され、完了の分類と定量化を行う円グラフと棒グラフ、エンゲージメントアクティビティを使用して、アカウントの進行状況の詳細が示されます。  <a href="../dashboards/journeys-dashboard.md">詳細情報</a> |
| 新機能 | Adobe Expressの画像編集 | Adobe Express クイックアクションを使用すると、画像に簡単な編集（切り抜きやサイズ変更など）を加えて、コンテンツをより洗練された外観にすることができます。 <a href="../content/image-edit-adobe-express.md#quick-actions-in-adobe-express">詳細情報</a>  <p>より包括的な設計ツールを実現するために、この統合により、Journey Optimizer B2B editionへの完全なAdobe Express ライセンスが有効になります。 この設定により、ローカルのアセットワークスペース内でAdobe Expressの完全なユーザーインターフェイスにアクセスできるようになります。 <a href="../content/image-edit-adobe-express.md#adobe-express-enterprise-license">詳細情報</a> |
| 新機能 | 購入グループの役割のインテントフィルター | インテントのキーワードを送信すると、インテント検出モデルは、リードのアクティビティに基づいて、十分な信頼性を持つ関心のあるソリューション/製品を予測します。 <a href="../admin/intent-data.md">詳細情報</a> <p>このインテントデータは、購入グループロールの条件を定義する際に使用できます <a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles"> 詳細情報 </a> |
| 機能強化 | ジャーニーでのMarketo Engage イベントのサポート | _イベントをリッスン_ ジャーニーノードは、人物レベルで 2 つのMarketo Engage イベント（_web ページを訪問_ および _フォームに入力_ をサポートするようになりました。 <a href="../journeys/listen-for-event-nodes.md#listen-for-marketo-engage-event">詳細情報</a> |
| 機能強化 | Marketo Engageスマートリスト用の購入グループフィルター | Marketo Engageの購買グループフィルターを使用して、スマートリストを表示および作成します。 これらの追加されたフィルターを使用すると、Journey Optimizer B2B edition内のアカウントジャーニーから、Marketo Engage キャンペーンおよびプログラム全体で購買グループメンバーを抑制し、含めることができます。 <a href="../buying-groups/marketo-engage-smart-list-buying-group-filters.md">詳細情報</a> |
| 機能強化 | ジャーニーおよびロールのMarketo Engage リストメンバーシップフィルター | Journey Optimizer B2B では、_ユーザーによる分割パス_ ノードの条件としてMarketo Engage リストのメンバーシップを確認して、ジャーニーアクティビティの重複を排除します。 <a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">詳細情報</a> <p> グループ ロール テンプレートを購入する場合は、リスト メンバーシップをロール条件として使用します。 <a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">詳細情報</a> |
| 機能強化 | エンゲージメントの概要ダッシュボード | このダッシュボードが更新され、エンゲージメントの包括的な表示が可能になりました。 スナップショットの円グラフとトレンドを明らかにする折れ線グラフを通じて、アカウントと個々のインタラクションのリアルタイム指標を時系列で表示します。 <a href="../dashboards/engagement-dashboard.md">詳細情報</a> |


## 2024年10月リリースノート {#Oct-2024}

**リリース日**:2024 年 10 月 29 日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 新機能 | メールテンプレート内の条件付きコンテンツ | アカウントレベルとリードレベルの両方で、受信者の行動とプロファイルの特性に基づいてメールコンテンツをパーソナライズします。 <p>メールビジュアルデザイン領域でアカウントジャーニーのメールを作成する際は、条件付きルールを使用して、任意のコンテンツコンポーネントの複数のバリアントを定義します。 <a href="../content/conditional-content.md">詳細情報</a> |
| 新機能 | ジャーニーでの _リストに追加_ および _リストから削除_ 人物アクション | アカウントレベルとリードレベルの両方で、受信者の行動とプロファイルの特性に基づいてメールコンテンツをパーソナライズします。 <a href="../journeys/action-nodes.md">詳細情報</a> |
| 新機能 | コンテンツガバナンスとコンポーネントロック | 承認済みのコンテンツデザインに確実に準拠するには、コンテンツガバナンス機能を使用してメールテンプレートコンテンツコンポーネントをロックします。 メールテンプレートでコンテンツガバナンスをアクティブ化すると、マーケターは、許可された要素のみを変更して、コンテンツ戦略に合わせることができます。 <a href="../content/template-content-governance.md">詳細情報</a> |
| 新機能 | 購買グループステージ | カスタムの購入グループステージングモデルを定義して公開する場合、購入グループのライフサイクルステージを通じて購入グループの進行状況を追跡できます。 これらのステージを使用して、グループメンバーを購入するための次に最適なアクションを特定します。 ステージの進行と変化に基づくトリガーアクションを決定するトランジションルールとジャーニーノードを設定します。 <a href="../buying-groups/buying-group-stages.md">詳細情報</a> |
| 機能強化 | 標準の新しいメールテンプレート | サンプルテンプレートライブラリに、B2B マーケター向けに設計された追加のメールテンプレートが含まれるようになりました。 これらのサンプルテンプレートを出発点として使用し、独自のブランディングとメッセージを追加します。 <a href="../content/email-templates.md#select-a-design-template">詳細情報</a> |
| 機能強化 | 人物属性としてのカスタムフィールド | Experience Platformのアカウントオーディエンススキーマで定義されたカスタム人物フィールドがある場合、これらのフィールドを条件の人物属性として使用することもできます。 これらのカスタム属性を次で使用します。 <li>役割テンプレート <a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles"> 詳細情報 </a></li><li>人物ジャーニーノード別にパスを分割します <a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node"> 詳細情報 </a></li> |
| 機能強化 | メールチャネルの設定 | メール設定がJourney Optimizer B2B edition インターフェイスに表示されるようになりました。 現在の設定をすばやく確認することができます。管理者は、「_[!UICONTROL 設定を編集]_」をクリックしてMarketo Engageの設定に直接移動し、組織の要件に応じて設定を更新することができます。 <a href="../admin/configure-channels-emails.md">詳細情報</a> |

## 2024年9月リリースノート {#Sept-2024}

**リリース日**:2024 年 10 月 7 日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能強化 | 中央アセットライブラリ | 強化された _中央アセットライブラリ_ を使用すると、Design Studio のワークスペース全体で、Marketo Engage インスタンスのすべての画像アセットを使用できます。 Journey Optimizer B2B editionからMarketo Engage アセットに対する編集や、削除および移動操作を防ぐガードレールが組み込まれています。 これらの保護機能により、ソースアセット（Marketo Engage Design Studio）が維持されると同時に、Journey Optimizer B2B editionでシームレスな読み取りと再利用が可能になります。<p>Journey Optimizer B2B editionでのみ使用するアセットの場合は、専用のワークスペースがアセット管理機能を完全に提供します。 <a href="../content/marketo-engage-design-studio.md">詳細情報</a> |
| 新機能 | 最近アクセスしたアセット | Journey Optimizer B2B edition アプリのホームページには、「_[!UICONTROL 最近アクセス済み]_ セクションが含まれるようになりました。このセクションには、マーケターまたは管理者向けの最近アクセスしたアセットのリストが表示されます。 このリストを使用すると、一連のアセットページを移動したり検索したりせずに、最近作業したアセットに直接移動できます。 <p>このリストには、変更に関する追加情報が表示されるので、どのアセットで最後のセッションからさらに変更が必要かを決定できます。 メールアセットの場合は、メールアセットが使用されているアカウントジャーニーが表示されます。 <a href="../home-page.md">詳細情報</a> |
| 機能強化 | ジャーニー分割ノード – パスの並べ替え | 分割パスノードでは、パスフィルタリングがトップダウンの順序で評価されます。 各ユーザーまたはアカウントは、一致する最初のパスに沿って進行します。 各パスカードの右上にある上向き矢印と下向き矢印をクリックして、定義済みのパスを並べ替え、リスト内で上下に移動できます。 <a href="../journeys/split-merge-paths-nodes.md#split-paths">詳細情報</a> |
| 機能強化 | ジャーニー分割ノード – 追加のアクティビティ履歴条件属性 | 条件を使用して分割ノードのパスフィルタリングをユーザーごとに定義する場合は、さらに 2 つの属性があります。_開封済みのメール_ および _配信済みのメール_ です。 これらの追加により、メールのアクティビティに基づいてジャーニーの人物をフィルタリングする柔軟性が向上します。 <a href="../journeys/journey-nodes.md#split-paths">詳細情報</a> |

## 2024年8月リリースノート {#Aug-2024}

**リリース日**:2024 年 8 月 29 日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 新機能 | LinkedIn アカウントでマッチしたオーディエンス | アカウントでマッチしたオーディエンスを通じて LinkedIn 広告オーディエンスを生成し、購入グループの空の役割を埋めるのに役立ちます。 購入グループフィルターのセットを定義することで、LinkedIn でマッチしたオーディエンスを維持し、購入グループパラメーターに一致する見込み客をターゲットにすることができます。 <p>この機能は、Experience Platform Destinations を活用して、統合の一部の側面を管理します。 <a href="../data/linkedin-account-matched-audiences.md">詳細情報</a> |
| 機能強化 | ビジュアルコンテンツフラグメントのステータスライフサイクル | ビジュアルフラグメントは、ステータスのライフサイクルを使用して管理されるようになりました。 フラグメントステータスは、メールまたはメールテンプレートで使用できるフラグメントの有無と、フラグメントに加えられる変更を決定します。 <p>この強化されたワークフローにより、プロモーションや通信のカレンダーに従って再利用されたコンテンツを簡単に管理できます。 <a href="../content/fragments.md#fragment-status-and-lifecycle">詳細情報</a> |
