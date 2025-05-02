---
title: Adobe Journey Optimizer B2B Edition の概要
description: Adobe Journey Optimizer B2B エディションの主な機能、ユースケース、アーキテクチャについて説明します。
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
source-git-commit: 5ca03b12fd459c64b245ad95e60a382c355922f9
workflow-type: ht
source-wordcount: '811'
ht-degree: 100%

---

# Adobe Journey Optimizer B2B Edition の概要

Adobe Journey Optimizer B2B Edition を使用すると、組み込みの生成 AI と業界をリードする自動化を使用して、アカウントと購買グループのジャーニーを調整し、マーケティング資格のある購買グループを使用して特定の製品に対する需要を最大化できます。

## 購買グループを含むアカウントジャーニー

Adobe Journey Optimizer B2B Edition を Marketo Engage および Adobe Journey Optimizer Standard と比較すると、アカウントジャーニーでは人物ではなくアカウントがジャーニーを通じて移動するという点が主な違いです。アカウントに関連付けられたユーザーは通常、個人のアクションではなく、ジャーニーを通じたアカウントの進行状況に基づいて非線形に進行します。例えば、アカウントが購入ジャーニーの早期フェーズにある場合、送信される情報は一般的なソリューションの機能に関するものになる可能性があります。購入プロセスがさらに進むにつれて、コンテンツは特定のオファーや、販売の成約に向けたその他の項目をよりターゲットにしたものになる可能性があります。ソリューションの購入後、ハウツーガイド、ベストプラクティス、今後のイベントに関する情報、追加のアップセルに関するコンテンツを提供するために、情報が再度変更される可能性があります。個人が早期フェーズのコンテンツを操作したことがない場合でも、その個人のアクションではなく、アカウントまたは購買グループ内の他の人物のアクションに基づいて、その個人を現在のフェーズに進める必要があります。

## 高レベルのアーキテクチャ

Adobe Journey Optimizer B2B Edition は、Adobe Experience Platform の&#x200B;_アカウントオーディエンス_&#x200B;と&#x200B;_人物オーディエンス_&#x200B;を使用して、Marketo Engage 内で実行されるアカウントジャーニーを強化します。Experience Platform は常にこのデータの信頼できるソースですが、アカウントジャーニーの実行と処理はすべて Marketo Engage B2B マーケティングインフラストラクチャ内で行われます。このオーケストレーションでは、既存の Marketo Engage - Adobe Real-Time CDP B2B Edition ソースコネクタによってデータがほぼリアルタイムで Experience Platform に戻され、Marketo Engage から Experience Platform にデータの変更がストリーミングされます。

![高レベルのデータアーキテクチャ](./assets/high-level-data-architecture.png){width="500" zoomable="yes"}

>[!NOTE]
>
>パフォーマンスガードレールと静的制限について詳しくは、ライセンスの使用権限と対応する[製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}を参照してください。

### サブスクリプションモデル

Journey Optimizer B2B Edition サブスクリプションは、Marketo Engage _Munchkin_ サブスクリプションを備えた Experience Platform（AEP）サンドボックスのペアによって定義されます。1 つの Marketo Engage サブスクリプションを複数の AEP サンドボックスとペアにすることはできません。既存の Marketo Engage サブスクリプションを Journey Optimizer B2B Edition とペアにすることを選択しない場合は、Journey Optimizer B2B Edition で使用するための新しい空の Marketo Engage サブスクリプションがプロビジョニングされます。

この設定での Experience Platform の目的は、Marketo Engage インスタンス（および接続されている CRM システム）からのデータの統合ビューを提供し、アカウントジャーニーを使用して統合データに対してアクションを実行できるようにすることです。

### アカウントジャーニーの操作

アカウントジャーニーは、Journey Optimizer B2B Edition で作成され、サブスクリプションに関連付けられた Marketo Engage インスタンスに保存されます。これは、Marketo Engage データストアに格納されますが、Marketo Engage UI からは表示されず、Journey Optimizer B2B Edition からのみ使用できます。

アカウントジャーニーは常に、ジャーニーのアカウントオーディエンスとして使用するアカウントセグメントの選択から開始します。オーディエンスの選択には、標準の Experience Platform オーディエンスセレクターコンポーネントを使用します。その後、マーケターは、アカウント条件、人物条件、購買グループ条件などの独自の条件に従ってジャーニーのパスを分割し、アカウントジャーニーを実装できます。各分岐では、メールの送信やイベントの発生の待機など、ジャーニーを実装するためのアクションを実行できます。

アカウントジャーニーを作成したら、公開する必要があります。公開時に、アカウントジャーニーが検証され、ジャーニーエクスペリエンスを実装する一連の Marketo Engage キャンペーンに変換されます。データフローを開始し、アカウントジャーニー操作を開始するには、データ統合サービスにお問い合わせください。最初の手順は、アカウントの人物のセグメントを作成することです。

### データフロー

Journey Optimizer B2B Edition では、ジャーニーに必要なアカウントセグメントと関連するアカウントユーザーセグメントの定義と実行の両方に、Real-Time CDP アカウントのセグメント化を使用します。公開したジャーニーが実行されると、人物とアカウントに関するデータが変更される可能性があり、ジャーニーとやり取りする人物に関するデータが収集されます。Journey Optimizer B2B Edition では、Real-Time CDP B2B Edition の Marketo Engage ソースコネクタに依存して、データの変更を信頼できるソースである Experience Platform サンドボックスにフローして戻します。このデータは、ほぼリアルタイムの方法で AEP に配信されます。

Marketo Engage ソースコネクタでサポートされている既存のデータタイプ（アカウント、人物、商談）のみが Real-Time CDP にフローして戻します。つまり、購買グループのデータは AEP にフローされず、代わりに Journey Optimizer B2B Edition サブスクリプションで使用される Marketo Engage インスタンスに存在します。
