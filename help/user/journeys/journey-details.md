---
title: ジャーニーの詳細
description: Adobe Journey Optimizer B2B Editionでアカウントと人物のジャーニーのパフォーマンスをモニタリングします。 各ジャーニーの完了率、エンゲージメント、チャネル指標を確認できます。
feature: Dashboards, Account Journeys, Person Journeys
role: User
exl-id: 09a0e06a-1fd3-44da-9774-23f125f2823d
autotag-review: 2026-03-30T23:21:08.953Z
TQID: 'https://experienceleague.adobe.com/a5tIOW39sq3Lq30pQ3yr7-IvLGaAXC6LKqY8-mpxCDY'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
    internal-label: Journeys
  - id: f979fe0e-02fe-4599-b492-7b3df1d4e7dc
    internal-label: Intelligent Insights
  - id: 7da10825-0f0b-5df3-8450-465ae8d76951
    internal-label: Dashboards
subfeature_v2:
  - id: c31bc6c7-76bc-467b-80c0-7315a4e3f6be
    internal-label: Account Journeys
  - id: ba367494-9862-4596-bd6f-299c7e10a46b
    internal-label: Person Journeys
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 5c053f91ea231cd8517e2329b7170aa08c33dc24
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 1%
---
# ジャーニーの詳細

[!DNL Adobe Journey Optimizer B2B Edition]で、公開されたアカウントまたは個人のジャーニーを開き、**[!UICONTROL 概要]** タブを選択します。 選択したジャーニーの進捗状況、エンゲージメント、チャネルのパフォーマンスを確認します。

アカウントのアカウントジャーニーレポートの進捗状況。 個人ジャーニーは、個人の進捗状況を報告します。 使用可能なウィジェットと指標ラベルは、ジャーニータイプによって異なります。 ダッシュボードの詳細に対応するタブを選択します。

ジャーニーをまたいで集計されたメール指標については、[&#x200B; メールパフォーマンスレポート &#x200B;](../dashboards/email-performance-dashboard.md)を使用してください。

>[!BEGINTABS]

>[!TAB  アカウントジャーニー]

アカウントジャーニーダッシュボードには、アカウントの進捗状況、エンゲージメント、チャネルパフォーマンス、生成AIの概要が表示されます。 データがチャートとテーブルの入力を開始するのに約4時間かかります。

進捗状況、エンゲージメント、チャネルパフォーマンスを表示する![&#x200B; アカウントジャーニーの概要タブ。](./assets/journey-detail-overview-account.png){width="700" zoomable="yes"}

## ジャーニー完了

このセクションでは、次の2つの完了指標を示します。

* **[!UICONTROL ジャーニー内のアカウントのステータス]**：合計アカウント数と、_完了_、_進行中_、_中止_&#x200B;など、ジャーニーステータス別の内訳を表示します。 各セグメントには、ステータス、割合、アカウント数が表示されます。
* **[!UICONTROL 完了したアカウント数]**：ジャーニーを完了したアカウント数を時系列で表示します。 横軸は日付を表示し、縦軸は口座数を表示します。

>[!NOTE]
>
>アカウントジャーニーでは、ジャーニー&#x200B;**グラフの** アカウントのステータスには、ジャーニーを通過したアカウントが、後に削除されたアカウントも含まれます。 **[!UICONTROL ドリルスルー]**&#x200B;では、削除されたアカウントが除外されるため、グラフよりも表示されるレコードの数が少なくなります。 この違いは予想されます。 アカウントを削除しても、過去のジャーニーのステータス数は変更されません。

## ジャーニーのエンゲージメント

このセクションでは、2つのエンゲージメント指標を紹介します。

* **[!UICONTROL アカウント別エンゲージメント]** – この円グラフは、ジャーニー内のアカウントを&#x200B;_エンゲージ_&#x200B;と&#x200B;_エンゲージしていない_ カテゴリーにセグメント化します。 中央の図は合計数を示しています。 このビジュアライゼーションは、アカウント全体のエンゲージメントをすばやく把握するのに役立ちます。
* **[!UICONTROL 人物によるエンゲージメント]**: ジャーニー内でエンゲージメントアクティビティを持つ人物の数を表示します。 この値は、エンゲージメント活動ではなく、人をカウントします。

## ジャーニーパフォーマンス

このセクションでは、次の2つの重要な指標を紹介します。

* **[!UICONTROL ジャーニー完了率]** - ジャーニーを正常に完了したアカウントの割合。
* **[!UICONTROL 平均ジャーニー完了時間]**: アカウントがジャーニーを完了するのにかかる平均時間（日数）です。

## チャネルパフォーマンス {#email-and-sms-performance}

ダッシュボードには、選択したアカウントジャーニーの&#x200B;**[!UICONTROL メールパフォーマンス]**、**[!UICONTROL SMS パフォーマンス]**、および&#x200B;**[!UICONTROL WhatsApp パフォーマンス]**&#x200B;のテーブルが含まれています。 利用可能な配信とエンゲージメントの指標を使用して、各コミュニケーション接点を評価します。

**[!UICONTROL 電子メールパフォーマンス]**&#x200B;のテーブル列：

* _[!UICONTROL アセット名]_ - アセットの名前
* _[!UICONTROL 送信済み]_ – 送信されたメール数
* _[!UICONTROL 配信率]_ – 配信されたメールの数を送信数で割った数
* _[!UICONTROL 開封率]_ – 開封された電子メールの数を配信数で割った数
* _[!UICONTROL クリック率]_ - クリックされた電子メールの数を配信数で割った数

**[!UICONTROL SMS パフォーマンス]**&#x200B;のテーブル列：

* _[!UICONTROL アセット名]_ - アセットの名前
* _[!UICONTROL 送信済み]_ - SMS メッセージの送信数
* _[!UICONTROL 配信率]_ – 配信されたSMS メッセージの数を送信数で割った数
* _[!UICONTROL クリック率]_ - クリックされたSMS メッセージの数を配信数で割った数
<!--
To generate a shareable PDF of your current view, click **[!UICONTROL Export]** at the top right of the page. 
-->

## その他のアクション

グラフまたはテーブルの&#x200B;**...** メニューを使用して、使用可能なアクションにアクセスします。

### ドリルスルー

ジャーニー&#x200B;**グラフの** アカウントのステータスについて、個々のアカウントのステータスを詳細に分析するには、**[!UICONTROL ドリルスルー]**&#x200B;を選択します。

![&#x200B; グラフデータのドリルスルー](./assets/journey-status-drill-through.png){width="600" zoomable="yes"}
<!--
The applied global filters are carried over to the view and displayed at the top. Click the _Filter_ icon at the top left to filter the data display by journey.
-->

### さらに表示

拡張データにアクセスするには、**[!UICONTROL 詳細を表示]**&#x200B;を選択します。 表示されるポップアップには、データの内訳が表示されます。

![拡張データを表示](./assets/journey-completion-over-time-view-more.png){width="600" zoomable="yes"}

データをダウンロードするには、**[!UICONTROL CSVをダウンロード]**&#x200B;を選択します。 _[!UICONTROL 概要]_ ダッシュボードに戻るには、**[!UICONTROL 閉じる]**&#x200B;を選択します。

>[!TAB  ユーザージャーニー]

人物ジャーニーダッシュボードには、選択したジャーニーの人物の完了率、エンゲージメント、メールパフォーマンスが表示されます。

進捗状況、エンゲージメント、メールのパフォーマンスを表示する![人物ジャーニーの概要タブ。](./assets/journey-detail-overview-person.png){width="700" zoomable="yes"}

## ジャーニー完了 {#person-journey-completion}

次のグラフを使用して、ジャーニーと完了傾向における人物のステータスを確認します。

* **[!UICONTROL ジャーニー内の人物のステータス]**：合計人数とジャーニーステータス別の内訳を表示します。 各セグメントには、ステータス、パーセンテージ、人数が表示されます。
* **[!UICONTROL 時間の経過に伴って完了したユーザー数]**：時間の経過に伴ってジャーニーを完了したユーザー数を表示します。 **[!UICONTROL 増分完了]**&#x200B;系列には、各時間間隔の完了が表示されます。 **[!UICONTROL 累積完了数]**&#x200B;系列は、完了数の合計を表示します。

>[!NOTE]
>
>対面ジャーニーでは、ジャーニー内の&#x200B;**[!UICONTROL 人物のステータス]**&#x200B;のグラフには、後に削除された場合でも、ジャーニーを通過した人物が含まれます。 **[!UICONTROL ドリルスルー]**&#x200B;は、削除されたユーザーを除外するので、グラフよりも表示されるレコード数が少なくなります。 この違いは予想されます。 ユーザーを削除しても、過去のジャーニーのステータス数は変更されません。

ジャーニー グラフの人物の&#x200B;_ ステータスの場合は、_&#x200B;詳細_ （**...**）アイコンをクリックし、**[!UICONTROL ドリルスルー]**&#x200B;を選択して個々の人物のステータスを確認します。

## ジャーニーのエンゲージメント {#person-journey-engagement}

**[!UICONTROL 人物によるエンゲージメント]** ウィジェットには、ジャーニー内でエンゲージメントアクティビティを持つ人物の数が表示されます。 この値は、エンゲージメント活動ではなく、人をカウントします。

## ジャーニーパフォーマンス {#person-journey-performance}

完了パフォーマンスを確認するには、次の指標を使用します。

* **[!UICONTROL ジャーニー完了率]**: ジャーニーを完了したユーザーの割合。
* **[!UICONTROL 平均ジャーニー完了時間]**：ユーザーがジャーニーを完了するのにかかった平均時間（日数）です。

## メールパフォーマンス {#person-journey-email-performance}

**[!UICONTROL 電子メールパフォーマンス]** テーブルには、選択した人物ジャーニーの各メールアセットのカウントが、レートではなく次のように表示されます。

* **[!UICONTROL アセット名]**：電子メールアセットの名前
* **[!UICONTROL 送信済み]**：送信されたメールの数
* **[!UICONTROL 配信済み]**：配信済みメールの数
* **[!UICONTROL 開封済み]**：開封済みメールの数
* **[!UICONTROL クリック数]**: クリックされた電子メール数

>[!ENDTABS]
