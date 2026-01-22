---
title: イベントをリッスン
description: アカウントおよび人物トリガーのイベントノードを設定 – Journey Optimizer B2B editionで購入グループの変更、メールのクリック数、フォームへの入力およびExperience Platform イベントをリッスンします。
feature: Account Journeys
role: User
exl-id: d852660b-f1da-4da0-86f0-85271f55b79f
source-git-commit: 2a676f3cbeb43616a75fa3fa6eb9106230b9fb40
workflow-type: tm+mt
source-wordcount: '1843'
ht-degree: 12%

---

# イベントのリッスン

_イベントをリッスン_ ノードを追加して、イベントが発生した場合に、オーディエンスをジャーニーの次のステップに進めます。

![&#x200B; ビデオ &#x200B;](../../assets/do-not-localize/icon-video.svg){width=&quot;30&quot;, vertical-align=&quot;middle&quot;} [&#x200B; 概要ビデオをご覧ください &#x200B;](#overview-video)

>[!NOTE]
>
>アカウントジャーニーの場合、このノードタイプを人物の分割パスに追加することはできません。

## アカウントイベント

アカウントジャーニーでは、アカウントアクティビティによってトリガーされるイベントに従ってジャーニー内でアカウントを前方に移動する際に、アカウントに基づいたイベントをリッスンできます。

### イベントと制約

| イベント | 制約 |
| ----- | ----------- |
| [!UICONTROL &#x200B; アカウントは興味深い瞬間を持っていた &#x200B;] | タイプ （メール、マイルストーン、Web） <br/> 追加の制約（オプション）: <li>説明</li><li>ソース</li><li>アクティビティの日付</li> <br/> タイムアウト （オプション） |
| [!UICONTROL &#x200B; 勘定科目データ値の変更 &#x200B;] | 属性 <br/> 追加制約（オプション）: <li>新しい値</li><li>前回の値</li><li>アクティビティの日付</li> <br/> タイムアウト （オプション） |
| [!UICONTROL &#x200B; 買付グループのステージの変更 &#x200B;] | ソリューションの関心 <br/> 追加の制約（オプション）: <li>新規ステージ</li><li>前のステージ</li><li>アクティビティの日付</li><br/> Timeout （オプション） |
| [!UICONTROL &#x200B; 購買グループの状態の変更 &#x200B;] | ソリューションの関心 <br/> 追加の制約（オプション）: <li>新規ステータス</li><li>前のステータス</li><li>アクティビティの日付</li><br/> Timeout （オプション） |
| [!UICONTROL &#x200B; 完全性スコアの変更 &#x200B;] | ソリューションの関心 <br/> 追加の制約（オプション）: <li>新規スコア</li><li>以前のスコア</li><li>アクティビティの日付</li><br/> Timeout （オプション） |
| [!UICONTROL &#x200B; エンゲージメントスコアの変更 &#x200B;] | ソリューションの関心 <br/> 追加の制約（オプション）: <li>新規スコア</li><li>以前のスコア</li><li>アクティビティの日付</li><br/> Timeout （オプション） |

### アカウントイベントの追加

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、「**[!UICONTROL イベントをリッスン]**」を選択します。

1. 右側のノードプロパティで、イベントタイプとして **[!UICONTROL アカウント]** を選択します。

   ![ジャーニーノード – アカウントのイベントをリッスン &#x200B;](./assets/node-listen-events-account.png){width="700" zoomable="yes"}

1. リストからイベントを選択します。

1. 「**[!UICONTROL イベントを編集]**」をクリックして、イベントの詳細を定義します。

## 人物イベント

アカウントジャーニーでは、人物のアクティビティによってトリガーされるイベントに従ってジャーニー内でアカウントを転送する場合、人物に基づくイベントをリッスンできます。 また、ユーザー属性に従ってイベントをフィルタリングすることもできます。

### イベントと制約

| 入力タイプ | イベント | 制約 |
| ---------- | ----- | ----------- |
| Journey Optimizer B2B | [!UICONTROL &#x200B; 購入グループに割り当て済み &#x200B;] | ソリューションの関心 <br/><br/> 追加の制約（オプション）: <li>役割</li><li>アクティビティの日付</li><br/> タイムアウト （オプション） |
| | [!UICONTROL &#x200B; メール内のリンクのクリック数 &#x200B;] | メール <br/><br/> 追加の制約（オプション）: <li>リンク</li><li>リンク ID</li><li>モバイルデバイスである</li><li>デバイス</li><li>Platform</li><li>ブラウザー</li><li>予測コンテンツ</li><li>ボットアクティビティ</li><li>ボットアクティビティパターン</li><li>ブラウザー</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL SMS 内のクリックリンク &#x200B;] | メール <br/><br/> 追加の制約（オプション）: <li>リンク</li><li>デバイス</li><li>Platform</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL &#x200B; データ値の変更 &#x200B;] | 人物属性 <br/><br/> 追加の制約（オプション）: <li>新しい値</li><li>前回の値</li><li>理由</li><li>ソース</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL &#x200B; メールを開く &#x200B;] | メール <br/><br/> 追加の制約（オプション）: <li>リンク</li><li>リンク ID</li><li>モバイルデバイスである</li><li>デバイス</li><li>Platform</li><li>ブラウザー</li><li>予測コンテンツ</li><li>ボットアクティビティ</li><li>ボットアクティビティパターン</li><li>ブラウザー</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL &#x200B; 購買グループから削除されました &#x200B;] | ソリューションの関心 <br/> アクティビティの日付（オプション） <br/> タイムアウト（オプション） |
| | [!UICONTROL &#x200B; スコアが変更されました &#x200B;] | スコア名 <br/><br/> 追加の制約（オプション）:<li>変更</li><li>新規スコア</li><li>緊急度</li><li>優先度</li><li>相対スコア</li><li>相対的緊急度</li><li>アクティビティの日付</li><li>分回数</li><br/> タイムアウト （オプション） |
| | [!UICONTROL SMS バウンス &#x200B;] | SMS メッセージ <br/><br/> 追加の制約（オプション）: <li>アクティビティの日付</li><li>最小回数</li><br/> タイムアウト （オプション） |
| Marketo Engage | [!UICONTROL &#x200B; 訪問回数 Web ページ &#x200B;] | Web ページ <br/> 一致させる 1 つ以上のMarketo Engage ページを選択します。 <br/><br/> 追加の制約（オプション）: <li>クエリ文字列</li><li>クライアント IP アドレス</li><li>リファラー</li><li>ユーザーエージェント</li><li>検索エンジン</li><li>検索クエリ</li><li>トークン</li><li>ブラウザー</li><li>Platform</li><li>デバイス</li><li>アクティビティの日付</li> |
| | [!UICONTROL &#x200B; フォームに入力 &#x200B;] | フォーム <br/> 一致するMarketo Engage フォームを 1 つ以上選択します。 <br/><br/> 追加の制約（オプション）: <li>アクティビティの日付</li><li>クエリ文字列</li><li>クライアント IP アドレス</li><li>リファラー</li><li>ユーザーエージェント</li><li>Platform</li><li>デバイス</li><br/> タイムアウト （オプション） |
| Adobe Experience Platform | [!UICONTROL &#x200B; イベント定義 &#x200B;] | イベントタイプ <br/><br/> 追加の制約（オプション）: <li>フィールド</li> <br/> 追加の制約（サポート対象外）: <li>アクティビティの日付</li><li>分回数</li><br/> Timeout （オプション） |

### 人物イベントフィルター

| フィルター | 説明 |
| ------------ | ----------- |
| [!UICONTROL &#x200B; アクティビティ履歴 &#x200B;] > [!UICONTROL &#x200B; メール &#x200B;] | ジャーニーの前の段階で選択した 1 つ以上のメールメッセージを使用して評価される条件に基づくメールアクティビティ： <li>[!UICONTROL &#x200B; メール内のクリックされたリンク &#x200B;] <li>メールを開封済み <li>電子メールで配信されました <li>電子メール <!-- <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not have the email activity).--> を送信しました |
| [!UICONTROL &#x200B; アクティビティ履歴 &#x200B;] > [!UICONTROL SMS メッセージ &#x200B;] | ジャーニーの前の段階で選択した 1 つ以上の SMS メッセージを使用して評価される条件に基づく SMS アクティビティ。 <li>[!UICONTROL SMS 内のクリックされたリンク &#x200B;] <li>[!UICONTROL SMS バウンス &#x200B;] <!--  <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not have the SMS activity). --> |
| [!UICONTROL &#x200B; アクティビティ履歴 &#x200B;] > [!UICONTROL &#x200B; データ値が変更されました &#x200B;] | 選択したユーザー属性に対して、値が変更されました。 次のような変更タイプがあります。 <li>新しい値<li>前回の値<li>理由<li>ソース<li>アクティビティの日付<li>分回 <!--  <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not have a data value change). --> |
| [!UICONTROL &#x200B; アクティビティの履歴 &#x200B;] > [!UICONTROL Had Interesting Moment] | 関連するMarketo Engage インスタンスで定義される興味深いモーメントアクティビティ。 制約には次のものが含まれます。 <li>マイルストーン<li>メール<li>Web <!-- <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not have an interesting moment).--> |
| [!UICONTROL &#x200B; アクティビティ履歴 &#x200B;] > [!UICONTROL &#x200B; 訪問した web ページ &#x200B;] | 関連付けられたMarketo Engage インスタンスによって管理される 1 つ以上の web ページに対して実行される web ページアクティビティ。 制約には次のものが含まれます。 <li>Web ページ （必須）<li>アクティビティの日付<li>クライアント IP アドレス <li>クエリ文字列 <li>リファラー <li>ユーザーエージェント <li>検索エンジン <li>検索クエリ <li>パーソナライズ URL <li>トークン <li>ブラウザー <li>Platform <li>デバイス <li>分回 <!-- <br>**[!UICONTROL Switch to inactivity filter]** - Use this option to filter based on lack of activity (a person did not visit the web page). --> |
| [!UICONTROL &#x200B; 人物の属性 &#x200B;] | ユーザープロファイルからの属性。以下が含まれます。 <li>市区町村 <li>国 <li>生年月日 <li>メールアドレス <li>メール無効 <li>メール中断済み <li>名 <li>推測される都道府県 / 地域<li>役職 <li>姓 <li>携帯電話番号 <li>人物エンゲージメントスコア <li>電話番号 <li>郵便番号 <li>ステート <li>配信停止完了 <li>登録解除の理由 |
| [!UICONTROL &#x200B; 特殊フィルター &#x200B;] > [!UICONTROL &#x200B; 購買グループのメンバー &#x200B;] | 次の 1 つ以上の条件に照らして評価された、その人物は購買グループ・メンバーであるか、そうでないメンバーである： <li>ソリューションの関心</li><li>購買グループのステータス</li><li>完全性スコア</li><li>エンゲージメントスコア</li><li>役割</li> |
| [!UICONTROL &#x200B; 特殊フィルター &#x200B;] > [!UICONTROL &#x200B; リストのメンバー &#x200B;] | ユーザーが 1 つ以上のMarketo Engage リストのメンバーである、またはメンバーではない。 |
| [!UICONTROL &#x200B; 特殊フィルター &#x200B;] > [!UICONTROL &#x200B; プログラムのメンバー &#x200B;] | ユーザーが 1 つ以上のMarketo Engage プログラムのメンバーである、またはメンバーではない。 |

### 人物イベントを追加

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、「**[!UICONTROL イベントをリッスン]**」を選択します。

1. 右側のノードプロパティで、イベントタイプとして **[!UICONTROL People]** を選択します。

   ![ジャーニー ノード – 人のイベントをリッスン &#x200B;](./assets/node-listen-events-people.png){width="700" zoomable="yes"}

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

   ![&#x200B; エクスペリエンスイベントをリッスン &#x200B;](./assets/node-listen-events-people-me-event.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL イベントを編集]**」をクリックし、一致させる 1 つ以上の web ページと、イベントの追加の制約を定義します。

   * （必須） _[!UICONTROL イベントを編集]_ ダイアログで **[!UICONTROL Web ページ]** または **[!UICONTROL フォームへの入力]** 制約を定義します。 選択した 1 つ以上のページまたはフォームと照合するには、**[!UICONTROL is]** （デフォルト）を使用します。 選択した 1 つ以上のページ/フォームを除外して、すべてのページの訪問/フォームを照合する **[!UICONTROL 次に当てはまらない]** を使用します。 または、**[!UICONTROL is any]** 演算子を使用して、Marketo Engage web ページの訪問または入力済みフォームで照合します。

   * （任意）「**[!UICONTROL 制約を追加]**」をクリックして、制約に使用するフィールドを選択します。 演算子とフィールドの値を設定します。

     ![&#x200B; エクスペリエンスイベントをリッスン &#x200B;](./assets/node-listen-events-people-me-event-edit-dialog.png){width="700" zoomable="yes"}

     このアクションを繰り返して、必要に応じてフィールド制約を追加できます。

   * 必要に応じて、「**[!UICONTROL フィルター]**」タブを選択して [&#x200B; イベントのフィルターを追加 &#x200B;](#add-a-filter-to-the-people-event) します。

   * 制約とフィルターを定義したら、「**[!UICONTROL 完了]**」をクリックします。

1. 必要に応じて、**[!UICONTROL タイムアウト]** オプションを設定して、イベントをリッスンする期間を制限します（[&#x200B; イベントノードへのタイムアウトの追加 &#x200B;](#add-a-timeout-to-an-event-node) を参照）。

1. ジャーニーマップで、イベントが発生したときに実行する次のノードを追加します。

### エクスペリエンスイベントをリッスン

管理者は [Adobe Experience Platform（AEP）エクスペリエンスイベント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/classes/experienceevent){target="_blank"} を選択できます。これにより、マーケターは、イベントに反応するアカウントおよび人物のジャーニーをほぼリアルタイムで作成できます。 ジャーニーでのエクスペリエンスイベントの使用は、次の 2 つの手順で構成されます。

1. 管理者 [&#x200B; イベントタイプと関心のあるフィールドを選択 &#x200B;](../admin/configure-aep-events.md#select-an-event) して、ジャーニーで使用できるようにします。

2. ジャーニーで、「_イベントをリッスン_」ノードを追加し、ユーザーベースのイベント用にExperience Platform イベントタイプを選択します。

<!--
![Video](../../assets/do-not-localize/icon-video.svg){width="30", vertical-align="middle"} [Watch the video overview](../admin/configure-aep-events.md#overview-video) -->

ジャーニーにエクスペリエンスイベントを含めるには（_T） :_

1. ジャーニーマップで **[!UICONTROL イベントをリッスン]** ノードを選択します。

1. （アカウントジャーニーのみ）右側のノードプロパティで、イベントタイプとして **[!UICONTROL 人物]** を選択します。

1. イベントを選択します。

   **_アカウントジャーニー_** の場合は、「**[!UICONTROL 人物イベントを選択]** セレクターの矢印をクリックし、「**[!UICONTROL Adobe Experience Platform]**」セクションまでスクロールします。

   ![&#x200B; エクスペリエンスイベントをリッスン &#x200B;](./assets/node-listen-events-people-aep-events.png){width="700" zoomable="yes"}

   個人のジャーニーの場合は、「**[!UICONTROL イベントを選択]** セレクターの矢印をクリックし、イベントを選択します。

1. 「**[!UICONTROL イベントを編集]**」をクリックし、イベントの 1 つ以上の制約を定義します。

   ![&#x200B; イベントの編集 &#x200B;](./assets/node-listen-events-people-aep-events-edit.png){width="400" zoomable="yes"}

   使用可能な制約は、イベント設定の管理フィールドとして定義されます。

   * 「**[!UICONTROL 制約を追加]**」をクリックして、制約に使用するフィールドを選択します。

   * 制約の条件を入力します。

     デフォルトの **[!UICONTROL is]** 演算子を使用して、1 つ以上のフィールド値に一致させることができます。 または、**[!UICONTROL is not]** 演算子を使用して、指定した 1 つ以上の値を除外し、すべての値を照合することもできます。

     ![&#x200B; エクスペリエンスイベントをリッスン &#x200B;](./assets/node-listen-events-people-aep-events-edit-dialog.png){width="700" zoomable="yes"}

   * 必要に応じて、「**[!UICONTROL フィルター]**」タブを選択して [&#x200B; イベントのフィルターを追加 &#x200B;](#add-a-filter-to-the-people-event) します。

   * （任意）「**[!UICONTROL 制約を追加]**」をクリックして上記の手順を繰り返し、必要に応じてフィールドの制約を追加します。

   * 制約とフィルターを定義したら、「**[!UICONTROL 完了]**」をクリックします。

1. 必要に応じて、**[!UICONTROL タイムアウト]** オプションを設定して、イベントをリッスンする期間を制限します（[&#x200B; イベントノードへのタイムアウトの追加 &#x200B;](#add-a-timeout-to-an-event-node) を参照）。

1. ジャーニーマップで、イベントが発生したときに実行する次のノードを追加します。

1. ジャーニーの残りのノードを完了して [&#x200B; 公開 &#x200B;](./journeys-overview.md) します。

   ジャーニーがライブ（公開）になり、_イベントをリッスン_ ノードに到達すると、AEP エクスペリエンスイベントのリッスンが開始されます。

### 人物イベントへのフィルターの追加

（アカウントジャーニーのみ）

1. イベントを定義したら、**[!UICONTROL イベントを編集]** ダイアログの _[!UICONTROL フィルター]_ タブを選択します。

   ![&#x200B; ユーザーによるイベントノードをリッスン – イベントを編集するための「フィルター」タブを選択 &#x200B;](./assets/node-listen-event-people-edit-event-filters.png){width="700" zoomable="yes"}

1. イベントの対象ユーザーを絞り込むためのフィルターを 1 つ以上追加します。

   * 任意の [&#x200B; 人物フィルター &#x200B;](#people-event-filters) を左側のナビゲーションからドラッグ&amp;ドロップし、一致の定義を完了します。

     >[!NOTE]
     >
     >Experience Platformのアカウントオーディエンススキーマで定義されたカスタム人物フィールドがある場合、これらのフィールドは **[!UICONTROL 属性]** でも使用でき、フィルターで人物属性として使用できます。

   * 上部の **[!UICONTROL フィルターロジック]** を適用して、フィルタリングを微調整します。 すべてのフィルターまたは任意のフィルターに一致するように選択します。

     ![&#x200B; イベント定義で使用される人物フィルター &#x200B;](./assets/node-split-conditions-people.png){width="700" zoomable="yes"}

   * 「**[!UICONTROL 完了]**」をクリックします。

## イベントノードへのタイムアウトの追加

必要に応じて、ジャーニーがイベントを待機する時間を定義します。 他のノードを追加できるタイムアウトパスを定義しない限り、ジャーニーはタイムアウトの後に終了します。

1. 「**[!UICONTROL タイムアウト]**」オプションを有効にします。

1. ジャーニーがイベントの発生を待ってからタイムアウトになるまでの時間を選択します。

   ここでパスを終了するか、別のパスを設定して別の操作を実行することができます。

1. ジャーニーに新しいパスを作成し、イベントが発生しなかったときにアカウントに適用できるアクションとイベントを追加するには、「**[!UICONTROL タイムアウトパスを設定]**」チェックボックスを選択します。

   ![ジャーニーイベントノード – タイムアウトパスを設定 &#x200B;](./assets/node-event-timeout-set-path.png){width="700" zoomable="yes"}

<!-- ## Overview video

>[!VIDEO](https://video.tv.adobe.com/v/3443235/?captions=jpn&learn=on) -->
