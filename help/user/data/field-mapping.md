---
title: XDM フィールド
description: Adobe Experience PlatformとJourney Optimizer B2B editionの間で同期されるデフォルトの属性フィールドを確認します。
feature: Data Management, Integrations
role: User
exl-id: 8c65fdec-e32d-4ba8-be7b-48522cc3dace
source-git-commit: b62891e3d87ac4ff5345dac564d63c0b8aaa9669
workflow-type: tm+mt
source-wordcount: '1097'
ht-degree: 21%

---

# XDM フィールド

アカウントオーディエンスデータは、XDM ビジネスアカウントと XDM ビジネスユーザーの両方のクラスに属性として保存されます。 Adobe Experience PlatformとJourney Optimizer B2B editionの間では、データは定期的に同期されます。 次のセクションでは、デフォルトの属性セットを示します。

>[!TIP]
>
>[Experience Platform XDM ドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/relationship-b2b){target="_blank"} に記載されているように、XDM ビジネスアカウントユーザー関係クラスを使用することで、XDM ビジネスユーザーと XDM ビジネスアカウントのクラスを多対多の関係でモデル化できます。

## XDM ビジネスアカウント人物関係属性

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md){target="_blank"} | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `personRoles` | 人物の役割 | 役割 | 文字列配列 | アカウント上の人物に関連付けられた役割の配列（`owner, accountant, designer` など）。 |

## XDM ビジネスユーザー属性

>[!IMPORTANT]
>
>メールアドレス属性は必須であり、適切に機能させるために入力する必要があります。 デフォルトでは、`workEmail.Address` が使用されます。 別の属性を使用する場合は、ジャーニーを公開する前にAdobe サポートに問い合わせて、適切に設定されていることを確認してください。<br/>
>
>データ同期やダウンストリームプロセスに影響を与える可能性があるので、メール属性が null でないことを確認します。
><ul><li>Real-time CDP B2B でメール属性が null で、その人物がJourney Optimizer B2B editionに存在する場合、の属性はJourney Optimizer B2B editionで同期中に null 値で上書きされます。 その後、Marketo Engageでは null として保持されます。<li>Real-time CDP B2B でメール属性が null で、人物がJourney Optimizer B2B editionに存在しない場合、人物レコードは同期されません。<ul/>

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md){target="_blank"} | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `b2b.isMarketingSuspended` | マーケティング中断指標 | マーケティング中断 | ブール値 | 値は、その人物のマーケティングが中断されているかどうかを示します。 |
| `b2b.marketingSuspendedCause` | マーケティングの中断理由 | マーケティングの中断理由 | 文字列 | その人物のマーケティングが停止されている場合、このプロパティがその理由となります。 |
| `b2b.personStatus` | 人物のステータス | リードのステータス | 文字列 | 人物の現在のマーケティング /販売ステータスを記録するフィールド。 |
| `consents.marketing.email.reason` | オプトアウトの理由 | 登録解除の理由 | 文字列 | 電子メールオプトアウトに関連付けられた理由。 |
| `consents.marketing.email.val` | 登録解除済み | 登録解除済み | 文字列 | unsubscribed が true （例：value = 1）の場合は、`consents.marketing.email.val` を（n）に設定します。 unsubscribed が false （例：value = 0）の場合は、`consents.marketing.email.val` を null に設定します。 |
| `extendedWorkDetails.jobTitle` | 役職 | 役職 | 文字列 | 人物の役職。 |
| `faxPhone.number` | 数字 | FAX 番号 | 文字列 | FAX の電話番号。 |
| `mobilePhone.number` | 数字 | 携帯電話番号 | 文字列 | 人物に関連付けられている携帯電話番号。 |
| `person.birthDate` | 生年月日（YYY-MM-DD） | 生年月日 | 文字列 | 個人が誕生した完全な日付。 YYYY-MM-DD |
| `person.name.courtesyTitle` | 敬称 | 敬称 | 文字列 | 通常、個人の肩書きの略称、敬称またはあいさつ文。 表題は、テキストの冒頭で、フルネームまたは姓の前に使用します。 例えば、Mr.、Ms.、Dr.などです。 |
| `person.name.firstName` | 名 | 名 | 文字列 | 名前の言語で最も一般的に受け入れられている、書かれた順序での名前の最初のセグメント。 多くの文化では、名前は好ましい個人または特定の名前です。 firstName プロパティと lastName プロパティが導入され、単純化され、セマンティックでなく、国際化できない方法で名前をモデル化する既存のシステムとの互換性が維持されています。 `xdm:fullName` を使用することが常に望ましい。 |
| `person.name.lastName` | 姓 | 姓 | 文字列 | 名前の言語で最も一般的に受け入れられている、書面による順序での名前の最後のセグメント。 多くの文化では、それは継承された姓、姓、父名、または母名です。 firstName プロパティと lastName プロパティが導入され、単純化され、セマンティックでなく、国際化できない方法で名前をモデル化する既存のシステムとの互換性が維持されています。 `xdm:fullName` を使用することが常に望ましい。 |
| `person.name.middleName` | ミドルネーム | ミドルネーム | 文字列 | 姓と名の間に付けられたミドルネーム、代替ネームまたは追加ネーム。 |
| `workAddress.city ` | 市区町村 | 市区町村 | 文字列 | 市区町村の名前。 |
| `workAddress.country` | 国 | 国 | 文字列 | 政府が管理する領土の名前。`xdm:countryCode` 以外の場合は、自由形式のフィールドであり、どの言語でも国名を持つことができます。 |
| `workAddress.postalCode` | 郵便番号 | 郵便番号 | 文字列 | 場所の郵便番号。一部の国には郵便番号がありません。国によっては、郵便番号の一部のみが含まれます。 |
| `workAddress.state` | State | State | 文字列 | 住所の都道府県の名前。 これは自由形式のフィールドです。 |
| `workAddress.street1` | 住所 1 | Address | 文字列 | プライマリの番地レベルの情報、アパート番号、通り番号、通り名。 |
| `workEmail.address` | Address | メールアドレス | 文字列 | **必須フィールド**<br/> 技術的アドレス（例：RFC2822 および後続の標準で一般的に定義されている `<name@domain.com>`）。 |
| `workEmail.status` | ステータス | メールの中断 | 文字列 | その電子メールアドレスを使用できるかどうかを示します。 |
| `workPhone.number` | 数字 | 電話番号 | 文字列 | 勤務先の電話番号。 |

## XDM ビジネスアカウント属性

>[!IMPORTANT]
>
>`accountName` 属性は必須です。 アカウントオーディエンスのアカウントで空の場合、そのアカウントは取り込まれず、オーディエンスを参照するアカウントジャーニーおよび購入グループから除外されます。

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/account/account-details.schema.md){target="_blank"} | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `accountBillingAddress.city` | 市区町村 | 市区町村 | 文字列 | 請求先住所で使用される市区町村の名前。 |
| `accountBillingAddress.country` | 国 | 国 | 文字列 | 請求先住所で使用される政府が管理する地域の名前。 `xdm:countryCode` 以外の場合は、自由形式のフィールドであり、どの言語でも国名を持つことができます。 |
| `accountBillingAddress.postalCode` | 郵便番号 | 住所（郵便番号） | 文字列 | 請求先住所の住所の郵便番号。 一部の国には郵便番号がありません。国によっては、郵便番号の一部のみが含まれます。 |
| `accountBillingAddress.region` | 地域 | 住所（地域） | 文字列 | 請求先住所の地域、郡または地区の部分。 |
| `accountBillingAddress.state` | State | State | 文字列 | 請求先住所の都道府県の名前。 これは自由形式のフィールドです。 |
| `accountBillingAddress.street1` | 住所 1 | 住所 1 | 文字列 | 請求先住所のプライマリの番地レベル情報。通常、アパート番号、ストリート番号、ストリート名が含まれます。 |
| `accountName` | 名前 | 名前 | 文字列 | **必須フィールド**<br/> 会社の名前。 このフィールドには、最大 255 文字まで入力できます。 |
| `accountOrganization.annualRevenue.amount` | 年間収益 | 年間売上高 | 数字 | 組織の年間売上高の推定金額。 |
| `accountOrganization.industry` | 業界 | 業界 | 文字列 | 業界は組織に起因する。 これは自由形式のフィールドで、クエリには構造化された値を使用するか、`xdm:classifier` プロパティを使用することをお勧めします。 |
| `accountOrganization.logoUrl` | ロゴ URL | ロゴ URL | 文字列 | アカウントに関連付けられたソーシャルネットワークプロファイル画像をリクエストする URL を生成するために、Salesforce インスタンスの URL （`https://yourInstance.salesforce.com/` など）と組み合わせるパス。 生成された URL は、アカウントのソーシャルネットワークプロファイル画像への HTTP リダイレクト（コード 302）を返します。 |
| `accountOrganization.numberOfEmployees` | 従業員数 | 従業員数 | 整数 | 組織の従業員数。 |
| `accountOrganization.SICCode` | SIC コード | SIC コード | 文字列 | Standard Industrial Classification （SIC） コードは、事業活動に基づいて会社が属する業界を分類する 4 桁のコードです。 |
| `accountOrganization.website` | Web サイトの URL | ドメイン名 | 文字列 | 組織の web サイトの URL。 |
| `accountPhone.number` | 該当なし | アカウントの電話番号 | 文字列 | アカウントに関連付けられている電話番号。 |
| `accountSourceType` | 該当なし | ソースのタイプ | 文字列 | アカウントのSourceタイプ。 |

<!-- ## XDM Business Opportunity attributes

Additionally, opportunity data is stored as attributes in the XDM Business Opportunity class, which can be associated with the XDM Business Account class through a many-to-one relationship, as described in the [Exerience Platform documentation](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/relationship-b2b#relationship-field){target="_blank"}.

|[Property](https://github.com/adobe/xdm/blob/master/docs/reference/adobe/experience/marketo/opportunity-marketo.schema.md){target="_blank"} |Display name |Journey Optimizer B2B display name |Data type |Description |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
|`expectedCloseDate` | Expected Close Date  | Expected opportunity close date   | String | Expected date of closure for the opportunity.   |
|`expectedRevenue.amount` | Expected Revenue  | Total opportunity expected revenue   | String | Calculated revenue based on the Amount and Probability.   |
|`fiscalQuarter` | Fiscal Quarter   | Opportunity fiscal quarter  | String | The targeted fiscal quarter for the opportunity.   |
|`fiscalYear` | Fiscal Year   | Opportunity fiscal year   | String | The targeted fiscal year for the opportunity.   |
|`forecastCategory`|Forecast Category | Opportunity Forecast category | String | Forecast Category determined by the opportunity Stage value. |
|`forecastCategoryName`|Forecast Category Name | Opportunity forecast category name | String | Forecast category name that is displayed in reports for a particular forecast category. |
|`isClosed` | Closed Flag  | Opportunity closed   | String | Flag that indicates if the opportunity is closed.   |
|`isWon` | Won Flag  | Opportunity won   | String | Flag that indicates if the opportunity is won.  |
|`lastActivityDate` | Last Activity Date  | Last activity date   | String | Last activity date for the opportunity.  |
|`leadSource` | Lead Source  | Lead source   | String | Source of the opportunity, such as Advertisement, Partner, or Web.   |
|`nextStep` | Next Step  | Opportunity next step   | String | Description of the next task for closing the opportunity.   |
|`opportunityAmount.amount` | Opportunity Amount  | Total Opportunity Amount | String | Estimated total sale amount for the opportunity.   |
|`opportunityDescription` | Opportunity Description   | Opportunity description  |String  | Additional information to describe the opportunity, such as possible products to sell or past purchases from the customer. |
|`opportunityName` | Opportunity Name   | Opportunity name |String  | Subject or descriptive name, such as the expected order or company name, for the opportunity. |
|`opportunityQuantity` | Opportunity Quantity  | Opportunity quantity   | String | Total of all quantity field values for all products in the related Products list for the opportunity.   |
|`opportunityStage` | Opportunity Stage   | Opportunity stage   | String | Sales stage of the opportunity to aid the sales team in their efforts to win it.  |
|`opportunityType` | Opportunity Type   | Opportunity type   | String | Type assigned to the opportunity, such as _Existing Business_ or _New Business_  |
|`probabilityPercentage` | Probability Percentage  | Opportunity probability percentage  | String | Likelihood of closing the opportunity, stated as a percentage.  |
 -->