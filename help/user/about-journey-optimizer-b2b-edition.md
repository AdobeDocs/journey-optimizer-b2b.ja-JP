---
title: Adobe Journey Optimizer B2B editionの概要
description: Adobe Journey Optimizer B2B エディションの主な機能、ユースケース、アーキテクチャについて説明します。
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
source-git-commit: d1696eb54c9ff25963b51a0e3934a02e103923e4
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 5%

---

# Adobe Journey Optimizer B2B editionの概要

Adobe Journey Optimizer B2B エディションを使用すると、組み込みの生成 AI と業界最先端の自動化機能を使用して、アカウントと購買グループのジャーニーを調整し、マーケティング資格のある購買グループを使用して特定のサービスに対する需要を最大限に高めることができます。

## 購入グループを含むアカウントジャーニー

Adobe Journey Optimizer B2B editionをMarketo EngageおよびAdobe Journey Optimizer standard と比較する際の主な違いは、アカウントジャーニーでは、人物ではなくジャーニーを介してアカウントを移動することです。 通常、アカウントに関連付けられているユーザーの進行は、個人のアクションではなく、ジャーニー全体でのアカウントの進行状況に基づいて直線的ではありません。 例えば、アカウントが購入ジャーニーの初期段階にある場合、送信される情報は一般的なソリューションの機能に関するものかもしれません。 さらに購入プロセスが進むと、コンテンツは、販売の成立に向けた特定のオファーやその他のアイテムに対してよりターゲットを絞ったものになる可能性があります。 ソリューションの購入後、情報が再び変更され、ハウツーガイド、ベストプラクティス、今後のイベントに関する情報、追加のアップセルに関するコンテンツが提供される場合があります。 個人が早期フェーズのコンテンツを操作していない場合でも、個人の行動ではなく、アカウントまたは購買グループ内の他の個人の行動に基づいて、個人を現行フェーズに進めます。

## アーキテクチャの概要

Adobe Journey Optimizer B2B editionは、Adobe Experience Platformの _アカウントオーディエンス_ と _人物オーディエンス_ を使用して、Marketo Engage内で実行されるアカウントジャーニーを強化します。 Experience Platformは、常にこのデータの信頼できる情報源ですが、アカウントジャーニーのすべての実行と処理は、Marketo EngageB2B マーケティングインフラストラクチャ内で行われます。 オーケストレーションは、Marketo EngageからExperience Platformへとデータの変化をストリーミングする既存のMarketo EngageであるAdobe Real-Time CDP B2B edition ソースコネクタによって、ほぼリアルタイムでデータをExperience Platformに戻します。

![ データアーキテクチャの概要 ](./assets/high-level-data-architecture.png){width="500" zoomable="yes"}

>[!NOTE]
>
>ライセンスの使用権限と、パフォーマンスガードレールと静的な制限に関する対応する [ 製品説明 ](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} を確認します。

### 購読モデル

Journey Optimizer B2B edition サブスクリプションは、Marketo Engageの _Munchkin_ サブスクリプションを持つExperience Platform（AEP）サンドボックスのペアによって定義されます。 1 つのMarketo Engageサブスクリプションを複数の AEP サンドボックスとペアにすることはできません。 既存のMarketo EngageサブスクリプションをJourney Optimizer B2B editionとペアリングしない場合は、Journey Optimizer B2B editionで使用する新しい空のMarketo Engageサブスクリプションがプロビジョニングされます。

この設定でのExperience Platformの目的は、Marketo Engageインスタンス（および接続された CRM システム）からのデータを統合ビューで参照し、アカウントジャーニーを使用して統合データに対してアクションを実行できるようにすることです。

### アカウントジャーニーの操作

アカウントジャーニーは、Journey Optimizer B2B editionで作成され、サブスクリプションに関連付けられたMarketo Engageインスタンスに保存されます。 Marketo Engageデータストアに格納されていますが、Marketo EngageUI からは表示されず、Journey Optimizer B2B editionからのみ使用できます。

アカウントジャーニーは常に、ジャーニーのアカウントオーディエンスとして使用するアカウントセグメントの選択で開始します。 オーディエンスの選択には、標準のExperience Platformオーディエンスセレクターコンポーネントが使用されます。 その後、マーケターは独自の条件（アカウント条件、人物条件、購入グループ条件など）に従ってジャーニーのパスを分割し、アカウントジャーニーを実装できます。 各分岐で、メールの送信やイベントの発生の待機など、ジャーニーを実装するためのアクションを実行できます。

アカウントジャーニーを作成したら、そのジャーニーを公開する必要があります。 アカウントジャーニーは、公開時に検証され、ジャーニーエクスペリエンスを実装した一連のMarketo Engageキャンペーンに変換されます。 Data Integration Services に連絡して、データフローを開始し、今度はアカウントジャーニー操作を開始します。 最初の手順は、アカウントのユーザー用のセグメントを作成することです。

### データフロー

Journey Optimizer B2B editionでは、アカウントセグメントおよびジャーニーで必要な関連するアカウント人物セグメントを定義および実行する際に、Real-Time CDP アカウントのセグメント化を使用します。 公開されたジャーニーが実行されると、人物とアカウントに関するデータが変更される可能性があり、ジャーニーとやり取りする人物に関するデータが収集されます。 Journey Optimizer B2B editionは、Real-Time CDP B2B editionのMarketo Engageソースコネクタを使用して、データの変更内容をExperience Platformのサンドボックス（信頼できる唯一の情報源）に返します。  このデータは、ほぼリアルタイムで AEP に配信されます。

Marketo Engageソースコネクタでサポートされている既存のデータタイプ（アカウント、人物、オポチュニティ）のみがReal-Time CDPに戻されます。 つまり、購入グループデータは AEP に送られず、代わりにJourney Optimizer B2B edition サブスクリプションで使用されるMarketo Engageインスタンスに存在します。
