---
title: Adobe Systems ジャーニーオプティマイザー B2B エディション 概要
description: Adobe Journey Optimizer B2B エディションの主な機能、ユースケース、アーキテクチャについて説明します。
exl-id: fdfbafdf-826f-44e9-bbb6-5e729d0e18ef
source-git-commit: 5ca03b12fd459c64b245ad95e60a382c355922f9
workflow-type: tm+mt
source-wordcount: '811'
ht-degree: 5%

---

# Adobe Systems Journey Optimizer B2B Edition の概要

Adobe Journey Optimizer B2B エディションを使用すると、組み込みの生成 AI と業界最先端の自動化機能を使用して、アカウントと購買グループのジャーニーを調整し、マーケティング資格のある購買グループを使用して特定のサービスに対する需要を最大限に高めることができます。

## 購入グループを含むアカウントジャーニー

Adobe Journey Optimizer B2B editionをMarketo EngageとAdobe Journey Optimizer standard と比較する際の主な違いは、アカウントジャーニーでは、人物ではなくジャーニーを介してアカウントを移動することです。 通常、アカウントに関連付けられているユーザーの進行は、個人のアクションではなく、ジャーニー全体でのアカウントの進行状況に基づいて直線的ではありません。 例えば、アカウントが購入ジャーニーの初期段階にある場合、送信される情報は一般的なソリューションの機能に関するものかもしれません。 さらに購入プロセスが進むと、コンテンツは、販売の成立に向けた特定のオファーやその他のアイテムに対してよりターゲットを絞ったものになる可能性があります。 ソリューションの購入後、情報が再び変更され、ハウツーガイド、ベストプラクティス、今後のイベントに関する情報、追加のアップセルに関するコンテンツが提供される場合があります。 個人が早期フェーズのコンテンツを操作していない場合でも、個人の行動ではなく、アカウントまたは購買グループ内の他の個人の行動に基づいて、個人を現行フェーズに進めます。

## アーキテクチャの概要

Adobe Journey Optimizer B2B editionは、Adobe Experience Platformの _アカウントオーディエンス_ と _人物オーディエンス_ を使用して、Marketo Engage内で実行されるアカウントジャーニーを強化します。 Experience Platformは常にこのデータの信頼できる情報源ですが、アカウントジャーニーのすべての実行と処理は、Marketo Engage B2Bマーケティングインフラストラクチャ内で行われます。 オーケストレーションは、Marketo EngageからExperience Platformにデータの変更をストリーミングする既存のMarketo Engage - Adobe Real-Time CDP B2B edition ソースコネクタによって、ほぼリアルタイムでExperience Platformにデータを戻します。

![やや高画質レベルのデータアーキテクチャ](./assets/high-level-data-architecture.png){width="500" zoomable="yes"}

>[!NOTE]
>
>パフォーマンス ガードレールと静的制限に関するライセンス版資格と対応する [製品の説明](https://helpx.adobe.com/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"} を確認します。

### サブスクリプションモデル

Journey Optimizer B2B edition サブスクリプションは、Marketo Engage _Munchkin_ サブスクリプションを使用するExperience Platform（AEP）サンドボックスのペアによって定義されます。 1 つのMarketo Engage サブスクリプションを複数のAEP サンドボックスとペアにすることはできません。 既存のMarketo Engage サブスクリプションをJourney Optimizer B2B editionとペアにすることを選択しない場合は、Journey Optimizer B2B editionで使用する新しい空のMarketo Engage サブスクリプションがプロビジョニングされます。

この設定でのExperience Platformの目的は、Marketo Engage インスタンス（および接続された CRM システム）からのデータに統合ビューを提供し、アカウントジャーニーを使用して統合データに対してアクションを実行できるようにすることです。

### アカウントジャーニーの操作

アカウントジャーニーは、Journey Optimizer B2B editionで作成され、サブスクリプションに関連付けられたMarketo Engage インスタンスに保存されます。 Marketo Engage データストアに格納されていますが、Marketo Engage UI からは表示されず、Journey Optimizer B2B editionからのみ使用できます。

アカウントジャーニーは常に、ジャーニーのアカウントオーディエンスとして使用するアカウントセグメントの選択で開始します。 オーディエンスの選択には、標準のExperience Platform オーディエンスセレクターコンポーネントが使用されます。 マーケターは、アカウント条件、人の条件、または購入グループ条件を含む独自の条件に従ってジャーニーのパスを分割することにより、アカウントジャーニー実装するできます。 各分岐で、電子メールの送信やイベントの発生の待機など、ジャーニー実装するアクションを実行できます。

アカウントジャーニーを作成したら、公開する必要があります。 公開する時に、アカウントジャーニーが検証され、ジャーニーエクスペリエンス実装する一連のMarketo Engageキャンペーンに変換されます。 データ統合サービスに接続して、アカウントジャーニー操作を開始するデータフロー開始ます。 最初のステップでは、取引先の People 用のセグメントを作成します。

### データフロー

Journey Optimizer B2B editionでは、アカウントセグメントおよびジャーニーで必要な関連するアカウント人物セグメントを定義および実行する際に、Real-Time CDP アカウントのセグメント化を使用します。 公開されたジャーニーが実行されると、人物とアカウントに関するデータが変更される可能性があり、ジャーニーとやり取りする人物に関するデータが収集されます。 Journey Optimizer B2B editionは、Real-Time CDP B2B editionのMarketo Engage ソースコネクタを使用して、データの変更をExperience Platform サンドボックスに返します。これは、信頼できる唯一のソースです。  このデータは、ほぼリアルタイムでAEPに配信されます。

Marketo Engage ソースコネクタでサポートされている既存のデータタイプ（アカウント、人物、オポチュニティ）のみがReal-Time CDPに戻されます。 つまり、購入グループデータはAEPに送られず、代わりに、Journey Optimizer B2B edition サブスクリプションで使用されるMarketo Engage インスタンスに存在します。
