---
title: ユーザ管理
description: チームメンバーをJourney Optimizer B2B edition製品プロファイルに割り当てる方法について説明します。
feature: Setup
roles: Admin
exl-id: ddbdc6a5-49bc-46cd-8d9b-1d37223dffe2
source-git-commit: d5197e740a17de507bf72b4d7b64deb5af672346
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 2%

---

# ユーザー管理

プロビジョニングが完了し、サンドボックスがバインドされたら、次の手順を実行して、チームとユーザーにAdobe Journey Optimizer B2B editionへのアクセスを提供します。

1. Admin Consoleで [Marketo Engage製品プロファイルを作成 ](#marketo-engage-profile) （新しいMarketo Engage インスタンスのみ）。
1. Admin Consoleで [ ユーザーグループを作成 ](#create-user-group) します。
1. Journey Optimizer B2B editionの権限を使用して、[ 組み込みの役割を編集 ](#edit-roles) または [ カスタムの役割を作成 ](#create-a-custom-role) します。
1. 役割への [ ユーザー ](#add-users) または [ グループ ](#add-user-groups-to-a-role) の追加

管理者は、Adobeの製品ライセンスとユーザーを一元的に管理する場所であるAdobe Admin Consoleで、これらのタスクを実行できます。 Admin Consoleでは、様々な個別のソリューション内ではなく、1 か所でユーザーを作成および管理できます。 機能と性能について詳しくは、[Admin Consoleの概要 ](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) を参照してください。

## Admin Console へのアクセス

Admin Consoleを使用してチーム内のユーザーを管理する前に、Admin Consoleにアクセスでき、適切な権限を持っていることを確認する必要があります。

1. システム管理者は、オンボーディングプロセスの一環としてAdobeから複数のメールを受信する必要があります。

   アクセス権が付与された組織名に関する情報を記載したお知らせメールを探します。

1. お知らせメールの **[!UICONTROL 使用を開始]** リンクをクリックして、Admin Consoleに移動します。

   メールが見つからない場合は、ブラウザーを開いてAdmin Console（[https://adminconsole.adobe.com](https://adminconsole.adobe.com)）に直接アクセスします。

1. Adobe IDを使用してログインします。

   ログインに成功すると、Adobe Admin Consoleの _概要_ ページが表示されます。

1. 複数の組織にアクセスできる場合は、正しい組織にログインしていることを確認します。

   組織を変更するには、右上隅の組織名をクリックし、アクセスが必要な組織を選択します。

1. **[!UICONTROL ユーザー]** カードから _[!UICONTROL 管理者]_ を選択して、自分がシステム管理者であることを確認します。

   ![Admin Consoleの概要 – 「管理者」をクリック ](./assets/admin-console-overview-administrators.png){width="700" zoomable="yes"}

1. Adobe IDのメールアドレス、ユーザー名、名、姓を入力して検索します。

   * アクセス権が正しく設定されている場合、検索はレコードを返します。

   * **[!UICONTROL 管理者の役割]** 列の値に `System` が表示されている場合、自分（または表示されているユーザー）がシステム管理者であることがわかります。

## Marketo Engage製品プロファイルの作成 {#marketo-engage-profile}

Adobe ソリューションに対するアクセス権をユーザーに付与する場合、必ずしも完全なアクセス権を付与する必要はありません。 製品プロファイルを使用すると、ソリューションごとに独自のユーザー権限を設定できます。 Admin Consoleを使用して製品プロファイルを割り当てます。

ユーザーの使用権限に製品プロファイルを使用する方法について詳しくは、Admin Console ドキュメントの [ エンタープライズユーザーの製品プロファイルの管理 ](https://helpx.adobe.com/jp/enterprise/using/manage-product-profiles.html){target="_blank"} を参照してください。
<!--
>[!BEGINSHADEBOX]

When you add a user to the Marketo Engage product profile, they are subsequently added to the _Standard User_ role within the Default workspace of the Marketo Engage subscription. This role grants them all _Standard User_ permissions for Marketo Engage in that workspace. Currently, all Journey Optimizer B2B Edition users are required to be Marketo Engage users. A Marketo Engage administrator can restrict access by updating the permissions for the _Standard User_ role or by moving the user to a different Marketo Engage user role with more restrictive permissions.

For more information about managing these permissions within Marketo Engage, see [Managing User Roles and Permissions](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/users-and-roles/managing-user-roles-and-permissions){target="_blank"} in the Marketo Engage documentation.

>[!ENDSHADEBOX]-->

![ 管理者の役割の要件 ](../../assets/do-not-localize/icon-admin-user.svg){width="30"} システム管理者またはMarketo Engageの製品管理者は、次の手順を実行できます。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) にログインします。

1. 「**[!UICONTROL 製品]**」タブを選択します。

1. プロファイルを追加するMarketo Engage インスタンスを開き、「**[!UICONTROL 新規プロファイル]**」をクリックします。

   ![Admin Console - Marketo Engage インスタンス – 新規プロファイル ](./assets/admin-console-marketo-engage-instance-new-profile.png){width="700" zoomable="yes"}

1. 「_標準ユーザー_」などの製品プロファイル名を入力します。

1. **次へ** をクリックしてから **保存** をクリックします。

## ユーザーグループの作成 {#create-user-group}

ユーザーグループは、一連の共有権限が付与されるユーザーの集まりです。 ユーザーグループのユーザーを追加または削除できます。 グループの権限は、グループ内のユーザーが変更されても、同じままです。

ユーザーグループを使用して権限を管理する方法について詳しくは、Admin Console ドキュメントの [ ユーザーグループの管理 ](https://helpx.adobe.com/jp/enterprise/using/user-groups.html){target="_blank"} を参照してください。

![ 管理者の役割の要件 ](../../assets/do-not-localize/icon-admin-user.svg){width="30"} システム管理者は、次の手順を実行できます。

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

   ![Admin Console - ユーザーグループ – 商品を追加 ](./assets/admin-console-user-group-add-products.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。

## グループへのユーザーの追加

User Management について詳しくは、Admin Console ドキュメントの [Admin Console ユーザー ](https://helpx.adobe.com/jp/enterprise/using/user-groups.html) を参照してください。

![ 管理者の役割の要件 ](../../assets/do-not-localize/icon-admin-user.svg){width="30"} システム管理者または製品管理者は、次の手順を実行できます。 製品管理者は、組織に既に存在するユーザーのみを追加できます。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) に移動します。

1. _[!UICONTROL クイック リンク]_ の下の [**[!UICONTROL ユーザーの追加]**] をクリックします。

1. 各ユーザーを追加します。

   * ユーザーのメールアドレス、名、姓を入力します。

     ![Experience Platform – 新しい役割のプロファイルを追加 ](./assets/admin-console-add-users.png){width="600" zoomable="yes"}

   * **[!UICONTROL ユーザーグループ]** の場合は、「**+**」をクリックします。

   * 前に作成したユーザーグループを選択します。

   * 「**[!UICONTROL 適用]**」をクリックします。

1. 「**[!UICONTROL 保存]**」をクリックします。

## 製品権限の役割の編集 {#edit-roles}

権限は、製品プロファイルに割り当てる許可を定義できる単一の権利です。 各権限は、Journey Optimizer B2B editionのさまざまな機能やオブジェクトに相当する、ジャーニーや購入グループなどの機能の下に収集されます。

Adobe Experience Platformの _権限_ 領域では、管理者は、ユーザーの役割とアクセスポリシーを定義して、製品アプリケーション内の機能とオブジェクトのアクセス権限を管理できます。 このアプリでは、役割を作成および管理すると共に、それらの役割に対して必要なリソース権限を割り当てることができます。 また、権限では、特定の役割に関連付けられたサンドボックスとユーザーを管理することもできます。

Experience Platformのロール権限について詳しくは、Experience Platform ドキュメントの [ ロールの権限の管理 ](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/abac/permissions-ui/permissions){target="_blank"} を参照してください。
<!-- 
### B2B product permissions

The following permissions govern access to Journey Optimizer B2B Edition capabilities:

| Category | Description | Permissions |
| -------- | ----------- | ---------- |
| B2B Account Lists | Configure, manage, view, and publish permissions for B2B account lists. These permissions include actions such as add, remove, import, and delete accounts from account lists. | <li>Manage B2B Account Lists |
| B2B Admin Configurations | Configure, manage, and view permissions for B2B administrative configurations. These permissions include digital asset management connections, asset repositories, and events. | <li>Manage B2B Admin Configurations |
| B2B Assets | Configure, manage, and view permissions for B2B assets. These permissions include emails, SMS, landing pages, fragments, templates, and images. | <li>Manage B2B Assets <li>Manage B2B Templates <li>Manage B2B Fragments|
| B2B Buying Groups | Configure, manage, and view permissions for B2B buying groups. These permissions include solution interests, roles templates, and buying group status. | <li>Manage B2B Buying Groups |
| B2B Channel Configurations | Configure, manage, and view permissions for B2B channel configurations. These permissions include settings for communication limits, API credentials, and security settings. | <li>Manage B2B Channels Configurations |
| B2B Dashboards |Configure and view permissions for B2B dashboards. These permissions include account engagement, buying group stages, surging accounts, and contact coverage. | <li>Manage B2B Dashboards |
| B2B Journeys | Configure manage, view, and publish permissions for B2B journeys. These permissions include account and person actions, event listeners, and split paths | <li>Manage B2B Journeys |

### B2B built-in roles

When your organization has the Journey Optimizer B2B Edition product provisioned, Experience Platform includes a set of built-in (default) roles that you can use to manage access to the product capabilities:

| Role | Permissions |
| ---- | ----------- |
| B2B Journey Manager | <li>Manage B2B Journeys <li>Manage B2B Buying Groups <li>Manage B2B Account Lists <li>View B2B Intelligent Dashboard <li>View B2B Insights Dashboard |
| B2B Channel Manager | <li>Manage B2B Assets <li>Manage B2B Templates <li>Manage B2B Fragments |
| B2B System Administrator | <li>Manage B2B Channels Configurations <li>Manage B2B Admin Configurations |
| B2B Sales User | <li>View Intelligent Dashboard |

### Edit role permissions

For built-in or custom roles, you can decide at any time to add or delete permissions. If you modify a default or custom role, it impacts every user assigned to the role.

In the following example, you want to add permissions related to the B2B Journeys resource for users assigned to the B2B Channel Manager role. This change enables users for that role to manage account journeys also.

>[!NOTE]
>
>An Admin Console system administrator can perform these steps.

_To change the permissions for a role:_

1. Go to [experience.adobe.com](https://experience.adobe.com/).

1. In the _[!UICONTROL Quick access]_ panel, select **[!UICONTROL Permissions]**.

   >[!NOTE]
   >
   >If you don't see _[!UICONTROL Permissions]_, you may need to click **[!UICONTROL View all]** and select it from the available applications.

   ![Experience Platform - access Permissions](./assets/aep-permissions.png){width="700" zoomable="yes"}

1. Select **[!UICONTROL Roles]** in the left navigation.

1. Click the **_B2B Channel Manager_** role name.

1. In the details page, click **[!UICONTROL Edit]** at the top right.

   ![Experience Platform - edit the role](./assets/aep-permissions-role-edit.png){width="700" zoomable="yes"}

   In the role editor, the _[!UICONTROL Resources]_ menu displays the list of resources that apply to the Experience Cloud - Platform powered applications products.

   You can enter _B2B_ in the search tool to filter the list for the B2B product permissions. 
   
1. Click the _Add_ icon (**+**) for the B2B Journeys resource.

   ![Experience Platform - edit the role](./assets/aep-permissions-role-edit-b2b-journeys-add.png){width="700" zoomable="yes"}

1. In the _[!UICONTROL B2B Journeys]_ permissions card, select **[!UICONTROL Manage B2B Account Journeys]**.

1. Click **[!UICONTROL Save]**.

   ![Experience Platform - edit the role](./assets/aep-permissions-role-edit-b2b-journeys-done.png){width="700" zoomable="yes"}

1. Click **[!UICONTROL Close]** to return to the details page. -->

### 役割にユーザーを追加

![ 管理者の役割要件 ](../../assets/do-not-localize/icon-admin-user.svg){width="30"} システム管理者または AEP 製品管理者は、次の手順を実行できます。

1. 役割の詳細を開き、「**[!UICONTROL ユーザー]**」タブを選択します。

   このタブには、役割に割り当てられたすべてのユーザーのリストが表示されます。

1. **[!UICONTROL ユーザーを追加]** をクリックします。

   ![Experience Platform - ロールにユーザーを追加 ](./assets/aep-permissions-role-add-users.png){width="700" zoomable="yes"}

1. _[!UICONTROL ユーザーを追加]_ ダイアログで、役割に追加するユーザーを見つけて選択します。

   * 検索ツールを使用して、ユーザーのリストをフィルタリングできます。

   * 各ユーザーのチェックボックスを選択します。

   ![Experience Platform - ユーザーを追加ダイアログ ](./assets/aep-permissions-role-add-users-dialog.png){width="600" zoomable="yes"}

1. 追加するすべてのユーザーを選択したら、「**[!UICONTROL 保存]**」をクリックします。

### 役割へのユーザーグループの追加

User Management について詳しくは、Admin Console ドキュメントの [Admin Console ユーザー ](https://helpx.adobe.com/jp/enterprise/using/user-groups.html) を参照してください。

![ 管理者の役割要件 ](../../assets/do-not-localize/icon-admin-user.svg){width="30"} システム管理者または AEP 製品管理者は、次の手順を実行できます。

1. 役割の詳細を開き、「**[!UICONTROL ユーザーグループ]**」タブを選択します。

   このタブには、役割に割り当てられたすべてのユーザーグループのリストが表示されます。

1. **[!UICONTROL グループを追加]** をクリックします。

   ![Experience Platform - ロールにユーザーを追加 ](./assets/aep-permissions-role-add-groups.png){width="700" zoomable="yes"}

1. _[!UICONTROL グループを追加]_ ダイアログで、役割に追加するグループを見つけて選択します。

   * 検索ツールを使用して、ユーザーグループのリストをフィルタリングできます。

   * 各ユーザーグループのチェックボックスを選択します。

   ![Experience Platform - グループを追加ダイアログ ](./assets/aep-permissions-role-add-groups-dialog.png){width="600" zoomable="yes"}

1. 追加するすべてのユーザーを選択したら、「**[!UICONTROL 保存]**」をクリックします。

## カスタムの役割の作成

![ 管理者の役割要件 ](../../assets/do-not-localize/icon-admin-user.svg){width="30"} システム管理者または AEP 製品管理者は、次の手順を実行できます。

1. 左側のナビゲーションで「**[!UICONTROL 役割]**」を選択し、「**[!UICONTROL 役割を作成]**」を選択します。

1. _[!UICONTROL 新しい役割の作成]_ ダイアログで、「_B2B マーケター_」などの役割の名前と説明（オプション）を入力します。

1. 「**[!UICONTROL 確認]**」をクリックします。

1. サンドボックスを選択します

   ![Experience Platform – 新しい役割用のサンドボックスを追加する ](./assets/aep-permissions-role-sandboxes.png){width="700" zoomable="yes"}

1. プロファイル権限を追加します。

   * 左側の _[!UICONTROL リソース]_ リストで「**[!UICONTROL プロファイル管理]**」項目を見つけ、「_追加_ （**+**）」アイコンをクリックして属性を追加します。

   * 属性に次の権限を追加します。
      * [!UICONTROL  セグメントの表示 ]
      * [!UICONTROL  セグメントの管理 ]
      * [!UICONTROL  プロファイルの表示 ]
      * [!UICONTROL  プロファイルの管理 ]
      * [!UICONTROL B2B プロファイルの表示 ]
      * [!UICONTROL B2B プロファイルの管理 ]

   ![Experience Platform – 新しい役割のプロファイルを追加 ](./assets/aep-permissions-role-profiles.png){width="700" zoomable="yes"}

1. B2B 製品の権限を追加します。

   役割に必要な製品機能を決定するには ](#b2b-product-permissions)[B2B 製品の権限のリストを参照してください。

   左側の _[!UICONTROL リソース]_ リストで、**[!UICONTROL B2B]** 項目を見つけ、_追加_ （**+**）アイコンをクリックして、役割に対して有効にする各属性を追加します。

   検索ツールに _B2B_ と入力して、B2B 製品の権限のリストをフィルタリングできます。

1. 右上の **[!UICONTROL 保存]** をクリックします。

1. 役割の詳細に移動し、「**[!UICONTROL ユーザーグループ]**」タブを選択します。

1. **[!UICONTROL グループを追加]** をクリックします。

   ![Experience Platform – 新しい役割のプロファイルを追加 ](./assets/aep-permissions-role-add-groups.png){width="700" zoomable="yes"}

1. Admin Consoleで以前に作成したユーザーグループの横にあるチェックボックスをオンにします。

1. 「**[!UICONTROL 保存]**」をクリックします。
