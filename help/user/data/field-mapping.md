---
title: XDM フィールドマッピング
description: AEP XDM Marketo Engage、スキーマおよびJourney Optimizer B2B Edition 間のフィールドマッピングを確認します。
source-git-commit: af287825508b2372f51aa8ea629cc6eda0a50b35
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 20%

---

# XDM フィールドマッピング

のデータ転送サービス（DTS）は、Adobe Experience PlatformからJourney Optimizer B2B Edition にデータを同期する役割を果たします。 DTS は、Experience Platform XDM スキーマフィールドと、Marketo Engage内の同等のスキーマフィールドとのマッピングに依存します。

## XDM ビジネスパーソンのデフォルトフィールドマッピング

| XDM ビジネス担当者 | Marketo Engage人物の表示名 | AJO B2B 人物の表示名 | XDM タイプ | Marketoタイプ | XDM の説明 |
|------------------- |---------------------------------- |--------------------------- |-------- |------------ |--------------- |
| `workAddress.street1` | 住所 | ？ | 文字列 | テキスト | プライマリの番地レベルの情報、アパート番号、通り番号、通り名。 |
| `workAddress.city ` | 市区町村 | 市区町村 | 文字列 | 文字列 | 市区町村の名前。 |
| `b2b.companyName` | 企業名 | ？ | 文字列 | 文字列 | ビジネスユーザーが関連付けられている会社の名前。 |
| `workAddress.country` | 国 | 国 | 文字列 | 文字列 | 政府が管理する領土の名前。 `xdm:countryCode` 以外の場合、これは自由形式のフィールドで、どの言語でも国名を持つことができます。 |
| `person.birthDate` | 生年月日 | 生年月日 | 文字列 | 日 | 個人が誕生した完全な日付。  YYYY-MM-DD |
| `workEmail.address` | メールアドレス | メールアドレス | 文字列 | メール | 技術的アドレス （例：RFC2822 および後続の標準で一般的に定義されている「<name@domain.com>」）。 |
| `workEmail.status` | メールの中断 | メールの中断 | 文字列 | boolean | その電子メールアドレスを使用できるかどうかを示します。 |
| `faxPhone.number` | FAX 番号 | ？ | 文字列 | 電話 | FAX 電話番号。 |
| `person.name.firstName` | 名 | 名 | 文字列 | 文字列 | 名前の言語で最も一般的に受け入れられている、書き順の名前の最初のセグメント。 多くの文化では、これが好ましい個人的または特定の名前です。 firstName プロパティと lastName プロパティが導入され、単純化され、セマンティックでなく、国際化できない方法で名前をモデル化する既存のシステムとの互換性が維持されています。 xdm:fullName の使用は常にお勧めします。 |
| `extendedWorkDetails.jobTitle` | 役職 | 役職 | 文字列 | 文字列 | 人物の役職。 |
| `person.name.lastName` | 姓 | 姓 | 文字列 | 文字列 | 名前の言語で最も一般的に受け入れられている、書き順の名前の最後のセグメント。 多くの文化では、これは継承された姓、姓、父名、または母名です。 firstName プロパティと lastName プロパティが導入され、単純化され、セマンティックでなく、国際化できない方法で名前をモデル化する既存のシステムとの互換性が維持されています。 xdm:fullName の使用は常にお勧めします。 |
| `b2b.personStatus` | リードのステータス | ？ | 文字列 | 文字列 | 人物の現在のマーケティング /販売ステータスを記録するフィールド。 |
| `b2b.isMarketingSuspended` | マーケティング中断 | ？ | boolean | boolean | その人物のマーケティングが中断されているかどうかを示します。 |
| `b2b.marketingSuspendedCause` | マーケティングの中断理由 | ？ | 文字列 | 文字列 | その人物のマーケティングが停止されている場合、このプロパティがその理由となります。 |
| `person.name.middleName` | ミドルネーム | ？ | 文字列 | 電話 | 姓と名の間のミドルネーム、別名または追加の名前。 |
| `mobilePhone.number` | 携帯電話番号 | 携帯電話番号 | 文字列 | 電話 | 携帯電話番号。 |
| `workPhone.number` | 電話番号 | 電話番号 | 文字列 | 電話 | 仕事用電話番号。 |
| `workAddress.postalCode` | 郵便番号 | 郵便番号 | 文字列 | 文字列 | 場所の郵便番号。 郵便番号は、すべての国で利用できるわけではありません。 一部の国では、郵便番号の一部のみが含まれます。 |
| `person.name.courtesyTitle` | 敬称 | ？ | 文字列 | 文字列 | 通常、個人の肩書きの略称、敬称またはあいさつ文。 表題は、冒頭のテキストで氏名の前に使用します。 たとえば、Mr.、Miss、Dr. |
| `workAddress.state` | 都道府県 | 都道府県 | 文字列 | 文字列 | 都道府県の名前。 これは自由形式フィールドです。 |
| `consents.marketing.email.val` | Unsubscribed | Unsubscribed | 文字列 | boolean | unsubscribed が true （例：value = 1）の場合は、`consents.marketing.email.val` を（n）に設定します。 unsubscribed が false （例：value = 0）の場合は、consents.marketing.email.val を null に設定します。 |
| `consents.marketing.email.reason` | 登録解除の理由 | 登録解除の理由 | 文字列 | 文字列 |  |
| `b2b.companyWebsite` | Web サイト | ？ | 文字列 | URL | ビジネスユーザーが関連付けられている会社の web サイト。 |
