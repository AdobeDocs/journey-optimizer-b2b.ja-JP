---
title: LinkedIn アカウントと一致するオーディエンス
description: LinkedIn アカウントを接続し、アカウントメンバーのデータフローをアクティブ化する方法について説明します。
feature: Integrations, Audiences, Buying Groups
role: User, Admin
exl-id: d2303529-16c4-4b0b-b8c8-404dff8ec63d
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a4b836d9-ffdd-4df3-a62a-f78b830cf059id: beb5f4be-cec3-471a-9db6-831a77dd3ac9id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: cad51180-f8ce-4cb7-aefc-437847b5d6d6
autotag-review: 2026-03-30T22:49:08.608Z
TQID: https://experienceleague.adobe.com/rFBH54jR-xCWenpoD13UzmONLdKn9WLdtNdTCtgQNbQ
source-git-commit: 9baf03a1ddc1733385b0398ffadde8f548c431cc
workflow-type: tm+mt
source-wordcount: 1015
ht-degree: 14%

---

# LinkedIn アカウントでマッチしたオーディエンス

[!DNL Journey Optimizer B2B Edition]は、アカウントに一致するオーディエンスを通じてLinkedIn広告オーディエンスを生成する機能を提供しており、購買グループの空の役割を埋めるのに役立つように設計されています。 一連の購買グループフィルターを定義することで、LinkedIn の一致するオーディエンスを維持し、購買グループのパラメーターに一致する見込み客をターゲットにすることができます。 _アクションを実行_ ノードからアカウントジャーニーからオーディエンスをアクティブ化することもできます。

この機能は、Experience Platform の宛先を活用して統合のいくつかの側面を管理します。 最大10個のデータフローがあります。

Journey Optimizer B2B editionからデータフローを開始する前に、Experience Platform アプリケーションで設定されたLinkedIn Campaign Manager アカウントを持つ[ （Companies） LinkedIn Matched Audience宛先コネクタ ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/catalog/social/linkedin#connect){target="_blank"}の少なくとも1つのインスタンスが必要です。

## 新しい LinkedIn アカウント接続を設定 {#linkedin-destination-setup}

>[!CONTEXTUALHELP]
>id="ajo-b2b_linkedin_destination_setup"
>title="LinkedIn の宛先の設定は必須です"
>abstract="購買グループ別にフィルタリングされたアカウントを LinkedIn の宛先に送信し、潜在的な購買グループのメンバーに関与します。 フィルタリングされたアカウントの 10 個の異なるグループに対して、最大 10 個のデータフローを作成できます。 この機能の使用を開始するには、まず Linkedin の宛先を追加します。"

1. Experience Platformで、左側のナビゲーションで&#x200B;**[!UICONTROL Connections]** > **[!UICONTROL Destinations]**&#x200B;に移動し、「**[!UICONTROL カタログ]**」タブを選択します。

1. カタログで、**[!UICONTROL （Companies） LinkedIn Matched Audience]** コネクタを見つけます。

   >[!TIP]
   >
   >検索ボックスに`LinkedIn`と入力すると、コネクタをすばやく見つけることができます。

1. コネクタカードで、_詳細_ （**...**）をクリックします アイコンをクリックし、**[!UICONTROL 新しい宛先を設定]**&#x200B;を選択します。

   ![LinkedIn Matched Audience コネクタに（企業）アクセス ](./assets/aep-destinations-catalog-linkedin.png){width="800" zoomable="yes"}

1. **[!UICONTROL 新しいアカウント]**&#x200B;を選択し、**[!UICONTROL 宛先に接続]**&#x200B;をクリックします。

   ![新しいLinkedIn アカウントを接続](./assets/aep-destinations-catalog-linkedin-new-account.png){width="500"}

1. LinkedInの資格情報を入力してログインします。

   認証後、LinkedIn アカウントはExperience Platformの宛先として接続されます。

   ![ アカウント接続の確認が表示されます](./assets/aep-destinations-catalog-linkedin-connected.png){width="400"}

   >[!IMPORTANT]
   >
   >この時点で、**は&#x200B;_[!UICONTROL 宛先の詳細]_を入力しません**。 接続だけが必要です。

## アカウント詳細の更新

LinkedIn アカウントの名前と説明は、Journey Optimizer B2B editionの購買グループに表示されます。 この情報を更新して、購買グループを扱うマーケターが容易に特定できるようにすることがベストプラクティスです。 アカウントの詳細は、Experience PlatformまたはJourney Optimizer B2B edition UIで変更できます。

1. 左側のナビゲーションで&#x200B;**[!UICONTROL 接続]** > **[!UICONTROL 宛先]**&#x200B;に移動し、**[!UICONTROL アカウント]** タブを選択します。

1. 作成した新しいアカウントの場合、_詳細_ （**...**）をクリックします メニューから&#x200B;**[!UICONTROL 詳細を編集]**&#x200B;を選択します。

   ![アカウントの詳細を編集](./assets/aep-destinations-accounts-edit-details.png){width="800" zoomable="yes"}

1. ダイアログで、名前と説明を更新します。

   ![名前と説明を編集](./assets/destinations-linkedin-account-edit-details-dialog.png){width="500"}

1. 「**[!UICONTROL 保存]**」をクリックします。

## 購買グループのアカウントをアクティブ化

>[!NOTE]
>
>既に10個のデータフローがある場合、別のデータフローを作成することはできません。 上限を設定している場合は、Journey Optimizer B2B editionで新しい値を作成する前に、Experience Platformで値を削除します。

1. Journey Optimizer B2B Edition で、左側のナビゲーションにある&#x200B;**[!UICONTROL アカウント]**／**[!UICONTROL 購買グループ]**&#x200B;に移動します。

1. 「**[!UICONTROL 参照]**」タブを選択します。

1. 右上の「**[!UICONTROL LinkedIn Destination]**&#x200B;にアクティベート」をクリックします。

   ![アカウントの詳細を編集](./assets/activate-linkedin-destination.png){width="800" zoomable="yes"}

1. データフローにわかりやすい名前と説明を付けます（オプション）。

   データフローを保存すると、データフローに指定した名前の先頭に&#x200B;_AJOB2B_&#x200B;が付き、Experience Platformでのデータフローの識別に役立ちます。

1. LinkedIn Campaign Manager アカウント ](https://www.linkedin.com/help/lms/answer/a424270)の[ アカウント IDを入力します。

   アカウント IDは、Campaign Manager UIのアカウント名で確認できます。

   ![ データフローの詳細を追加](./assets/destinations-linkedin-activate-details.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 購買グループフィルターを選択]**」をクリックし、アカウントオーディエンスのパラメーターを定義します。

   >[!IMPORTANT]
   >
   >現時点では、データフローがアクティブ化された後にフィルターを編集することはできません。 データフローをアクティブ化する前に、作業を再確認します。

   ![購買グループに応じてアカウントオーディエンスフィルタリングを指定](./assets/destinations-linkedin-activate-buying-group-filters.png){width="400"}

   **[!UICONTROL エンゲージメントスコア]**&#x200B;の場合、演算子 `Between` は、パーセンテージ範囲と同様に包括的です。 例えば、5.1 と 5 は、どちらも 5 と 6 の&#x200B;_間_&#x200B;にあります。

   空の条件は`Is Any`のように扱われます。

   **[!UICONTROL 保存]**&#x200B;をクリックして、指定したフィルターを追加します。

1. 「**[!UICONTROL LinkedInの宛先]**&#x200B;を選択」をクリックし、使用する設定済みのLinkedInの宛先を選択します。

   この設定は、アクティブ化すると、宛先設定と対応する仮想セグメントを使用してデータフローを作成します。

1. 設定を再確認し、右上の「**[!UICONTROL アクティブ化]**」をクリックします。

   確認ダイアログで「**[!UICONTROL アクティブ化]**」をもう一度クリックします。

   Experience Platformのデータフローメニューへのリンクがバナーに表示され、データフローレコードを確認できます。

## アカウントジャーニーからオーディエンスをアクティブ化

2025.10 リリース以降、_宛先に対してアクティブ化_ アクションを使用して、アカウントをジャーニーから直接LinkedIn宛先に対してアクティブ化します。 LinkedInの宛先に対してアクションを使用すると、マルチシステムのハンドオフを排除し、待ち時間を短縮して、キャンペーンの実行を効率化できます。 たとえば、マーケターは、主要な購買役割が欠けている場合はリターゲティングのために、インテント率の高いアカウントをLinkedInで自動的に活用したり、非アクティブなフィルターにもとづいて休眠アカウントをリエンゲージしたりできます。

1. ジャーニーキャンバスで「_アクションを実行_」ノードを選択した状態で、「**[!UICONTROL アカウントに対するアクション]**」を「**[!UICONTROL 宛先に対するアクティブ化]**」に設定します。

   ![ジャーニーノード – アカウントに対してアクションを実行 – アクティベート先](./assets/node-activate-destination.png){width="550" zoomable="yes"}

1. 右側のノードプロパティから、宛先を選択します。

   * 1つ以上の宛先が作成されている場合は、**[!UICONTROL 宛先を選択]**&#x200B;をクリックして、既存の宛先を選択できます。

   * 既存の宛先がない場合、または新しい宛先を作成する場合は、**[!UICONTROL 宛先の設定]**&#x200B;をクリックします。

     ![ジャーニーノード – アカウントに対してアクションを実行 – 宛先に対してアクティブ化 – 宛先を設定](./assets/node-activate-destination-set-up-destination.png){width="550" zoomable="yes"}

     このアクションは、新しいブラウザータブで宛先カタログページを開きます。

   ![ジャーニーノード – アカウントに対してアクションを実行 – アクティベート先](../journeys/assets/node-activate-destination-select-destination.png){width="600" zoomable="yes"}

1. ダイアログで、設定したLinkedInの宛先を選択し、**[!UICONTROL 保存]**&#x200B;をクリックします。

   ![ジャーニーノード – アカウントに対してアクションを実行 – 宛先に対してアクティブ化 – 宛先を選択ダイアログ ](../journeys/assets/node-activate-destination-select-destination-dialog.png){width="700" zoomable="yes"}

1. 宛先でアクティブ化されたオーディエンスを識別するために使用される&#x200B;**[!UICONTROL オーディエンス名]**&#x200B;を入力します。

   ![ジャーニーノード – アカウントに対してアクションを実行 – アクティベート先 – 完了した設定](../journeys/assets/node-activate-destination-settings.png){width="550" zoomable="yes"}

## 有料メディアエンゲージメントのオーケストレーション

LinkedIn広告オーディエンスなどの有料メディアチャネルを通じてアカウントメンバーとエンゲージし、獲得、育成をおこない、セールスにつなげることができます。 アカウントジャーニーで&#x200B;_アクション_ ノードを使用して、様々なアカウントメンバーに最適な外部チャネルを通じて、アカウントの主要メンバーとのエンゲージメントを自動化します。

>[!VIDEO](https://video.tv.adobe.com/v/3448649/?learn=on)