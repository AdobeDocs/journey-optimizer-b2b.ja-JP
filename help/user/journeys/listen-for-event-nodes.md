---
title: イベントをリッスン
description: アカウントおよび人物トリガーのイベントノードを設定 – Journey Optimizer B2B editionで購入グループの変更、メールのクリック数、フォームへの入力およびExperience Platform イベントをリッスンします。
feature: Account Journeys
role: User
exl-id: d852660b-f1da-4da0-86f0-85271f55b79f
source-git-commit: f5fc362d52ff83335c71b5efe7ea2915d6a7e330
workflow-type: tm+mt
source-wordcount: '1833'
ht-degree: 12%

---

# イベントのリッスン

_イベントをリッスン_ ノードを追加して、イベントが発生した場合に、オーディエンスをアカウントジャーニーの次のステップに進めます。

![ ビデオ ](../../assets/do-not-localize/icon-video.svg){width=&quot;30&quot;, vertical-align=&quot;middle&quot;} [ 概要ビデオをご覧ください ](#overview-video)

>[!NOTE]
>
>このノードタイプを人物による分割パスに追加することはできません。

## アカウントイベント

アカウントアクティビティによってトリガーされるイベントに従ってジャーニー内でアカウントを転送する場合は、アカウントに基づいたイベントをリッスンします。

### イベントと制約

| イベント | 制約 |
| ----- | ----------- |
| [!UICONTROL  アカウントは興味深い瞬間を持っていた ] | タイプ （メール、マイルストーン、Web） <br/> 追加の制約（オプション）: <li>説明</li><li>ソース</li><li>アクティビティの日付</li> <br/> タイムアウト （オプション） |
| [!UICONTROL  勘定科目データ値の変更 ] | 属性 <br/> 追加制約（オプション）: <li>新しい値</li><li>前回の値</li><li>アクティビティの日付</li> <br/> タイムアウト （オプション） |
| [!UICONTROL  買付グループのステージの変更 ] | ソリューションの関心 <br/> 追加の制約（オプション）: <li>新規ステージ</li><li>前のステージ</li><li>アクティビティの日付</li><br/> Timeout （オプション） |
| [!UICONTROL  購買グループの状態の変更 ] | ソリューションの関心 <br/> 追加の制約（オプション）: <li>新規ステータス</li><li>前のステータス</li><li>アクティビティの日付</li><br/> Timeout （オプション） |
| [!UICONTROL  完全性スコアの変更 ] | ソリューションの関心 <br/> 追加の制約（オプション）: <li>新規スコア</li><li>以前のスコア</li><li>アクティビティの日付</li><br/> Timeout （オプション） |
| [!UICONTROL  エンゲージメントスコアの変更 ] | ソリューションの関心 <br/> 追加の制約（オプション）: <li>新規スコア</li><li>以前のスコア</li><li>アクティビティの日付</li><br/> Timeout （オプション） |

### アカウントイベントの追加

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、「**[!UICONTROL イベントをリッスン]**」を選択します。

1. 右側のノードプロパティで、イベントタイプとして **[!UICONTROL アカウント]** を選択します。

   ![ジャーニーノード – アカウントのイベントをリッスン ](./assets/node-listen-events-account.png){width="700" zoomable="yes"}

1. リストからイベントを選択します。

1. 「**[!UICONTROL イベントを編集]**」をクリックして、イベントの詳細を定義します。

## 人物イベント

人物のアクティビティによってトリガーされるイベントに従って、ジャーニー内でアカウントを前方に移動させる場合は、人物に基づいたイベントをリッスンします。 また、ユーザー属性に従ってイベントをフィルタリングすることもできます。

### イベントと制約

| 入力タイプ | イベント | 制約 |
| ---------- | ----- | ----------- |
| Journey Optimizer B2B | [!UICONTROL  購入グループに割り当て済み ] | ソリューションの関心 <br/><br/> 追加の制約（オプション）: <li>役割</li><li>アクティビティの日付</li><br/> タイムアウト （オプション） |
| | [!UICONTROL  メール内のリンクのクリック数 ] | メール <br/><br/> 追加の制約（オプション）: <li>リンク</li><li>リンク ID</li><li>モバイルデバイスである</li><li>デバイス</li><li>Platform</li><li>ブラウザー</li><li>予測コンテンツ</li><li>ボットアクティビティ</li><li>ボットアクティビティパターン</li><li>ブラウザー</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL SMS 内のクリックリンク ] | メール <br/><br/> 追加の制約（オプション）: <li>リンク</li><li>デバイス</li><li>Platform</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL  データ値の変更 ] | 人物属性 <br/><br/> 追加の制約（オプション）: <li>新しい値</li><li>前回の値</li><li>理由</li><li>ソース</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL  メールを開く ] | メール <br/><br/> 追加の制約（オプション）: <li>リンク</li><li>リンク ID</li><li>モバイルデバイスである</li><li>デバイス</li><li>Platform</li><li>ブラウザー</li><li>予測コンテンツ</li><li>ボットアクティビティ</li><li>ボットアクティビティパターン</li><li>ブラウザー</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL  購買グループから削除されました ] | ソリューションの関心 <br/> アクティビティの日付（オプション） <br/> タイムアウト（オプション） |
| | [!UICONTROL  スコアが変更されました ] | スコア名 <br/><br/> 追加の制約（オプション）:<li>変更</li><li>新規スコア</li><li>緊急度</li><li>優先度</li><li>相対スコア</li><li>相対的緊急度</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL SMS バウンス ] | SMS メッセージ <br/><br/> 追加の制約（オプション）: <li>アクティビティの日付</li><li>最小回数</li><br/> タイムアウト （オプション） |
| Marketo Engage | [!UICONTROL  訪問回数 Web ページ ] | Web ページ <br/> 一致させる 1 つ以上のMarketo Engage ページを選択します。 <br/><br/> 追加の制約（オプション）: <li>クエリ文字列</li><li>クライアント IP アドレス</li><li>リファラー</li><li>ユーザーエージェント</li><li>検索エンジン</li><li>検索クエリ</li><li>トークン</li><li>ブラウザー</li><li>Platform</li><li>デバイス</li><li>アクティビティの日付</li> |
| | [!UICONTROL  フォームに入力 ] | フォーム <br/> 一致するMarketo Engage フォームを 1 つ以上選択します。 <br/><br/> 追加の制約（オプション）: <li>アクティビティの日付</li><li>クエリ文字列</li><li>クライアント IP アドレス</li><li>リファラー</li><li>ユーザーエージェント</li><li>Platform</li><li>デバイス</li><br/> タイムアウト （オプション） |
| Adobe Experience Platform | [!UICONTROL  イベント定義 ] | イベントタイプ <br/><br/> 追加の制約（オプション）: <li>フィールド</li> <br/> 追加の制約（サポート対象外）: <li>アクティビティの日付</li><li>分回数</li><br/> Timeout （オプション） |

### 人物イベントフィルター

| フィルター | 説明 |
| ------------ | ----------- |
| [!UICONTROL  アクティビティ履歴 ] > [!UICONTROL  メール ] | ジャーニーの前の段階で選択した 1 つ以上のメールメッセージを使用して評価される条件に基づくメールアクティビティ： <li>[!UICONTROL  メール内のクリックされたリンク ] <li>メールを開封済み <li>電子メールで配信されました <li>電子メール <!-- <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not have the email activity).--> を送信しました |
| [!UICONTROL  アクティビティ履歴 ] > [!UICONTROL SMS メッセージ ] | ジャーニーの前の段階で選択した 1 つ以上の SMS メッセージを使用して評価される条件に基づく SMS アクティビティ。 <li>[!UICONTROL SMS 内のクリックされたリンク ] <li>[!UICONTROL SMS バウンス ] <!--  <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not have the SMS activity). --> |
| [!UICONTROL  アクティビティ履歴 ] > [!UICONTROL  データ値が変更されました ] | 選択したユーザー属性に対して、値が変更されました。 次のような変更タイプがあります。 <li>新しい値<li>前回の値<li>理由<li>ソース<li>アクティビティの日付<li>分回 <!--  <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not have a data value change). --> |
| [!UICONTROL  アクティビティの履歴 ] > [!UICONTROL Had Interesting Moment] | 関連するMarketo Engage インスタンスで定義される興味深いモーメントアクティビティ。 制約には次のものが含まれます。 <li>マイルストーン<li>メール<li>Web <!-- <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not have an interesting moment).--> |
| [!UICONTROL  アクティビティ履歴 ] > [!UICONTROL  訪問した web ページ ] | 関連付けられたMarketo Engage インスタンスによって管理される 1 つ以上の web ページに対して実行される web ページアクティビティ。 制約には次のものが含まれます。 <li>Web ページ （必須）<li>アクティビティの日付<li>クライアント IP アドレス <li>クエリ文字列 <li>リファラー <li>ユーザーエージェント <li>検索エンジン <li>検索クエリ <li>パーソナライズ URL <li>トークン <li>ブラウザー <li>Platform <li>デバイス <li>分回 <!-- <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not visit the web page). --> |
| [!UICONTROL  人物の属性 ] | ユーザープロファイルからの属性。以下が含まれます。 <li>市区町村 <li>国 <li>生年月日 <li>メールアドレス <li>メール無効 <li>メール中断済み <li>名 <li>推測される都道府県 / 地域<li>役職 <li>姓 <li>携帯電話番号 <li>人物エンゲージメントスコア <li>電話番号 <li>郵便番号 <li>ステート <li>登録解除 <li>登録解除の理由 |
| [!UICONTROL  特殊フィルター ] > [!UICONTROL  購買グループのメンバー ] | 次の 1 つ以上の条件に照らして評価された、その人物は購買グループ・メンバーであるか、そうでないメンバーである： <li>ソリューションの関心</li><li>購買グループのステータス</li><li>完全性スコア</li><li>エンゲージメントスコア</li><li>役割</li> |
| [!UICONTROL  特殊フィルター ] > [!UICONTROL  リストのメンバー ] | ユーザーが 1 つ以上のMarketo Engage リストのメンバーである、またはメンバーではない。 |
| [!UICONTROL  特殊フィルター ] > [!UICONTROL  プログラムのメンバー ] | ユーザーが 1 つ以上のMarketo Engage プログラムのメンバーである、またはメンバーではない。 |

### 人物イベントを追加

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、「**[!UICONTROL イベントをリッスン]**」を選択します。

1. 右側のノードプロパティで、イベントタイプとして **[!UICONTROL People]** を選択します。

   ![ジャーニー ノード – 人のイベントをリッスン ](./assets/node-listen-events-people.png){width="700" zoomable="yes"}

1. リストからイベントを選択します。

1. 「**[!UICONTROL イベントを編集]**」をクリックして、イベントの詳細を定義します。

### Marketo Engage イベントをリッスン

接続したMarketo Engage インスタンスに web ページがある場合、これらの web ページへの訪問/訪問なし、および入力された/または入力されなかったMarketo Engage フォームに基づいてイベントをトリガーできます。

1. ジャーニーマップで **[!UICONTROL イベントをリッスン]** ノードを選択します。

1. 右側のノードプロパティで、イベントタイプとして **[!UICONTROL People]** を選択します。

1. **[!UICONTROL 人物イベントを選択]** セレクターの矢印をクリックし、メニューをスクロールして「**[!UICONTROL Marketo Engage]**」セクションを表示します。

1. Market Engage アクティビティタイプを選択します。

   * **[!UICONTROL Web ページを訪問]**。
   * **[!UICONTROL フォームに入力]**

   ![ エクスペリエンスイベントをリッスン ](./assets/node-listen-events-people-me-event.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL イベントを編集]**」をクリックし、一致させる 1 つ以上の web ページと、イベントの追加の制約を定義します。

   * （必須） _[!UICONTROL イベントを編集]_ ダイアログで **[!UICONTROL Web ページ]** または **[!UICONTROL フォームへの入力]** 制約を定義します。 選択した 1 つ以上のページまたはフォームと照合するには、**[!UICONTROL is]** （デフォルト）を使用します。 選択した 1 つ以上のページ/フォームを除外して、すべてのページの訪問/フォームを照合する **[!UICONTROL 次に当てはまらない]** を使用します。 または、**[!UICONTROL is any]** を使用して、Marketo Engage web ページの訪問または入力済みフォームに一致させます。

   * （任意）「**[!UICONTROL 制約を追加]**」をクリックして、制約に使用するフィールドを選択します。 演算子とフィールドの値を設定します。

     ![ エクスペリエンスイベントをリッスン ](./assets/node-listen-events-people-me-event-edit-dialog.png){width="700" zoomable="yes"}

     このアクションを繰り返して、必要に応じてフィールド制約を追加できます。

   * 必要に応じて、「**[!UICONTROL フィルター]**」タブを選択して [ イベントのフィルターを追加 ](#add-a-filter-to-the-people-event) します。

   * 制約とフィルターを定義したら、「**[!UICONTROL 完了]**」をクリックします。

1. 必要に応じて、**[!UICONTROL タイムアウト]** オプションを設定して、イベントをリッスンする期間を制限します（[ イベントノードへのタイムアウトの追加 ](#add-a-timeout-to-an-event-node) を参照）。

1. ジャーニーマップで、イベントが発生したときに実行する次のノードを追加します。

### エクスペリエンスイベントをリッスン

管理者は、Adobe Experience Platform（AEP）ベースのイベント定義を設定できます。これにより、マーケターは、[AEP Experience Events](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/experienceevent){target="_blank"} に反応するアカウントジャーニーを作成できます。 アカウントジャーニーでAEP エクスペリエンスイベントを使用するには、次の 2 つの手順があります。

1. [AEP イベント定義を作成して公開します ](../admin/configure-aep-events.md)。

2. アカウントジャーニーで、「_イベントをリッスン_」ノードを追加し、ユーザーベースのイベント用に「Experience Platform イベント定義」を選択します。

![ ビデオ ](../../assets/do-not-localize/icon-video.svg){width=&quot;30&quot;, vertical-align=&quot;middle&quot;} [ ビデオの概要をご覧ください ](../admin/configure-aep-events.md#overview-video)

ジャーニーにエクスペリエンスイベントを含めるには（_T） :_

1. ジャーニーマップで **[!UICONTROL イベントをリッスン]** ノードを選択します。

1. 右側のノードプロパティで、イベントタイプとして **[!UICONTROL People]** を選択します。

1. **[!UICONTROL 人物イベントを選択]** セレクターの矢印をクリックし、メニューをスクロールして「**[!UICONTROL Adobe Experience Platform]**」セクションを表示します。

   ![ エクスペリエンスイベントをリッスン ](./assets/node-listen-events-people-aep-events.png){width="700" zoomable="yes"}

1. イベントを選択します。

   ノードの詳細で、イベントタイプが空と表示されます。

   ![ イベントの編集 ](./assets/node-listen-events-people-aep-events-edit.png){width="400" zoomable="yes"}

1. 「**[!UICONTROL イベントを編集]**」をクリックし、イベントタイプとイベントの追加の制約を定義します。

   * （必須） _[!UICONTROL イベントを編集]_ ダイアログで、イベントタイプを定義します。 デフォルトの **[!UICONTROL is]** 演算子を使用して、選択した 1 つ以上のイベントタイプに一致させることができます。 または、**[!UICONTROL is not]** 演算子を使用すると、選択した 1 つ以上のイベントタイプを除外して、すべてのイベントタイプを照合できます。

   * （任意）「**[!UICONTROL 制約を追加]**」をクリックして、制約に使用するフィールドを選択します。 演算子とフィールドの値を設定します。

     ![ エクスペリエンスイベントをリッスン ](./assets/node-listen-events-people-aep-events-edit-dialog.png){width="700" zoomable="yes"}

     >[!NOTE]
     >
     >_アクティビティの日付_ および _最小回数_ の制約はサポートされていません。

     このアクションを繰り返して、必要に応じてフィールド制約を追加できます。

   * 必要に応じて、「**[!UICONTROL フィルター]**」タブを選択して [ イベントのフィルターを追加 ](#add-a-filter-to-the-people-event) します。

   * 制約とフィルターを定義したら、「**[!UICONTROL 完了]**」をクリックします。

1. 必要に応じて、**[!UICONTROL タイムアウト]** オプションを設定して、イベントをリッスンする期間を制限します（[ イベントノードへのタイムアウトの追加 ](#add-a-timeout-to-an-event-node) を参照）。

1. ジャーニーマップで、イベントが発生したときに実行する次のノードを追加します。

1. ジャーニーの残りのノードを完了して [ 公開 ](./journey-overview.md) します。

   ジャーニーがライブ（公開）になり、_イベントをリッスン_ ノードに到達すると、AEP エクスペリエンスイベントのリッスンが開始されます。

### 人物イベントへのフィルターの追加

1. イベントを定義したら、**[!UICONTROL イベントを編集]** ダイアログの _[!UICONTROL フィルター]_ タブを選択します。

   ![ ユーザーによるイベントノードをリッスン – イベントを編集するための「フィルター」タブを選択 ](./assets/node-listen-event-people-edit-event-filters.png){width="700" zoomable="yes"}

1. イベントの対象ユーザーを絞り込むためのフィルターを 1 つ以上追加します。

   * 任意の [ 人物フィルター ](#people-event-filters) を左側のナビゲーションからドラッグ&amp;ドロップし、一致の定義を完了します。

     >[!NOTE]
     >
     >Experience Platformのアカウントオーディエンススキーマで定義されたカスタム人物フィールドがある場合、これらのフィールドは **[!UICONTROL 属性]** でも使用でき、フィルターで人物属性として使用できます。

   * 上部の **[!UICONTROL フィルターロジック]** を適用して、フィルタリングを微調整します。 すべてのフィルターまたは任意のフィルターに一致するように選択します。

     ![ イベント定義で使用される人物フィルター ](./assets/node-split-conditions-people.png){width="700" zoomable="yes"}

   * 「**[!UICONTROL 完了]**」をクリックします。

## イベントノードへのタイムアウトの追加

必要に応じて、ジャーニーがイベントを待機する時間を定義します。 他のノードを追加できるタイムアウトパスを定義しない限り、ジャーニーはタイムアウトの後に終了します。

1. 「**[!UICONTROL タイムアウト]**」オプションを有効にします。

1. ジャーニーがイベントの発生を待ってからタイムアウトになるまでの時間を選択します。

   ここでパスを終了するか、別のパスを設定して別の操作を実行することができます。

1. ジャーニーに新しいパスを作成し、イベントが発生しなかったときにアカウントに適用できるアクションとイベントを追加するには、「**[!UICONTROL タイムアウトパスを設定]**」チェックボックスを選択します。

   ![ジャーニーイベントノード – タイムアウトパスを設定 ](./assets/node-event-timeout-set-path.png){width="700" zoomable="yes"}

## 概要ビデオ

>[!VIDEO](https://video.tv.adobe.com/v/3443219/?learn=on)
