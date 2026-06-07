---
title: Adobe Journey Optimizer B2B Edition の概要
description: Adobe Journey Optimizer B2B Edition について - B2B マーケティング向けの購買グループ、AI インサイトおよび Experience Platform 統合を使用してアカウントジャーニーを調整します。
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
autotag-review: 2026-04-29T23:21:13.339Z
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: f467931a-9b22-4ca8-869f-adfbd64061ce
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
TQID: https://experienceleague.adobe.com/L58cK4MP-S-8U9fFiXU2qZn4HCieNzjoOaSRCLkyanI
source-git-commit: ca0c6b10cf6a979249901d514116f373014544ad
workflow-type: tm+mt
source-wordcount: 803
ht-degree: 66%

---

# Adobe Journey Optimizer B2B Edition の概要

Adobe Journey Optimizer B2B Edition を使用すると、ビルトインの生成 AI と業界をリードする自動化を使用して、アカウントと購買グループのジャーニーを調整し、マーケティング資格のある購買グループを使用して特定の製品に対する需要を最大化できます。

## 購買グループを含むアカウントジャーニー

アカウントジャーニーとMarketo EngageおよびAdobe Journey Optimizer standard のジャーニー機能を比較する場合、主な違いは、アカウントジャーニーでは、人物ではなくジャーニー内でアカウントが移動することです。 アカウントに関連付けられたユーザーは通常、個人のアクションではなく、ジャーニーを通じたアカウントの進行状況に基づいて非線形に進行します。 例えば、アカウントが購入ジャーニーの初期段階にいる場合、一般的なソリューションの機能や特徴に関する情報が送信されます。 購入プロセスに沿って、コンテンツは、特定のオファーや販売を成立させるために必要な他のアイテムをよりターゲットにします。 製品を購入すると、情報が再度変更され、ハウツーガイド、ベストプラクティス、今後のイベントに関する情報、追加のアップセルに関するコンテンツが提供されます。 初期段階のコンテンツで顧客とやり取りしたことがない場合でも、アカウントや購買グループ内の他のメンバーの行動にもとづいて、訪問者を現在の段階に進めることができます。

## 高レベルのアーキテクチャ

Adobe Journey Optimizer B2B Edition は、Adobe Experience Platform の&#x200B;_アカウントオーディエンス_&#x200B;と&#x200B;_人物オーディエンス_&#x200B;を使用して、Marketo Engage 内で実行されるアカウントジャーニーを強化します。 Experience Platformは、常にこのデータの主要な情報源ですが、アカウントジャーニーのあらゆる実行と処理は、Marketo Engage B2B マーケティングインフラストラクチャ内で行われます。 このオーケストレーションでは、既存の Marketo Engage - Adobe Real-Time CDP B2B Edition ソースコネクタによってデータがほぼリアルタイムで Experience Platform に戻され、Marketo Engage から Experience Platform にデータの変更がストリーミングされます。

![高レベルのデータアーキテクチャ](./assets/high-level-data-architecture.png){width="500" zoomable="yes"}

>[!NOTE]
>
>パフォーマンスガードレールと静的制限について詳しくは、ライセンスの使用権限と対応する[製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}を参照してください。

### サブスクリプションモデル

Marketo Engage _Munchkin_ サブスクリプションを持つExperience Platform（AEP）サンドボックスのペアで、Journey Optimizer B2B edition サブスクリプションを定義します。 1 つの Marketo Engage サブスクリプションを複数の AEP サンドボックスとペアにすることはできません。 既存の Marketo Engage サブスクリプションを Journey Optimizer B2B Edition とペアにすることを選択しない場合は、Journey Optimizer B2B Edition で使用するための新しい空の Marketo Engage サブスクリプションがプロビジョニングされます。

Experience Platformでは、Marketo Engageのインスタンスと接続されたCRM システムからのデータを包括的に把握し、アカウントジャーニーを通じて活用できます。

### アカウントジャーニーの操作

アカウントジャーニーは、Journey Optimizer B2B Edition で作成され、サブスクリプションに関連付けられた Marketo Engage インスタンスに保存されます。 これらはMarketo Engage データストアに保存されますが、Marketo Engage UIからは表示されず、Journey Optimizer B2B editionでのみ使用できます。

アカウントジャーニーは常に、ジャーニーのアカウントオーディエンスとして使用するアカウントセグメントの選択から開始します。 オーディエンスの選択には、標準の Experience Platform オーディエンスセレクターコンポーネントを使用します。 その後、マーケターは、アカウント条件、人物条件、購買グループ条件などの独自の条件に従ってジャーニーのパスを分割し、アカウントジャーニーを実装できます。 各分岐では、メールの送信やイベントの発生の待機など、ジャーニーを実装するためのアクションを実行できます。

アカウントジャーニーを作成したら、公開する必要があります。 公開時に、アカウントジャーニーが検証され、ジャーニーエクスペリエンスを実装する一連の Marketo Engage キャンペーンに変換されます。 データ統合サービスに連絡してデータフローを開始し、その後アカウントジャーニー操作を開始します。 最初の手順は、アカウントの人物のセグメントを作成することです。

### データフロー

Journey Optimizer B2B Edition では、ジャーニーに必要なアカウントセグメントと関連するアカウントユーザーセグメントの定義と実行の両方に、Real-Time CDP アカウントのセグメント化を使用します。 公開したジャーニーが実行されると、人物とアカウントに関するデータが変更される可能性があり、ジャーニーとやり取りする人物に関するデータが収集されます。 Journey Optimizer B2B editionは、Real-Time CDP B2B edition用のMarketo Engage ソースコネクタを使用して、データの変更をプライマリデータソースであるExperience Platform サンドボックスに戻します。  そうしたデータは、ほぼリアルタイムでAEPに配信されます。

Marketo Engage ソースコネクタでサポートされている既存のデータタイプ（アカウント、人物、商談）のみが Real-Time CDP にフローして戻します。 つまり、購買グループのデータは AEP にフローされず、代わりに Journey Optimizer B2B Edition サブスクリプションで使用される Marketo Engage インスタンスに存在します。
