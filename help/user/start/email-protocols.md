---
title: トラッキングと E メール配信のプロトコル
description: Journey Optimizer B2B editionでトラッキングおよびメールチャネル機能に使用するために、Marketo Engageでプロトコルを設定する方法を説明します。
feature: Setup
role: Admin
source-git-commit: a8ca8b99ddf33b4a64b42b751f7be798274d0084
workflow-type: tm+mt
source-wordcount: '1798'
ht-degree: 10%

---

# トラッキングと E メール配信のプロトコル

Adobe Journey Optimizer B2B editionは、メールチャネル機能とMarketo Engageのイベントトラッキングを活用します。 制限付きのファイアウォールやプロキシサーバー設定を使用する組織でメール配信が期待どおりに動作することを確認するには、システム管理者が特定のドメインと IP アドレス範囲を許可リストに追加する必要があります。

>[!NOTE]
>
>接続されたMarketo Engageインスタンスを既に使用してマーケティングオペレーションを実行している場合は、これらのプロトコルと設定が既に設定されています。

すべてのMarketo Engageリソースと Web ソケットを有効にするには、次のドメイン（アスタリスクを含む）が許可リストに追加されていることを確認します。

* `*.experience.adobe.com`
* `*.adobe.net`
* `*.marketo.com`
* `*.marketodesigner.com`
* `*.mktoweb.com`

トラッキングとメール配信を確実に行うには、次の手順を実行します。

1. [の DNS レコードを作成 ](#create-dns-records-for-landing-pages-and-email)
1. [SPF と DKIM の設定](#set-up-spf-and-dkim)
1. [DMARCの設定](#set-up-dmarc)
1. [ドメインの MX レコードの設定](#set-up-mx-records-for-your-domain)
1. [許可リストに加えるへの送信 IP アドレスの追加](#outbound-ip-addresses)

## <!-- landing pages and -->E メールの DNS レコードを作成

CNAME レコードを接続すると、マーケターは、トラフィックとコンバージョンを改善する一貫したブランディングを使用して、メール、ランディングページ、ブログの web バージョンをホストできます。 マーケティングに焦点を当てた web アセットをホストするためのMarketo Engageとして、CNAME をルートドメインホストに追加することを強くお勧めします。 管理者は、マーケティングチームと協力して、Marketo Engageを通じて送信されるメールに含まれるトラッキングリンクの CNAME レコードを計画および実装する必要があります。
<!-- As an administrator, you should work with your Marketing team to plan and implement two CNAME records. The first one is for landing page URLs, so that the landing pages appear in URLs that reflect your domain and not Adobe Marketo Engage (the actual host). The second one is for the tracking links that are included in the emails sent through Marketo Engage.

### Add the CNAME for landing pages

Add the landing page CNAME to your DNS record, so that `[YourLandingPageCNAME]` points to the unique account string that is assigned to your landing pages. Log in to your domain registrar's site and enter the landing page CNAME and account string. This entry usually involves three fields:

* Alias: Enter `[YourLandingPageCNAME]`
* Type: CNAME
* Point to: Enter `[MunchkinID].mktoweb.com`
-->

### メールトラッキングリンクの CNAME を追加

メール CNAME を追加して、`[YourEmailCNAME]` が、Marketo Engageによって割り当てられたデフォルトのトラッキングリンクである `[MktoTrackingLink]` を指すようにします。

`[YourEmailCNAME].[YourDomain].com` CNAME 内 `[MktoTrackingLink]`

例：

`pages.abc.com IN CNAME mkto-a0244.com`

>[!NOTE]
>
>`[MktoTrackingLink]` の値は、デフォルトのブランディングドメインにする必要があります。

### SSL 証明書のプロビジョニング

SSL 証明書のプロビジョニングのプロセスを開始するには、[Adobeサポート ](https://experienceleague.adobe.com/home?lang=en&amp;support-tab=home#support){target="_blank"} にお問い合わせください。

このプロセスが完了するまでに最大 3 営業日かかる場合があります。

## SPF と DKIM の設定

マーケティングチームは、DNS リソースレコードに追加する DKIM （ドメインキー識別メール）情報を提供する必要があります。 次の手順に従って、DKIM と SPF （Sender Policy Framework）を設定し、更新されたらマーケティングチームに通知します。

1. SPF を設定するには、DNS エントリに次の行を追加します。

   ```
   [CompanyDomain] IN TXT v=spf1 mx ip4:[CorpIP]  
   include: mktomail.com ~all
   ```

   DNS エントリに既存の SPF レコードがある場合は、次のレコードを追加するだけです。

   ```
   include: mktomail.com
   ```

   `CompanyDomain` を web サイトのメインドメイン（`company.com/` など）に、`CorpIP` を会社のメールサーバーの IP アドレス（`255.255.255.255` など）に置き換えます。 Marketo Engageを通じて複数のドメインからメールを送信する予定がある場合は、ドメインごとにこの行を（1 行に）追加します。

1. DKIM の場合、ドメインごとに DNS リソースレコードを作成します。

   各ドメインのホストレコードと TXT 値を追加します。

   `[DKIMDomain1]`：ホストレコードが `[HostRecord1]` で、TXT 値が `[TXTValue1]` です。

   `[DKIMDomain2]`：ホストレコードが `[HostRecord2]` で、TXT 値が `[TXTValue2]` です。

   Marketo Engageドキュメントの [ 手順 ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"} に従った後、各 DKIM ドメインの `HostRecord` と `TXTValue` をコピーします。 Journey Optimizer B2B editionでドメインを検証できます（[SPF/DKIM](../admin/configure-channels-emails.md#spfdkim) を参照）。

## DMARCの設定

DMARC（Domain-based Message Authentication, Reporting, and Conformance）は、組織がドメインを不正使用から保護するために使用する認証プロトコルです。 SPF や DKIM などの既存の認証プロトコルを拡張して、ドメインで認証エラーが発生した場合に実行するアクションについて受信者サーバーに通知します。 DMARCはオプションですが、ブランドと評判を保護するのに役立つので、強くお勧めします。 Googleや Yahoo などの主要プロバイダーは、2024 年 2 月から、一括送信者にDMARCを使用する必要を課し始めました。

DMARC が機能するには、次の DNS TXT レコードの 1 つ以上が必要です。

* 有効な SPF
* FROM: ドメインの有効な DKIM レコード （Marketo EngageおよびJourney Optimizer B2B editionの場合に推奨）

また、`FROM:` ドメイン用のDMARC固有の DNS TXT レコードも必要です。 オプションで、レポート監視用に組織内でDMARC レポートを配置する場所を指定するメールアドレスを定義できます。

### DMARC ワークフローの例

>[!TIP]
>
>DMARCを _低速なロールアウト_ として実装することをお勧めします。 DMARC ポリシーを `p=none`、`p=quarantine`、`p=reject` にエスカレーションして潜在的な影響を把握し、SPF と DKIM の整合性を緩めるようにDMARC ポリシーを設定します。

DMARC レポートを受け取った場合は、次の操作を行う必要があります。

1. `p=none` を使用して、受け取ったフィードバックとレポートを分析します。 これらのレポートは、受信者に対して、認証に失敗したメッセージに対するアクションを実行せず、メールレポートを送信者に送信するように指示します。

   * 正当なメッセージが認証に失敗する場合は、SPF/DKIM の問題を確認して修正します。

   * SPF または DKIM が整列され、すべての正規メールの認証に合格しているかどうかを確認します。

   * レポートをレビューして、SPF/DKIM ポリシーに基づいて期待される結果が得られることを確認します。

1. ポリシーを `p=quarantine` に調整します。この設定により、認証に失敗したメール（通常、これらのメッセージをスパムフォルダーに配置する）を強制隔離するように受信メールサーバーが指示されます。

   レポートをレビューして、結果が期待どおりであることを確認します。

1. `p=quarantine` レベルのメッセージの動作に満足したら、ポリシーを（`p=reject`）に調整できます。

   拒否ポリシーは、認証に失敗したドメインのメールを拒否（バウンス）するように受信者に指示します。 このポリシーを有効にすると、ドメインで 100% 認証されたと確認されたメールのみが、インボックスの配置のチャンスを得ます。

   >[!CAUTION]
   >
   >このポリシーは慎重に使用し、組織に対して適切かどうかを判断します。

### DMARC レポート

DMARC は、SPF／DKIM に失敗したメールに関するレポートを受信する機能を備えています。認証プロセスの一環として、ISP サービサーによって生成されるレポートは 2 つあります。 送信者は、DMARC ポリシーの RUA/RUF タグを介して、これらのレポートを受け取ることができます。

* **集計レポート（RUA）**:GDPR （一般データ保護規則）に影響を与える可能性のある PII （個人を特定できる情報）が含まれていません。

* **フォレンジックレポート（RUF）** - GDPR に敏感なメールアドレスを含みます。 このレポートを実装する前に、GDPR に準拠する必要のある情報を処理するための組織のポリシーを確認してください。

これらのレポートの主な使用方法は、スプーフィングが試みられたメールの概要を取得することです。これらは非常に技術的なレポートで、サードパーティのツールを介してダイジェストするのが最適です。

### DMARC レコードの例

* 必要最小限のレコード：`v=DMARC1; p=none`

* レポートを受信するために電子メール アドレスにリダイレクトするレコード：`v=DMARC1; p=none;  rua=mailto:emaill@domain.com;  ruf=mailto:email@domain.com`

### DMARC タグ

DMARC レコードには、_DMARC タグ_ と呼ばれる複数のコンポーネントがあります。 各タグには、DMARC の特定の側面を指定する値があります。

| タグ名 | 用途 | 機能 | 例 | デフォルト値 |
|-----------|------------------------|-----------|----------|-----------------------------------|
| `v` | 必須 | バージョンを指定します。 バージョンは 1 つだけなので、固定値は `v=DMARC1` です | V=DMARC1 DMARC1 | DMARC1 |
| `p` | 必須 | DMARC ポリシーを指定します。このポリシーは、認証チェックに失敗したメールを報告、強制隔離または拒否するように受信者に指示します。 | `p=none`、`p=quarantine` または `p=reject` | - |
| `fo` | オプション | ドメイン所有者はレポートオプションを指定できます。 | `0`:SPF と DKIM の両方が失敗した場合にレポートを生成 <br> `1` - SPF または DKIM が失敗した場合にレポートを生成しま <br> `d` - DKIM が失敗した場合のレポートの生成 <br> `s` - SPF が失敗した場合にレポートを生成 | `1` （DMARC レポートの場合に推奨） |
| `pct` | オプション | フィルタリング対象となるメッセージの割合を指定します。 | `pct=20` | `100` |
| `rua` | オプション（推奨） | 集約レポートが配信される場所を指定します。 | `rua=mailto:aggrep@example.com` | - |
| `ruf` | オプション（推奨） | フォレンジックレポートの配信先を指定します。 | `ruf=mailto:authfail@example.com` | - |
| `sp` | オプション | 親ドメインのサブドメインのDMARC ポリシーを指定します。 | `sp=reject` | - |
| `adkim` | オプション | 厳密な配置（`s`）または緩やかな配置（`r`）を指定します。 緩やかな整合性とは、ドメインが DKIM 署名に使用され、`From:` アドレスのサブドメインにできることを意味します。 厳密な整合性とは、ドメインが DKIM 署名に使用されることを意味し、`From:` アドレスで使用されるドメインと完全に一致する必要があります。 | `adkim=r` | `r` |
| `aspf` | オプション | 厳密（`s`）またはリラックス（`r`）のいずれかを指定できます。 Relaxed モードは、Return-Path ドメインが `From:` アドレスのサブドメインであることを意味します。 Strict モードは、Return-Path ドメインが `From:` アドレスと完全に一致する必要があることを意味します。 | `aspf=r` | `r` |

DMARCおよびそのすべてのオプションについて詳しくは、[https://dmarc.org/](https://dmarc.org/){target="_blank"} を参照してください。

### Marketo EngageのためのDMARCの実装

DMARCの整列には、次の 2 種類があります。

* **DKIM** （Domain Keys Identified Mail）の整合性：メールの `From:` ヘッダーで指定されたドメインが DKIM-Signature と一致します。 DKIM 署名には、`From:` ヘッダードメインと照合するためにドメインが指定されている `d=` 値が含まれています。

  DKIM の整合性では、送信者がドメインからのメールを送信する権限があるかどうかを検証し、メールの送信中にコンテンツが変更されていないことを確認します。 DKIM に合わせたDMARCを実装するには：

   * メッセージの MAIL FROM ドメインに DKIM を設定します。 Marketo Engageドキュメントの [ 手順 ](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/email-marketing/deliverability/set-up-a-custom-dkim-signature){target="_blank"} を使用します。

   * ドメインからの DKIM メール用にDMARCを設定します。

  >[!NOTE]
  >
  >Marketo Engageについては、DKIM の整合性をお勧めします。

* **SPF** （Sender Policy Framework）の整合性：`From:` ヘッダーのドメインは、Return-Path: ヘッダーのドメインと一致する必要があります。 両方の DNS ドメインが同じ場合、SPF は一致（アライン）し、合格の結果が得られます。 SPF 調整されたDMARCを実装するには：

   * ブランドの Return-Path ドメインを設定します。

      * 適切な SPF レコードを設定します。
      * メールの送信元のデータセンターのデフォルト MX を指すように MX レコードを変更します

   * ブランドの Return-Path ドメインにDMARCを設定します。

  >[!NOTE]
  >
  >厳密な SPF の関連付けは、Marketo Engageではサポートされておらず、推奨もされていません。

### 専用 IP および共有プール

専用の IP 経由でMarketo Engageを介してメールを送信し、ブランドのリターンパスを実装していない（または実装しているかどうかわからない）場合は、[Adobeサポート ](https://experienceleague.adobe.com/home?lang=en&amp;support-tab=home#support){target="_blank"} でチケットを開きます。

信頼済み IP は IP の共有プールであり、月額 75,000 個未満の送信を行うボリュームの少ないユーザーに対して予約され、専用 IP の対象にはなりません。 これらのユーザーは、ベストプラクティスの要件も満たす必要があります。

* IP の共有プールを使用してMarketo Engage経由でメールを送信している場合は、[ 信頼済み IP の送信範囲プログラムに申し込む ](https://na-sjg.marketo.com/lp/marketoprivacydemo/Trusted-IP-Sending-Range-Program.html){target="_blank"} ことで、信頼済み IP の対象かどうかを確認できます。 Marketo Engageの信頼済み IP から送信する場合、ブランドの return-path が含まれます。 このプログラムで承認された場合は、Adobeサポートに連絡して、ブランドのリターンパスを設定してください。

* 1 か月に 10 万通を超えるメッセージを送信し、共通の IP を使用してMarketo Engageでメールを送信する場合は、Adobeアカウントチーム（アカウントマネージャー）に連絡して、専用の IP を購入してください。

## ドメインの MX レコードの設定

MX レコードを使用すると、メールの送信元のドメインに対するメールを受信して、返信や自動返信を処理することができます。企業ドメインからを送信している場合は、おそらく既に設定されています。 そうでない場合は、通常、会社のドメイン MX レコードにマッピングするように設定できます。

## アウトバウンド IP アドレス

アウトバウンド接続とは、お客様に代わってインターネット上のサーバーにMarketo Engageして行われる接続です。 IT 部門および一部のパートナー/ベンダーは、許可リストを使用してサーバへのアクセスを制限する場合があります。 その場合、Marketo Engage のアウトバウンド IP アドレスブロックを提供し、許可リストに追加してもらう必要があります。

<!-- ### Webhooks

Marketo Engage webhooks are an outbound integration mechanism. When a Smart Campaign executes a _Call Webhook_ flow action, it makes an HTTP request to an external web service. If the web service publisher uses an allowlist on the firewall of the network where the external web service is located, the publisher must add the IP address blocks listed below to their allowlist. For more information, see [Create a webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/administration/additional-integrations/create-a-webhook){target="_blank"} and [Call Webhook](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/core-marketo-concepts/smart-campaigns/flow-actions/call-webhook){target="_blank"} in the Marketo Engage documentation.

### CRM sync

Marketo Engage Salesforce CRM Sync and Microsoft Dynamics Sync are integration mechanisms that make outbound HTTP requests to APIs published by your CRM vendor. Ensure that your IT organization does not block any of the IP address blocks below from accessing your CRM vendor APIs. For more information, see [Add an Existing Salesforce Field to the Marketo Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/salesforce-sync/sfdc-sync-details/add-an-existing-salesforce-field-to-the-marketo-sync){target="_blank"} and [Understanding the Microsoft Dynamics Sync](https://experienceleague.adobe.com/en/docs/marketo/using/product-docs/crm-sync/microsoft-dynamics/understanding-the-microsoft-dynamics-sync){target="_blank"} in the Marketo Engage documentation. -->

## 送信 IP アドレスブロック

次のリストは、アウトバウンドコールを行うすべてのMarketo Engageサーバーをカバーしています。 Marketo Engageからの発信コネクションを受け取るために IP許可リスト、サーバ、ファイアウォール、アクセス制御リスト、セキュリティグループ、サードパーティサービスを設定する場合は、これらのリストを参照してください。

| IP ブロック（CIDR 表記） | 個別の IP アドレス |
| ------------------------ | --------------------- |
| <ul><li>`94.236.119.0/26`</li><li>`103.237.104.0/22`</li><li>`130.248.172.0/24`</li><li>`130.248.173.0/24`</li><li>`130.248.244.88/29`</li><li>`185.28.196.0/22`</li><li>`192.28.144.0/20`</li><li>`192.28.160.0/19`</li><li>`199.15.212.0/22`</li></ul> | <ul><li>`13.237.155.207`</li><li>`13.55.192.247`</li><li>`18.200.201.81`</li><li>`34.247.24.245`</li><li>`35.165.244.220`</li><li>`44.235.171.179`</li><li>`52.20.211.99`</li><li>`52.64.109.86`</li><li>`54.160.246.246`</li><li>`54.212.167.17`</li><li>`54.220.138.65`</li><li>`54.237.141.197`</li><li>`130.248.168.16`</li><li>`130.248.168.17`</li></ul> |
