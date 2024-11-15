---
title: ユーザ管理
description: チームメンバーをJourney Optimizer B2B edition製品プロファイルに割り当てる方法について説明します。
feature: Setup
roles: Admin
exl-id: ddbdc6a5-49bc-46cd-8d9b-1d37223dffe2
source-git-commit: 97a9932a8a2a1c7a37dcc110b59cee70a61b5763
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 4%

---

# ユーザー管理

プロビジョニングが完了し、サンドボックスがバインドされたら、次の手順を実行して、チームとユーザーにAdobe Journey Optimizer B2B editionへのアクセスを提供します。

1. Admin Consoleで [Marketo Engage製品プロファイルを作成 ](#marketo-engage-profile) （新しいMarketo Engageインスタンスのみ）。
1. Admin Consoleで [ ユーザーグループを作成 ](#create-user-group) します。
1. AEP 権限の [ 役割を作成 ](#create-role) します。
1. Admin Consoleの [ ユーザーを追加 ](#add-users) します。

管理者は、Adobe Admin Consoleでこれらのタスクを実行できます。この場所では、Adobeの製品ライセンスとユーザーを一元的に管理および管理できます。 Admin Consoleでは、様々な個別のソリューション内ではなく、1 か所でユーザーを作成および管理できます。 関数と機能について詳しくは、[Admin Consoleの概要 ](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) ページを参照してください。

## Admin Console へのアクセス

Admin Consoleを使用してチーム内のユーザーを管理する前に、Admin Consoleにアクセスし、適切な権限を持っていることを確認する必要があります。

1. システム管理者は、オンボーディングプロセスの一環としてAdobeから複数のメールを受け取る必要があります。

   アクセス権が付与された組織名に関する情報を記載したお知らせメールを探します。

1. お知らせメールの **[!UICONTROL 使用を開始]** リンクをクリックして、Admin Consoleに移動します。

   メールが見つからない場合は、ブラウザーを開いてAdmin Console（[https://adminconsole.adobe.com](https://adminconsole.adobe.com)）に直接アクセスします。

1. Adobe IDを使用してログインします。

   ログインに成功すると、Adobe Admin Consoleの _概要_ ページが表示されます。

1. 複数の組織にアクセスできる場合は、正しい組織にログインしていることを確認します。

   組織を変更するには、右上隅の組織名をクリックし、アクセスが必要な組織を選択します。

1. **[!UICONTROL ユーザー]** カードから _[!UICONTROL 管理者]_ を選択して、自分がシステム管理者であることを確認します。

   ![Admin Consoleの概要 – [ 管理者 ] をクリックしてください ](./assets/admin-console-overview-administrators.png){width="700" zoomable="yes"}

1. Adobe IDのメールアドレス、ユーザー名、名、姓を入力して検索します。

   * アクセス権が正しく設定されている場合、検索はレコードを返します。

   * **[!UICONTROL 管理者の役割]** 列の値に `System` が表示されている場合、自分（または表示されているユーザー）がシステム管理者であることがわかります。

## Marketo Engage製品プロファイルの作成 {#marketo-engage-profile}

Adobeソリューションに対するアクセス権をユーザーに付与する場合、必ずしも完全なアクセス権を付与する必要はありません。 製品プロファイルを使用すると、ソリューションごとに独自のユーザー権限を設定できます。 Admin Consoleを使用して、製品プロファイルを割り当てます。

ユーザーの使用権限に製品プロファイルを使用する方法について詳しくは、製品ドキュメントの [ エンタープライズユーザーのAdmin Consoleプロファイルの管理 ](https://helpx.adobe.com/jp/enterprise/using/manage-product-profiles.html){target="_blank"} を参照してください。
<!--
>[!BEGINSHADEBOX]

When you add a user to the Marketo Engage product profile, they are subsequently added to the _Standard User_ role within the Default workspace of the Marketo Engage subscription. This role grants them all _Standard User_ permissions for Marketo Engage in that workspace. Currently, all Journey Optimizer B2B Edition users are required to be Marketo Engage users. A Marketo Engage administrator can restrict access by updating the permissions for the _Standard User_ role or by moving the user to a different Marketo Engage user role with more restrictive permissions.

For more information about managing these permissions within Marketo Engage, see [Managing User Roles and Permissions](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/users-and-roles/managing-user-roles-and-permissions){target="_blank"} in the Marketo Engage documentation.

>[!ENDSHADEBOX]-->

>[!NOTE]
>
>これらの手順は、Admin Consoleシステム管理者またはMarketo Engageプロダクト管理者が実行できます。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) にログインします。

1. 「**[!UICONTROL 製品]**」タブを選択します。

1. プロファイルを追加する Market Engage インスタンスを開き、「新規プロファイル」をクリックします。

   ![Admin Console- Marketo Engageインスタンス – 新しいプロファイル ](./assets/admin-console-marketo-engage-instance-new-profile.png){width="700" zoomable="yes"}

1. 「_標準ユーザー_」などの製品プロファイル名を入力します。

1. **次へ** をクリックしてから **保存** をクリックします。

## ユーザーグループの作成 {#create-user-group}

ユーザーグループは、一連の共有権限が付与されるユーザーの集まりです。 ユーザーグループのユーザーを追加または削除できます。 グループの権限は、グループ内のユーザーが変更されても、同じままです。

ユーザーグループを使用して権限を管理する方法について詳しくは、Admin Consoleドキュメントの [ ユーザーグループの管理 ](https://helpx.adobe.com/jp/enterprise/using/user-groups.html){target="_blank"} を参照してください。

>[!NOTE]
>
>Admin Consoleシステム管理者は、これらの手順を実行できます。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) にログインします。

1. 「**[!UICONTROL ユーザー]**」タブを選択します。

1. 左側のナビゲーションで **[!UICONTROL ユーザーグループ]** を選択します。

1. 右上で **[!UICONTROL 新規ユーザーグループ]** をクリックします。

1. _標準ユーザー_ のようにユーザーグループの名前を入力し、「**[!UICONTROL 保存]**」をクリックします。

1. 作成したユーザーグループをクリックします。

1. 「**[!UICONTROL 割り当てられた製品プロファイル]**」タブを選択し、「**[!UICONTROL プロファイルを割り当て]**」をクリックします。

1. 「**+**」をクリックして、次の製品の各インスタンスを追加します。

   * [!UICONTROL Marketo Engage]
   * [!UICONTROL Adobe Experience Platform - AEP-Default-All-Users]
   * [!UICONTROL Adobe Experience Platform のデータ収集]
   * [!UICONTROL  データ収集のすべてのアクセス ]

   ![Admin Console- ユーザーグループ – 商品を追加 ](./assets/admin-console-user-group-add-products.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。

## AEP 権限での役割の作成 {#create-role}

権限は、製品プロファイルに割り当てる許可を定義できる単一の権利です。 各権限は、Journey Optimizer B2B editionのさまざまな機能やオブジェクトに相当する、ジャーニーや購入グループなどの機能の下に収集されます。

Adobe Experience Platformの _権限_ 領域では、管理者は、ユーザーの役割とアクセスポリシーを定義して、製品アプリケーション内の機能とオブジェクトのアクセス権限を管理できます。 このアプリでは、役割を作成および管理すると共に、それらの役割に対して必要なリソース権限を割り当てることができます。 また、権限では、特定の役割に関連付けられたラベル、サンドボックス、ユーザーを管理することもできます。

詳しくは、Experience Platformドキュメントの [ 役割の権限の管理 ](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions){target="_blank"} を参照してください。

>[!NOTE]
>
>次の手順を実行するには、Adobe Experience Platformの製品管理者である必要があります。

1. [experience.adobe.com](https://experience.adobe.com/) に移動します。

1. _[!UICONTROL クイックアクセス]_ パネルで、「**[!UICONTROL 権限]**」を選択します。

   >[!NOTE]
   >
   >_[!UICONTROL 権限]_ が表示されない場合は、「**[!UICONTROL すべて表示]**」をクリックし、使用可能なアプリケーションから選択する必要がある場合があります。

   ![Experience Platform- アクセス許可 ](./assets/aep-permissions.png){width="700" zoomable="yes"}

1. 左側のナビゲーションで「**[!UICONTROL 役割]**」を選択し、「**[!UICONTROL 役割を作成]**」を選択します。

1. _[!UICONTROL 新しい役割を作成]_ ダイアログで、「_AJO B2B_」などの役割の名前と説明（オプション）を入力します。

1. 「**[!UICONTROL 確認]**」をクリックします。

1. サンドボックスを選択します

   ![Experience Platform – 新しい役割用のサンドボックスを追加します ](./assets/aep-permissions-role-sandboxes.png){width="700" zoomable="yes"}

1. プロファイル権限を追加します。

   * 左側の _[!UICONTROL リソース]_ リストで「**[!UICONTROL プロファイル管理]**」項目を見つけ、プラス（**+**）アイコンをクリックして属性を追加します。

   * 属性に次の権限を追加します。
      * [!UICONTROL  セグメントの表示 ]
      * [!UICONTROL  セグメントの管理 ]
      * [!UICONTROL  プロファイルの表示 ]
      * [!UICONTROL  プロファイルの管理 ]
      * [!UICONTROL B2B プロファイルの表示 ]
      * [!UICONTROL B2B プロファイルの管理 ]

   ![Experience Platform – 新しい役割のプロファイルを追加します ](./assets/aep-permissions-role-profiles.png){width="700" zoomable="yes"}

1. 右上の **[!UICONTROL 保存]** をクリックします。

1. 役割の詳細に移動し、「**[!UICONTROL ユーザーグループ]**」タブを選択します。

1. **[!UICONTROL グループを追加]** をクリックします。

   ![Experience Platform – 新しい役割のプロファイルを追加します ](./assets/aep-permissions-role-add-groups.png){width="700" zoomable="yes"}

1. Admin Consoleで前に作成したユーザーグループの横にあるチェックボックスをオンにします。

1. 「**[!UICONTROL 保存]**」をクリックします。

## ユーザーをAdmin Consoleのグループに追加します

>[!NOTE]
>
>これらの手順は、Admin Consoleシステム管理者またはプロダクト管理者が実行できます。

User Management について詳しくは、Admin Consoleドキュメントの [Admin Consoleユーザー ](https://helpx.adobe.com/jp/enterprise/using/user-groups.html) を参照してください。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) に移動します。

1. _[!UICONTROL クイック リンク]_ の下の [**[!UICONTROL ユーザーの追加]**] をクリックします。

1. 各ユーザーを追加します。

   * ユーザーのメールアドレス、名、姓を入力します。

     ![Experience Platform – 新しい役割のプロファイルを追加します ](./assets/admin-console-add-users.png){width="600" zoomable="yes"}

   * **[!UICONTROL ユーザーグループ]** の場合は、「**+**」をクリックします。

   * 前に作成したユーザーグループを選択します。

   * 「**[!UICONTROL 適用]**」をクリックします。

1. 「**[!UICONTROL 保存]**」をクリックします。
