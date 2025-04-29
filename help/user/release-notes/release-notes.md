---
title: リリースノート
description: Adobe Journey Optimizer B2B エディションの最新のリリースノート
exl-id: 7d3f1c26-d8a6-4065-a70f-5b30cb975dc8
source-git-commit: f4c0870e3cf8a8c1db3ed2f11f7ecfdf244f69fe
workflow-type: tm+mt
source-wordcount: '2008'
ht-degree: 81%

---

# Journey Optimizer B2B Edition リリースノート

Adobe Journey Optimizer B2B Edition では、新機能、既存機能の強化およびバグ修正が継続的に提供されます。

Journey Optimizer B2B Edition は、[!DNL Adobe Experience Platform] 上にネイティブに作成され、最新のイノベーションと改善点を継承しています。以下の変更点について詳しくは、[Adobe Experience Platform リリースノート](https://experienceleague.adobe.com/ja/docs/experience-platform/release-notes/latest){target="_blank"}を参照してください。

使用権限、パフォーマンスガードレール、制限について詳しくは、[ 製品説明 ](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} を参照してください。

## 2025.4 リリースノート

**リリース日**：2025年4月29日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | アカウントリスト | 静的または動的アカウントリストを作成して、業界、場所、会社の規模など、定義した条件に基づいて指定顧客をターゲットにできるようになりました。 <a href="../accounts/account-lists.md">詳細情報</a> |
| 機能 | アカウントリストのジャーニーオーケストレーション | ジャーニーアクションノードを使用して、静的アカウントリストのアカウントを追加および削除します。 <a href="../accounts/account-lists-journeys.md#take-an-action-node---add-to-account">詳細情報</a> |
| 機能強化 | Marketo Engageのジャーニーメンバーシップのフィルタリング | ジャーニーオーディエンスにAdobe Journey Optimizer B2B edition アカウントリストを使用してから、Marketo Engage スマートリストで _アカウントリストのメンバー_ フィルターを使用する。 &lt;a href=&quot;../accounts/account-lists-journeys.md#marketo-engage-program---member-of-account-list> 詳細情報 </a> |
| 機能 | 非アクティブフィルター | メールの無操作状態、興味深い瞬間、データ値の変化、訪問した web ページなど、Marketo Engageのキャンペーンやプログラム内の無操作状態に基づいてジャーニーを調整します。 <a href="../journeys/split-merge-paths-nodes.md#activity-filtering">詳細情報</a> |
| 機能強化 | 訪問済み web ページフィルター | Marketo Engageのキャンペーンとプログラムに関連付けられた、訪問した web ページのアクティビティに基づいてジャーニーを調整します。 <a href="../journeys/split-merge-paths-nodes.md#people-path-conditions">詳細情報</a> |

## 2025.3 リリースノート

**リリース日**：2025年4月1日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | アカウントジャーニーの複製 | アカウントジャーニーで重複アクションを使用できるようになりました。 アカウントジャーニーの詳細を複製するか、フローとパス構造の単純なスケルトンのみを複製できます。 <a href="../journeys/journey-overview.md#duplicate-journey">詳細情報</a> |
| 機能 | アカウントジャーニーのマイトークン | アカウントジャーニーに固有の値を持つカスタムトークンのセットを定義できるようになりました。 このカスタムトークンのセットは _マイトークン_ と呼ばれ、これらのカスタムトークンはすべて、ジャーニーメールのオーサリング時にパーソナライゼーション用に使用されます。 <a href="../content/personalization-my-tokens.md">詳細情報</a> |
| 機能 | 購買グループ ステージの削除 | 購入グループステージモデルは、ドラフト状態または公開済み状態の場合に削除できます。 公開（ライブ）されている場合は、ソリューションの関心に関連付けられていない場合にのみ削除できます。 <a href="../buying-groups/buying-group-stages.md#delete-the-buying-group-stages-model">詳細情報</a> |
| 機能強化 | ジャーニーノードの数 | ノードレベルでの公開済みジャーニーメンバーシップのカウントに対する可視性が向上しました。 _ジャーニーマップ_ では、ノードに _[!UICONTROL 入力されたアカウントの合計]_ が表示されます。 アクションノードを選択すると、右側の詳細に _[!UICONTROL まだアクションが実行されていないアカウント]_ も含まれます。 _イベントをリッスン_ ノードの詳細には、_[!UICONTROL この手順のアカウント]_ が含まれます。 この情報を使用して、ライブジャーニー、完了ジャーニーおよび中止されたジャーニーでのアカウントの進行状況を検証します。 |

## 2025.2 リリースノート

**リリース日**：2025年3月11日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | カスタマイズ可能なフィールド - コンテンツフラグメント | コンテンツフラグメントデザイナーは、フラグメント内のコンポーネントのパラメーターを編集可能として指定できます。これにより、メールまたはテンプレートの作成者は、必要に応じてカスタムフィールド値を指定できます。このカスタマイズフラグは、画像、テキストおよびボタンのビジュアルコンポーネントに制限されます。<a href="../content/fragment-authoring.md#enable-fragment-customization">詳細情報</a> |
| 機能 | B2B の組み込みの役割と製品の権限 | Experience Platform には、B2B 製品機能へのアクセスの管理に使用できる、一連の組み込みの（デフォルトの）役割が含まれるようになりました。<a href="../admin/user-management.md#b2b-built-in-roles">詳細情報</a> <br/>管理者は、Adobe Experience Platform でカスタムの役割を定義して、Journey Optimizer B2B Edition 製品の権限を含めることができるようになりました。<a href="../admin/user-management.md#b2b-product-permissions">詳細情報</a> |
| 機能 | ジャーニーの複製タイプ | アカウントジャーニーを複製する際、Journey Optimizer B2B editionで作成されたメールと SMS メッセージを除く、ノードの詳細を含めることができます。 別の方法として、ノードの詳細や設定を行わずに、構造およびパス フローのスケルトン コピーを作成することもできます。 <a href="../journeys/journey-overview.md#duplicate-journey">詳細情報</a> |
| 機能強化 | 4 個の追加のサンプルメールテンプレート | サンプルメールテンプレートライブラリには、再エンゲージメント、通知、育成、フィードバックコンテンツの例として、4 個の SecurFinacial テンプレートが含まれるようになりました。 |

## 2025.1 リリースノート {#Jan-2025}

**リリース日**：2025年2月6日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | エクスペリエンスイベント転送 | 管理者は、Adobe Experience Platform（AEP）ベースのイベント定義を設定できます。これらの設定により、マーケターは、AEP エクスペリエンスイベントに反応するアカウントジャーニーを作成できます。<a href="../admin/configure-aep-events.md">詳細情報</a> |
| 機能 | 有料メディアの宛先 | アカウントジャーニーから有料メディアキャンペーンの対象となる既知の人物を選定し、LinkedIn などの広告プラットフォームでさらに関与できます。アカウントジャーニーで分割パスノードを使用して、特定の行動に基づいてアカウントオーディエンスをセグメント化し、追加のエンゲージメントが必要なアカウントを識別します。次に、Real-Time CDP を通じて、これらのアカウントの人物を、サポートされている有料メディアの宛先への外部顧客オーディエンスに追加します。<a href="../journeys/action-nodes.md#journey-optimizer-b2b-actions">詳細情報</a> |
| 機能 | インテリジェントダッシュボード | よりインテリジェントな分析と正確なアカウントの優先順位付けの AI 生成のインサイトなど、アカウントジャーニーを通じて購買グループの進行状況を表示します。<a href="../dashboards/intelligent-dashboard.md">詳細情報</a> |
| 機能 | 購買グループとアカウントの詳細 | 購買グループとアカウントレベルでインサイトを表示して、顧客との関与を開始する際に、より多くのコンテキストと履歴データを入手します。<p>購買グループの詳細には、検出されたファーストパーティのインテントが含まれます。<a href="../buying-groups/buying-group-details.md">詳細情報</a><p>アカウントの詳細アカウントでは、検出されたエンゲージメントの急増がハイライト表示されるので、カスタマイズされた販売に焦点を当てたエンゲージメントの準備が整ったアカウントに関して販売に警告できます。<a href="../accounts/account-details.md">詳細情報</a> |
| 機能 | ジャーニーの概要 | アカウントジャーニーにアクセスすると、「概要」タブにアクティブなアカウントジャーニーの包括的なスナップショットが表示され、完了とエンゲージメントアクティビティを分類および選定する円グラフと棒グラフを使用してアカウントの進行状況の詳細が表示されます。<a href="../dashboards/journeys-dashboard.md">詳細情報</a> |
| 機能 | Adobe Express の画像編集 | Adobe Express クイックアクションを使用すると、画像に簡単な編集（切り抜きやサイズ変更など）を加え、コンテンツの外観をより洗練されたものにすることができます。<a href="../content/image-edit-adobe-express.md#quick-actions-in-adobe-express">詳細情報</a>  <p>より包括的なデザインツールセットを実現することを目的に、この統合により、Journey Optimizer B2B Edition への完全な Adobe Express ライセンスが有効になります。この設定により、ローカルアセットワークスペース内で完全な Adobe Express ユーザーインターフェイスにアクセスできるようになります。<a href="../content/image-edit-adobe-express.md#adobe-express-enterprise-license">詳細情報</a> |
| 機能 | 購買グループの役割のインテントフィルター | インテントキーワードを送信すると、インテント検出モデルは、リードのアクティビティに基づいて、十分な信頼性を持つソリューション／製品に対する関心を予測します。<a href="../admin/intent-data.md">詳細情報</a> <p>このインテントデータは、購買グループの役割条件を定義するのに使用できます。<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">詳細情報</a> |
| 機能強化 | ジャーニーでの Marketo Engage イベントのサポート | _イベントをリッスン_&#x200B;ジャーニーノードは、人物レベルで _Web ページにアクセス_&#x200B;と&#x200B;_フォームを入力_&#x200B;という 2 つの Marketo Engage イベントをサポートするようになりました。<a href="../journeys/listen-for-event-nodes.md#listen-for-marketo-engage-event">詳細情報</a> |
| 機能強化 | Marketo Engage スマートリストの購買グループフィルター | Marketo Engage で購買グループフィルターを使用してスマートリストを表示および作成します。これらの追加されたフィルターを使用すると、Journey Optimizer B2B Edition 内のアカウントジャーニーから、Marketo Engage キャンペーンおよびプログラムをまたいで購買グループメンバーを抑制したり、含めたりすることができます。<a href="../buying-groups/marketo-engage-smart-list-buying-group-filters.md">詳細情報</a> |
| 機能強化 | ジャーニーと役割の Marketo Engage リストメンバーシップフィルター | Journey Optimizer B2B では、ジャーニーアクティビティの重複を排除することを目的に、_人物でパスを分割_&#x200B;ノードの条件として Marketo Engage リストのメンバーシップを確認します。<a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">詳細情報</a> <p> 購買グループの役割テンプレートの場合は、役割の条件としてリストメンバーシップを使用します。<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">詳細情報</a> |
| 機能強化 | エンゲージメントの概要ダッシュボード | このダッシュボードは、エンゲージメントの包括的なビューを表示するのに更新されています。スナップショットの円グラフと、時間の経過と共にトレンドを示す折れ線グラフを通じて、アカウントと個々のインタラクションのリアルタイムの指標が表示されます。<a href="../dashboards/engagement-dashboard.md">詳細情報</a> |


## 2024年10月リリースノート {#Oct-2024}

**リリース日**：2024年10月29日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | メールテンプレートの条件付きコンテンツ | アカウントレベルとリードレベルの両方で、受信者の行動とプロファイル特性に基づいてメールのコンテンツをパーソナライズします。 <p>メールのビジュアルデザインスペースでアカウントジャーニーのメールを作成する際に、条件付きルールを使用して、任意のコンテンツコンポーネントに複数のバリアントを定義します。<a href="../content/conditional-content.md">詳細情報</a> |
| 機能 | ジャーニーでの&#x200B;_リストに追加_&#x200B;および&#x200B;_リストから削除_&#x200B;の人物アクション | アカウントレベルとリードレベルの両方で、受信者の行動とプロファイル特性に基づいてメールのコンテンツをパーソナライズします。<a href="../journeys/action-nodes.md">詳細情報</a> |
| 機能 | コンテンツガバナンスとコンポーネントのロック | 承認済みのコンテンツデザインに準拠するには、コンテンツガバナンス機能を使用して、メールテンプレートのコンテンツコンポーネントをロックします。メールテンプレートでコンテンツガバナンスをアクティベートすると、マーケターは、許可された要素のみを変更して、コンテンツ戦略に合わせた状態を維持できます。<a href="../content/template-content-governance.md">詳細情報</a> |
| 機能 | 購買グループステージ | カスタムの購買グループのステージングモデルを定義して公開すると、購買グループのライフサイクルステージを通じて購買グループの進行状況を追跡できます。これらのステージを使用して、購買グループのメンバーに対する次の最適なアクションを識別します。ステージの進行状況を判断し、変更に基づいてアクションをトリガーするトランジションルールとジャーニーノードを設定します。<a href="../buying-groups/buying-group-stages.md">詳細情報</a> |
| 機能強化 | 新しい標準メールテンプレート | サンプルテンプレートライブラリに、B2B マーケター向けに設計された追加のメールテンプレートが含まれるようになりました。これらのサンプルテンプレートを開始点として使用し、独自のブランドとメッセージを追加します。<a href="../content/email-templates.md#select-a-design-template">詳細情報</a> |
| 機能強化 | ユーザー属性としてのカスタムフィールド | Experience Platform のアカウントオーディエンススキーマでカスタムのユーザーフィールドが定義されている場合は、これらのフィールドを条件内のユーザー属性として使用することもできます。これらのカスタム属性は次で使用します。 <li>役割テンプレート<a href="../buying-groups/buying-groups-role-templates.md#add-the-template-roles">詳細情報</a></li><li>人物ジャーニーノード別にパスを分割<a href="../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node">詳細情報</a></li> |
| 機能強化 | メールチャネル設定 | Journey Optimizer B2B Edition インターフェイスにメール設定が表示されるようになりました。現在の設定をすばやく確認でき、管理者は「_[!UICONTROL 設定を編集]_」をクリックして Marketo Engage の設定に直接移動し、組織の要件に応じて設定を更新できます。<a href="../admin/configure-channels-emails.md">詳細情報</a> |

## 2024年9月リリースノート {#Sept-2024}

**リリース日**：2024年10月7日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能強化 | 中央アセットライブラリ | 強化された&#x200B;_中央アセットライブラリ_&#x200B;を使用すると、Design Studio ワークスペースをまたいで Marketo Engage インスタンス内のすべての画像アセットを使用できます。Journey Optimizer B2B Edition からの Marketo Engage アセットの編集、削除、移動操作を防ぐガードレールが組み込まれています。これらの保護により、ソースアセット（Marketo Engage Design Studio）が維持され、Journey Optimizer B2B Edition でシームレスな読み取りと再利用が可能になります。<p>Journey Optimizer B2B Edition 専用アセットの場合、特定のワークスペースで完全なアセット管理機能が提供されます。<a href="../content/marketo-engage-design-studio.md">詳細情報</a> |
| 機能 | 最近アクセス済みのアセット | Journey Optimizer B2B Edition アプリのホームページに「_[!UICONTROL 最近アクセス済み]_」セクションが追加され、マーケターや管理者に対して最近アクセス済みのアセットのリストが表示されるようになりました。このリストを使用すると、一連のアセットページを移動して検索することなく、最近作業済みのアセットに直接移動できます。 <p>リストには、変更に関する追加情報が提供され、前回のセッションからさらに変更が必要なアセットを決定できます。メールアセットの場合、メールアセットを使用するアカウントジャーニーが表示されます。<a href="../home-page.md">詳細情報</a> |
| 機能強化 | ジャーニー分割ノード - パスを並べ替え | 分割パスノードでは、パスフィルタリングは上から下へ順に評価されます。各ユーザーまたはアカウントは、一致する最初のパスに沿って進行します。各パスカードの右上にある上向き矢印と下向き矢印をクリックして、定義済みのパスをリスト内で上下に移動することで、パスの順序を変更できます。<a href="../journeys/split-merge-paths-nodes.md#split-paths">詳細情報</a> |
| 機能強化 | ジャーニー分割ノード - 追加のアクティビティ履歴条件属性 | 条件を使用して、人物別に分割ノードのパスフィルタリングを定義する場合、_開封済みのメール_&#x200B;と&#x200B;_配信済みのメール_&#x200B;という 2 つの追加属性があります。これらの追加により、メールのアクティビティに基づいてジャーニー内の人物をフィルタリングする際の柔軟性が向上します。<a href="../journeys/journey-nodes.md#split-paths">詳細情報</a> |

## 2024年8月リリースノート {#Aug-2024}

**リリース日**：2024年8月29日（PT）

このリリースには、次の新機能および機能強化が含まれています。

| タイプ | 項目 | 説明 |
| ---- | ---- | ----------- |
| 機能 | LinkedIn Account Matched Audiences | Account Matched Audiences を通じて LinkedIn 広告オーディエンスを生成し、購買グループ内の空いている役割を埋めるのに役立ちます。一連の購買グループフィルターを定義することで、LinkedIn Matched Audience を維持し、購買グループのパラメーターに一致する見込み客をターゲットにすることができます。 <p>この機能は、Experience Platform の宛先を活用して統合のいくつかの側面を管理します。<a href="../data/linkedin-account-matched-audiences.md">詳細情報</a> |
| 機能強化 | ビジュアルコンテンツフラグメントのステータスライフサイクル | ビジュアルフラグメントは、ステータスライフサイクルを使用して管理されるようになりました。フラグメントのステータスによって、メールまたはメールテンプレートでの使用の可用性と、フラグメントに行われる変更が決定されます。 <p>この強化されたワークフローにより、プロモーションや通信のカレンダーに従って再利用コンテンツを簡単に管理できます。<a href="../content/fragments.md#fragment-status-and-lifecycle">詳細情報</a> |
