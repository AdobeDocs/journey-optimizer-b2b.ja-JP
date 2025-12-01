---
title: アクションの実行
description: アカウントおよび人物アクション用のアクションノードの設定 – メールの送信、購買グループの更新、スコアの変更、Journey Optimizer B2B editionのMarketo Engageとの統合などを行います。
feature: Account Journeys
role: User
exl-id: 167cb627-96ee-42a8-8657-bb8040bb4bfe
source-git-commit: ab6629f97231ecde67dcc38d3fcb815b29eb5e37
workflow-type: tm+mt
source-wordcount: '1699'
ht-degree: 2%

---

# アクションの実行

アカウントジャーニーで、_[!UICONTROL アクションの実行]_ ノードを追加して、メールの送信、スコアの変更、購入グループへの割り当てなどのアクションを実行できます。 アクションは、通常、イベントや以前のアクションなど、何らかのトリガーの結果として発生させるもので、

![ビデオ](../../assets/do-not-localize/icon-video.svg){width="30"} [概要ビデオを視聴](#overview-video)

## アカウントのアクション

ノードパス上のアカウントに属するすべてのユーザーに変更を適用する場合は、アカウントに対するアクションを使用します。

### アクションと制約 {#account-action-constraints}

| アクション | 制約 |
| ------ | ----------- |
| [!UICONTROL  アカウント興味深い瞬間 ] | タイプ （メール、マイルストーン、web） <br/> 説明（オプション） |
| [!UICONTROL  宛先に対してアクティブ化 ] | 宛先を選択 |
| [!UICONTROL  （その他）ジャーニーにアカウントを追加 ] | ライブアカウントジャーニーを選択 |
| [!UICONTROL  アカウントリストに追加 ] | ライブの静的アカウントリストを選択 |
| [!UICONTROL ジャーニーからアカウントを削除 ] | ライブアカウントジャーニーを選択 |
| [!UICONTROL  アカウントリストから削除 ] | ライブ静的アカウントリストの選択 |
| [!UICONTROL  販売アラートの送信 ] | ソリューションの関心 <br/> メールの送信先を選択 |
| [!UICONTROL  アカウントプロファイルを更新 ] | 属性 <br/> 新しい値を選択 |
| [!UICONTROL  購買グループの更新ステージ ] | ソリューションの興味 <br/> 購入グループのステージを選択 |
| [!UICONTROL  購買グループ・ステータスの更新 ] | ソリューションの関心 <br/> ステータスを選択（必須、最大 50 文字） |

>[!NOTE]
>
>2025.10 リリースでは、_[!UICONTROL アカウント変更データ値]_ アクションは非推奨（廃止予定）になりました。 _[!UICONTROL 簡略化されたアーキテクチャ]_ では、[ アカウントプロファイルを更新 ](../simplified-architecture.md) に置き換えられました <br/>。
>
>管理者は、_[!UICONTROL XDM クラス]_/_[!UICONTROL 標準クラス]_ のフィールドを更新することで、XDM ビジネスアカウントで使用可能な属性を設定できます。 詳しくは、[ 標準クラス ](../admin/xdm-field-management.md#standard-classes) を参照してください。

### アカウントベースのアクションの追加

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、「**[!UICONTROL アクションを実行]**」を選択します。

   ![ ジャーニーノードを追加 – アクションを実行 ](./assets/add-node-action.png){width="400"}

1. 右側のノードプロパティで、アクションとして **[!UICONTROL アカウント]** を選択します。

1. リストからアクションを選択し、アクションの値を設定します。

   ![ジャーニーノード – アカウントに対してアクションを実行 ](./assets/node-take-action-account.png){width="700" zoomable="yes"}

>[!BEGINSHADEBOX]

### LinkedIn 宛先に対してアクティブ化

アカウントの _宛先に対してアクティブ化_ アクションを使用して、ジャーニーから直接Experience Platformの宛先に対してアカウントをアクティブ化します。 このアクションを使用すると、サポートされている宛先で、一致したオーディエンスに（購入グループフィルター、エンゲージメントスコア、その他の条件に基づいて）選定されたアカウントをプッシュできます。 0.43188884

2025.10 リリース以降、**_LinkedIn_** が最初にサポートされる宛先タイプです。 LinkedIn 宛先のアクションを使用すると、複数システムのハンドオフを排除し、待ち時間を短縮して、キャンペーンの実行を効率化できます。 例えば、マーケターは、主要な購入の役割が見つからない場合のリターゲティング用に LinkedIn に対してハイインテントのアカウントを自動的にアクティブ化したり、非アクティブなフィルターに基づいて休眠中のアカウントを再エンゲージしたりできます。

LinkedIn 宛先に対してアカウントに一致したオーディエンスを使用する方法について詳しくは、[LinkedIn アカウントに一致したオーディエンス ](../data/linkedin-account-matched-audiences.md) を参照してください。

+++ LinkedIn の宛先に対するアカウントのアクティベーションの設定

1. ジャーニーキャンバスで _アクションの実行_ ノードを選択した状態で、**[!UICONTROL アカウントに対するアクション]** を **[!UICONTROL 宛先に対してアクティブ化]** に設定します。

1. **[!UICONTROL 宛先を選択]** をクリックします。

   ![ジャーニー ノード – アカウントに対してアクションを実行 – 宛先に対してアクティブ化 ](./assets/node-activate-destination-select-destination.png){width="600" zoomable="yes"}

1. ダイアログで、設定済みの LinkedIn の宛先を選択し、「**[!UICONTROL 保存]**」をクリックします。

![ジャーニーノード – アカウントに対するアクションの実行 – 宛先に対するアクティブ化 – 宛先を選択ダイアログ ](./assets/node-activate-destination-select-destination-dialog.png){width="700" zoomable="yes"}

1. 宛先でアクティブ化されたオーディエンスを識別するために使用される **[!UICONTROL オーディエンス名]** を入力します。

   ![ジャーニー ノード – アカウントに対するアクションの実行 – 宛先に対するアクティブ化 – 設定完了 ](./assets/node-activate-destination-settings.png){width="550" zoomable="yes"}

+++

>[!ENDSHADEBOX]

## 顧客のアクション

ノードパス上のすべてのユーザーに変更を適用する場合は、「ユーザーに対するアクション」を使用します。 このノードタイプは、分割パス内で人物またはアカウントごとに使用できます。

### アクションと制約 {#people-action-constraints}

| コンテキスト | アクション | 制約 |
| ------- | ------ | ----------- |
| [Journey Optimizer B2B](#journey-optimizer-b2b-actions) | [!UICONTROL  外部顧客オーディエンスに追加 ] | 外部の顧客オーディエンスを選択 |
| | [!UICONTROL  購買グループへの割当て ] | ソリューションの関心 <br/> 役割を選択 |
| | [!UICONTROL  スコアを変更 ] | スコア名 <br/> スコアの変更 |
| | [!UICONTROL  人物の興味深い瞬間 ] | タイプ <br/> 説明 |
| | [!UICONTROL  購入グループから削除 ] | ソリューションに対する関心を選択 |
| | [!UICONTROL  メールを送信 ] | 新しいメールを作成 <br/>Marketo Engageからメールを選択 |
| | [!UICONTROL SMS を送信 ] | SMS を作成 |
| | [!UICONTROL  ユーザープロファイルを更新 ] | 人物属性 <br/> 新しい値を設定を選択 |
| [Marketo Engage](#marketo-engage-actions) | [!UICONTROL Marketo Engage リクエストキャンペーンに追加 ] | Marketo Engage Workspace を選択し <br/> リクエストキャンペーンを選択します。 |
| | [!UICONTROL Marketo リストに追加 ] | 外部Marketo接続の名前を選択 <br/> リスト名 |
| | [!UICONTROL Marketoリストから削除 ] | 外部Marketo接続の名前を選択 <br/> リスト名 |

>[!NOTE]
>
>2025.10 リリースでは _[!UICONTROL Marketo Engageの人物パーティションを変更]_ アクションは非推奨となり、Journey Optimizer B2B editionの [ シンプルなアーキテクチャ ](../simplified-architecture.md) では使用できません。<br/>
>
>_[!UICONTROL データ値を変更]_ アクションは 2025.10 リリースで非推奨（廃止予定）になりました。 簡略化されたアーキテクチャでは、_[!UICONTROL 人物プロファイルを更新]_ に置き換えられています。

### ユーザーベースのアクションを追加

1. ジャーニーマップに移動します。

1. パスのプラス（**+**）アイコンをクリックし、「**[!UICONTROL アクションを実行]**」を選択します。

1. 右側のノードのプロパティで、アクションとして **[!UICONTROL People]** を選択します。

1. リストからアクションを選択し、アクションの値を設定します。

![ジャーニー ノード – 人物に対してアクションを実行 ](./assets/node-take-action-people.png){width="700" zoomable="yes"}

### Journey Optimizer B2B アクション

Journey Optimizer B2B の人物ベースのアクションは、設定されたチャネルを通じてのコミュニケーションを管理し、購入グループおよびアカウント内の人物の分類を管理するように設計されています。 ジャーニーは、ユーザープロファイルを持つ資格のあるアカウントがノードに到達すると、アクションを適用します。

+++[!UICONTROL  外部顧客オーディエンスに追加 ]

このアクションを使用して、外部オーディエンスにユーザーをプッシュします。このオーディエンスは、有料メディアチャネルでアクティブ化でき、購入グループのメンバーをさらにターゲットにすることができます。 このアクションは、Real-Time CDP B2B editionを通じて実行されます。

>[!NOTE]
>
>個人プロファイルを含む資格のあるアカウントが公開済みのジャーニーの _外部顧客オーディエンスに追加_ ノードに達した場合、これらのプロファイルが外部オーディエンスに入力されるまで最大 48 時間かかる場合があります。

![ アクションの実行 – 外部の顧客オーディエンスに追加 ](./assets/node-action-add-to-external-audience-options.png){width="300"}

この人物ベースのアクションを選択すると、新しい外部オーディエンスを作成したり、既存の外部オーディエンスのリストから選択したりできます。

* 既存のオーディエンスの場合は、[!DNL Journey Optimizer B2B Edition] でのみ作成された外部の顧客オーディエンスから選択できます。
* オーディエンスを作成し、このジャーニーアクションに使用する場合は、必ず宛先に接続してください。 詳しくは、[ ドキュメントの ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/connect-destination){target="_blank"} 新しい宛先接続の作成 [ および ](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activation-overview#activate-audiences-from-the-destinations-catalog){target="_blank"} アクティベーションの概要 [!DNL Experience Platform] を参照してください。

![ ビデオ ](../../assets/do-not-localize/icon-video.svg){width="30"}[ 有料メディアオーケストレーションの概要に関するビデオをご覧ください ](../data/linkedin-account-matched-audiences.md#orchestrate-paid-media-engagement)

2025.10 リリース以降、[!DNL Experience Platform] で作成された外部オーディエンス（[!DNL Adobe Target] の宛先など）を使用してオーケストレーションを行うこともできます。 このオーディエンス統合について詳しくは、[Adobe Target外部オーディエンス ](../audiences/target-external-audience.md) を参照してください。

外部オーディエンスを作成するには（_T） :_

1. 「**[!UICONTROL 新規作成]**」を選択します。

1. **[!UICONTROL 外部顧客オーディエンスを作成]** をクリックします。

1. 新しい外部オーディエンスの **[!UICONTROL 名前]** （必須）と **[!UICONTROL 説明]** （オプション）を入力します。

   ![ 外部顧客オーディエンスに追加 – オーディエンスを作成 ](./assets/node-action-add-to-external-create-new.png){width="300"}

1. 「**[!UICONTROL 作成]**」をクリックします。

   新しいオーディエンスが作成され、確認メッセージが表示されます。 その後、ノードアクションの既存のオーディエンスとして使用に進むことができます。

   >[!NOTE]
   >
   >Journey Optimizer B2B editionから新しい外部カスタマーオーディエンスが作成されると、ダミーレコードがシードされます（`test@email.com`）。 このレコードは、最初の実際のプロファイルがジャーニーから外部オーディエンスに追加されるとすぐに上書きされます。

既存のオーディエンスを使用するには（_T） :_

1. **[!UICONTROL 外部顧客オーディエンスを選択]** をクリックします。

1. ダイアログで、使用するオーディエンスを選択します。

   ![ 外部顧客オーディエンスに追加 – オーディエンスを追加 ](./assets/node-action-add-to-external-audience-select.png){width="700" zoomable="yes"}

1. **[!UICONTROL オーディエンスを追加]** をクリックします。

+++

+++[!UICONTROL  購買グループへの割当て ]

このアクションを使用して、選択したソリューションの関心と役割に基づいて、人物プロファイルを [ 購入グループ ](../buying-groups/buying-groups-overview.md) に追加します。

![ アクションを実行 – 購入グループに追加 ](./assets/node-action-add-to-buying-group.png){width="300"}

+++

+++[!UICONTROL  スコアを変更 ]

Marketo Engageで人物スコアを変更するには、このアクションを使用します。 [詳細情報](https://experienceleague.adobe.com/en/docs/marketo-learn/tutorials/lead-and-data-management/lead-scoring-learn){target="_blank"}

![ アクションの実行 – スコアの変更 ](./assets/node-action-change-score.png){width="300"}

+++

+++[!UICONTROL  人物の興味深い瞬間 ]

このアクションを使用して、人物に興味深い瞬間を記録します。 タイプ（メール、マイルストーン、web）を選択し、説明（オプション）を追加します。

![ アクションを取る – 人物興味深い瞬間 ](./assets/node-action-person-interesting-moment.png){width="300"}

+++

+++[!UICONTROL  購入グループから削除 ]

このアクションを使用して、選択したソリューションの関心に基づいて [ 購入グループ ](../buying-groups/buying-groups-overview.md) から人物プロファイルを削除します。

![ アクションを実行 – 購入グループに追加 ](./assets/node-action-remove-from-buying-group.png){width="300"}

+++

+++[!UICONTROL  メールを送信 ]

メールを送信するには、このアクションを使用します。 ノードの [ メールを作成 ](../content/add-email.md#add-an-email-to-your-journey) した後は、メールデザイン領域でメールメッセージのデザイン、パーソナライズおよびプレビューを行うことができます（[ メールのオーサリング ](../content/email-authoring.md) を参照）。 [Marketo Engageからメールを送信する ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/general/creating-an-email/create-an-email){target="_blank"} ともできます。 Marketo Engage Workspace を選択し、送信するメールを選択します。

![ アクションの実行 – メールの送信 ](./assets/node-action-send-email-from-marketo.png){width="300"}

+++

+++[!UICONTROL SMS を送信 ]

SMS メッセージを送信するには、このアクションを使用します。 ビジュアルデザインスペースで SMS メッセージの作成、パーソナライズ、プレビューを行うことができます（「[SMS オーサリング ](../content/sms-authoring.md)」を参照）。

![ アクションの実行 – SMS の送信 ](./assets/node-action-send-sms.png){width="300"}

+++

+++[!UICONTROL  ユーザープロファイルを更新 ]

[ 人物プロファイル属性 ](../admin/field-mapping.md#xdm-business-person-attributes) の値を変更するには、このアクションを使用します。 属性を選択して、新しい値を設定します。

![ アクションの実行 – 人物プロファイルの更新 ](./assets/node-action-update-person-profile.png){width="300"}

>[!NOTE]
>
>_[!UICONTROL 簡略化されたアーキテクチャ]_ に対する _[!UICONTROL データ値を変更]_ アクションは、[ 人物プロファイルを更新 ](../simplified-architecture.md) に置き換わります。<br/>
>
>管理者は、_[!UICONTROL XDM クラス]_/[!UICONTROL  標準クラス ] のフィールドを更新することで、XDM 個人プロファイルで使用可能な属性を設定できます。 詳しくは、[ 標準クラス ](../admin/xdm-field-management.md#standard-classes) を参照してください。

+++

### Marketo Engageアクション

Marketo Engageのユーザーベースのアクションは、Marketo Engage B2B editionのアカウントベースのマーケティングオーケストレーションとJourney Optimizerのリードベースのマーケティング活動を調整するように設計されています。 これらのアクションを使用して、リストメンバーシップを調整し、キャンペーンをリクエストします。

>[!NOTE]
>
>Marketo Engageのアクションには、1 つ以上の外部Marketo Engage インスタンスとの設定済みの統合が必要です。<!-- For detailed information about configuring these connections, see #. -->

例えば、Journey Optimizer B2B editionの購買グループに属するユーザーに対しては、Marketo Engageのキャンペーンを抑制できます。 この場合、特にソリューションの関心に合わせて、Marketo Engageで静的リストを作成できます。 次に、購入グループによる分割パスで、ジャーニーノードから _Marketo リストに追加_ アクションを使用します。 このアクションにより、接続されたMarketo Engage インスタンス内の特定の静的リストに購入グループメンバーが追加されます。 次に、Marketo Engageのスマートリストフィルターにソリューションの関心に焦点を当てた静的リストを使用します。

+++[!UICONTROL Marketo Engage リクエストキャンペーンに追加 ]

Marketo Engageの [ リクエストキャンペーン ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-campaigns/flow-actions/request-campaign){target="_blank"} に人物プロファイルを追加するには、このアクションを使用します。

まず、接続されたMarketo Engage インスタンスを選択します。 次に、リクエストキャンペーン名を選択します。

![ アクションを実行 – Marketo Engage リクエストキャンペーンに追加 ](./assets/node-action-add-to-request-campaign-options.png){width="300"}

+++

+++[!UICONTROL Marketo リストに追加 ]

Marketo Engageでユーザーを [ 静的リスト ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-lists-and-static-lists/static-lists/understanding-static-lists){target="_blank"} に追加するには、このアクションを使用します。

まず、接続されたMarketo Engage インスタンスを選択します。 次に、リスト名を選択します。

![ アクションを実行 – Marketo リストに追加 ](./assets/node-action-add-to-list-options.png){width="300"}

+++

+++[!UICONTROL Marketoリストから削除 ]

Marketo Engageの [ 静的リスト ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-lists-and-static-lists/static-lists/understanding-static-lists){target="_blank"} からユーザーを削除するには、このアクションを使用します。

まず、接続されたMarketo Engage インスタンスを選択します。 次に、リスト名を選択します。

![ アクションの実行 – Marketoリストから削除 ](./assets/node-action-remove-from-list-options.png){width="300"}

+++

## 概要動画

>[!VIDEO](https://video.tv.adobe.com/v/3443207/?learn=on)
