---
title: XDM フィールド
description: Adobe Experience PlatformとJourney Optimizer B2B editionの間で同期されるデフォルトの属性フィールドを確認します。
exl-id: 8c65fdec-e32d-4ba8-be7b-48522cc3dace
source-git-commit: 34ef9681b75ef1cd43d34e3f2836a60affb95b33
workflow-type: tm+mt
source-wordcount: '1342'
ht-degree: 23%

---

# XDM フィールド

アカウントオーディエンスデータは、XDM ビジネスアカウントと XDM ビジネスユーザーの両方のクラスに属性として保存されます。 Adobe Experience PlatformとJourney Optimizer B2B editionの間では、データは定期的に同期されます。 次のセクションでは、デフォルトの属性セットを示します。

>[!TIP]
>
>[Experience Platform XDM ドキュメント ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/relationship-b2b) に記載されているように、XDM ビジネスアカウントユーザー関係クラスを使用することで、XDM ビジネスユーザーと XDM ビジネスアカウントのクラスを多対多の関係でモデル化できます。

## XDM ビジネスアカウント人物関係属性

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md) | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `personRoles` | 人物の役割 | ロール | 文字列配列 | アカウント上の人物に関連付けられた役割の配列（`owner, accountant, designer` など）。 |

## XDM ビジネスユーザー属性

>[!IMPORTANT]
>
>`workEmail.Address` 属性は必須です。 アカウントオーディエンスメンバーが空の場合、そのユーザーは取り込まれず、オーディエンスを参照するアカウントジャーニーおよび購入グループから除外されます。

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md) | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `b2b.isMarketingSuspended` | マーケティング中断指標 | マーケティング中断 | ブール値 | 値は、その人物のマーケティングが中断されているかどうかを示します。 |
| `b2b.marketingSuspendedCause` | マーケティングの中断理由 | マーケティングの中断理由 | 文字列 | その人物のマーケティングが停止されている場合、このプロパティがその理由となります。 |
| `b2b.personStatus` | 人物のステータス | リードのステータス | 文字列 | 人物の現在のマーケティング /販売ステータスを記録するフィールド。 |
| `consents.marketing.email.reason` | オプトアウトの理由 | 登録解除の理由 | 文字列 | 電子メールオプトアウトに関連付けられた理由。 |
| `consents.marketing.email.val` | Unsubscribed | Unsubscribed | 文字列 | unsubscribed が true （例：value = 1）の場合は、`consents.marketing.email.val` を（n）に設定します。 unsubscribed が false （例：value = 0）の場合は、`consents.marketing.email.val` を null に設定します。 |
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
| `workAddress.state` | 都道府県 | 都道府県 | 文字列 | 住所の都道府県の名前。 これは自由形式のフィールドです。 |
| `workAddress.street1` | 住所 1 | 住所 | 文字列 | プライマリの番地レベルの情報、アパート番号、通り番号、通り名。 |
| `workEmail.address` | 住所 | メールアドレス | 文字列 | **必須フィールド**<br/> 技術的アドレス（例：RFC2822 および後続の標準で一般的に定義されている `<name@domain.com>`）。 |
| `workEmail.status` | ステータス | メールの中断 | 文字列 | その電子メールアドレスを使用できるかどうかを示します。 |
| `workPhone.number` | 数字 | 電話番号 | 文字列 | 勤務先の電話番号。 |

## XDM ビジネスアカウント属性

>[!IMPORTANT]
>
>`accountName` 属性は必須です。 アカウントオーディエンスのアカウントで空の場合、そのアカウントは取り込まれず、オーディエンスを参照するアカウントジャーニーおよび購入グループから除外されます。

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/account/account-details.schema.md) | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `accountBillingAddress.city` | 市区町村 | 市区町村 | 文字列 | 請求先住所で使用される市区町村の名前。 |
| `accountBillingAddress.country` | 国 | 国 | 文字列 | 請求先住所で使用される政府が管理する地域の名前。 `xdm:countryCode` 以外の場合は、自由形式のフィールドであり、どの言語でも国名を持つことができます。 |
| `accountBillingAddress.postalCode` | 郵便番号 | 住所（郵便番号） | 文字列 | 請求先住所の住所の郵便番号。 一部の国には郵便番号がありません。国によっては、郵便番号の一部のみが含まれます。 |
| `accountBillingAddress.region` | 地域 | 住所（地域） | 文字列 | 請求先住所の地域、郡または地区の部分。 |
| `accountBillingAddress.state` | 都道府県 | 都道府県 | 文字列 | 請求先住所の都道府県の名前。 これは自由形式のフィールドです。 |
| `accountBillingAddress.street1` | 住所 1 | 住所 1 | 文字列 | 請求先住所のプライマリの番地レベル情報。通常、アパート番号、ストリート番号、ストリート名が含まれます。 |
| `accountName` | 名前 | 名前 | 文字列 | **必須フィールド**<br/> 会社の名前。 このフィールドには、最大 255 文字まで入力できます。 |
| `accountOrganization.annualRevenue.amount` | 年間収益 | 年間売上高 | 数字 | 組織の年間売上高の推定金額。 |
| `accountOrganization.industry` | 業界 | 業界 | 文字列 | 業界は組織に起因する。 これは自由形式のフィールドで、クエリには構造化された値を使用するか、`xdm:classifier` プロパティを使用することをお勧めします。 |
| `accountOrganization.logoUrl` | ロゴ URL | ロゴ URL | 文字列 | アカウントに関連付けられたソーシャルネットワークプロファイル画像をリクエストする URL を生成するために、Salesforce インスタンスの URL （`https://yourInstance.salesforce.com/` など）と組み合わせるパス。 生成された URL は、アカウントのソーシャルネットワークプロファイル画像への HTTP リダイレクト（コード 302）を返します。 |
| `accountOrganization.numberOfEmployees` | 従業員数 | 従業員数 | 整数 | 組織の従業員数。 |
| `accountOrganization.SICCode` | SIC コード | SIC コード | 文字列 | Standard Industrial Classification （SIC） コードは、事業活動に基づいて会社が属する業界を分類する 4 桁のコードです。 |
| `accountOrganization.website` | Web サイトの URL | ドメイン名 | 文字列 | 組織の web サイトの URL。 |
| `accountPhone.number` | なし | アカウントの電話番号 | 文字列 | アカウントに関連付けられている電話番号。 |
| `accountSourceType` | なし | ソースのタイプ | 文字列 | アカウントのSourceタイプ。 |

## XDM Business Opportunity 属性

さらに、商談データは XDM Business Opportunity クラスの属性として保存されます。この属性は、[ こちら ](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/tutorials/relationship-b2b#relationship-field) で説明されているように、多対 1 の関係を通じて XDM Business Account クラスに関連付けることができます。

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/adobe/experience/marketo/opportunity-marketo.schema.md) | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `expectedCloseDate` | 商談完了予定日 | 商談のクローズ予定日 | 文字列 | オポチュニティに対して期待されるクローズ日。 |
| `expectedRevenue.amount` | 予想収益 | 商談の収益予測合計 | 文字列 | 金額と確率に基づいて計算された売上高。 |
| `fiscalQuarter` | 会計四半期 | オポチュニティ会計四半期 | 文字列 | オポチュニティをターゲットにした会計四半期。 |
| `fiscalYear` | 会計年度 | オポチュニティ会計年度 | 文字列 | オポチュニティのターゲットとなる会計年度。 |
| `forecastCategory` | 予測カテゴリ | 商談予測カテゴリ | 文字列 | オポチュニティのステージ値によって決定された予測カテゴリ。 |
| `forecastCategoryName` | 予測カテゴリ名 | 商談予測カテゴリ名 | 文字列 | 特定の予測カテゴリに関するレポートに表示される予測カテゴリ名。 |
| `isClosed` | クローズドフラグ | クローズした商談 | 文字列 | オポチュニティがクローズされているかどうかを示すフラグ。 |
| `isWon` | 獲得フラグ | 獲得した商談 | 文字列 | オポチュニティが獲得されたかどうかを示すフラグ。 |
| `lastActivityDate` | 最後のアクティビティ日 | 最後のアクティビティの日付 | 文字列 | オポチュニティの最後のアクティビティの日付。 |
| `leadSource` | リードのソース | リードのソース | 文字列 | オポチュニティのSource（広告、パートナー、web など）。 |
| `nextStep` | 次のステップ | オポチュニティの次のステップ | 文字列 | オポチュニティをクローズするための次のタスクの説明。 |
| `opportunityAmount.amount` | 商談額 | 合計商談数 | 文字列 | オポチュニティの推定合計販売金額。 |
| `opportunityDescription` | 商談の説明 | オポチュニティの説明 | 文字列 | オポチュニティを説明する追加情報（販売する可能性のある製品や顧客からの過去の購入など）。 |
| `opportunityName` | 商談名 | 商談名 | 文字列 | オポチュニティの件名または説明的な名前（期待される注文や会社名など）。 |
| `opportunityQuantity` | 商談の数量 | オポチュニティの数量 | 文字列 | オポチュニティの関連製品リストにあるすべての製品に関するすべての数量フィールド値の合計。 |
| `opportunityStage` | 商談のステージ | 商談のステージ | 文字列 | セールス・チームの取り組みを支援するオポチュニティのセールス・ステージ。 |
| `opportunityType` | 商談のタイプ | 商談のタイプ | 文字列 | オポチュニティに割り当てられたタイプ （_既存のビジネス_ または _新規ビジネス_ など） |
| `probabilityPercentage` | 確率率 | 商談確率の割合 | 文字列 | オポチュニティをクローズする可能性（パーセンテージ）。 |
