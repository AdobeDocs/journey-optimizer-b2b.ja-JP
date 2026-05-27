---
title: スパムレポートを確認
description: SpamAssassin スコアリングを利用してスパムレポートを生成することで、電子メールがスパムフィルターをトリガーしているかどうかを確認し、Journey Optimizer B2B editionの配信品質を向上できます。
feature: Email Authoring
level: Beginner
role: User
exl-id: 0ab2a85c-fbab-4681-9964-74b7fd1d574f
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: c8f3fb27-3167-48ac-a66a-fa4bc3f58ddaid: f01b5556-e951-40ba-8625-2e3001864f2b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: beb7a3c1-66ab-4786-b879-7621375b3c40
autotag-review: 2026-03-30T22:30:57.478Z
TQID: https://experienceleague.adobe.com/SX8ewAjGolTNim8LeVKhLXne6EntrSMs8aMETVahYaQ
source-git-commit: 8226114f1a34adf85437579ef17a50b80ccfa596
workflow-type: tm+mt
source-wordcount: 378
ht-degree: 2%

---

# スパムレポートの検証

多くの電子メール受信箱プロバイダーと、多くの企業のシステムは、スパムフィルタリングのプロセスを採用しています。 これらのフィルターをトリガーした電子メールを送信すると、配信品質に大きな影響を与える可能性があります。 Journey Optimizer B2B editionでは、迷惑メールレポートを作成して、メールコンテンツの迷惑メールのスコアを確認できます。 このレポートでは、[[!DNL SpamAssassin]](https://spamassassin.apache.org/)を使用して電子メールをテストし、迷惑メール対策ツールでメッセージを迷惑メールと見なすかどうかを判断するのに役立ちます。 レポートの情報を使用して、メールコンテンツのスコアと配信品質を向上させるアクションを実行できます。 コンテンツを調整した後、[電子メールパフォーマンスレポート ](../dashboards/email-performance-dashboard.md)で直帰率と配信を追跡します。

メール設定を確認するか、内容を編集する際に、_[!UICONTROL Simulate]_ ページを開き、_スパムレポート_&#x200B;を生成して、スパム対策フィルタリングをトリガーできるスコアリングとフラグ付き要素を確認します。

1. _[!UICONTROL Simulate]_ ページで、右上の&#x200B;**[!UICONTROL スパムレポート]**&#x200B;をクリックします。

   ![ スパムレポートボタン ](./assets/email-spam-report-button.png){width="700" zoomable="yes"}

   レポートプロセスでは、メールコンテンツをスキャンし、スコアの生成に使用されたトリガーフィルタリングルールのリストを含むスコアを生成します。 要因には、ボディレイアウト、構造、画像サイズ、迷惑メールトリガーの単語などの要素が含まれます。 メール要素のルール評価テストのリストについては、[[!DNL SpamAssassin]  テストリスト ](https://spamassassin.apache.org/old/tests_3_0_x.html)を参照してください。

1. 各項目のスコアと説明を確認します。

   >[!NOTE]
   >
   >スパムスコアはSpamAssassinを通じて計算されるため、Adobeはルールやスコアリングロジックを所有していません。 [!DNL SpamAssassin] オープンソースプロジェクトについて詳しくは、[[!DNL SpamAssassin]  ドキュメント ](https://cwiki.apache.org/confluence/display/SPAMASSASSIN/)を参照してください。

   スコアが低いほど、その電子メールがスパムとしてマークされる可能性は低くなります。

   ![ スパムレポートの肯定的なスコア ](./assets/email-spam-report-positive.png){width="600" zoomable="yes"}

   スコアが5を超えると、レポートには、一部のメッセージがブロックされたり、受信したときに迷惑メールとしてマークされたりする可能性があるという警告が含まれます。 スコアが2未満であることを確認することをお勧めします。

   ![ スパムレポートのネイティブスコア ](./assets/email-spam-report-negative.png){width="600" zoomable="yes"}

1. メールコンテンツ内に改善すべき要素がある場合は、コンテンツを編集して、必要な更新を適用します。

1. 変更が完了したら、_[!UICONTROL シミュレート]_ ページに戻り、**[!UICONTROL スパムレポート]**&#x200B;をもう一度クリックして、結果として生じるスコアの改善を確認します。
