---
title: 販売通知メール
description: アカウントジャーニーに自動販売警告メールを含める方法を説明します。
feature: Email Authoring, Account Journeys
role: User
exl-id: 01bffbce-6c73-483a-8731-de4e5569cf61
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 6%

---

# 販売アラートメール

_セールスに関するアラート・メール_ は、セールスへの購買グループの引き継ぎを通知します。 このメールには、購入グループの概要と、購入グループのメンバーとそのアクティビティに関する情報が含まれています。

マーケターは、アカウントジャーニーでセールスアラートメールノードを設定し、特定の購入グループのジャーニーの完了についてセールスチームにアラートを送信できます。 ノード内では、営業チームのメールアドレスや、アカウントのセットに到達する配信エイリアスを指定できます。

>[!IMPORTANT]
>
>セールスのアラートメールを配信できるように、組織の許可リストが更新されていることを確認します。 詳しくは、[ トラッキングとメール配信のプロトコル ](../start/email-protocols.md) を参照してください。

## メールコンテンツ

+++販売アラートメールのサンプル
![ デフォルトテンプレートを使用した販売アラートメールの例 ](./assets/sales-alert-email-example.png){width="500" zoomable="yes"}

+++

| セクション | 名前 | 説明 |
| - | ---- | ----------- |
| 購買グループ情報 | 購買グループ名 | 購買グループの表示名です。 |
|   | アカウント名 | アカウントの名前。 |
|   | エンゲージメントスコア | 過去 30 日間のアクティブなエンゲージメントアクティビティに基づいた、購入グループのエンゲージメントスコア。 |
|   | 完全性スコア | 購入グループの完全性スコア。 |
|   | ソリューションに対する関心 | 購入グループにリンクされたソリューションの関心 |
|   | ステータス | 購買グループの状態です。 |
| 購買グループのハイライト | 上位のエンゲージメントメンバー | 購入グループメンバーのエンゲージメントスコアと役割で、購入グループの上位のエンゲージメントメンバーに表示されます。 |
|   | 関心のあるトピック | メール、ダウンロード、チャット、PDF レビュー、アクティビティの概要、ウェビナーの質問に基づいて、コンテンツエンゲージメントで最も頻繁に使用されるキーワード。 |
|   | 役割がありません | テンプレート内の必須の役割ですが、購入グループにありません。 |
| 購買グループの概要 | アクティビティの概要（生成 AI を活用） | メンバーのアクティビティに基づいて、AI が生成した購入グループの概要。 過去 30 日間のアクティビティが考慮されます。 |
|   | 重要な注目すべきアクション | 購入グループのメンバーに関連する最近の興味深い瞬間。 |
| メンバー | 4 人の購入メンバーのリスト | エンゲージメントスコアと役割別の上位 4 つの購入グループメンバーの詳細。 |
| 各購買グループ メンバー | メンバー名 | 購買グループ メンバーの名前です。 |
|   | 職位 | 購買グループ メンバーの役職です。 |
|   | 役割 | メンバーの購買グループ ロール。 |
|   | エンゲージメントスコア | 購入グループメンバーエンゲージメントスコア。 このスコアは、過去 30 日間のアクティブなエンゲージメントアクティビティに基づいています。 |
|   | 最新の注目のアクション | メンバーに関連する最新の最も興味深い瞬間。 |
|   | 最新のアクティビティ | 購入グループメンバーに関連する最新の 2 つのアクティビティ。 |
|   | メール ID | 購買グループ メンバーの電子メール ID。 |
|   | 電話番号 | 購買グループ メンバーの電話番号です。 |

## アカウントジャーニーへの販売アラートメールアクションの追加

「_[!UICONTROL アクションを実行]_」ノードを追加して以下の操作を実行すると、アカウントジャーニーで販売アラートメール配信を設定できます。

1. _[!UICONTROL アクション対象]_ ターゲットとして、「**[!UICONTROL アカウント]**」を選択します。

1. _[!UICONTROL アカウントに対するアクション]_ については、「**[!UICONTROL セールスアラートの送信]**」を選択します。

1. **[!UICONTROL ソリューションの関心を選択]** については、生成されたメールコンテンツに使用するソリューションの関心を選択します。

1. **[!UICONTROL メールの送信先]** については、配信に含める各メールアドレスまたはエイリアスを入力します。

   ![ 新しいメールを作成ダイアログ ](assets/sales-alert-email-journey-node.png){width="600" zoomable="yes"}

   アカウントジャーニーが公開されると、これらのパラメーターに従って販売アラートが配信されます。
