---
title: CRM 内インサイト
description: SalesforceのJourney Optimizer B2B edition購入グループに直接アクセスします。 営業チームメンバーは、エンゲージメントデータを表示し、CRM 内インサイトを使用して販売機会を特定できます。
feature: Sales Insights, Buying Groups
role: User
source-git-commit: de7f5620556a48fe6f12ed1c70e925e11ec770f1
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---


# CRM 内インサイト

In-CRM Insights は、Salesforceに統合される web ベースアプリケーションであり、Salesforce内からJourney Optimizer B2B editionの購買グループに直接アクセスできます。 これにより、エンゲージメントとセールスの可能性を高める機会を特定できます。

CRM 内インサイトアプリケーションは、[Marketo Sales Insights パッケージ &#x200B;](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/marketo-sales-insight/msi-for-salesforce/installation/install-marketo-sales-insight-package-in-salesforce-appexchange) で利用できます。

## 権限

アプリケーションにアクセスするには、ユーザーは **Sales Insights:ViewSales Insights** 権限を持つ役割のメンバーシップが必要です。

ユーザーのグループを InCRM-Insights に制限する場合は、次のガイドラインを使用して、InCRM-Insights 専用のカスタムの役割を作成します。

* **Sales Insights:View Sales Insights** 権限セットのみを持つカスタム役割を作成します。
* 製品プロファイルを追加せずに、新規ユーザーグループを作成します。
* 別のユーザーグループを作成してAEP製品プロファイルを追加するか、作成したユーザーグループに既存のAEP プロファイルを追加します。
* 新しいユーザーグループを新しい役割に割り当て、新しいユーザーを新しいユーザーグループに追加します。

## CRM 内インサイトの使用

In-CRM Insights アプリケーションは、アプリランチャーを通じてSalesforceで使用できます。

1. Salesforceのアプリランチャーをクリックします。
1. `Journey Optimizer B2B Edition` を選択または検索します。
1. 「表示」タブで、Adobeの資格情報を使用してログインします。
1. アカウントジャーニーをホストするサンドボックスを選択します。

購入グループが読み込まれ、使用可能になります。 データは、CRM 内インサイトを通じて読み取り専用です。

>[!NOTE]
>
>In-CRM Insights にアクセスするには [&#128279;](../admin/user-management.md#b2b-built-in-roles)B2B Sales User 製品ロールのメンバーシップが必要です。

購入グループを選択した後は、Journey Optimizer B2B editionと同様に [&#x200B; グループの詳細 &#x200B;](https://experienceleague.adobe.com/en/docs/journey-optimizer-b2b/user/accounts/sales-experience/buying-group-details#) を参照できます。
