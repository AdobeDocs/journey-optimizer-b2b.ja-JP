---
title: Adobe Journey Optimizer B2B Edition の概要
description: Adobe Journey Optimizer B2B Edition の主な機能、ユースケース、アーキテクチャについて説明します。
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
source-git-commit: 78d82aa8b3bb8b8d432eeb187d75e2354dbff3ee
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 0%

---

# Adobe Journey Optimizer B2B Edition の概要

Adobe Journey Optimizer B2B Edition を使用すると、組み込みのジェネレーティブ AI と業界をリードする自動化機能を使用してアカウントジャーニーと購入グループジャーニーを調整し、マーケティング資格のある購入グループを使用して、特定のオファーに対する需要を最大限に高めることができます。

## 購入グループを含むアカウントジャーニー

Adobe Journey Optimizer B2B Edition とMarketo EngageおよびAdobe Journey Optimizer Standard を比較する際の主な違いは、アカウントジャーニーでは、人物ではなくジャーニーを通じてアカウントを移動することです。 アカウントに関連付けられている人物は、個々のアクションではなく、ジャーニー全体を通したアカウントの進行状況に基づいて非線形の進行を示す可能性が高くなります。 例えば、アカウントが購入ジャーニーの初期段階にある場合、送信される情報は一般的なソリューションの機能に関するものかもしれません。 さらに購入プロセスが進むと、コンテンツは、販売の成立に向けた特定のオファーやその他のアイテムに対してよりターゲットを絞ったものになる可能性があります。 ソリューションの購入後、情報が再び変更され、ハウツーガイド、ベストプラクティス、今後のイベントに関する情報、追加のアップセルに関するコンテンツが提供される場合があります。 個人が早期フェーズのコンテンツを操作していない場合でも、個人の行動ではなく、アカウントまたは購買グループ内の他の個人の行動に基づいて、個人を現行フェーズに進めます。

## アーキテクチャの概要

Adobe Journey Optimizer B2B Edition は、Adobe Experience Platformの _アカウントオーディエンス_ とアカウントの _People オーディエンス_ を使用して、Marketo Engage内で実行されるアカウントジャーニーを強化します。 Experience Platformは、常にこのデータの信頼できる情報源ですが、アカウントジャーニーのすべての実行と処理は、Marketo EngageB2B マーケティングインフラストラクチャ内で行われます。 オーケストレーションは、既存のMarketo EngageであるAdobe Real-Time CDP B2B Edition ソースコネクタによって、ほぼリアルタイムでデータをExperience Platformに戻します。このコネクタは、Marketo EngageからExperience Platformへとデータの変化をストリーミングします。

![ データアーキテクチャの概要 ](./assets/high-level-data-architecture.png){width="500" zoomable="yes"}

### 購読モデル

Journey Optimizer B2B Edition サブスクリプションは、Marketo Engageの _munchkin_ サブスクリプションを持つExperience Platform（AEP）サンドボックスのペアによって定義されます。 1 つのMarketo Engageサブスクリプションを複数の AEP サンドボックスとペアにすることはできません。 Journey Optimizer B2B Edition で既存のMarketo Engageサブスクリプションを使用しない場合、または現在Marketo Engageを使用していない場合は、Journey Optimizer B2B Edition で使用する新しい空のMarketo Engageサブスクリプションがプロビジョニングされます。

この設定でのExperience Platformの目的は、Marketo Engageインスタンス（および接続された CRM システム）からのデータを統合ビューで参照し、アカウントジャーニーを使用して統合データに対してアクションを実行できるようにすることです。

### アカウントジャーニーの操作

アカウントジャーニーは、Journey Optimizer B2B Edition で作成され、サブスクリプションに関連付けられたMarketo Engageインスタンスに保存されます。 Marketo Engageデータストアに保存されていますが、Marketo EngageUI からは表示されず、Journey Optimizer B2B Edition からのみ使用できます。

アカウントジャーニーは常に、ジャーニーのアカウントオーディエンスとして使用するアカウントセグメントの選択で開始します。 オーディエンスの選択には、標準のExperience Platformオーディエンスセレクターコンポーネントが使用されます。 その後、マーケターは独自の条件（アカウント条件、人物条件、購入グループ条件など）に従ってジャーニーのパスを分割し、アカウントジャーニーを実装できます。 各分岐で、メールの送信やイベントの発生の待機など、ジャーニーを実装するためのアクションを実行できます。

アカウントジャーニーを作成したら、そのジャーニーを公開する必要があります。 公開時に、アカウントジャーニーが検証され、ジャーニーエクスペリエンスを実装する一連のMarketo Engageキャンペーンに変換されます。また、Data Integration Services に連絡してデータフローが開始され、そのデータフローが今度はアカウントジャーニーの操作を開始します。 最初の手順は、アカウントのユーザー用のセグメントを作成することです。

### データフロー

Journey Optimizer B2B Edition では、アカウントセグメントとジャーニーに必要な関連するアカウント人物セグメントを定義および実行する際に、Real-Time CDP アカウントのセグメント化を使用します。 公開されたジャーニーが実行されると、人物とアカウントに関するデータが変更される可能性があり、ジャーニーとやり取りする人物に関するデータが収集されます。 Journey Optimizer B2B Edition は、Real-Time CDP B2B Edition のMarketo Engageソースコネクタを使用して、データの変更を真のソースであるExperience Platformサンドボックスに返します。  このデータは、ほぼリアルタイムで AEP に配信されます。

Marketo Engageソースコネクタでサポートされている既存のデータタイプ（アカウント、人物、オポチュニティ）のみがReal-Time CDPに戻されます。 つまり、購入グループデータは AEP に送られず、代わりにJourney Optimizer B2B Edition サブスクリプションで使用されるMarketo Engageインスタンスに存在します。
