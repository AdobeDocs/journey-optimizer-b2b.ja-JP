---
title: トラッキングとメール配信のプロトコル
description: Journey Optimizer B2B Edition によるトラッキングとメールチャネル機能の使用のために Marketo Engage でプロトコルを設定する方法について説明します。
feature: Setup, Channels
role: Admin
exl-id: 3d56f147-ad0a-4686-b14e-375c2eca8806
source-git-commit: 4bbe641305065888a59b3e77357e9b39fa6d402e
workflow-type: ht
source-wordcount: '1798'
ht-degree: 100%

---

# トラッキングとメール配信のプロトコル

Adobe Journey Optimizer B2B Edition では、Marketo Engage のメールチャネル機能とイベントトラッキングを活用します。制限的なファイアウォールまたはプロキシサーバー設定を使用する組織でメール配信が期待どおりに機能することを保証するには、システム管理者が特定のドメインと IP アドレス範囲を許可リストに追加する必要があります。

>[!NOTE]
>
>組織が既に接続された Marketo Engage インスタンスを使用してマーケティング業務を実行している場合は、これらのプロトコルと設定は既に適用されています。

すべての Marketo Engage リソースと web ソケットを有効にするには、次のドメイン（アスタリスクを含む）が許可リストに追加されていることを確認します。

* `*.experience.adobe.com`
* `*.adobe.net`
* `*.marketo.com`
* `*.marketodesigner.com`
* `*.mktoweb.com`

トラッキングとメールの配信を確実に行うには、次の手順を実行します。

1. [メールの DNS レコードを作成 ](#create-dns-records-for-landing-pages-and-email)
1. [SPF と DKIM を設定](#set-up-spf-and-dkim)
1. [DMARC を設定](#set-up-dmarc)
1. [ドメインの MX レコードを設定](#set-up-mx-records-for-your-domain)
1. [アウトバウンド IP アドレスを許可リストに追加](#outbound-ip-addresses)

## <!-- landing pages and -->メールの DNS レコードを作成

CNAME レコードを接続すると、マーケターは、トラフィックとコンバージョンを向上させる一貫性のあるブランドで、メール、ランディングページ、ブログの web バージョンをホストできます。マーケティングに焦点を当てた web アセットをホストするために、Marketo Engage のルートドメインホストに CNAME を追加することを強くお勧めします。管理者は、マーケティングチームと連携して、Marketo Engage を通じて送信されるメールに含まれるトラッキングリンクの CNAME レコードを計画および実装する必要があります。
<!-- As an administrator, you should work with your Marketing team to plan and implement two CNAME records. The first one is for landing page URLs, so that the landing pages appear in URLs that reflect your domain and not Adobe Marketo Engage (the actual host). The second one is for the tracking links that are included in the emails sent through Marketo Engage.

### Add the CNAME for landing pages

Add the landing page CNAME to your DNS record, so that `[YourLandingPageCNAME]` points to the unique account string that is assigned to your landing pages. Log in to your domain registrar's site and enter the landing page CNAME and account string. This entry usually involves three fields:

* Alias: Enter `[YourLandingPageCNAME]`
* Type: CNAME
* Point to: Enter `[MunchkinID].mktoweb.com`
-->

### メールトラッキングリンク用の CNAME の追加

`[YourEmailCNAME]` が、Marketo Engage で割り当てられたデフォルトのトラッキングリンクである `[MktoTrackingLink]` を指すように、次の形式でメール CNAME を追加します。

`[YourEmailCNAME].[YourDomain].com` IN CNAME `[MktoTrackingLink]`

例：

`pages.abc.com IN CNAME mkto-a0244.com`

>[!NOTE]
>
>`[MktoTrackingLink]` 値は、デフォルトの[ブランディングドメイン](../admin/configure-channels-emails.md#branding-domains)にする必要があります。

### SSL 証明書のプロビジョニング

SSL 証明書のプロビジョニングのプロセスを開始するには、[アドビサポート](https://experienceleague.adobe.com/home?lang=ja&support-tab=home#support){target="_blank"}にお問い合わせください。

このプロセスが完了するまでに最大 3 営業日かかる場合があります。

## SPF と DKIM を設定

マーケティングチームは、DNS リソースレコードに追加する DKIM（Domain Keys Identified Mail）情報を提供する必要があります。次の手順に従って、DKIM と SPF（Sender Policy Framework）を設定し、更新されたらマーケティングチームに通知します。

1. SPF を設定するには、DNS エントリに次の行を追加します。

   ```
   [CompanyDomain] IN TXT v=spf1 mx ip4:[CorpIP]  
   include: mktomail.com ~all
   ```

   DNS エントリに既に SPF レコードがある場合は、次のコードを追加するだけです。

   ```
   include: mktomail.com
   ```

   `CompanyDomain` を web サイトのメインドメイン（`company.com/` など）に置き換え、`CorpIP` を会社のメールサーバーの IP アドレス（`255.255.255.255` など）に置き換えます。Marketo Engage を通じて複数のドメインからメールを送信する予定の場合は、ドメインごとにこの行を（1 行で）追加します。

1. DKIM の場合は、ドメインごとに DNS リソースレコードを作成します。

   各ドメインのホストレコードと TXT 値を追加します。

   `[DKIMDomain1]`：ホストレコードが `[HostRecord1]` で、TXT 値が `[TXTValue1]` です。

   `[DKIMDomain2]`：ホストレコードが `[HostRecord2]` で、TXT 値が `[TXTValue2]` です。

   Marketo Engage ドキュメントの[手順](https://experienceleague.adobe.com/ja/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"}に従って、各 DKIM ドメインの `HostRecord` と `TXTValue` をコピーします。Journey Optimizer B2B Edition でドメインを検証できます（[SPF／DKIM](../admin/configure-channels-emails.md#spfdkim) を参照）。

## DMARC を設定

DMARC（Domain-based Message Authentication, Reporting, and Conformance）は、組織がドメインを不正使用から保護するのに役立つ認証プロトコルです。SPF や DKIM などの既存の認証プロトコルを拡張し、ドメインで認証エラーが発生した場合に実行するアクションを受信者サーバーに通知します。DMARC はオプションですが、ブランドと評判を保護するのに役立つので、強くお勧めします。Google や Yahoo などの大手プロバイダーは、2024年2月から一括送信者に対して DMARC の使用の義務付けを開始しました。

DMARC が機能するには、次の DNS TXT レコードの 1 つ以上が必要です。

* 有効な SPF
* FROM:ドメインに対する有効な DKIM レコード（Marketo Engage および Journey Optimizer B2B Edition に推奨）

また、`FROM:` ドメインに対する DMARC 固有の DNS TXT レコードも必要です。オプションで、レポートモニタリング用に組織内の DMARC レポートの送信先を指定するメールアドレスを定義できます。

### DMARC ワークフローの例

>[!TIP]
>
>DMARC を&#x200B;_段階的なロールアウト_&#x200B;として実装することをお勧めします。潜在的な影響を理解したら、DMARC ポリシーを `p=none` から `p=quarantine`、さらに `p=reject` へとエスカレートし、DMARC ポリシーを SPF と DKIM に対して Relaxed 整列に設定します。

DMARC レポートを受信した場合は、次の操作を行う必要があります。

1. `p=none` を使用して、受信したフィードバックとレポートを分析します。レポートでは、認証に失敗したメッセージに対して何もアクションを実行せず、送信者にメールレポートを送信するよう受信者に指示します。

   * 正当なメッセージが認証に失敗した場合は、SPF／DKIM の問題を確認して修正します。

   * SPF または DKIM が整列され、すべての正規メールの認証に合格しているかどうかを確認します。

   * レポートを確認して、結果が SPF／DKIM ポリシーに基づいて期待どおりであることを確認します。

1. ポリシーを `p=quarantine` に調整します。これにより、認証に失敗したメールを強制隔離するように受信メールサーバーに通知されます（通常、これらのメッセージはスパムフォルダーに配置されます）。

   レポートを確認して、結果が期待どおりであることを確認します。

1. `p=quarantine` レベルでのメッセージの動作に問題がない場合は、ポリシーを（`p=reject`）に調整できます。

   拒否ポリシーは、認証に失敗したドメインのすべてのメールを拒否（バウンス）するように受信者に指示します。このポリシーを有効にすると、ドメインによって 100％認証されたことが確認されたメールのみがインボックスに配置されます。

   >[!CAUTION]
   >
   >このポリシーは慎重に使用し、組織に対して適切かどうかを判断します。

### DMARC レポート

DMARC は、SPF／DKIM に失敗したメールに関するレポートを受信する機能を備えています。認証プロセスの一環として、ISP サービス業者によって生成されるレポートは 2 つあります。送信者は、DMARC ポリシーの RUA／RUF タグを通じて、これらのレポートを受信できます。

* **集計レポート（RUA）**：GDPR（EU 一般データ保護規則）の対象となる可能性のある PII（個人を特定できる情報）は含まれません。

* **フォレンジックレポート（RUF）** - GDPR の対象となるメールアドレスが含まれます。このレポートを実装する前に、GDPR に準拠する必要がある情報の処理に関する組織のポリシーを確認します。

これらのレポートの主な使用方法は、スプーフィングが試みられたメールの概要を取得することです。これらは高度に技術的なレポートで、サードパーティのツールを使用するのが最も効果的です。

### DMARC レコードの例

* 最低限のレコード：`v=DMARC1; p=none`

* レポートを受信するメールアドレスを指定するレコード：`v=DMARC1; p=none;  rua=mailto:emaill@domain.com;  ruf=mailto:email@domain.com`

### DMARC タグ

DMARC レコードには、_DMARC タグ_&#x200B;と呼ばれる複数のコンポーネントがあります。各タグには、DMARC の特定の側面を指定する値があります。

| タグ名 | 用途 | 機能 | 例 | デフォルト値 |
|-----------|------------------------|-----------|----------|-----------------------------------|
| `v` | 必須 | バージョンを指定します。バージョンは 1 つしかないので、`v=DMARC1` という固定値になります。 | V=DMARC1 DMARC1 | DMARC1 |
| `p` | 必須 | 認証チェックに失敗したメールを報告、強制隔離、却下するように受信者に指示する DMARC ポリシーを指定します。 | `p=none`、`p=quarantine` または `p=reject` | - |
| `fo` | オプション | ドメイン所有者はレポートオプションを指定できます。 | `0`：SPF と DKIM の両方が失敗した場合にレポートを生成<br> `1` - SPF または DKIM のいずれかが失敗した場合にレポートを生成<br> `d` - DKIM が失敗した場合にレポートを生成<br> `s` - SPF が失敗した場合にレポートを生成 | `1`（DMARC レポートに推奨） |
| `pct` | オプション | フィルタリングの対象となるメッセージの割合を指定します。 | `pct=20` | `100` |
| `rua` | オプション（推奨） | 集計レポートが配信される場所を指定します。 | `rua=mailto:aggrep@example.com` | - |
| `ruf` | オプション（推奨） | フォレンジックレポートの配信先を指定します。 | `ruf=mailto:authfail@example.com` | - |
| `sp` | オプション | 親ドメインのサブドメインに対して DMARC ポリシーを指定します。 | `sp=reject` | - |
| `adkim` | オプション | Strict（`s`）整列または Relaxed（`r`）整列を指定します。Relaxed 整列とは、つまり、DKIM 署名で使用されるドメインを `From:` アドレスのサブドメインに指定できます。Strict 整列とは、つまり、DKIM 署名で使用されるドメインを `From:` アドレスで使用するドメインと完全に一致させる必要があります。 | `adkim=r` | `r` |
| `aspf` | オプション | Strict（`s`）または Relaxed（`r`）のいずれかを指定できます。Relaxed モードとは、つまり、Return-Path ドメインを `From:` アドレスのサブドメインに指定できます。Strict モードとは、つまり、Return-Path ドメインを `From:` アドレスと完全に一致させる必要があります。 | `aspf=r` | `r` |

DMARC とそのすべてのオプションについて詳しくは、[https://dmarc.org/](https://dmarc.org/){target="_blank"} を参照してください。

### Marketo Engage の DMARC 実装

DMARC の整列には、次の 2 つのタイプがあります。

* **DKIM**（Domainkeys Identified Mail）整列：メールの `From:` ヘッダーに指定したドメインを DKIM 署名と一致させます。DKIM 署名には、`From:` ヘッダードメインと一致するドメインが指定される `d=` 値が含まれます。

  DKIM 整列では、送信者がドメインからメールを送信する権限を持っているかどうかを検証し、メールの送信中にコンテンツが変更されていないことを確認します。DKIM 整列の DMARC を実装するには：

   * メッセージの MAIL FROM ドメインに対して DKIM を設定します。Marketo Engage ドキュメントの[手順](https://experienceleague.adobe.com/ja/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"}に従います。

   * DKIM MAIL FROM ドメインに対して DMARC を設定します。

  >[!NOTE]
  >
  >Marketo Engage では DKIM 整列をお勧めします。

* **SPF**（Sender Policy Framework）整列：`From:` ヘッダーのドメインを Return-Path: ヘッダーのドメインと一致させる必要があります。両方の DNS ドメインが同じ場合、SPF は一致（整列）し、合格の結果が返されます。SPF 整列の DMARC を実装するには：

   * ブランドの Return-Path ドメインを設定します。

      * 適切な SPF レコードを設定します。
      * メールの送信元となるデータセンターのデフォルトの MX を指すように MX レコードを変更します

   * ブランドの Return-Path ドメインに対して DMARC を設定します。

  >[!NOTE]
  >
  >Strict SPF 整列は Marketo ではサポートされておらず、推奨されてもいません。

### 専用 IP および共有プール

専用 IP を通じて Marketo Engage 経由でメールを送信し、ブランドの Return-Path を実装していない場合（または実装しているかどうかわからない場合）は、[アドビサポート](https://experienceleague.adobe.com/home?lang=ja&support-tab=home#support){target="_blank"}にチケットを開いてください。

信頼できる IP は、月間 75,000 未満の送信を行う低ボリュームユーザー向けに予約されている共有 IP プールで、専用 IP の対象にはなりません。また、これらのユーザーは、ベストプラクティスの要件も満たす必要があります。

* IP の共有プールを使用して Marketo Engage 経由でメールを送信する場合は、[信頼できる IP 送信範囲プログラムに申し込む](https://na-sjg.marketo.com/lp/marketoprivacydemo/Trusted-IP-Sending-Range-Program.html){target="_blank"}ことで、信頼できる IP の対象であるかどうかを確認できます。Marketo Engage の信頼できる IP から送信する場合は、ブランドの Return-Path が含まれます。このプログラムに対して承認された場合は、アドビサポートに連絡して、ブランドの Return-Path を設定してください。

* 毎月 100,000 件を超えるメッセージを送信し、共有 IP を使用して Marketo Engage 経由でメールを送信する場合は、アドビのアカウントチーム（担当のアカウントマネージャー）に連絡して専用 IP を購入してください。

## ドメインの MX レコードを設定

MX レコードを使用すると、メールの送信元のドメインに対するメールを受信して、返信や自動返信を処理できます。会社ドメインから送信する場合は、既に設定されている可能性があります。そうでない場合は、通常、会社ドメインの MX レコードにマッピングするように設定できます。

## アウトバウンド IP アドレス

アウトバウンド接続は、Marketo Engage がユーザーに代わってインターネット上のサーバーに対して行う接続です。IT 組織および一部のパートナー／ベンダーは、許可リストを使用してサーバーへのアクセスを制限する場合があります。その場合、Marketo Engage のアウトバウンド IP アドレスブロックを提供し、許可リストに追加してもらう必要があります。

<!-- ### Webhooks

Marketo Engage webhooks are an outbound integration mechanism. When a Smart Campaign executes a _Call Webhook_ flow action, it makes an HTTP request to an external web service. If the web service publisher uses an allowlist on the firewall of the network where the external web service is located, the publisher must add the IP address blocks listed below to their allowlist. For more information, see [Create a webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/additional-integrations/create-a-webhook){target="_blank"} and [Call Webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-campaigns/flow-actions/call-webhook){target="_blank"} in the Marketo Engage documentation.

### CRM sync

Marketo Engage Salesforce CRM Sync and Microsoft Dynamics Sync are integration mechanisms that make outbound HTTP requests to APIs published by your CRM vendor. Ensure that your IT organization does not block any of the IP address blocks below from accessing your CRM vendor APIs. For more information, see [Add an Existing Salesforce Field to the Marketo Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/salesforce-sync/sfdc-sync-details/add-an-existing-salesforce-field-to-the-marketo-sync){target="_blank"} and [Understanding the Microsoft Dynamics Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/microsoft-dynamics/understanding-the-microsoft-dynamics-sync){target="_blank"} in the Marketo Engage documentation. -->

## アウトバウンド IP アドレスブロック

次のリストには、アウトバウンド呼び出しを行うすべての Marketo Engage サーバーが記載されています。Marketo Engage からの送信接続を受信するために IP 許可リスト、サーバー、ファイアウォール、アクセス制御リスト、セキュリティグループ、サードパーティサービスを設定するには、次のリストを参照してください。

| IP ブロック（CIDR 表記） | 個別の IP アドレス |
| ------------------------ | --------------------- |
| <ul><li>`94.236.119.0/26`</li><li>`103.237.104.0/22`</li><li>`130.248.172.0/24`</li><li>`130.248.173.0/24`</li><li>`130.248.244.88/29`</li><li>`185.28.196.0/22`</li><li>`192.28.144.0/20`</li><li>`192.28.160.0/19`</li><li>`199.15.212.0/22`</li></ul> | <ul><li>`13.237.155.207`</li><li>`13.55.192.247`</li><li>`18.200.201.81`</li><li>`34.247.24.245`</li><li>`35.165.244.220`</li><li>`44.235.171.179`</li><li>`52.20.211.99`</li><li>`52.64.109.86`</li><li>`54.160.246.246`</li><li>`54.212.167.17`</li><li>`54.220.138.65`</li><li>`54.237.141.197`</li><li>`130.248.168.16`</li><li>`130.248.168.17`</li></ul> |
