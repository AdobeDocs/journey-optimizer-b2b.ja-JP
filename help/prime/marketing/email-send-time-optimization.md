---
title: メール送信時間の最適化
description: Adobe Journey Optimizer B2B Primeの送信時間最適化（STO）により、個人のジャーニーに合わせてメール配信をパーソナライズ。 STOを有効にしてエンゲージメントを向上させる方法について説明します。
autotag-review: '2026-06-17T20:52:02.535Z'
TQID: 'https://experienceleague.adobe.com/wlxhS7E8DnbThm5ge-wzTkMcn-eBzFUXfw3ZGrfcRHA'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: bef5003b-cad2-4f40-bdb2-a80426d52ef5id: f01b5556-e951-40ba-8625-2e3001864f2bid: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1fid: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
source-git-commit: 951d9ceaa95656952e36b6d8f238348b08c796ca
workflow-type: tm+mt
source-wordcount: 403
ht-degree: 0%

---

# メール送信時間の最適化

送信時間の最適化（STO）機能を使用して、各プロファイルがエンゲージする可能性が最も高いタイミングを予測し、[人のジャーニー](./person-journeys.md)のメール配信タイミングをパーソナライズします。 STOは、送信時間を固定するのではなく、過去のメールエンゲージメントシグナルを利用して、各受信者に最適な時間に配信をスケジュールし、エンゲージメント全体を向上させます。

STOは、大規模な言語モデルを使用して、各プロファイルの過去のエンゲージメントを分析します。 潜在的な送信時間を予測およびランク付けし、最適化ウィンドウ内で最も高いランク付けされた時間に配信をスケジュールします。

<!-- Performance insights, such as usage, engagement lift, and STO vs. non-STO comparisons, are available through natural language queries in the AI Assistant. -->

>[!BEGINSHADEBOX]

STOに対して計画されている&#x200B;**_今後の機能強化_**&#x200B;は多数あります。

* _[!UICONTROL 管理者]_&#x200B;領域のグローバル STO設定
* ジャーニーレベルのSTO有効化
* 設定可能なテスト/コントロール分割

>[!ENDSHADEBOX]

## 設定 {#configuration}

[ ユーザーのジャーニーに&#x200B;_[!UICONTROL アクション]_ ノード ](./action-nodes.md)を追加し、**[!UICONTROL 電子メールを送信]** アクションを選択すると、送信時間の最適化を設定できます。

1. 「_メールを送信_ ジャーニーアクションノード」を選択します。

1. 右側のノードプロパティで、**[!UICONTROL 送信時間の最適化]** オプションを有効にします。

   ![ メールジャーニーノードの送信 – 送信時間の最適化オプション ](./assets/email-node-send-time-optimization.png){width="450" zoomable="no"}

1. ウィンドウとテスト配布を指定するには、STO オプションを設定します。

   * **[!UICONTROL 次の]**&#x200B;以内に送信 – この値により、最適化ウィンドウ（日数）が決定されます。これは、メールを配信できる時間範囲です。 例えば、5日間で開催されるウェビナーの場合、4日間または5日間の期間を設定できます。 STOは、このウィンドウ内の各プロファイルに最適な予測送信時間を選択します。

   * **STO / 固定ディストリビューション** - STOは、_テストとコントロールの分割_&#x200B;を自動的に作成し、対象プロファイルを最適化された送信時間と固定された送信時間で分割します。 分割により、パフォーマンスを直接比較できます。 （カスタムの分割率を許可するように、今後の機能強化が計画されています）。

   >[!NOTE]
   >
   >強力なエンゲージメント履歴を持つプロファイルは、STOの影響を測定するために、コントロールグループとテストグループに均等に分割されます。 統計的に信頼性の高い結果を得るために、STOと非STOの分割は30%から70%の間で制限されています。 これにより、より小さなコホートで結果が歪むことを防ぎ、有意義な比較を実現できます。

1. _[!UICONTROL メールを送信]_ ノードの直後に、[様が&#x200B;_待機_ ノード ](./wait-nodes.md)を追加します。

   待機ノードは、STO対応のメールアクションに直ちに従う必要があります。 このノードを追加すると、最適化ウィンドウ全体がクリアされ、すべてのSTO送信が完了するまで、プロファイルがジャーニーに残ります。 このノードを省略すると、システムは設定を無効としてフラグ付けします。

1. ユーザージャーニーの残りの部分を完了したら、[公開](./person-journeys.md#publish)に進みます。

## レポート


