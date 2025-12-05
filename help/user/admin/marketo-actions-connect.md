---
title: ジャーニー操作をサポートするMarketo Engageのアクティブ化
description: Marketo Engage Connections をアクティブ化して、ジャーニーアクションをサポートし、マーケターがMarketo EngageとJourney Optimizer B2B editionの間でキャンペーンを調整できるようにします。
feature: Integrations, Audiences, Buying Groups
role: User, Admin
source-git-commit: 9b77570ddb9b416251f38db51a57507a935a526a
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 1%

---


# アクションをサポートするMarketo Engage インスタンスのアクティブ化

Marketo Engage アクションは _人物ベース_ のアクションであり、Journey Optimizer B2B editionとMarketo Engageの _リードベース_ マーケティング活動の間で _アカウントベース_ のマーケティングオーケストレーションを調整できます。 これらのアクションを使用して、静的なリストメンバーシップを調整し、キャンペーンにユーザーを配置します。

Marketo Engageのジャーニーアクションを使用するには、管理者はまず、認証に必要な資格情報を提供する [&#x200B; カスタムサービス &#x200B;](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services){target="_blank"} をMarketo Engageで作成します。 次に、Journey Optimizer B2B editionの製品管理者は、資格情報を使用してMarketo Engageへの接続を作成します。 その後、Journey Optimizer B2B edition ユーザーは接続を参照して、Marketo Engage リストへのユーザーの追加や削除、リクエストキャンペーンへの追加など、<!-- person and --> アカウントジャーニーでMarketo Engage アクションを設定できます。

## Marketo Engage接続の設定 {#external-marketo-configure}

>[!CONTEXTUALHELP]
>id="ajo-b2b_marketo-configure-connections"
>title="外部Marketo Engage接続"
>abstract="製品管理者は、外部Marketo Engage インスタンスへの接続を設定して、ジャーニーアクションで使用できるようにします。"

ジャーニーアクションで使用する外部Marketo Engage インスタンスを設定するには、次のタスクを実行します。

### Marketo Engage カスタムサービスの作成

1. Marketo Engageに管理者としてログインし、「カスタムサービスを作成 [&#x200B; し &#x200B;](https://experienceleague.adobe.com/ja/docs/marketo/using/product-docs/administration/additional-integrations/create-a-custom-service-for-use-with-rest-api){target="_blank"} す。
1. Journey Optimizer B2B edition接続に使用する値を以下のようにコピーします。

   * Munchkin ID
   * クライアント ID
   * クライアント秘密鍵

リストやキャンペーンなどのアセットのMarketo Engage Workspace の表示は、[&#x200B; カスタムサービスで割り当てられるロール権限 &#x200B;](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#permission-list){target="_blank"} によって制御されます。 マーケターは、1 つのジャーニー内で同じ接続を複数回使用し、同じジャーニー内で異なるMarketo Engage接続を使用できます。

### 統合の追加

![&#x200B; 統合の詳細を追加 &#x200B;](assets/integration-connection-details.png){width="800" zoomable="yes"}

1. Journey Optimizer B2B editionで、**[!UICONTROL 管理]**/**[!UICONTROL 設定]** に移動します。
1. 「**[!UICONTROL 統合]**」タブを選択します。
1. **[!UICONTROL 接続を作成]** をクリックします。
1. **[!UICONTROL 名前]** （必須）と **[!UICONTROL 説明]** （オプション）を入力します。
1. 一致する人物レコードにアクションを適用するために使用される更新ポリシーを選択します。

   接続されたMarketo Engage インスタンスに対してアクションが実行されると、選択された _更新ポリシー_ によって、Marketo Engageの人物レコードが決定され、統合された人物プロファイルに複数の識別子が存在するかどうかが選択されます。

   * **[!UICONTROL 一致するすべてのレコードを更新]**
   * **[!UICONTROL 最も古い一致するレコードのみを更新]**
   * **[!UICONTROL 最新の一致するレコードのみを更新]**

   >[!NOTE]
   >
   >ユーザーは、一致するエラーが発生した場合を除き、ジャーニーを進めます。

1. 外部Marketo Engage インスタンスで作成したサービスのMunchkin ID、クライアント ID およびクライアント秘密鍵を入力します。
1. **[!UICONTROL Marketoに接続]** をクリックします。
1. 「**[!UICONTROL 作成]**」をクリックします。

## ジャーニーアクションでの接続の使用

マーケターがジャーニーでMarketo Engage アクションを使用する場合、接続名を使用してノードを設定できます。

完了した統合により、Marketo Engageのアクションは、ノードのプロパティの **アクション on:** から使用できます。

![Marketo アクションリスト &#x200B;](assets/marketo-actions-list.png){width="800" zoomable="yes"}