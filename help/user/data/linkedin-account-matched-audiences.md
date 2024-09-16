---
title: LinkedIn アカウントでマッチしたオーディエンス
description: linkedIn アカウントを連携し、購入グループ用のデータフローをアクティブ化する方法を説明します。
exl-id: d2303529-16c4-4b0b-b8c8-404dff8ec63d
source-git-commit: 00315c9d245d8d19954643e4dd51920ae2baafbe
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 8%

---

# LinkedIn アカウントでマッチしたオーディエンス

Journey Optimizer B2B Edition は、アカウントでマッチしたオーディエンスを通じてLinkedIn広告オーディエンスを生成する機能を提供し、購入グループの空の役割を満たすのを支援するように設計されています。 購入グループフィルターのセットを定義することで、LinkedInでマッチしたオーディエンスを維持し、購入グループパラメーターに一致する見込み客をターゲットにすることができます。 この機能は、Experience Platformの宛先を活用して、統合の一部の側面を管理します。 データフローの上限は 10 個です。

Journey Optimizer B2B Edition からデータフローを開始する前に、Experience Platformアプリケーションで設定されたLinkedIn Campaign Manager アカウントを持つ、[ （Companies）LinkedInと一致するオーディエンスの宛先コネクタのインスタンスが少なくとも 1 つ必要で ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/social/linkedin#connect)。

## 新しい LinkedIn アカウント接続を設定 {#linkedin-destination-setup}

>[!CONTEXTUALHELP]
>id="ajo-b2b_linkedin_destination_setup"
>title="LinkedIn の宛先の設定は必須です"
>abstract="購買グループ別にフィルタリングされたアカウントを LinkedIn の宛先に送信し、潜在的な購買グループのメンバーに関与します。フィルタリングされたアカウントの 10 個の異なるグループに対して、最大 10 個のデータフローを作成できます。この機能の使用を開始するには、まず Linkedin の宛先を追加します。"

1. Experience Platformで、左側のナビゲーションで **[!UICONTROL 接続]**/**[!UICONTROL 宛先]** に移動し、「**[!UICONTROL カタログ]**」タブを選択します。

1. カタログ内で、**[!UICONTROL （会社）LinkedInの一致したオーディエンス]** コネクタを見つけます。

   >[!TIP]
   >
   >検索ボックスに `LinkedIn` と入力すると、コネクタをすばやく見つけることができます。

1. コネクタカードで「_詳細_ （**...**）」アイコンをクリックし、「**[!UICONTROL 新しい宛先を設定]**」を選択します。

   ![ （会社）LinkedInと一致したオーディエンスコネクタへのアクセス ](./assets/aep-destinations-catalog-linkedin.png){width="800" zoomable="yes"}

1. **[!UICONTROL 新規アカウント]** を選択し、「**[!UICONTROL 宛先に接続]**」をクリックします。

   ![ 新しいLinkedIn アカウントを接続する ](./assets/aep-destinations-catalog-linkedin-new-account.png){width="500"}

1. linkedInの資格情報を入力し、ログインします。

   認証後、LinkedIn アカウントはExperience Platformの宛先として接続されます。

   ![ アカウント接続の確認が表示されます ](./assets/aep-destinations-catalog-linkedin-connected.png){width="400"}

   >[!IMPORTANT]
   >
   >この時点で、**宛先の詳細 _[!UICONTROL を入力**ないでください]_。 接続のみが必要です。

## アカウントの詳細の更新

linkedIn アカウントの名前と説明は、Journey Optimizer B2B Edition の購入グループに表示されます。 この情報を更新して、購入グループに所属するマーケターが容易に識別できるようにすることがベストプラクティスです。 アカウントの詳細は、Experience PlatformまたはJourney Optimizer B2B Edition UI で変更できます。

1. 左側のナビゲーションで **[!UICONTROL 接続]**/**[!UICONTROL 宛先]** に移動し、「**[!UICONTROL アカウント]**」タブを選択します。

1. 作成した新しいアカウントについて、「_詳細_ （**...**）」メニューをクリックし、「**[!UICONTROL 詳細を編集]**」を選択します。

   ![ アカウントの詳細を編集 ](./assets/aep-destinations-accounts-edit-details.png){width="800" zoomable="yes"}

1. ダイアログで、名前と説明を更新します。

   ![ 名前と説明を編集 ](./assets/destinations-linkedin-account-edit-details-dialog.png){width="500"}

1. 「**[!UICONTROL 保存]**」をクリックします。

## 購買グループのアカウントを有効化します

>[!NOTE]
>
>既に 10 個のデータフローがある場合、別のデータフローを作成することはできません。 最大数に達した場合は、Experience Platformで削除してから、Journey Optimizer B2B Edition で新しく作成します。

1. Journey Optimizer B2B Edition で、左側のナビゲーションの **[!UICONTROL アカウント]**/**[!UICONTROL 購入グループ]** に移動します。

1. 「**[!UICONTROL 参照]** タブを選択します。

1. 右上の **[!UICONTROL LinkedInの宛先に対してアクティブ化]** をクリックします。

   ![ アカウントの詳細を編集 ](./assets/activate-linkedin-destination.png){width="800" zoomable="yes"}

1. データフローにわかりやすい名前と説明を付けます（オプション）。

   保存すると、Experience Platform内のデータフローを識別できるように、データフローに指定した名前の先頭に _AJOB2B_ が付加されます。

1. [LinkedIn Campaign Manager アカウントのアカウント ID](https://www.linkedin.com/help/lms/answer/a424270) を入力します。

   アカウント ID は、Campaign Manager UI のアカウント名で確認できます。

   ![ データフローの詳細を追加 ](./assets/destinations-linkedin-activate-details.png){width="700" zoomable="yes"}

1. **[!UICONTROL 購入グループフィルターを選択]** をクリックし、アカウントオーディエンスのパラメーターを定義します。

   >[!IMPORTANT]
   >
   >現時点では、データフローをアクティブ化した後にフィルターを編集することはできません。 データフローをアクティブ化する前に、作業内容を再度確認します。

   ![ 購入グループに応じたアカウントオーディエンスフィルタリングの指定 ](./assets/destinations-linkedin-activate-buying-group-filters.png){width="400"}

   **[!UICONTROL エンゲージメントスコア]** の場合、演算子 `Between` はパーセンテージ範囲を含みます。 例えば、5.1 と 5 はどちらも _5 と 6_ す。

   空の条件は `Is Any` のように扱われます。

   「**[!UICONTROL 保存]**」をクリックして、指定したフィルターを追加します。

1. **[!UICONTROL LinkedInの宛先を選択]** をクリックし、使用する設定済みのLinkedInの宛先を選択します。

   アクティブ化すると、この設定によって、宛先設定と対応する仮想セグメントを使用してデータフローが作成されます。

1. 設定を再度確認し、右上の **[!UICONTROL アクティブ化]** をクリックします。

   確認ダイアログで **[!UICONTROL アクティブ化]** を再度クリックします。

   バナーとExperience Platformのデータフローメニューへのリンクが表示されるので、データフローレコードを確認できます。