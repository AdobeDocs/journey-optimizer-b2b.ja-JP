---
title: 購買グループの詳細
description: Journey Optimizer B2B editionが提供するAI インサイトを使用して購買グループの詳細を確認、メンバーの役割を管理、エンゲージメントスコアを追跡、インテントデータを分析します。
feature: Buying Groups, Intelligent Insights
role: User
exl-id: f14301dc-d605-4ed2-8867-6a49675019de
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: afadf741-c5fe-42cd-8013-23bb6ff2d1bcid: f979fe0e-02fe-4599-b492-7b3df1d4e7dc
subfeature_v2: id: dd41174d-42f1-4265-98b1-dfe80da860ce
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
autotag-review: '2026-03-30T21:46:01.279Z'
source-git-commit: ff337a5f215daee1ea6dbe8d6b643087ac3324e2
workflow-type: tm+mt
source-wordcount: 788
ht-degree: 5%

---

# 購買グループの詳細

Journey Optimizer B2B editionの任意の場所から購買グループ名をクリックすると、購買グループの詳細が表示されます。 この概要では、生成AIの概要など、購買グループに関する有用な情報を提供します。 アカウントに関連付けられた連絡先に対して実行できる[ アクション ](#buying-group-actions)もあります。

![購買グループの詳細にアクセス ](./assets/buying-group-details.png){width="800" zoomable="yes"}

アカウントに関する情報を確認するには「**[!UICONTROL 概要]**」タブを使用し、購買グループのメンバーのリストにアクセスするには「**[!UICONTROL メンバー]**」タブを使用します。

## 「概要」タブ

「概要」タブは、次の3つの主要セクションで構成されています。

### 購買グループの要約

![購買グループの概要](./assets/details-page-buying-group-overview.png){zoomable="yes"}

「購買グループの概要」セクションには、次の購買グループ情報が含まれます。

* 購買グループ名
* アカウント名（名前をクリックして[ アカウントの詳細](../accounts/account-details.md)を開きます）
* 購買グループのメンバー数
* エンゲージメントスコア
* 完全性スコア
* 現在の購買グループステージ
* 役割テンプレート （名前をクリックして[役割テンプレート ](buying-groups-role-templates.md#access-and-browse-role-templates)を開きます）
* 最終更新日/更新日
* 購買グループの生成AI概要

### アカウントの概要

![購買グループアカウントの概要](./assets/details-page-buying-group-account-overview.png){zoomable="yes"}

アカウントの概要セクションには、次のアカウント情報が含まれます。

* アカウント名（名前をクリックしてアカウントの詳細を開きます）
* アカウント内の人数
* 業界
* オープンな機会
* アカウントが現在使用されている最新の3つのアカウントジャーニー（名前をクリックしてジャーニーの詳細を開く）
* アカウントの生成AI概要

### インテントデータ

Journey Optimizer B2B editionでは、インテント検出モデルにより、購買グループメンバーのアクティビティにもとづいて、十分な信頼性で関心のあるソリューションや製品を予測できます。 購買グループのメンバーの意図は、製品に興味を持つ可能性と解釈できます。

{{intent-data-note}}

![ インテントデータ – 購買グループの詳細](../accounts/assets/intent-data-panel.png){width="700" zoomable="yes"}

* 意図のレベル
* インテントシグナルの種類 – キーワード、製品、ソリューション

### 購買グループのメンバー

![購買グループのメンバー](./assets/details-page-buying-group-members.png){width="800" zoomable="yes"}

_[!UICONTROL 購買グループメンバー]_ セクションには、購買グループメンバーを強調表示する2つの行が表示されます。

* **[!UICONTROL 意思決定者]** – 人物のエンゲージメントスコアに基づく上位3人の意思決定者
* **[!UICONTROL 最もエンゲージメントの高いメンバー]** – 人物のエンゲージメントスコアに基づくその他の最もエンゲージメントの高いメンバー

各メンバーカードには、次の詳細が記載されています。

* 名前
* 職位
* 役割
* リードエンゲージメントスコア

「**[!UICONTROL 詳細を表示]**」をクリックして、次のメンバー情報にアクセスします。

* 生成AIによる要約
* 最新の注目のアクション
* 最近の活動（2）
* リードがメンバーであるその他の購買グループ（直近に追加された購買グループに基づいて3つの購買グループに限定）。
* メールアドレス
* 電話番号

![購買グループ メンバーの詳細を表示](./assets/details-page-buying-group-members-view-details.png){width="600" zoomable="yes"}

## 「メンバー」タブ

「**[!UICONTROL メンバー]**」タブを選択して、すべての購買グループメンバーのリストを表示します。 各メンバーリストには、名前、役割、役職、メールアドレス、電話番号、ソースが含まれます。

![ メンバーのタブ – 購買グループの詳細](./assets/buying-group-details-members-tab.png){width="700" zoomable="yes"}

「_メンバー_」タブから実行できるアクションは複数あります。

### 新しいメンバーの割り当て

アカウントには1つ以上の購買グループを関連付けることができます。購買グループメンバーは、通常、アカウントの連絡先のサブセットです。 関連するアカウントの任意の連絡先を購買グループに手動で追加できます。

1. 右上の「**[!UICONTROL 新しいメンバーを割り当て]**」をクリックします。

1. _[!UICONTROL メンバーを割り当て]_ ダイアログで、購買グループに追加するアカウントリードを選択し、**[!UICONTROL 次へ]**&#x200B;をクリックします。

   ![ メンバーのタブ – 新規メンバーの割り当て](./assets/buying-group-details-assign-member.png){width="700" zoomable="yes"}

1. _[!UICONTROL 新しいメンバーの役割を編集]_ ダイアログで、新しいメンバーのそれぞれに割り当てる役割を選択します。

   ![ メンバーのタブ – 新しいメンバーの役割を割り当てる](./assets/buying-group-details-assign-member-edit-role.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。

### メンバーの削除

選択した1人以上のメンバー（一度に50人まで）を購買グループから削除できます。

1. 削除するメンバーのチェックボックスをオンにします。

1. 下部の選択バーで、**[!UICONTROL メンバーの削除]**&#x200B;をクリックします。

   ![ メンバーのタブ – メンバーの削除](./assets/buying-group-details-remove-selected.png){width="700" zoomable="yes"}

1. 確認ダイアログで、**[!UICONTROL 削除]**&#x200B;をクリックします。

### ロールを編集

購買グループの1人または複数の選択したメンバー（一度に最大50人）の役割を変更できます。

1. 役割を変更するメンバーのチェックボックスをオンにします。

1. 下部の選択バーで、**[!UICONTROL 役割を編集]**&#x200B;をクリックします。

   ![ メンバーのタブ – 役割の編集](./assets/buying-group-details-edit-roles.png){width="700" zoomable="yes"}

1. _[!UICONTROL メンバーの役割を編集]_ ダイアログで、各メンバーに割り当てる役割を選択します。

   ![ メンバーの役割を編集 – ロールを選択](./assets/buying-group-details-edit-roles-choose-roles.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。

### メールを送信

マーケター承認済みのメールを、購買グループの1人または複数の選択したメンバー（1回に最大50人）に送信できます。 利用可能なメールのリストは、接続されたMarketo Engage インスタンスからの承認済みメールに限定されます。

1. メールを受信するメンバーのチェックボックスをオンにします。

1. 右上または下部の選択バーで、**[!UICONTROL メールを送信]**&#x200B;をクリックします。

   ![ メンバーのタブ – メールを送信](./assets/buying-group-details-send-email.png){width="700" zoomable="yes"}

1. _[!UICONTROL メールを送信]_ ダイアログで、Marketo Engage ワークスペースを選択し、送信するメールのチェックボックスをオンにします。

   ![購買グループのメンバーに送信するメールを選択](../accounts/assets/account-details-send-email-dialog.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 送信]**」をクリックします。
