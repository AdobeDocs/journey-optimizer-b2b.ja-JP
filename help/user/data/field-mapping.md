---
title: XDM フィールド
description: Adobe Experience PlatformとJourney Optimizer B2B Edition の間で同期されるデフォルトの属性フィールドを確認します。
exl-id: 8c65fdec-e32d-4ba8-be7b-48522cc3dace
source-git-commit: b38878ca063967e6c1ae56617674af52c10913df
workflow-type: tm+mt
source-wordcount: '897'
ht-degree: 25%

---

# XDM フィールド

アカウントオーディエンスデータは、XDM ビジネスアカウントと XDM ビジネスユーザーの両方のクラスに属性として保存されます。 Adobe Experience PlatformとJourney Optimizer B2B Edition の間では、データは定期的に同期されます。 次のセクションでは、デフォルトの属性セットを示します。

## XDM ビジネスユーザー属性

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/profile/b2b-person-details.schema.md) | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `b2b.companyName` | 企業名 | 企業名 | 文字列 | ビジネスユーザーが関連付けられている会社の名前。 |
| `b2b.companyWebsite` | 会社の Web サイト | Web サイト | 文字列 | ビジネスユーザーが関連付けられている会社の web サイト。 |
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
| `workEmail.address` | 住所 | メールアドレス | 文字列 | 例えば、技術的アドレス `<name@domain.com>`、RFC2822 および後続の標準で一般的に定義されています。 |
| `workEmail.status` | ステータス | メールの中断 | 文字列 | その電子メールアドレスを使用できるかどうかを示します。 |
| `workPhone.number` | 数字 | 電話番号 | 文字列 | 勤務先の電話番号。 |

## XDM ビジネスアカウント属性

| [プロパティ](https://github.com/adobe/xdm/blob/master/docs/reference/mixins/account/account-details.schema.md) | 表示名 | Journey Optimizer B2B の表示名 | データタイプ | 説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |--------------- |
| `accountBillingAddress.city` | 市区町村 | 市区町村 | 文字列 | 請求先住所で使用される市区町村の名前。 |
| `accountBillingAddress.country` | 国 | 国 | 文字列 | 請求先住所で使用される政府が管理する地域の名前。 `xdm:countryCode` 以外の場合は、自由形式のフィールドであり、どの言語でも国名を持つことができます。 |
| `accountBillingAddress.postalCode` | 郵便番号 | 住所（郵便番号） | 文字列 | 請求先住所の住所の郵便番号。 一部の国には郵便番号がありません。国によっては、郵便番号の一部のみが含まれます。 |
| `accountBillingAddress.region` | 地域 | 住所（地域） | 文字列 | 請求先住所の地域、郡または地区の部分。 |
| `accountBillingAddress.state` | 都道府県 | 都道府県 | 文字列 | 請求先住所の都道府県の名前。 これは自由形式のフィールドです。 |
| `accountBillingAddress.street1` | 住所 1 | 住所 1 | 文字列 | 請求先住所のプライマリの番地レベル情報。通常、アパート番号、ストリート番号、ストリート名が含まれます。 |
| `accountName` | 名前 | 名前 | 文字列 | 会社の名前。 このフィールドには、最大 255 文字まで入力できます。 |
| `accountOrganization.annualRevenue.amount` | 年間収益 | 年間売上高 | 数字 | 組織の年間売上高の推定金額。 |
| `accountOrganization.industry` | 業界 | 業界 | 文字列 | 業界は組織に起因する。 これは自由形式のフィールドで、クエリには構造化された値を使用するか、`xdm:classifier` プロパティを使用することをお勧めします。 |
| `accountOrganization.logoUrl` | ロゴ URL | ロゴ URL | 文字列 | アカウントに関連付けられたソーシャルネットワークプロファイル画像をリクエストする URL を生成するために、Salesforce インスタンスの URL （例：`https://yourInstance.salesforce.com/`）と組み合わせるパス。 生成された URL は、アカウントのソーシャルネットワークプロファイル画像への HTTP リダイレクト（コード 302）を返します。 |
| `accountOrganization.numberOfEmployees` | 従業員数 | 従業員数 | 整数 | 組織の従業員数。 |
| `accountOrganization.SICCode` | SIC コード | SIC コード | 文字列 | 標準産業分類（SIC） コード。事業活動に基づいて会社が属する業種を分類する 4 桁のコードです。 |
| `accountOrganization.website` | Web サイトの URL | ドメイン名 | 文字列 | 組織の web サイトの URL。 |
| `accountPhone.number` | なし | アカウントの電話番号 | 文字列 | アカウントに関連付けられている電話番号。 |
| `accountSourceType` | なし | ソースのタイプ | 文字列 | アカウントのSourceタイプ。 |
