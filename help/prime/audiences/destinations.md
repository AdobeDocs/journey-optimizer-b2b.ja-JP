---
title: 宛先
description: 必要な権限、サポートされている宛先、Journey Optimizer B2B Primeの宛先を接続して、静的な人物リストを広告およびソーシャルプラットフォームにアクティベートする方法について説明します。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
autotag-review: '2026-06-17T18:30:02.442Z'
TQID: 'https://experienceleague.adobe.com/xO1p-VvIfv1KB77g0l2-fFRHQ0w2hy97vnG1QHpMw8c'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
  - id: beb5f4be-cec3-471a-9db6-831a77dd3ac9
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 7a954ba7ade748d5d51cae82a0cddb64449fa2a2
workflow-type: tm+mt
source-wordcount: 655
ht-degree: 9%

---

# 宛先

宛先は、[静的な人物リスト &#x200B;](./people-lists.md#static-lists)を[!DNL Journey Optimizer B2B Prime]から外部の広告またはソーシャルプラットフォーム（LinkedIn キャンペーンオーディエンス、Google Customer Match オーディエンス、Facebook カスタムオーディエンスなど）に送信できる事前定義済みの統合です。 宛先に静的リストをアクティベートすると、メンバーシップが同期されます。ユーザーがリストに追加されたりリストから削除されたりすると、それに応じて宛先オーディエンスに追加されたり、オーディエンスがフィードするキャンペーンから削除されたりします。

接続された宛先に対してユーザーをアクティブ化するには、次の2つの方法があります。

* **静的リストから** – 既存の静的リストを&#x200B;**_[!UICONTROL 人物リスト]_** タブから直接有効にします。 [宛先に対するアクティブ化](./people-lists.md#static-list-activate)を参照してください。
* **個人ジャーニー**&#x200B;から – **_[!UICONTROL 宛先にアクティベート]_** アクションをジャーニーパスに追加すると、そのノードに到達したユーザーがリストに追加され、宛先に送信されます。 [_アクションノードの追加_](../marketing/action-nodes.md#add-an-action-node)&#x200B;を参照してください。

>[!BEGINSHADEBOX]

## 必要な権限 {#required-permissions}

完全な宛先機能を有効にするには、次の[!DNL Adobe Experience Platform]権限が必要です。

| カテゴリ | 権限 | 必須 |
|--- |--- |--- |
| サンドボックス | サンドボックスアクセス _（デフォルトで有効）_ | はい |
| ダッシュボード | 標準ダッシュボードを表示 | はい |
| ダッシュボード | 標準ダッシュボードの管理 | はい |
| 宛先 | 宛先の表示 | はい |
| 宛先 | 宛先の管理 | はい |
| 宛先 | 宛先のアクティブ化 | はい |
| 宛先 | マッピングなしでセグメントをアクティブ化 | はい |
| 宛先 | データセット宛先の管理とアクティブ化 | はい |
| 宛先 | 宛先オーサリング | はい |
| データガバナンス | データ使用ポリシーの表示 | はい |
| データガバナンス | データ使用ポリシーの管理 | はい |
| データ取り込み | ソースの表示 | はい |
| データ取り込み | ソースの管理 | はい |
| プロファイル管理 | プロファイル設定の表示 | はい |
| プロファイル管理 | プロファイル設定の管理 | はい |

>[!ENDSHADEBOX]

## サポートされる宛先 {#supported-destinations}

静的リストをアクティブ化する前に、宛先カタログに宛先が存在する必要があります。 左側のナビゲーションで、**[!UICONTROL 接続]**&#x200B;を展開し、**[!UICONTROL 宛先]**&#x200B;を選択します。 [!DNL Journey Optimizer B2B Prime]は現在、次の宛先をサポートしています：

* **[!UICONTROL Google カスタマーマッチ]** （Advertising）
* **[!UICONTROL Facebook カスタムオーディエンス]** （ソーシャル）
* **[!UICONTROL LinkedIn Matched Audience]** （Social）

![使用可能なコネクタタイプにアクセス &#x200B;](./assets/destinations-catalog.png){width="800" zoomable="yes"}

>[!NOTE]
>
>このカタログは、完全な[!DNL Adobe Experience Platform]宛先カタログではありません。 [!DNL Experience Platform]から宛先に直接アクセスすると、大きなカタログが表示されますが、現在これらの宛先のみが[!DNL Journey Optimizer B2B Prime]でアクティブ化できます。 今後のリリースのために、さらに宛先を追加する予定です。

## 宛先の設定 {#set-up-destination}

サポートされている各宛先カードには、**[!UICONTROL 新しい宛先の設定]**&#x200B;が表示されます。 宛先を設定することは、アクティベーションの前提条件です。

1. コネクタカードで、**[!UICONTROL 新しい宛先の設定]**&#x200B;をクリックします。

1. **[!UICONTROL 既存のアカウント]**&#x200B;または&#x200B;**[!UICONTROL 新しいアカウント]**&#x200B;を選択し、アカウント名や説明などのアカウントの詳細を入力します。

   ![新しい宛先アカウントを接続](./assets/destinations-configure-new.png){width="500"}

1. 「**[!UICONTROL 宛先に接続]**」をクリックします。

   OAuth フローを使用すると、対応するアカウント（LinkedIn、Google、またはFacebook）にログインできます。

   >[!IMPORTANT]
   >
   >この時点で、**は&#x200B;_[!UICONTROL 宛先の詳細]_&#x200B;を入力しません**。 接続だけが必要です。

1. 人物の属性と宛先に必要なフィールドの間の必須フィールドマッピングを完了します。

1. データガバナンスとマーケティングアクションの設定を確認し、**[!UICONTROL 保存]**&#x200B;をクリックします。

完全な設定手順については、[!DNL Experience Platform] ドキュメントの[新しい宛先接続の作成](https://experienceleague.adobe.com/ja/docs/experience-platform/destinations/ui/connect-destination){target="_blank"}を参照してください。

設定すると、宛先はどこでもアクティブ化でき、[!DNL Journey Optimizer B2B Prime]で宛先を選択できます。

## アクティベーションと同期 {#activation-sync}

アクティベーションは、リストと宛先オーディエンス間の双方向同期を持つ静的なリストメンバーシップによって実行されます。

* 静的リストに人物を追加すると、24時間以内に宛先にアクティベートされ、宛先オーディエンスに追加され、その後、オーディエンスがフィードするキャンペーンに追加されます。
* 静的リストからユーザーを削除すると、そのユーザーは宛先から無効になります。そのユーザーは、宛先オーディエンスおよび接続されているキャンペーンから削除されます。
* 同じリストを一度に複数の宛先にアクティベートできます。メンバーシップは、それらすべてに同期されます。

>[!TIP]
>
>セグメントに対してLinkedIn キャンペーンを実行するには、それらの人物の静的リストをLinkedIn Matched Audienceの宛先に対してアクティブ化します。 リスト内の全員がLinkedInでマッチングされたオーディエンスに追加されます。このオーディエンスは、キャンペーンでターゲティングでき、リストが変更されてもオーディエンスは自動的に最新の状態を維持します。
