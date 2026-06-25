---
title: メール配信品質の設定
description: Journey Optimizer B2B Primeのサブドメインデリゲーション、DMARC、SPF、DKIM、IP プールを設定します。
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、限定的なベータ版リリースの一部です。"
autotag-review: '2026-06-12T22:43:42.799Z'
TQID: 'https://experienceleague.adobe.com/RKZSQkjSRvHixOm2faRT5D-yB00IykXfPO06vvIUQ6k'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 6227b7f64baf307e3778e73bcceabb140ab65fb8
workflow-type: tm+mt
source-wordcount: 1920
ht-degree: 1%

---

# メールの配信品質

次の情報は、マーケターとメールコンテンツ作成者をサポートするように送信インフラストラクチャを設定する管理者向けです。 配信品質の機能と、サブドメイン、認証、IP プールの設定方法について説明します。 メールチャネルについて詳しくは、次のトピックを参照してください。

* 電子メールチャネルの設定 – [電子メールチャネル設定](../admin/email-channel-configuration.md)
* メールの作成 – [&#x200B; ジャーニーにメールを追加](../marketing/email-channel.md)
* 電子メールコンテンツのデザイン - [電子メールコンテンツのオーサリング &#x200B;](../content/email-authoring.md)。

[!DNL Journey Optimizer B2B Prime]の電子メールの配信品質は、電子メールメッセージが迷惑メールフォルダーではなく受信者の受信トレイに届き、ISP （インターネットサービスプロバイダー）によってブロックされないように支援する、一連のインフラストラクチャと認証設定です。

管理者が設定した次の構成要素を、通常は次の順序で使用します。

1. [1つ以上のサブドメイン &#x200B;](#subdomain-delegation)をAdobeにデリゲートします。
1. [各サブドメインでDMARC、SPF、DKIM レコード &#x200B;](#dmarc-spf-dkim)を設定します。
1. [&#x200B; サブドメインのメール送信に使用するIP プール &#x200B;](#ip-pools)を確認します。
1. [&#x200B; サブドメイン、IP プール、送信者IDをバインドする1つ以上の電子メールチャネル設定](../admin/email-channel-configuration.md#create-email-channel-configuration)を作成します。

![Journey Optimizer B2B Primeのメール配信品質の設定](./assets/email-deliverability-diagram.svg){width="450" zoomable="yes"}

>[!TIP]
>
>配信品質とチャネル設定を1回限りの管理者アクティビティとして扱います。 設定されている場合、マーケターとメール作成者は再検討する必要はありません。

## 現在の制限事項 {#limitations}

* サブドメインのデリゲーション用の&#x200B;**カスタム デリゲーション メソッド**&#x200B;はまだ使用できません。完全委任またはCNAMEを使用してください。 カスタム委任は、GA リリースを対象としています。
* **専用IP プール**&#x200B;は、Betaでは利用できません。 共有IP プールは唯一のオプションです。 専用IPは、IP ウォームアッププランニングやPTR レコード管理など、GAに搭載されます。

## 主要概念 {#key-concepts}

メールを設定する前に、メールチャネルの配信性機能に適用される次の概念を確認してください。

| 概念 | [!DNL Journey Optimizer B2B Prime]の意味 |
| ------- | ---------------------- |
| **_サブドメイン_** | Primeを通じてメールを送信するために使用される、送信ドメインのデリゲートされた部分（例：`mail.contoso.com`）。 サブドメインは、B2B マーケティングのレピュテーションを企業メールやトランザクションメールから分離します。 |
| **_IP プール_** | 1つ以上のサブドメインに関連付けられたIP アドレスのグループ。 Primeでは、このリリースでAdobeが管理する共有IP プールをサポートしています。専用IP プールはGA ロードマップに記載されています。 |
| **_チャネル設定_** | ジャーニーのメールアクションに添付する、再利用可能なメール送信設定（送信者ID、返信先アドレス、サブドメイン、IP プール、メールタイプ、トラッキング）。 ブランド、事業部門、送信タイプごとに、複数の名前付きチャネル設定を使用できます。 |

<!--

## Roles and permissions {#roles-permissions}

[!DNL Journey Optimizer B2B Prime] uses role-based access control (RBAC) for email features. Permissions are managed in the Adobe Admin Console (IMS) and synced at login. Product administrators assign granular permissions to product profiles, and then attach those product profiles to users.

Access to email functionality in [!DNL Journey Optimizer B2B Prime] is gated by two layers:

1. **Feature flag (LD).** A LaunchDarkly flag controls whether the entire feature is turned on for your organization. Email authoring and deliverability are gated by `dx_ajo_btob_channel_foundation`. Without this flag, the feature is hidden regardless of permissions.
2. **Functional permission.** A user-level permission that controls whether a specific user can read or write within a feature.

Most email features follow a `view-*` (read) and `manage-*` (write) pattern. A user needs the read permission to see a feature in the navigation, and the write permission to create, edit, or delete within it.

### Email authoring permissions {#email-authoring-permissions}

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View emails** | `view-b2b-emails` | View the email list, open emails, view content (read-only). |
| **Create / edit / delete emails** | `manage-b2b-emails` | All read access plus create, edit, duplicate, and delete emails. Required to author email content within a journey. |
| **View templates** | `view-b2b-templates` | Browse and preview templates in the Templates gallery (read-only). |
| **Create / edit / delete templates** | `manage-b2b-templates` | All read access plus create, edit, and delete saved templates. |
| **View fragments** | `view-b2b-fragments` | Browse and preview visual fragments (read-only). |
| **Create / edit fragments** | `manage-b2b-fragments` | All read access plus create and edit visual fragments. |
| **Publish fragments** | `publish-b2b-fragments` | Publish a fragment so it becomes available to email authors across the organization. |
| **Manage shared assets and library items** | `manage-b2b-library-items` | Manage the underlying shared library used by templates, fragments, and emails. Often granted alongside the template/fragment manage permissions. |
| **Manage usage labels** | `manage-b2b-delete-usage-labels` | Manage data usage labels (DULE) attached to library items for governance. |
| **Manage packages** | `manage-b2b-packages` | Bundle and move templates, fragments, and emails between sandboxes. |
| **View assets (Marketo Design Studio assets in Prime)** | `view-b2b-assets` | Browse the asset picker and preview images. Read-only. |
| **Manage assets** | `manage-b2b-assets` | All read access plus future asset-management actions (Beta scope). |
| **Export message data** | `manage-b2b-message-export` | Export email-level message data and reports. |

Within a person journey, the **Send email** action requires `manage-b2b-person-journeys` (to add the action and activate the journey). A user with only email permissions can author content but cannot add an email to a journey.

### Email deliverability permissions {#email-deliverability-permissions}

Deliverability features (subdomains, DMARC, IP pools, suppression lists, allowed lists, IP warmup plans, and seed lists) are administrator-level configuration. They are governed by two permissions covering the entire **[!UICONTROL Channels]** > **[!UICONTROL Email settings]** area:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **View email settings** | `view-b2b-email-settings` | View subdomains, PTR records, IP pools, suppression list, allowed list, IP warmup plans, and seed lists (read-only). |
| **Manage email settings** | `manage-b2b-email-settings` | All read access plus delegate subdomains, configure DMARC, manage suppression and allowed lists, manage IP warmup plans and seed lists. |

Some sub-features within Email settings are gated by additional LaunchDarkly flags — Suppression list (`enable-suppression`), Allowed list (`enable-allow-list`), Seed lists (`enable-seedlist-ui`). If a sub-feature is not visible in your organization, check with your Adobe representative on flag enablement.

### Channel configuration permissions {#channel-configuration-permissions}

Channel configurations sit under **[!UICONTROL Channels]** → **[!UICONTROL General settings]**. They tie deliverability primitives (subdomain, IP pool, sender identity) to a reusable object that journey authors reference. They are governed by a single permission:

| Capability | Permission | What it allows |
| ---------- | ---------- | -------------- |
| **Manage channel configurations** | `manage-b2b-channels-configurations` | View, create, edit, and delete email channel configurations. |

-->

## サブドメインデリゲーション {#subdomain-delegation}

サブドメインデリゲーションは、Adobeがドメインの特定のサブドメイン（例：`mail.contoso.com`）の代わりにメールを送信することを許可されていることをインターネットに伝えます。 ルートドメインではなく専用のサブドメインをデリゲートすると、企業のメールが保護され、次のメリットが得られます。

* **レピュテーションの分離。** マーケティング送信は、企業メールとは別に管理されます。 マーケティングのレピュテーションが低下しても、トランザクションメールや企業メールは影響を受けません。
* **IP ウォームアップの高速化。** 専用サブドメインは、ISPによる肯定的なレピュテーションの確立に役立ちます。
* **最新の認証。** SPF、DKIM、DMARCは、他のメールフローに影響を与えることなく、サブドメインごとにクリーンに設定できます。
* **コンプライアンス。** GmailやYahooなどの主要なISPからの一括送信者の要件を満たすのに役立ちます。

>[!NOTE]
>
>Primeの各サブドメインは、1つのAdobe製品でのみ使用できます。 Primeと、Adobe Marketo EngageやAdobe Campaignなどの他の製品との間で同じ送信サブドメインを共有することはできません。異なるサブドメインを使用する必要があります。

### サポートされているメソッド {#supported-methods}

Primeは、このBeta リリースで3つのサブドメインデリゲーション手法のうち2つをサポートしています。 3つ目の方法（カスタム委任）は、ロードマップ上にあります。

| メソッド | 使用するタイミング | このプロセスの内容 |
| ------ | ----------- | ---------------- |
| **完全に委任** | 推奨 | サブドメインの完全なDNS権限をAdobeに委任します。 Adobeは、MX、SPF、DKIM、DMARC、A、およびCNAME レコードを作成および管理します。 運用オーバーヘッドを低減。 AdobeがDNSの変更を処理します。 |
| **CNAME** | 制限付きポリシーの場合 | DNS権限を維持し、Adobeで管理されるレコードを指すCNAME レコードを作成します。 組織のDNS ポリシーで完全なデリゲーションが許可されていない場合に使用します。 DNS レコードを管理する責任があります。 |
| **カスタム委任** | ロードマップ（GA） | DNS証明書とSSL証明書の完全な所有権を維持する。 独自の証明書を使用する機能など、最大限の制御を提供します。 これはGA リリースを対象としています。 |

### サブドメインのデリゲート（完全デリゲート済みメソッド） {#delegate-fully-delegated}

>[!PREREQUISITES]
>
>* サブドメインの命名規則を決定します（たとえば、マーケティングの場合は`mail.contoso.com`、トランザクションの場合は`alerts.contoso.com`）。
>* IT/DNS チームがサブドメイン（NS レコード）をAdobeにデリゲートできることを確認します。
>* DNS プロバイダーで新しいサブドメインを作成してから、DNSの伝搬を24～48時間待ってから、Adobeにデリゲートします。
>* Primeで管理者の役割を持っていることを確認します。

1. 左側の[!DNL Adobe Journey Optimizer B2B Prime] ナビゲーションで、**[!UICONTROL 管理]**&#x200B;を展開し、**[!UICONTROL チャネル]**&#x200B;を選択します。
1. パネルで、**[!UICONTROL メール設定]**&#x200B;を展開し、**[!UICONTROL サブドメイン]**&#x200B;を選択します。
1. **[!UICONTROL サブドメインを設定]**&#x200B;をクリックします。
1. 完全なサブドメイン名を入力します（例：`mail.contoso.com`）。
1. 委任方法として「**[!UICONTROL 完全委任済み]**」を選択します。
1. サブドメイン用にDMARCを設定します（[DMARC、SPF、およびDKIM](#dmarc-spf-dkim)を参照）。

   少なくとも、配信に影響を与えることなくレポートを監視できるように、開始ポリシーが`none`のDMARC レコードを設定します。

1. Adobeで管理するDNS レコードのリストを確認します。

   通常は、MX、SPF、DKIM、DMARC、A、CNAME レコード（トラッキングおよびミラーページ URL用）が含まれます。

1. **[!UICONTROL レコードをダウンロード]** ボタンを使用して、DNS レコードをCSV ファイルとしてダウンロードします。 このファイルをDNS チームと共有します。

1. DNS チームは、サブドメインをAdobeにデリゲートするドメインホスティングソリューションにNS レコードを追加します。

1. DNS チームがレコードが配置されていることを確認したら、[!DNL Journey Optimizer B2B Prime]に戻り、ホスティングサイトで必要なレコードを作成したことを確認するチェックボックスをオンにします。

1. 「**[!UICONTROL 送信]**」をクリックして、一連の検証チェックを開始します（事前検証、MX、SPF、DKIM、DMARC、FBL登録）。

1. サブドメインのステータスが&#x200B;**[!UICONTROL Success]**&#x200B;に変わるのを待ちます。

   これは通常、DNSの伝搬が完了してから数分かかります。

>[!NOTE]
>
>検証が失敗すると、ステータスが&#x200B;**[!UICONTROL 失敗]**&#x200B;および[!DNL Journey Optimizer B2B Prime]に変わり、その理由が表示されます（例えば、NS レコードが見つからなかったり、MX レコードが見つからなかったり、DMARCが設定ミスがあったりします）。 基礎となるDNSの問題を修正してから、送信を再試行してください。

### サブドメインのデリゲート（CNAME メソッド） {#delegate-cname}

この方法は、組織のDNS ポリシーで完全なデリゲーションが禁止されている場合にのみ使用してください。 CNAMEを使用すると、DNS レコードを自分の側で管理できます。

1. 左側の[!DNL Adobe Journey Optimizer B2B Prime] ナビゲーションで、**[!UICONTROL 管理]**&#x200B;を展開し、**[!UICONTROL チャネル]**&#x200B;を選択します。
1. パネルで、**[!UICONTROL メール設定]**&#x200B;を展開し、**[!UICONTROL サブドメイン]**&#x200B;を選択します。
1. **[!UICONTROL サブドメインを設定]**&#x200B;をクリックします。
1. 完全なサブドメイン名を入力します。
1. 委任方法として&#x200B;**[!UICONTROL CNAME]**&#x200B;を選択します。
1. サブドメイン （[DMARC、SPF、およびDKIM](#dmarc-spf-dkim)）用にDMARCを設定します。
1. 生成するCNAME レコードのリストを確認します。 これにより、サブドメインのコンポーネントが、Adobeで管理されるレコードにポイントされます。
1. レコードをCSVとしてダウンロードし、DNS チームと共有します。
1. DNS チームは、各CNAME レコードをDNS ホスティングソリューションに追加します。
1. レコードが配置され、伝播されたら、[!DNL Adobe Journey Optimizer B2B Prime]に戻って確認します。
1. 「**[!UICONTROL 送信]**」をクリックします。
1. ステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;に達するのを待ちます。

>[!IMPORTANT]
>
>CNAMEでは、Adobeは、サブドメインのDNSの変更、管理、トラブルシューティングを支援できません。 機能アップデート用に新しいCNAMEを追加するなど、今後の変更は、DNS チームが行う必要があります。

### サブドメインのガードレール {#subdomain-guardrails}

* **既定の制限：** 10個のサブドメイン （組織あたり）。 詳細が必要な場合は、Adobe担当者にお問い合わせください（契約によって最大100件）。
* **DNSの伝搬：**&#x200B;変更がグローバルに伝搬されるまで24～48時間かかります。 DNSがまだ伝播されていないため、検証が失敗する可能性があります。
* **サブドメインの再利用：**&#x200B;別のAdobe製品（Marketo Engage、Adobe Campaign）で既に使用されているサブドメインは、Primeで再利用できません。

## DMARC、SPF、DKIM {#dmarc-spf-dkim}

DMARC、SPF、DKIMは、メール認証の標準です。 これらを組み合わせることで、メールサーバーを受信した際に、メッセージがドメインの代理として本当に送信され、スプーフィングされていないことを証明できます。 Gmail、Yahoo、Microsoftなどの最新のISPでは、一括送信者にこれらの標準が必要です。

| レコード | は次の意味です | 目的 |
| ------ | ---------- | ------- |
| **SPF** | Sender Policy Framework | ドメインからメールを送信できるメールサーバーIPを一覧表示します。 受信サーバーは、このリストに含まれていないIPからのメールを拒否します。 Adobeは、サブドメインをデリゲートする際に、SPF レコードを自動的に作成および管理します（完全委任）。 |
| **DKIM** | DomainKeys Identified Mail | すべての送信メールに追加された暗号署名。 受信サーバーは、DNSで公開された公開鍵に対して署名を検証します。 Adobeは、サブドメインのデリゲーション中に、DKIM キーとDNS レコードを自動的に生成します。 |
| **DMARC** | Domain-based Message Authentication, Reporting &amp; Conformance | SPFまたはDKIMが失敗した場合に何をすべきかをサーバーに伝え、認証結果に関するレポートを提供します。 DMARCには、「なし」、「強制隔離」、「却下」の3つのポリシーモードがあります。 |

### DMARC ポリシーモード {#dmarc-policy-modes}

| ポリシー | アクション | 使用するタイミング |
| ------ | ------ | ----------- |
| `none` | 監視 | 受信側のサーバーは、DMARCが失敗しても何もしませんが、レポートを送信します。 この機能は、最初にサブドメインをデリゲートして認証が機能していることを確認する際に、メッセージの損失のリスクを回避する場合に使用します。 |
| `quarantine` | 強制隔離 | 受信サーバーは、スパム/迷惑メールフォルダーに失敗したメッセージを配置します。 |
| `reject` | 却下 | 受信サーバーは、認証に失敗したメッセージを拒否（バウンス）します。 厳格なモード： 認証設定に自信があれば、お勧めします。 |

### DMARCの設定 {#configure-dmarc}

DMARCは、サブドメインデリゲーション時に設定されますが、既にデリゲートされたサブドメインに対してDMARCを追加または更新することもできます。

1. 左側の[!DNL Adobe Journey Optimizer B2B Prime] ナビゲーションで、**[!UICONTROL 管理]**&#x200B;を展開し、**[!UICONTROL チャネル]**&#x200B;を選択します。

1. パネルで、**[!UICONTROL メール設定]**&#x200B;を展開し、**[!UICONTROL サブドメイン]**&#x200B;を選択します。

1. サブドメイン リストで、サブドメインを見つけ、DMARC レコード列を確認します。

   レコードが見つからない場合は、アラートが表示されます。

1. サブドメインを開き、「DMARC レコード」セクションまでスクロールします。

   * 親ドメインにDMARC レコードが既に存在する場合、[!DNL Journey Optimizer B2B Prime]は値を自動的に取得します。 保存することも上書きすることもできます。
   * レコードが存在しない場合は、「**[!UICONTROL Adobeで管理]**」を選択し、AdobeがDMARC レコードを作成してホストします。

1. ポリシー`none`、`quarantine`または`reject`を設定します。 親ドメインで成熟したDMARCの姿勢を既に持っていない限り、`none`から開始します。

1. （オプション）追加のDMARC タグを設定します（`sp` サブドメインポリシーの場合、パーセンテージの場合は`pct`、レポートアドレスの場合は`rua`および`ruf`）。

1. 完全委任を使用している場合は、**[!UICONTROL 保存]**&#x200B;をクリックします。

   Adobeは、レコードを自動的に適用します。 CNAMEを使用している場合は、DNS レコードをコピーしてDNS チームに追加してもらい、[!DNL Journey Optimizer B2B Prime]で確認します。

1. DNSの伝搬に最大48時間を許可し、サブドメインページのDMARC ステータスインジケーターが緑色または正常であることを確認します。

>[!TIP]
>
>`policy=none`から開始して認証レポートを監視し、次に`quarantine`に進み、レポートでSPFとDKIMの正常な整合性が確認されたら、最後に`reject`に進みます。 監視せずに`reject`に直接移動すると、正当なメールが拒否される可能性があります。

## IP プール {#ip-pools}

IP プールは、メールの送信に使用されるIP アドレスの名前付きグループです。 IP プールは、送信者のレピュテーションに不可欠です。各プールは、ISPに対して独自のレピュテーションを持つため、あるプールの問題（スパムの苦情をトリガーするマーケティングバーストなど）は、別のプール（トランザクションの確認など）を汚染しません。

### プールタイプ {#pool-types}

| プールタイプ | 対応プラットフォーム | 説明 |
| --------- | ------------ | ----------- |
| **共有IP プール** | Betaで利用可能 | Adobeによって管理され、多くの顧客で共有されるIP アドレスのプール。 レピュテーションは、Adobeによってプール全体で維持されます。 IP ウォームアップを管理したくない低～中程度のメール量と顧客に最適です。 |
| **専用IP プール** | ロードマップ（GA） | 組織にのみ割り当てられた1つ以上のIP アドレス。 自社の評判。 大量の送信者に推奨。 IP ウォームアップ計画とPTR レコード管理が含まれます。 |

### IP プールの確認と割り当て {#review-ip-pool}

このリリースでは、組織にIP プールが事前にプロビジョニングされています。 電子メールチャネル設定を作成する際に、IP プールを割り当てます。

1. 左側の[!DNL Adobe Journey Optimizer B2B Prime] ナビゲーションで、**[!UICONTROL 管理]**&#x200B;を展開し、**[!UICONTROL チャネル]**&#x200B;を選択します。
1. パネルで、**[!UICONTROL メール設定]**&#x200B;を展開し、**[!UICONTROL IP プール]**&#x200B;を選択します。
1. ステータスが&#x200B;**[!UICONTROL Active]**&#x200B;のIP プールが組織で使用可能であることを確認します。
1. プールにカーソルを合わせると、IP アドレスとそのPTR レコード（逆引きDNS）が表示されます。
1. 組織に複数の事業部またはブランドがある場合は、チャネル設定を作成する前に、IP プール（マーケティングプールとウェビナープールなど）の使用方法を計画します。

>[!IMPORTANT]
>
>共有プールが利用可能な場合でも、同じIP プール上でマーケティングトラフィックとトランザクショントラフィックを混在させないでください。 チャネル設定（マーケティングとトランザクション）の「電子メールの種類」設定は、抑制の動作を制御しますが、チャネル設定では可能な限り異なるプールを使用する必要があります。

<!--

### Frequently asked questions {#faq}

| Question | Answer |
| -------- | ------ |
| **Can I reuse the subdomain I already use in Marketo Engage?** | No. A subdomain can only be associated with one Adobe product at a time. Create a new subdomain (for example, mail2.contoso.com) for Prime. |
| **Why does my channel configuration show Failed?** | The most common reasons are: MX record validation failed (your subdomain DNS isn't fully configured); DMARC misalignment; or an IP pool that is in Processing and has never been associated with the selected subdomain. Open the configuration to see the specific reason. |
| **What happens if a personalization token has no value at send time?** | If you defined a fallback with the Handlebars `default` helper, the fallback is used. If not, the token resolves to an empty string. Prime warns you when a token has no fallback and the underlying attribute is not guaranteed by the audience definition. |
| **Can I personalize using account-level attributes?** | Not in this release. Personalization in Prime today supports profile attributes only. |
| **What's the maximum email size?** | 100 KB is the recommended best-practice cap for inbox rendering. Prime warns you in the editor if you exceed it. |
| **Can I migrate existing Marketo email templates into Prime?** | A guided self-serve migration tool — including Velocity-to-Handlebars conversion — is delivered at GA. In this release, you can manually rebuild templates or paste raw HTML. |
| **Will my updates to Marketo assets show up in Prime?** | No. Asset availability in Prime is based on a one-time copy from Marketo Design Studio. Re-uploaded or modified Marketo assets are not reflected in Prime today. Native asset upload and management within Prime is on the Beta roadmap. |

## Glossary {#glossary}

| Term | Definition |
| ---- | ---------- |
| **DKIM** | DomainKeys Identified Mail — cryptographic email signature. |
| **DMARC** | Domain-based Message Authentication, Reporting & Conformance. |
| **FBL** | Feedback Loop — a service ISPs offer to receive spam-complaint reports back to senders. |
| **Handlebars** | JavaScript templating language used in Prime for personalization expressions. |
| **IP pool** | Group of IP addresses used to send email. |
| **MX record** | Mail Exchange DNS record — directs incoming mail to the correct mail servers. |
| **NS record** | Name Server DNS record — used to delegate a subdomain. |
| **PTR record** | Pointer record — reverse DNS that maps an IP address back to a hostname. |
| **RBAC** | Role-Based Access Control. |
| **SPF** | Sender Policy Framework — DNS record listing authorized sending IPs. |
| **Subdomain delegation** | Granting Adobe authority over a portion of your domain (a subdomain) for sending email. |

-->

