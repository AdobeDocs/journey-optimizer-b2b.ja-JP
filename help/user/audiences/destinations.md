---
title: 宛先
description: サポートされているExperience Platformの宛先と、宛先を接続してJourney Optimizer B2B Editionで静的な人物リストをアクティブ化する方法について説明します。
feature: Audiences, Integrations
role: User
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
feature_v2:
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
    internal-label: Audiences
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
    internal-label: Audience segmentation
source-git-commit: 734966636b6d2addf014905431fa755f6fe92ee6
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 6%
---

# 宛先

宛先は、[静的な人物リスト &#x200B;](./people-lists-static.md)のメンバーとアカウントジャーニーのオーディエンスをソーシャルプラットフォームに送信できる、事前定義済みの統合です。 宛先に対して静的リストをアクティブ化すると、メンバーシップが同期したままになります。 オーディエンスがリストに追加またはリストから削除されると、オーディエンスは宛先オーディエンスに追加または削除され、拡張機能としてオーディエンスがフィードする任意のキャンペーンに追加または削除されます。

接続された宛先に対してユーザーをアクティブ化するには、次の3つの方法があります。

* **静的リストから** – 既存の静的リストを&#x200B;**_[!UICONTROL 人物リスト]_** タブから直接有効にします。 [_宛先に対するアクティブ化_](./people-lists-static.md#static-list-activate)&#x200B;を参照してください。
* **アカウントジャーニーから** - **_[!UICONTROL 宛先にアクティベート]_** アクションノードをジャーニーパスに追加して、適格なアカウントがそのノードに到達したときに宛先にアクティベートされるようにします。 [_宛先に対してアクティブ化または非アクティブ化_](../journeys/action-nodes.md#activate-deactivate-destination)&#x200B;を参照してください。
* **購買グループから** – 購買グループ内の空の役割を埋めるために、LinkedIn Matched Audienceをアクティブ化して、購買グループのパラメーターに一致する見込み顧客をターゲットにすることができます。 [_LinkedIn Account Matched audience_s](../data/linkedin-account-matched-audiences.md#activate-buying-group)を参照してください。

>[!BEGINSHADEBOX]

## 必要な権限 {#required-permissions}

完全な宛先機能には、次の[!DNL Adobe Experience Platform]権限が必要です。

| カテゴリ | 権限 |
|--- |--- |--- |
| サンドボックス | サンドボックスアクセス |
| ダッシュボード | 標準ダッシュボードを表示 |
| ダッシュボード | 標準ダッシュボードの管理 |
| 宛先 | 宛先の表示 |
| 宛先 | 宛先の管理 |
| 宛先 | 宛先のアクティブ化 |
| 宛先 | マッピングなしでセグメントをアクティブ化 |
| 宛先 | データセット宛先の管理とアクティブ化 |
| 宛先 | 宛先オーサリング |
| データガバナンス | データ使用ポリシーの表示 |
| データガバナンス | データ使用ポリシーの管理 |
| データ取り込み | ソースの表示 |
| データ取り込み | ソースの管理 |
| プロファイル管理 | プロファイル設定の表示 |
| プロファイル管理 | プロファイル設定の管理 |

>[!ENDSHADEBOX]

## サポートされる宛先 {#supported-destinations}

静的リストをアクティブ化する前に、宛先カタログに宛先が存在する必要があります。 左側のナビゲーションで、**[!UICONTROL 接続]**&#x200B;を展開し、**[!UICONTROL 宛先]**&#x200B;を選択します。 [!DNL Journey Optimizer B2B Edition]は現在、**[!UICONTROL LinkedIn Matched Audience]** （Social）宛先をサポートしています。 [_LinkedIn Account Matched audiences_](../data/linkedin-account-matched-audiences.md)&#x200B;を参照して、以下を行います

<!-- 
the following destinations:

* **[!UICONTROL Google Customer Match]** (Advertising)
* **[!UICONTROL Facebook Custom Audience]** (Social)
* **[!UICONTROL LinkedIn Matched Audience]** (Social)

![Access the available connector types](./assets/destinations-catalog.png){width="800" zoomable="yes"}

-->

>[!NOTE]
>
>表示されたカタログは、完全な[!DNL Adobe Experience Platform]宛先カタログではありません。 [!DNL Experience Platform]から宛先に直接アクセスすると、大きなカタログが表示されますが、現在これらの宛先のみが[!DNL Journey Optimizer B2B Edition]でアクティブ化できます。 今後のリリースのために、さらに宛先を追加する予定です。

## 宛先を設定 {#set-up-destination}

サポートされている各宛先カードには、**[!UICONTROL 新しい宛先の設定]**&#x200B;が表示されます。 宛先を設定することは、アクティベーションの前提条件です。

1. コネクタカードで、**[!UICONTROL 新しい宛先の設定]**&#x200B;をクリックします。

   ![新しい宛先を設定](./assets/destinations-configure-new.png){width="500"}

1. **[!UICONTROL 既存のアカウント]**&#x200B;または&#x200B;**[!UICONTROL 新しいアカウント]**&#x200B;を選択し、アカウント名や説明などのアカウントの詳細を入力します。

1. 「**[!UICONTROL 宛先に接続]**」をクリックします。

   OAuth フローを使用すると、対応するアカウント（LinkedIn、Google、またはFacebook）にログインできます。

   >[!IMPORTANT]
   >
   >この時点で、_[!UICONTROL 宛先の詳細]_&#x200B;を入力しないでください。 接続だけが必要です。

1. 人物の属性と宛先に必要なフィールドの間の必須フィールドマッピングを完了します。

1. データガバナンスとマーケティングアクションの設定を確認し、**[!UICONTROL 保存]**&#x200B;をクリックします。

完全な設定手順については、[!DNL Experience Platform] ドキュメントの[新しい宛先接続の作成](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/connect-destination){target="_blank"}を参照してください。

設定すると、宛先はどこでもアクティブ化でき、[!DNL Journey Optimizer B2B Edition]で宛先を選択できます。

## アクティベーションと同期 {#activation-sync}

アクティベーションは、リストと宛先オーディエンス間の双方向同期を持つ静的なリストメンバーシップによって実行されます。

* 静的リストに人物を追加すると、24時間以内に宛先にアクティベートされ、宛先オーディエンスに追加され、その後、オーディエンスがフィードするキャンペーンに追加されます。
* 静的リストからユーザーを削除すると、そのユーザーは宛先から非アクティブになります。 宛先オーディエンスと、接続されているすべてのキャンペーンから削除されます。
* 同じリストを一度に複数の宛先にアクティベートできます。 メンバーシップはすべてに同期されます。

>[!TIP]
>
>セグメントに対してLinkedIn キャンペーンを実行するには、それらの人物の静的リストをLinkedIn Matched Audienceの宛先に対してアクティブ化します。 リスト内の全員がLinkedInでマッチングされたオーディエンスに追加されます。このオーディエンスは、キャンペーンでターゲティングでき、リストが変更されてもオーディエンスは自動的に最新の状態を維持します。
