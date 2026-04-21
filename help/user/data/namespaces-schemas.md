---
title: B2B 名前空間とスキーマ
description: Experience Platform自動生成ユーティリティを使用して、Journey Optimizer B2B edition用にPostman B2B 名前空間とスキーマを設定します。
feature: Setup, Data Management
role: Admin
exl-id: 40d01027-7cf2-4189-8a49-7a0783c00721
source-git-commit: 0f34a98753b71b388c822ef4a26dbae6b4c8fb1b
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 96%

---

# B2B 名前空間とスキーマ

Journey Optimizer B2B Editionの設定には、B2B ソースで使用されるExperience Platform名前空間とスキーマの設定が含まれます。 B2B 名前空間とスキーマを生成するには、Postman自動処理ユーティリティが必要です。

>[!AVAILABILITY]
>
>- B2B スキーマが  リアルタイム顧客プロファイル [&#128279;](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/intro/rtcdpb2b-intro/b2b-overview){target="_blank"} に適合するには、[Adobe Real-Time Customer Data Platform B2B edition](https://experienceleague.adobe.com/ja/docs/experience-platform/profile/home){target="_blank"} へのアクセス権が必要です。
>
>- Experience Platform B2B エンティティは、[B2B 名前空間およびスキーマガイド &#x200B;](https://experienceleague.adobe.com/en/docs/experience-platform/rtcdp/schemas/b2b){target="_blank"} に概説されている標準的な関係を使用する必要があります。

B2B ソースで使用するネームスペースとスキーマの基礎となる設定について、次の情報を確認します。 また、B2B 名前空間とスキーマを生成するために必要な、Postman自動処理ユーティリティの設定に関する詳細も提供します。

## 自動生成ユーティリティの設定

前提条件については、次のリソースを参照してください。また、B2B 名前空間とスキーマ自動生成ユーティリティをサポートする [!DNL Postman] 環境の設定方法に関する詳細情報も参照してください。

- 名前空間およびスキーマ自動生成ユーティリティのコレクションと環境を [GitHub リポジトリ &#x200B;](https://github.com/adobe/experience-platform-postman-samples/tree/master/Postman%20Collections/CDP%20Namespaces%20and%20Schemas%20Utility){target="_blank"} からダウンロードします。
- 必要なヘッダーの値の収集やサンプル API 呼び出しの読み取りの詳細など、Experience Platform API の使用については、[_Adobe Experience Platform API の概要_](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/platform-apis/api-guide){target="_blank"} を参照してください。
- Experience Platform API の資格情報の生成について詳しくは、[_Experience Platform API の認証とアクセス_](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/api-authentication){target="_blank"} を参照してください。
- Experience Platform API の [!DNL Postman] の設定について詳しくは、Adobe Experience Platformの [_[!DNL Postman] を参照してください _](https://experienceleague.adobe.com/en/docs/experience-platform/landing/platform-apis/postman){target="_blank"}

### 環境値

Experience Platform Developer Console をセットアップす [!DNL Postman] と、適切な環境設定の値を [!DNL Postman] 環境に適用できます。 次の表に、値の例と、[!DNL Postman] 環境へのデータ入力に関する追加情報を示します。

| 変数 | 説明 | 例 |
| --- | --- | --- |
| `CLIENT_SECRET` | `{ACCESS_TOKEN}` ータの生成に使用される一意の ID。 | `{CLIENT_SECRET}` |
| `API_KEY` | Experience Platform API への呼び出しの認証に使用される一意の ID。 | `c8d9a2f5c1e03789bd22e8efdd1bdc1b` |
| `ACCESS_TOKEN` | Experience Platform API を呼び出すために必要な認証トークン。 | `Bearer {ACCESS_TOKEN}` |
| `META_SCOPE` | [!DNL Journey Optimizer B2B] および [!DNL Marketo Engage] に関しては、この値は固定で、常に `ent_dataservices_sdk` に設定されます。 | `ent_dataservices_sdk` |
| `CONTAINER_ID` | `global` コンテナには、標準のAdobeおよびExperience Platform パートナー提供のすべてのクラス、スキーマフィールドグループ、データタイプおよびスキーマが含まれます。 [!DNL Marketo] に関しては、この値は固定で、常に `global` に設定されます。 | `global` |
| `TECHNICAL_ACCOUNT_ID` | Adobe I/Oへの統合に使用する資格情報。 | `D42AEVJZTTJC6LZADUBVPA15@techacct.adobe.com` |
| `IMS` | Identity Management System （IMS）は、Adobe サービスに対して認証を行うためのフレームワークを提供します。 [!DNL Journey Optimizer B2B] および [!DNL Marketo Engage] に関しては、この値は固定で、常に `ims-na1.adobelogin.com` に設定されます。 | `ims-na1.adobelogin.com` |
| `IMS_ORG` | 製品およびサービスを所有またはライセンスし、そのメンバーへのアクセスを許可できる法人組織。 | `ABCEH0D9KX6A7WA7ATQE0TE@adobeOrg` |
| `SANDBOX_NAME` | 使用している仮想サンドボックスパーティションの名前。 | `prod` |
| `TENANT_ID` | 作成するリソースの名前空間が適切に設定され、組織内に含まれていることを確認するために使用される ID。 | `b2bcdpproductiontest` |
| `PLATFORM_URL` | API 呼び出しを行う URL エンドポイント。 この値は固定で、常に `http://platform.adobe.io/` に設定されます。 | `http://platform.adobe.io/` |

{style="table-layout:auto"}

### スクリプトの実行

環境の値を設定したら、[!DNL Postman] インターフェイスを使用して、名前空間とスキーマを作成するためのスクリプトを実行します。 自動生成ユーティリティのルートフォルダーを選択し、上部のヘッダーから **[!DNL Run]** を選択します。

![Postman UI の名前空間およびスキーマジェネレーターのルートフォルダー &#x200B;](./assets/namespaces-schemas-postman-root-folder.png){width="500" zoomable="yes"}

[!DNL Runner] インターフェイスが表示されます。 ここから、すべてのチェックボックスが選択されていることを確認してから選択し **[!DNL Run Namespaces and Schemas Autogeneration Utility]** す。

![Postman UI の名前空間およびスキーマ コレクションで複数のリクエストが選択されています。](./assets/namespaces-schemas-postman-run-generator.png){width="800" zoomable="yes"}

リクエストが成功すると、必要な B2B 名前空間とスキーマが作成されます。

## B2B 名前空間

ID 名前空間は、ID のコンテキストを区別するのに役立つExperience Platform [[!DNL Identity Service]](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/home){target="_blank"} のコンポーネントです。 完全修飾 ID には、ID 値と名前空間が含まれます。 詳しくは、[&#x200B; 名前空間の概要 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/identity/features/namespaces){target="_blank"} を参照してください。

B2B 名前空間は、エンティティのプライマリ ID で使用されます。

| 表示名 | ID シンボル | ID タイプ |
| --- | --- | --- |
| B2B ユーザー | `b2b_person` | `CROSS_DEVICE` |
| B2B アカウント | `b2b_account` | `B2B_ACCOUNT` |
| B2B オポチュニティ | `b2b_opportunity` | `B2B_OPPORTUNITY` |
| B2B オポチュニティ人物関係 | `b2b_opportunity_person_relation` | `B2B_OPPORTUNITY_PERSON` |
| B2B キャンペーン | `b2b_campaign` | `B2B_CAMPAIGN` |
| B2B キャンペーンメンバー | `b2b_campaign_member` | `B2B_CAMPAIGN_MEMBER` |
| B2B マーケティングリスト | `b2b_marketing_list` | `B2B_MARKETING_LIST` |
| B2B マーケティングリストメンバー | `b2b_marketing_list_member` | `B2B_MARKETING_LIST_MEMBER` |
| B2B アカウント人物関係 | `b2b_account_person_relation` | `B2B_ACCOUNT_PERSON` |

{style="table-layout:auto"}

## B2B スキーマ

Experience Platform では、スキーマを使用して、一貫性のある再利用可能な方法でデータの構造を記述します。 システムをまたいで一貫したデータを定義することで、意味を保有しやすくなり、データから価値を得ることができます。

Experience Platformがデータを取り込む前に、データの構造を記述し、各フィールドに含めることができるデータのタイプに制約を与えるスキーマが必要です。 スキーマは、基本クラスと 0 個以上のスキーマフィールドグループで構成されます。

デザインの原則やベストプラクティスなど、スキーマ構成モデルについて詳しくは、[_スキーマ構成の基本_](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/composition){target="_blank"} を参照してください。

+++ B2B アカウント

<table>
    <tr>
        <td style="width: 30%;">基本クラス</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account" target="_blank">XDM ビジネスアカウント</a></td>
    </tr>
    <tr>
        <td>フィールドグループ</td>
        <td>XDM ビジネスアカウントの詳細</td>
    </tr>
    <tr>
        <td>[!DNL Profile] スキーマ内</td>
        <td>有効</td>
    </tr>
    <tr>
        <td>プライマリ ID</td>
        <td><code>accountKey.sourceKey</code> 基本クラス内</td>
    </tr>
    <tr>
        <td>プライマリ ID 名前空間</td>
        <td>B2B アカウント</td>
    </tr>
    <tr>
        <td>セカンダリID</td>
        <td><code>extSourceSystemAudit.externalKey.sourceKey</code> 基本クラス内</td>
    </tr>
    <tr>
        <td>セカンダリid 名前空間</td>
        <td>B2B アカウント</td>
    </tr>
    <tr>
        <td>関係</td>
        <td><ul><li><code>accountParentKey.sourceKey</code> XDM ビジネスアカウントの詳細フィールドグループ内</li><li>宛先のプロパティ： <code>/accountKey/sourceKey</code></li><li>タイプ : 1 対 1</li><li>参照スキーマ：B2B アカウント</li><li>名前空間：B2B アカウント</li></ul> </td>
    </tr>
</table>

+++

+++ B2B ユーザー

<table>
    <tr>
        <td style="width: 30%;">基本クラス</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/individual-profile">XDM 個人プロファイル </a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>フィールドグループ</td>
        <td><ul><li>XDM ビジネスパーソンの詳細</li><li>XDM ビジネスパーソンのコンポーネント</li><li>identityMap</li><li>同意と環境設定の詳細</li></ul> </td>
    </tr>
    <tr>
        <td>[!DNL Profile] スキーマ内</td>
        <td>有効</td>
    </tr>
    <tr>
        <td>プライマリ ID</td>
        <td><code>b2b.personKey.sourceKey</code> XDM ビジネス人物の詳細フィールドグループ</td>
    </tr>
    <tr>
        <td>プライマリ ID 名前空間</td>
        <td>B2B ユーザー</td>
    </tr>
    <tr>
        <td>セカンダリID</td>
        <td><ol><li><code>extSourceSystemAudit.externalKey.sourceKey</code> XDM ビジネス人物の詳細フィールドグループの</li><li><code>workEmail.address</code> XDM ビジネス人物の詳細フィールドグループの</li></ol></td>
    </tr>
    <tr>
        <td>セカンダリid 名前空間</td>
        <td><ol><li>B2B ユーザー</li><li>メール</li></ol></td>
    </tr>
    <tr>
        <td>関係</td>
        <td><ul><li><code>personComponents.sourceAccountKey.sourceKey</code> XDM ビジネスユーザーコンポーネントフィールドグループの</li><li>タイプ：多対 1</li><li>参照スキーマ：B2B アカウント</li><li>名前空間：B2B アカウント</li><li>宛先プロパティ：accountKey.sourceKey</li><li>現在のスキーマからの関係名：アカウント</li><li>参照スキーマからの関係名：人物</li></ul> </td>
    </tr>
</table>

+++

<!--

+++B2B Opportunity

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity">XDM Business Opportunity</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Opportunity Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>opportunityKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Opportunity</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td><code>extSourceSystemAudit.externalKey.sourceKey</code> in the base class</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>B2B Opportunity</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td><ul><li><code>accountKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Account</li><li>Namespace: B2B Account</li><li>Destination property: <code>accountKey.sourceKey</code></li><li>Relationship name from current schema: Account</li><li>Relationship name from reference schema: Opportunities</li></ul></td>
    </tr>
</table>

+++

+++B2B Opportunity Person Relation

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-opportunity-person-relation">XDM Business Opportunity Person Relation</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>opportunityPersonKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Opportunity Person Relation</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td> **First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Opportunities</li></ul>**Second relationship**<ul><li><code>opportunityKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Opportunity </li><li>Namespace: B2B Opportunity </li><li>Destination property: <code>opportunityKey.sourceKey</code></li><li>Relationship name from current schema: Opportunity</li><li>Relationship name from reference schema: People</li></ul> </td>
    </tr>
</table>


+++

+++B2B Campaign

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign">XDM Business Campaign</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Campaign Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>campaignKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Campaign</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>None</td>
    </tr>
</table>

+++

+++B2B Campaign Member

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-campaign-members">XDM Business Campaign Members</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>XDM Business Campaign Member Details</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>campaignMemberKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Campaign Member</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Campaigns</li></ul>**Second relationship**<ul><li><code>campaignKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Campaign</li><li>Namespace: B2B Campaign</li><li>Destination property: <code>campaignKey.sourceKey</code></li><li>Relationship name from current schema: Campaign</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

+++B2B Marketing List

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list">XDM Business Marketing List</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>marketingListKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Marketing List</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>None</td>
    </tr>
</table>

>[!NOTE]
>
>Static List in [!UICONTROL Marketo Engage] is not synced from Salesforce and therefore does not have a secondary identity.

+++

+++B2B Marketing List Member

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-marketing-list-members">XDM Business Marketing List Members</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>None</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>marketingListMemberKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Marketing List Member</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: Person</li><li>Relationship name from reference schema: Marketing Lists</li></ul>**Second relationship**<ul><li><code>marketingListKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Marketing List</li><li>Namespace: B2B Marketing List</li><li>Destination property: <code>marketingListKey.sourceKey</code></li><li>Relationship name from current schema: Marketing List</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

>[!NOTE]
>
>Static List member in [!UICONTROL Marketo Engage] is not synced from Salesforce and therefore does not have a secondary identity.

+++

+++B2B Account Person Relation

<table>
    <tr>
        <td style="width: 30%;">Base class</td>
        <td style="width: 70%;"><a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/classes/b2b/business-account-person-relation">XDM Business Account Person Relation</a>{target="_blank"}</td>
    </tr>
    <tr>
        <td>Field groups</td>
        <td>Identity Map</td>
    </tr>
    <tr>
        <td>[!DNL Profile] in Schema</td>
        <td>Enabled</td>
    </tr>
    <tr>
        <td>Primary identity</td>
        <td><code>accountPersonKey.sourceKey</code> in the base class</td>
    </tr>
    <tr>
        <td>Primary identity namespace</td>
        <td>B2B Account Person Relation</td>
    </tr>
    <tr>
        <td>Secondary identity</td>
        <td>None</td>
    </tr>
    </tr>
    <tr>
        <td>Secondary identity namespace</td>
        <td>None</td>
    </tr>
    <tr>
        <td>Relationship</td>
        <td>**First relationship**<ul><li><code>personKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Person</li><li>Namespace: B2B Person</li><li>Destination property: <code>b2b.personKey.sourceKey</code></li><li>Relationship name from current schema: People</li><li>Relationship name from reference schema: Account</li></ul>**Second relationship**<ul><li><code>accountKey.sourceKey</code> in the base class</li><li>Type: Many-to-one</li><li>Reference Schema: B2B Account</li><li>Namespace: B2B Account</li><li>Destination property: <code>accountKey.sourceKey</code></li><li>Relationship name from current schema: Account</li><li>Relationship name from reference schema: People</li></ul></td>
    </tr>
</table>

+++
-->
