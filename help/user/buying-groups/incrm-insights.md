---
title: CRM 内インサイト
description: CRM 内のJourney Optimizer B2B edition購入グループに直接アクセスします。 営業チームメンバーは、エンゲージメントデータを表示し、CRM 内インサイトを使用して販売機会を特定できます。
feature: Sales Insights, Buying Groups
role: User
source-git-commit: 2eb5b6226730a1948b480a9dee0c6f2786e01cc5
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 1%

---


# CRM 内インサイト

[!DNL In-CRM Insights] は、SalesforceおよびMicrosoft Dynamics 365 に統合される web ベースアプリケーションであり、CRM 内の [!DNL Journey Optimizer B2B Edition] 購入グループに直接アクセスできます。 販売データソースが統合されるので、エンゲージメントと販売の可能性を高める機会を特定しやすくなります。

## インストール

インストールプロセスには次が含まれます。

* ユーザー権限とグループの設定
* ソフトウェアパッケージのインストール
* CRM を使用したログイン

### 権限の設定

ソフトウェアをインストールするユーザーには、Salesforce パッケージをインストールする権限が必要です。

アプリケーションにアクセスするには、ユーザーは **Sales Insights:ViewSales Insights** 権限を持つ役割のメンバーシップである必要があります。

ユーザーを [!DNL In-CRM Insights] のみに制限する場合：

1. [ カスタムの役割 ](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/accounts/buying-groups/default-custom-roles#create-a-custom-role) を作成し、**Sales Insights:View Sales Insights** 権限に割り当てます。
1. 新規 [ ユーザーグループ ](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/admin/user-management#create-user-group) を作成します。
1. Experience Platform製品プロファイルをグループに追加します。

### パッケージのインストール

CRM 内インサイトパッケージをインストールするには、SalesforceまたはMicrosoft Dynamicsの手順に従います。

#### Salesforce

1. [CRM 内インサイトインストーラーパッケージ ](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=salesforce) をダウンロードします。
1. ログインすると、パッケージのインストールページにリダイレクトされます。
1. 「**[!UICONTROL すべてのユーザー用にインストール]**」オプションを選択し、「**[!UICONTROL インストール]**」をクリックします。

   ![CRM 内インサイトパッケージのインストール ](assets/incrm-install-sf.png){width=500}

1. ダイアログでサードパーティアクセスを承認し、「**[!UICONTROL 続行]**」をクリックします。
1. インストールが完了したら、「**[!UICONTROL 完了]**」をクリックします。

   現在は、**インストール済みパッケージ** ページにリストされ、**Journey Optimizer B2B edition** がアプリランチャーにリストされています。

   ![Salesforce内で設定された CRM 内インサイト ](assets/in-crm-install-sf-done.png){width=800 zoomable="yes"}

#### MS Dynamics

1. [CRM 内インサイトインストーラーパッケージ ](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=dynamics) をダウンロードします。
1. [ 電源アプリのポータル ](https://make.powerapps.com/){target=_blank} に移動します。
1. ログイン後、パッケージの環境を選択し、左のメニューから **[!UICONTROL ソリューション]** に移動します。
1. **[!UICONTROL ソリューションをインポート]** をクリックします。
1. を参照してインストーラーパッケージをアップロードし、「**[!UICONTROL 次へ]**」をクリックします。
1. パッケージの詳細を確認し、「**[!UICONTROL 次へ]**」をクリックします。
1. _環境変数_ の下で、値が `prod` に設定されていることを確認し（値は変更しないでください）、**[!UICONTROL 読み込み]** をクリックします。
1. インストールが完了すると、**[!UICONTROL Journey Optimizer B2B edition]** / **[!UICONTROL 購入グループ]** が左側のナビゲーションバーに表示されます。

   ![Microsoft Dynamicsで利用可能な CRM 内インサイト ](assets/incrm-ms-install-done.png){width=800 zoomable="yes"}

## 購入グループを表示

画面の指示に従って、Adobe アカウントにログインします。 購入グループが読み込まれ、表示できます。

購入グループを選択したら、[ グループの詳細 ](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/accounts/sales-experience/buying-group-details#) を参照できます。 これは、Journey Optimizer B2B editionに表示されるデータおよびインサイトと同じですが、データは [!DNL In-CRM Insights] を通じて読み取り専用です。
