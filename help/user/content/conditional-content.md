---
title: 条件付きコンテンツ
description: アカウントジャーニー用のメールコンテンツをオーサリングする際に、コンテンツのバリエーションを作成し、条件付きルールを適用する方法を説明します。
feature: Email Authoring, Content
exl-id: 7a789412-ea52-482f-8dc9-4a1599e85268
source-git-commit: bf57c152e758a757279f7666423f6a6ca61e1092
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 15%

---

# 条件付きコンテンツ

条件付きコンテンツを使用すると、条件付きルールに基づいてメールコンテンツを適応させることができます。 これらのルールは、プロファイル属性またはコンテキストイベントを使用して定義されます。 ルールビルダーで条件付きルールを作成し、アカウントジャーニーをまたいで再利用するのに保存できます。

Adobe Journey Optimizerでは、条件付きコンテンツをメールメッセージに追加するために、_条件_ ライブラリに保存されている条件付きルールを適用できます。 [ アカウントジャーニー用のメールコンテンツの作成 ](./email-authoring.md) の際に、メールデザインスペース内で条件付きルールを適用します。

## メールへの条件付きコンテンツの追加 {#email-content}

>[!CONTEXTUALHELP]
>id="ajo-b2b_conditional_content"
>title="条件付きコンテンツ"
>abstract="条件付きルールを使用すると、コンテンツコンポーネントのバリアントを複数作成できます。 メッセージの送信時にどの条件も満たされない場合は、デフォルトバリアントのコンテンツが表示されます。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_conditional_rule_select"
>title="条件付きコンテンツ"
>abstract="ライブラリに保存されている条件付きルールを使用するか、新しい条件付きルールを作成します。"

メールデザイン スペースでアカウントジャーニーのメールを作成する際には、条件付きルールを使用してコンテンツコンポーネントの複数のバリアントを定義します。

1. コンテンツコンポーネントを選択し、コンポーネントツールバーの **[!UICONTROL 条件付きコンテンツを有効にする]** アイコンをクリックします。

   このコンポーネントは、条件付きコンポーネントとしてアクティブであることを示すために、オレンジで囲まれます。 **[!UICONTROL 条件付きコンテンツ]** パネルが左側に表示され、_デフォルトバリアント_ と_バリアント - 1 が表示されます。

   ![ テキストコンポーネントの条件付きコンテンツを有効にする ](./assets/conditions-enable.png){width="700" zoomable="yes"}

   デフォルトは、選択してアクティベートした元のコンテンツで、定義したバリアントのいずれにも条件ルールが満たされない場合に適用されます。

   このパネルでは、条件付きルールを使用して、選択したコンテンツコンポーネントに複数のバリアントを定義できます。

1. 最初のバリアント（_バリアント - 1_）にポインタを合わせ、「_条件を選択_」アイコン（![ 条件アイコン ](../assets/do-not-localize/icon-select-condition.svg)）をクリックします。

   ![ バリアントの条件を選択 ](./assets/conditions-variant-select.png){width="700" zoomable="yes"}

   _[!UICONTROL 条件を選択]_ ダイアログが開き、条件ライブラリが表示されます。

   条件の詳細を表示して目的に合わせるには、_詳細メニュー_ アイコン（**...**）をクリックし、「**[!UICONTROL 情報を表示]**」を選択します。

   ![ 条件ライブラリアクセス条件の詳細 ](assets/conditions-select-dialog.png){width="600" zoomable="yes"}

   必要な条件が存在しない場合は、「新規作成 [ をクリックして ](#create-condition) 条件付きルールを作成 **[!UICONTROL します]**。

1. 条件付きルールを選択し、「**[!UICONTROL 選択]** をクリックして、バリアントに関連付けます。

   関連する条件を確認するには、バリアントの _その他メニュー_ アイコン（**...**）をクリックし、「**[!UICONTROL 条件を表示]**」を選択します。

   ![ バリアントに関連付けられた条件を表示 ](./assets/conditions-variant-view-condition.png){width="600" zoomable="yes"}

   右上の X をクリックして、ポップアップを閉じます。

   ![ 関連付けられた条件の詳細を表示 ](./assets/conditions-info-popup.png){width="500"}

1. 読みやすくするために、バリアントの _その他メニュー_ アイコン（**...**）をクリックし、「名前を変更 **[!UICONTROL を選択して、バリアントの名前を変更し]** す。

   バリアントとその目的を識別するのに役立つ、バリアントにわかりやすい名前を入力します。

   ![ バリアントの名前を変更 ](./assets/conditions-variant-rename.png){width="600" zoomable="yes"}

1. 左側のペインでバリアントを選択した状態で、条件が true の場合にメールメッセージに表示される方法を変更するように、コンポーネントを変更します。

   この例では、テキストコンポーネントのバリアントが、受信者の地域に基づいて異なる説明を使用しています。

   ![ バリアントのコンポーネントを変更 ](./assets/conditions-variant-component-edit.png){width="600" zoomable="yes"}

1. 必要に応じて、「**[!UICONTROL バリアントを追加]**」をクリックして別のバリアントを定義します。

   手順 2～5 を繰り返して、条件を選択し、バリアントの名前を変更し、バリアントのコンポーネントを変更します。

   コンテンツコンポーネントには、必要な数だけバリアントを追加できます。 左側のペインで選択したバリアントをいつでも変更して、条件に対するコンテンツコンポーネントの表示方法を確認できます。

   >[!IMPORTANT]
   >
   >条件付きコンテンツは、関連付けられているルールに照らして、バリアントのリスト順に評価されます。 コンポーネントには、true と評価される条件を持つ最初のバリアントが使用されます。
   >
   >定義されたバリアント条件のいずれもメールの送信時に true と評価されない場合、コンテンツコンポーネントは **[!UICONTROL デフォルトバリアント]** に従って表示されます。

1. バリアントを削除するには、バリアントの _その他メニュー_ アイコン（**...**）をクリックし、「**[!UICONTROL 削除]**」を選択します。

   確認ダイアログで **[!UICONTROL 削除]** をクリックします。

## 条件付きルール

条件付きルールは、true または false として評価できる一連の条件式です。 これらのルールを使用して、プロファイル属性やコンテキストイベントなどの様々なフィルターに基づいて、メールメッセージに表示するコンテンツバリアントを決定できます。

条件付きルールは、条件ライブラリに保存され、組織のジャーニーコンテンツ間で再利用できます。
<!-- 

>[!NOTE]
>
>You need the [Manage Library Items](../administration/ootb-product-profiles.md) permission to save or delete conditional rules. Saved conditions are available for use by all users within an organization. -->

### 条件フィルター {#condition-filters}

| 条件タイプ | フィルター | 説明 |
| -------------- | ------- | ----------- |
| **アカウント** | アカウント属性 | アカウントプロファイルからの属性。次のものが含まれます。 <li>年間売上高</li><li>市区町村</li><li>国</li><li>従業員数</li><li>業界</li><li>名前</li><li>SIC コード</li><li>State</li> |
| | [!UICONTROL &#x200B; 特殊フィルター &#x200B;] > [!UICONTROL &#x200B; 購入グループあり &#x200B;] | アカウントに購買グループのメンバーがいないか、メンバーがいません。 また、次の 1 つ以上の条件に照らして評価することもできます。 <li>ソリューションの関心</li><li>購買グループのステータス</li><li>完全性スコア</li><li>エンゲージメントスコア</li> |
| | [!UICONTROL &#x200B; 特別なフィルター &#x200B;] > [!UICONTROL &#x200B; 商談あり &#x200B;] | アカウントがオポチュニティに関連している、または関連していない。 次のオポチュニティ属性の 1 つ以上に対して評価することもできます。 <li>Amount<li>クローズ日<li>説明<li>予測収益<li>会計四半期<li>会計年度<li>予測カテゴリ<li>予測カテゴリ名<li>クローズ済み<li>獲得済み</li><li>最後のアクティビティの日付</li><li>顧客ソース<li>名前</li><li>次の手順</li><li>Probability<li>Quantity<li>Stage</li><li>タイプ |
| **人物** | [!UICONTROL &#x200B; アクティビティ履歴 &#x200B;] > [!UICONTROL &#x200B; メール &#x200B;] | ジャーニーに関連付けられたメールアクティビティ： <li>[!UICONTROL &#x200B; メール内のクリックされたリンク &#x200B;]</li><li>メール開封済み</li><li>メール配信済み</li><li>メールを送信済み</li> これらの条件は、ジャーニーの前半で選択したメールメッセージを使用して評価されます。 |
|  | [!UICONTROL &#x200B; 人物の属性 &#x200B;] | ユーザープロファイルからの属性。以下が含まれます。 <li>市区町村</li><li>国</li><li>生年月日</li><li>メールアドレス</li><li>メール無効</li><li>メール中断済み</li><li>名</li><li>推測される都道府県 / 地域</li><li>役職</li><li>姓</li><li>携帯電話番号</li><li>電話番号</li><li>郵便番号</li><li>ステート</li><li>登録解除</li><li>登録解除の理由</li> |
| | [!UICONTROL &#x200B; 特殊フィルター &#x200B;] > [!UICONTROL &#x200B; 購買グループのメンバー &#x200B;] | 次の 1 つ以上の条件に照らして評価された、その人物は購買グループ・メンバーであるか、そうでないメンバーである： <li>ソリューションの関心</li><li>購買グループのステータス</li><li>完全性スコア</li><li>エンゲージメントスコア</li><li>役割</li> |

<!-- 

| | [!UICONTROL Activity history] > [!UICONTROL Data Value Changed] | For a selected person attribute, a value change occurred. These change types include: <li>New value</li><li>Previous value</li><li>Reason</li><li>Source</li><li>Date of activity</li><li>Min. number of times</li> |
| | [!UICONTROL Activity history] > [!UICONTROL Had Interesting Moment] | Interesting moment activity that is defined in the associated Marketo Engage instance. Constraints include: <li>Milestone</li><li>Email</li><li>Web</li>|

| | [!UICONTROL Special filters] > [!UICONTROL Member of List] | The person is or is not a member of one or more Marketo Engage lists. |
| | [!UICONTROL Special filters] > [!UICONTROL Member of Program] | The person is or is not a member of one or more Marketo Engage programs. |
|  [People](#add-a-split-path-by-people-node) > [!UICONTROL Account-person attributes only] | Role in account attributes | The person is or is not assigned a role in the account. Optional constraints: <li>Enter a role name</li> | 
-->

### 条件付きルールの作成 {#create-condition}

>[!CONTEXTUALHELP]
>id="ajo-b2b_conditions_rule_editor"
>title="条件の作成"
>abstract="属性とコンテキストイベントを組み合わせて、メールメッセージに表示するコンテンツバリアントを決定するルールを作成します。"

コンポーネントバリアントの条件を選択する際に、メールデザインスペースから条件付きルールビルダーにアクセスできます。

1. _[!UICONTROL 条件の選択]_ ダイアログで、「**[!UICONTROL 新規作成]** をクリックして、条件タイプを選択します。

   * **[!UICONTROL 人物条件]** – このタイプを選択すると、人物属性とコンテキストイベントを使用して条件付きルールを作成できます。
   * **[!UICONTROL アカウント条件]** - アカウント属性を使用して条件付きルールを作成する場合に選択します。

   ![ 作成する条件タイプを選択 ](./assets/conditions-select-create-new.png){width="600" zoomable="yes"}

1. 必要に応じて、条件付きルールを作成します。

   ルールに含める属性またはイベントごとに、項目をルールキャンバスにドラッグ&amp;ドロップします。 フィルターを展開し、式を入力します。

   ![ 評価する式を入力 ](./assets/conditions-rule-add-attribute.png){width="600" zoomable="yes"}

   複数のフィルターを含める場合は、**[!UICONTROL フィルターロジック]** を設定します。

   * **[!UICONTROL すべてのフィルターを適用]** - ルールは、フィルターが true の場合 **all** と評価されます。
   * **[!UICONTROL 任意のフィルターを適用]** - ルールは、フィルターの **いずれか** が true の場合に true と評価されます。

1. 右側で、ルールの **[!UICONTROL 名前]** と **[!UICONTROL 説明]** （オプション）を入力します。

   別の重複条件を作成する代わりに再利用できるように、意味のある名前や、組織内の他のユーザーにとって役に立つ説明を使用します。

   ![ 条件付きルールの名前と説明を追加 ](./assets/conditions-rule-name-description.png){width="600" zoomable="yes"}

1. 条件付きルールが完成したら、「**[!UICONTROL 保存]**」をクリックします。

   条件付きルールがライブラリに保存され、現在のバリアントに対して選択できます。 また、アカウントジャーニーをまたいだ他の動的コンテンツのバリアントで使用するために、ライブラリにも含まれています。

### ルールの複製

ライブラリに保存された条件付きルールは変更できません。ただし、既存のルールを複製して変更し、新しいルールを作成することはできます。

1. バリアントの _その他メニュー_ アイコン（**...**）をクリックし、「複製 **[!UICONTROL を選択し]** す。

   ルールビルダーでルールの複製が開きます。 複製を、作成するルールの出発点として使用します。

   ![ 重複するルールを使用して、必要なルールを作成する ](./assets/conditions-rule-duplicate.png){width="600" zoomable="yes"}

1. ルールビルダーで、必要に応じて条件を変更、追加または削除します。

1. ルール内の目的または項目に一致するように、名前と説明を変更します。

1. 条件付きルールが完成したら、「**[!UICONTROL 保存]**」をクリックします。
