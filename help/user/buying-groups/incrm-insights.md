---
title: CRM 内インサイト
description: CRMから直接、Journey Optimizer B2B editionの購買グループにアクセスできます。 営業部門のメンバーは、エンゲージメントデータを確認し、CRM内のインサイトから販売機会を特定することができます。
feature: Sales Insights, Buying Groups
role: User
exl-id: c55a1fce-2ddc-481b-9f60-5e67a4bf9633
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: afadf741-c5fe-42cd-8013-23bb6ff2d1bc
  - id: fc1ff3b2-6614-41ad-a113-de48597598fd
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
subfeature_v2:
  - id: fe583b80-65a2-48c2-b4e1-9ea8fbac0a8a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
autotag-review: '2026-03-30T21:40:22.011Z'
source-git-commit: ff337a5f215daee1ea6dbe8d6b643087ac3324e2
workflow-type: tm+mt
source-wordcount: 483
ht-degree: 2%

---

# CRM 内インサイト

[!DNL In-CRM Insights]は、SalesforceとMicrosoft Dynamics 365に統合されたweb ベースのアプリケーションで、CRM内で[!DNL Journey Optimizer B2B Edition]個の購買グループに直接アクセスできます。 営業データソースをつなぎ合わせることで、エンゲージメントを高め、売上を伸ばす機会を容易に特定することができます。

## インストール

インストールプロセスには次のものが含まれます。

* ユーザー権限とグループの設定
* ソフトウェアパッケージのインストール
* CRMからログインする

### 権限の設定

ソフトウェアをインストールするユーザーには、Salesforce パッケージをインストールするための権限が必要です。

アプリケーションにアクセスするには、ユーザーが&#x200B;**Sales Insights:View Sales Insights**&#x200B;権限を持つ役割のメンバーシップを持っている必要があります。

ユーザーを[!DNL In-CRM Insights]のみに制限する場合：

1. [&#x200B; カスタム役割](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/accounts/buying-groups/default-custom-roles#create-a-custom-role)を作成し、**セールスインサイト：セールスインサイトの表示**&#x200B;権限を割り当てます。
1. 新しい[&#x200B; ユーザーグループ &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/admin/user-management#create-user-group)を作成します。
1. グループにExperience Platform製品プロファイルを追加します。

### パッケージのインストール

In-CRM Insights パッケージをインストールするには、SalesforceまたはMicrosoft Dynamicsの手順に従います。

#### Salesforce

1. [In-CRM Insights インストーラーパッケージ &#x200B;](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=salesforce)をダウンロードします。
1. ログイン後、パッケージのインストールページにリダイレクトされます。
1. 「**[!UICONTROL すべてのユーザーにインストール]**」オプションを選択し、**[!UICONTROL インストール]**&#x200B;をクリックします。

   ![CRM内インサイトパッケージのインストール &#x200B;](assets/incrm-install-sf.png){width=500}

1. ダイアログでサードパーティのアクセスを承認し、**[!UICONTROL 続行]**&#x200B;をクリックします。
1. インストールが完了したら、**[!UICONTROL 完了]**&#x200B;をクリックします。

   **インストール済みパッケージ** ページに表示され、**Journey Optimizer B2B edition**&#x200B;がアプリランチャーに表示されるようになりました。

   ![Salesforce内でCRM内インサイトを設定](assets/in-crm-install-sf-done.png){width=800 zoomable="yes"}

#### MS Dynamics

1. [In-CRM Insights インストーラーパッケージ &#x200B;](https://experience.adobe.com/solutions/OneAdobe-sales-workflow-optimizer-sales-insight-ui/install/sales-insight?crm=dynamics)をダウンロードします。
1. [Power Apps ポータル &#x200B;](https://make.powerapps.com/){target=_blank}に移動します。
1. ログイン後、パッケージの環境を選択し、左側のメニューから&#x200B;**[!UICONTROL Solutions]**&#x200B;に移動します。
1. 「**[!UICONTROL ソリューションの読み込み]**」をクリックします。
1. インストーラーパッケージを参照してアップロードし、**[!UICONTROL 次へ]**&#x200B;をクリックします。
1. パッケージの詳細を確認し、**[!UICONTROL 次へ]**&#x200B;をクリックします。
1. _環境変数_&#x200B;で、値が`prod`に設定されていることを確認し（値を変更しないでください）、**[!UICONTROL 読み込み]**&#x200B;をクリックします。
1. インストールが完了すると、左側のナビゲーションバーに&#x200B;**[!UICONTROL Journey Optimizer B2B edition]** > **[!UICONTROL 購買グループ]**&#x200B;が表示されます。

   Microsoft Dynamicsで![In-CRM インサイトを利用できます](assets/incrm-ms-install-done.png){width=800 zoomable="yes"}

## 購買グループの表示

画面の指示に従って、Adobe アカウントにログインします。 購買グループが読み込まれ、表示できます。

購買グループを選択した後、[&#x200B; グループの詳細](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/accounts/sales-experience/buying-group-details#)を参照できます。 これは、Journey Optimizer B2B editionに表示されるデータとインサイトと同じですが、データは[!DNL In-CRM Insights]を通じて読み取り専用です。
