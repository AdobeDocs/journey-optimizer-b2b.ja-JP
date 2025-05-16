---
title: ジャーニーとプログラムでアカウント一覧を使用する
description: ジャーニーでアカウントリストメンバーシップを調整し、アカウントリストメンバーシップに基づいてMarketo Engage スマートリストをフィルタリングする方法について説明します。
feature: Account Lists, Account Journeys
role: User
exl-id: 7cda080d-6263-4ccd-b144-432e4e78c298
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '684'
ht-degree: 0%

---

# ジャーニーとプログラムでのアカウントリストの使用

ライブ（公開済み）アカウントリストをアカウントジャーニーに組み込む方法はいくつかあります。

## アカウントオーディエンスノード

すべてのアカウントジャーニーは、[_アカウントオーディエンス_ ノード ](../journeys/account-audience-nodes.md) で開始します。 アカウントリストを使用するようにこのノードを設定すると、メンバーアカウントは実稼働（公開）時にジャーニーを移動します。

1. 開始 **[!UICONTROL アカウントオーディエンス]** ノードの _アカウントリスト_ オプションを選択します。

   ![ アカウントオーディエンスノードのアカウントリストオプションを選択 ](../journeys/assets/node-audience-account-list.png){width="500"}

1. **[!UICONTROL アカウントリストを追加]** をクリックします。

1. アカウントリストのチェックボックスを選択し、「**[!UICONTROL 保存]**」をクリックします。

   ![ アカウントオーディエンスノードのアカウントリストオプションを選択 ](../journeys/assets/node-audience-account-list-select-dialog.png){width="600" zoomable="yes"}

## アクションノードの作成 – アカウントに追加

**_静的アカウントリストのみ_**

アカウントジャーニー内で、[a _アクションを実行_ ノード ](../journeys/action-nodes.md) を使用して、アカウントを静的アカウントリストに追加します。

例えば、メールを送信するジャーニーパスがあり、一部のアカウントが応答アクションとして様々なアクションを実行する場合などです。 このアクティビティをジャーニーの選定ポイントと見なし、選定アカウントのフローが異なる別のジャーニーのオーディエンスとして使用されるアカウントリストに追加するとします。

>[!NOTE]
>
>ノードの実行時にアカウントがリストに既に含まれている場合、そのアクションは無視されます。

1. _[!UICONTROL アカウントに対するアクション]_ オプション **[!UICONTROL 選択]** ます。

1. _[!UICONTROL アカウントに対するアクション]_ については、**[!UICONTROL アカウントリストに追加]** を選択します。

   ![ 「アカウントに追加」リストを選択 ](../journeys/assets/node-action-account-add-to-account-list.png){width="500"}

1. **[!UICONTROL ライブ静的アカウントリストを選択]** については、アカウントを追加するアカウントリストを選択します。

   ![ 「アカウントに追加」リストを選択 ](../journeys/assets/node-action-account-add-to-account-list-select.png){width="500"}

## アクションノードの実行 – アカウントから削除

**_静的アカウントリストのみ_**

アカウントジャーニー内で、[a _アクションを実行_ ノード ](../journeys/action-nodes.md) を使用して、静的アカウントリストからアカウントを削除します。

例えば、メールを送信するジャーニーパスがあり、一部のアカウントが応答アクションとして様々なアクションを実行する場合などです。 このアクティビティをジャーニーの選定ポイントと見なし、選定コミュニケーションが重複しないように、追加のメールを送信する別のジャーニーのオーディエンスとしてに使用されるアカウントリストから削除するとします。

>[!NOTE]
>
>アカウントが削除予定のリストにない場合、アクションは無視されます。

1. _[!UICONTROL アカウントに対するアクション]_ オプション **[!UICONTROL 選択]** ます。

1. _[!UICONTROL アカウントに対するアクション]_ については、**[!UICONTROL アカウントリストから削除]** を選択します。

   ![ 「アカウントに追加」リストを選択 ](../journeys/assets/node-action-account-remove-from-account-list.png){width="500"}

1. **[!UICONTROL ライブ静的アカウントリストを選択]** については、アカウントを削除するアカウントリストを選択します。

   ![ 「アカウントに追加」リストを選択 ](../journeys/assets/node-action-account-remove-from-account-list-select.png){width="500"}

## Marketo Engage プログラム – アカウントのメンバーリスト

マーケターの場合、Journey Optimizer B2B editionのアカウントリストに含まれているユーザーに対しては、Marketo Engageのプログラムを抑制することができます。

Journey Optimizer B2B editionに接続されたMarketo Engage インスタンスでは、スマートリストで _[!UICONTROL アカウントリストのメンバー]_ フィルターを使用し、キャンペーン戦略に従ってこれらのリードを特定することができます。 スマートリストについて詳しくは、[Marketo Engage ドキュメント ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-lists-and-static-lists/understanding-smart-lists){target="_blank"} を参照してください。

### スマート・リストへのフィルタの追加

1. Marketo Engageでキャンペーンを選択し、「**[!UICONTROL スマートリスト]**」タブをクリックします。

1. 右側に表示されたフィルターリストで、`Member` と入力して **[!UICONTROL アカウントリストのメンバー]** フィルターを見つけます。

1. フィルターをスマート・リスト・キャンバスにドラッグします。

1. スマート・リスト・キャンバスで、**[!UICONTROL アカウントのメンバー]** リスト値を設定します。

   下向き矢印をクリックしてすべてのアカウントリストを表示するか、アカウントリスト名の一部を入力して必要なアカウントリストを見つけます。

   ![ アカウントリストメンバーシップ用Marketo Engage スマートリストフィルター ](./assets/account-lists-marketo-engage-smart-list.png){width="800" zoomable="yes"}

1. キャンペーンフローで、「**[!UICONTROL リストに追加]**」手順を追加し、Journey Optimizer B2B edition アカウントリストからユーザーを入力するリストを選択します。

   フローにステップを追加する方法について詳しくは、Marketo Engage ドキュメントの _[スマートキャンペーンへのフローステップの追加 ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-campaigns/flow-actions/add-a-flow-step-to-a-smart-campaign){target="_blank"}_ を参照してください。

### メンバーのレビュー

フローを実行した後、リストに入力されたユーザーのリストを表示できます。 リストを開いて「人物」タブを選択します。

![ アカウントリストから入力されたMarketo Engage キャンペーンリスト ](./assets/account-lists-marketo-engage-smart-list-people.png){width="800" zoomable="yes"}
