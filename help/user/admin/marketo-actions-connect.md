---
title: ジャーニー操作をサポートするMarketo Engageのアクティブ化
description: Marketo Engage Connections をアクティブ化して、ジャーニーアクションをサポートし、マーケターがMarketo EngageとJourney Optimizer B2B editionの間でキャンペーンを調整できるようにします。
feature: Integrations, Audiences, Buying Groups
role: User, Admin
source-git-commit: de7f5620556a48fe6f12ed1c70e925e11ec770f1
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 2%

---


# アクションをサポートするMarketo Engage インスタンスのアクティブ化

Marketo Engage アクションは _人物ベース_ のアクションであり、Journey Optimizer B2B editionとMarketo Engageの _リードベース_ マーケティング活動の間で _アカウントベース_ のマーケティングオーケストレーションを調整できます。 これらのアクションを使用して、静的なリストメンバーシップを調整し、キャンペーンにユーザーを配置します。

Marketo Engageのアクションを使用するには、管理者はまず、認証に必要な資格情報を提供する [&#x200B; カスタムサービス &#x200B;](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#) をMarketo Engageで作成します。
次に、Journey Optimizer B2B editionの製品管理者が、資格情報を入力してMarketo Engageへの接続を作成します。
その後、Journey Optimizer B2B edition ユーザーは接続を参照して、Marketo Engage リストへのユーザーの追加や削除、リクエストキャンペーンへの追加など、<!-- Person and --> アカウントジャーニーでMarketo Engage アクションを設定できます。

リストやキャンペーンなどのアセットのMarketo Engage ワークスペースの表示は、カスタムサービスで割り当てられるロール権限によって制御されます。

同じ接続を 1 つのジャーニー内で複数回使用でき、1 つのジャーニーに異なるMarketo Engage接続を共存させることができます。

アクションを実行すると、選択ポリシーを使用して、Marketo Engageのどの人物レコードを特定し、統合された人物プロファイルに複数の識別子が存在するかどうかを選択します。 Marketo Engageの最も古いレコード、新しいレコード、一致するすべてのレコードから選択することもできます。 ユーザーは、一致するエラーが発生した場合を除き、ジャーニーを進めます。

## Marketo Engage接続の設定

Marketo Engage ジャーニーアクションで使用するリモート Marketo Engage インスタンスを設定します。

### Marketo Engage カスタムサービスの作成

1. Marketo Engageに管理者としてログインし、カスタムサービスを作成します。
1. 接続に使用する次の値を記録します。

   * Munchkin ID
   * クライアント ID
   * クライアント秘密鍵

### 統合の追加

![&#x200B; 統合の詳細を追加 &#x200B;](assets/integration-connection-details.png)

1. Journey Optimizer B2B editionで、**管理**/**設定** に移動します。
1. 「**統合**」タブを選択します。
1. **[!UICONTROL 接続を作成]** をクリックします。
1. 名前（必須）と説明（オプション）を入力します。
1. 一致する人物レコードの **選択ポリシー** を選択します。
1. Munchkin ID、クライアント ID およびクライアント秘密鍵を入力します。
1. **[!UICONTROL Marketoに接続]** をクリックします。
1. 「**[!UICONTROL 作成]**」をクリックします。

マーケターがジャーニーでMarketo Engage アクションを使用する場合、接続名を使用してノードを設定できます。

完了した統合により、Marketo Engageのアクションは、ノードのプロパティの **アクション on:** から使用できます。

![Marketo アクションリスト &#x200B;](assets/marketo-actions-list.png)