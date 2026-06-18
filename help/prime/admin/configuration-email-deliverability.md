---
title: メールの配信性とチャネル設定
description: Journey Optimizer B2B Primeのサブドメインデリゲーション、DMARC、SPF、DKIM、IP プール、メールチャネルの設定を行います。
autotag-review: '2026-06-12T22:43:42.799Z'
TQID: 'https://experienceleague.adobe.com/RKZSQkjSRvHixOm2faRT5D-yB00IykXfPO06vvIUQ6k'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: d6e625c1-468f-4d73-9f32-fd1edb87f96bid: f01b5556-e951-40ba-8625-2e3001864f2bid: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2: id: d270a788-eb1d-40ed-b74e-9158ed975b1fid: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 0a877cc1fc0dfd9c3d8271c8f7be6a5e34a69a9a
workflow-type: tm+mt
source-wordcount: 3095
ht-degree: 1%

---

# メールの到達性とチャネル設定

次の情報は、マーケターとメール作成者をサポートするように送信インフラストラクチャを設定する管理者向けです。 配信品質の機能、役割、権限、サブドメイン、認証、IP プール、チャネル設定の設定方法について説明します。

電子メールデザイン領域での電子メールの作成と電子メールコンテンツのオーサリングについて詳しくは、[電子メールオーサリング ](../content/email-authoring.md)を参照してください。

## 主要概念 {#key-concepts}

メールを設定する前に、メールチャネルの配信性機能に適用される次の概念を確認してください。

| 概念 | [!DNL Journey Optimizer B2B Edition] Primeでの意味 |
| ------- | ---------------------- |
| **_チャネル設定_** | 送信者ID、返信先アドレス、サブドメイン、IP プール、メールタイプ（マーケティングまたはトランザクション）、トラッキングなど、ジャーニーのメールアクションに添付する、再利用可能なメール送信設定。 ブランド、事業部門、送信タイプごとに、複数の名前付きチャネル設定を使用できます。 |
| **_サブドメイン_** | Primeを通じてメールを送信するために使用される、送信ドメインのデリゲートされた部分（例：`mail.contoso.com`）。 サブドメインは、B2B マーケティングのレピュテーションを企業メールやトランザクションメールから分離します。 |
| **_IP プール_** | 1つ以上のサブドメインに関連付けられたIP アドレスのグループ。 Primeでは、このリリースでAdobeが管理する共有IP プールをサポートしています。専用IP プールはGA ロードマップに記載されています。 |

## 役割と権限 {#roles-permissions}

[!DNL Journey Optimizer B2B Edition] Primeでは、電子メール機能にロールベースのアクセス制御（RBAC）が使用されています。 権限はAdobe Admin Console（IMS）で管理され、ログイン時に同期されます。 製品管理者は、製品プロファイルに詳細な権限を割り当て、それらの製品プロファイルをユーザーに添付します。

[!DNL Journey Optimizer B2B Edition] Primeの電子メール機能へのアクセスは、次の2つのレイヤーによって制限されています。

1. **機能フラグ （LD）。** LaunchDarkly フラグは、組織で機能全体をオンにするかどうかを制御します。 メールのオーサリングと配信品質は`dx_ajo_btob_channel_foundation`によって制限されています。 このフラグを使用しない場合、権限に関係なく機能は非表示になります。
2. **機能的な権限。** 特定のユーザーが機能の中で読み取りまたは書き込みを行えるかどうかを制御するユーザーレベルの権限。

ほとんどのメール機能は、`view-*` （読み取り）と`manage-*` （書き込み）のパターンに従っています。 ユーザーには、ナビゲーションで機能を表示するための読み取り権限と、その中で作成、編集または削除するための書き込み権限が必要です。

### メール作成権限 {#email-authoring-permissions}

| 機能 | 権限 | できること |
| ---------- | ---------- | -------------- |
| **メールを表示** | `view-b2b-emails` | メールリストの表示、メールの開封、コンテンツの表示（読み取り専用）。 |
| **メールの作成/編集/削除** | `manage-b2b-emails` | 読み取りアクセスに加えて、電子メールの作成、編集、複製、削除もすべて可能です。 ジャーニー内でメールコンテンツを作成する必要があります。 |
| **テンプレートの表示** | `view-b2b-templates` | テンプレートギャラリーでテンプレートを参照してプレビューします（読み取り専用）。 |
| **テンプレートの作成/編集/削除** | `manage-b2b-templates` | 読み取りアクセス権と、保存したテンプレートの作成、編集、削除を備えています。 |
| **フラグメントを表示** | `view-b2b-fragments` | ビジュアルフラグメントの参照とプレビュー（読み取り専用）。 |
| **フラグメントの作成/編集** | `manage-b2b-fragments` | ビジュアルフラグメントを作成、編集できます。 |
| **フラグメントを公開** | `publish-b2b-fragments` | フラグメントを公開して、組織全体でメール作成者が利用できるようにします。 |
| **共有アセットとライブラリアイテムの管理** | `manage-b2b-library-items` | テンプレート、フラグメント、電子メールで使用される共有ライブラリを管理します。 多くの場合、テンプレート/フラグメント管理権限とともに付与されます。 |
| **使用状況ラベルの管理** | `manage-b2b-delete-usage-labels` | ガバナンス用にライブラリ項目に添付されたデータ使用ラベル（DULE）を管理します。 |
| **パッケージの管理** | `manage-b2b-packages` | サンドボックス間でテンプレート、フラグメント、電子メールをバンドルして移動します。 |
| **アセットの表示（PrimeのMarketo Design Studio アセット）** | `view-b2b-assets` | アセットピッカーとプレビュー画像を参照します。 読み取り専用： |
| **アセットの管理** | `manage-b2b-assets` | 読み取りアクセス権と今後のアセット管理施策（Betaスコープ）。 |
| **メッセージデータのエクスポート** | `manage-b2b-message-export` | メールレベルのメッセージデータとレポートを書き出します。 |

個人ジャーニー内で、**電子メールを送信** アクションには`manage-b2b-person-journeys`が必要です（アクションを追加し、ジャーニーをアクティブ化するには）。 メール権限のみを持つユーザーは、コンテンツの作成は可能ですが、ジャーニーにメールを追加することはできません。

### メール配信品質の権限 {#email-deliverability-permissions}

配信性機能（サブドメイン、DMARC、IP プール、抑制リスト、許可リスト、IP ウォームアッププラン、シードリスト）は、管理者レベルの設定です。 これらは、**[!UICONTROL チャネル]** > **[!UICONTROL 電子メール設定]** エリア全体をカバーする2つの権限によって管理されます。

| 機能 | 権限 | できること |
| ---------- | ---------- | -------------- |
| **メール設定の表示** | `view-b2b-email-settings` | サブドメイン、PTR レコード、IP プール、抑制リスト、許可リスト、IP ウォームアッププラン、シードリスト（読み取り専用）を表示します。 |
| **電子メール設定の管理** | `manage-b2b-email-settings` | すべての読み取りアクセスに加えて、サブドメインのデリゲート、DMARCの設定、抑制と許可リストの管理、IP ウォームアッププランとシードリストの管理を行います。 |

メール設定の一部のサブ機能は、抑制リスト （`enable-suppression`）、許可リスト （`enable-allow-list`）、シードリスト （`enable-seedlist-ui`）などのLaunchDarkly フラグによってゲートされます。 サブフィーチャーが組織内に表示されない場合は、フラグの有効化についてAdobe担当者に確認します。

### チャネル設定の権限 {#channel-configuration-permissions}

チャネル設定は、**[!UICONTROL チャネル]**→**[!UICONTROL 一般設定]**&#x200B;の下にあります。 配信品質プリミティブ（サブドメイン、IP プール、送信者ID）を、ジャーニー作成者が参照する再利用可能なオブジェクトに関連付けます。 管理者は、次の1つの権限で管理されます。

| 機能 | 権限 | できること |
| ---------- | ---------- | -------------- |
| **チャネル設定の管理** | `manage-b2b-channels-configurations` | メールチャネル設定を表示、作成、編集、削除します。 |

## 電子メールの配信品質の概要 {#deliverability-overview}

[!DNL Journey Optimizer B2B Edition] Primeの電子メールの配信品質は、電子メールメッセージがスパムフォルダーではなく、受信者の受信トレイに届き、ISP （インターネットサービスプロバイダー）によってブロックされないように支援する、一連のインフラストラクチャと認証設定です。

管理者が設定した次の構成要素を、通常は次の順序で使用します。

1. 1つ以上のサブドメインをAdobeにデリゲートします。
1. 各サブドメインでDMARC、SPF、DKIM レコードを設定します。
1. サブドメインにメールを送信するIP プールを確認します。
1. サブドメイン、IP プール、送信者IDをバインドする、1つ以上のメールチャネル設定を作成します。
1. ジャーニーのメールアクションでこれらのチャネル設定を使用します。

>[!TIP]
>
>配信品質の設定は、事業部門やブランドごとに1回限りの管理者アクティビティとして扱います。 設定されている場合、マーケターとメール作成者は再検討する必要はありません。

## サブドメインデリゲーション {#subdomain-delegation}

サブドメインデリゲーションは、Adobeがドメインの特定のサブドメイン（例：`mail.contoso.com`）の代わりにメールを送信することを許可されていることをインターネットに伝えます。 ルートドメインではなく専用のサブドメインをデリゲートすると、企業のメールが保護され、結果として

* **レピュテーションの分離。** マーケティング送信は、企業メールとは別に管理されます。 マーケティングのレピュテーションが低下しても、トランザクションメールや企業メールは影響を受けません。
* **IP ウォームアップの高速化。** 専用サブドメインは、ISPによる肯定的なレピュテーションの確立に役立ちます。
* **最新の認証。** SPF、DKIM、DMARCは、他のメールフローに影響を与えることなく、サブドメインごとにクリーンに設定できます。
* **コンプライアンス。** GmailやYahooなどの主要なISPからの一括送信者の要件を満たすのに役立ちます。

>[!NOTE]
>
>Primeの各サブドメインは、1つのAdobe製品でのみ使用できます。 Primeと、Adobe Marketo EngageやAdobe Campaignなどの他の製品との間で同じ送信サブドメインを共有することはできません。異なるサブドメインを使用する必要があります。

### サポートされているメソッド

Primeは、Alphaで3つのサブドメインデリゲーション手法のうち2つをサポートしています。 3つ目の方法（カスタム委任）は、ロードマップ上にあります。

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

1. [!DNL Adobe Journey Optimizer B2B Edition] Primeで、**[!UICONTROL 管理]** → **[!UICONTROL チャネル]** → **[!UICONTROL メール設定]** → **[!UICONTROL サブドメイン]**&#x200B;に移動します。
1. **[!UICONTROL サブドメインを設定]**&#x200B;をクリックします。
1. 完全なサブドメイン名を入力します（例：`mail.contoso.com`）。
1. 委任方法として「**[!UICONTROL 完全委任済み]**」を選択します。
1. サブドメイン用にDMARCを設定します（[DMARC、SPF、およびDKIM](#dmarc-spf-dkim)を参照）。

   少なくとも、配信に影響を与えることなくレポートを監視できるように、開始ポリシーが`none`のDMARC レコードを設定します。

1. Adobeで管理するDNS レコードのリストを確認します。

   通常は、MX、SPF、DKIM、DMARC、A、CNAME レコード（トラッキングおよびミラーページ URL用）が含まれます。

1. **[!UICONTROL レコードをダウンロード]** ボタンを使用して、DNS レコードをCSV ファイルとしてダウンロードします。 このファイルをDNS チームと共有します。

1. DNS チームは、サブドメインをAdobeにデリゲートするドメインホスティングソリューションにNS レコードを追加します。

1. DNS チームがレコードが配置されていることを確認したら、[!DNL Journey Optimizer B2B Edition] Primeに戻り、ホスティングサイトで必要なレコードを作成したことを確認するチェックボックスをオンにします。

1. 「**[!UICONTROL 送信]**」をクリックして、一連の検証チェックを開始します（事前検証、MX、SPF、DKIM、DMARC、FBL登録）。

1. サブドメインのステータスが&#x200B;**[!UICONTROL Success]**&#x200B;に変わるのを待ちます。

   これは通常、DNSの伝搬が完了してから数分かかります。

>[!NOTE]
>
>検証が失敗すると、ステータスが&#x200B;**[!UICONTROL 失敗]**&#x200B;および[!DNL Journey Optimizer B2B Edition] Primeに変わり、その理由が表示されます（例えば、NS レコードが見つからなかったり、MX レコードが見つからなかったり、DMARCが設定ミスがあったりします）。 基礎となるDNSの問題を修正してから、送信を再試行してください。

### サブドメインのデリゲート（CNAME メソッド） {#delegate-cname}

この方法は、組織のDNS ポリシーで完全なデリゲーションが禁止されている場合にのみ使用してください。 CNAMEを使用すると、DNS レコードを自分の側で管理できます。

1. [!DNL Adobe Journey Optimizer B2B Edition] Primeで、**[!UICONTROL 管理]** → **[!UICONTROL チャネル]** → **[!UICONTROL メール設定]** → **[!UICONTROL サブドメイン]**&#x200B;に移動します。
1. **[!UICONTROL サブドメインを設定]**&#x200B;をクリックします。
1. 完全なサブドメイン名を入力します。
1. 委任方法として&#x200B;**[!UICONTROL CNAME]**&#x200B;を選択します。
1. サブドメイン （[DMARC、SPF、およびDKIM](#dmarc-spf-dkim)）用にDMARCを設定します。
1. Primeが生成するCNAME レコードのリストを確認します。サブドメインのコンポーネントがAdobeで管理されるレコードにポイントされます。
1. レコードをCSVとしてダウンロードし、DNS チームと共有します。
1. DNS チームは、各CNAME レコードをDNS ホスティングソリューションに追加します。
1. レコードを準備して反映したら、Primeに戻って確定します。 「**[!UICONTROL 送信]**」をクリックします。
1. ステータスが&#x200B;**[!UICONTROL 成功]**&#x200B;に達するのを待ちます。

>[!IMPORTANT]
>
>CNAMEでは、Adobeは、サブドメインのDNSの変更、管理、トラブルシューティングを支援できません。 今後の変更（機能アップデート用の新しいCNAMEの追加など）は、DNS チームが行う必要があります。

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

### DMARC ポリシーモード

| ポリシー | アクション | 使用するタイミング |
| ------ | ------ | ----------- |
| `none` | 監視 | 受信側のサーバーは、DMARCが失敗しても何もしませんが、レポートを送信します。 この機能は、最初にサブドメインをデリゲートして認証が機能していることを確認する際に、メッセージの損失のリスクを回避する場合に使用します。 |
| `quarantine` | 強制隔離 | 受信サーバーは、スパム/迷惑メールフォルダーに失敗したメッセージを配置します。 |
| `reject` | 却下 | 受信サーバーは、認証に失敗したメッセージを拒否（バウンス）します。 厳格なモード： 認証設定に自信があれば、お勧めします。 |

### DMARCの設定 {#configure-dmarc}

DMARCは、サブドメインデリゲーション時に設定されますが、既にデリゲートされたサブドメインに対してDMARCを追加または更新することもできます。

1. **[!UICONTROL 管理]** → **[!UICONTROL チャネル]** → **[!UICONTROL メール設定]** → **[!UICONTROL サブドメイン]**&#x200B;に移動します。

1. サブドメイン リストで、サブドメインを見つけ、DMARC レコード列を確認します。

   レコードが見つからない場合は、アラートが表示されます。

1. サブドメインを開き、「DMARC レコード」セクションまでスクロールします。

   * 親ドメインにDMARC レコードが既に存在する場合、[!DNL Journey Optimizer B2B Edition] Primeは値を自動的に取得します。 保存することも上書きすることもできます。
   * レコードが存在しない場合は、「**[!UICONTROL Adobeで管理]**」を選択し、AdobeがDMARC レコードを作成してホストします。

1. ポリシー`none`、`quarantine`または`reject`を設定します。 親ドメインで成熟したDMARCの姿勢を既に持っていない限り、`none`から開始します。

1. （オプション）追加のDMARC タグを設定します（`sp` サブドメインポリシーの場合、パーセンテージの場合は`pct`、レポートアドレスの場合は`rua`および`ruf`）。

1. 完全委任を使用している場合は、**[!UICONTROL 保存]**&#x200B;をクリックします。

   Adobeは、レコードを自動的に適用します。 CNAMEを使用している場合は、DNS レコードをコピーしてDNS チームに追加してもらい、[!DNL Journey Optimizer B2B Edition] Primeで確認します。

1. DNSの伝搬に最大48時間を許可し、サブドメインページのDMARC ステータスインジケーターが緑色または正常であることを確認します。

>[!TIP]
>
>`policy=none`から開始して認証レポートを監視し、次に`quarantine`に進み、レポートでSPFとDKIMの正常な整合性が確認されたら、最後に`reject`に進みます。 監視せずに`reject`に直接移動すると、正当なメールが拒否される可能性があります。

## IP プール {#ip-pools}

IP プールは、メールの送信に使用されるIP アドレスの名前付きグループです。 IP プールは、送信者のレピュテーションに不可欠です。各プールは、ISPに対して独自のレピュテーションを持つため、あるプールの問題（スパムの苦情をトリガーするマーケティングバーストなど）は、別のプール（トランザクションの確認など）を汚染しません。

### プールタイプ

| プールタイプ | 対応プラットフォーム | 説明 |
| --------- | ------------ | ----------- |
| **共有IP プール** | Alphaで利用可能 | Adobeによって管理され、多くの顧客で共有されるIP アドレスのプール。 レピュテーションは、Adobeによってプール全体で維持されます。 IP ウォームアップを管理したくない低～中程度のメール量と顧客に最適です。 |
| **専用IP プール** | ロードマップ（GA） | 組織にのみ割り当てられた1つ以上のIP アドレス。 自社の評判。 大量の送信者に推奨。 IP ウォームアップ計画とPTR レコード管理が含まれます。 |

### IP プールの確認と割り当て {#review-ip-pool}

このリリースでは、組織にIP プールが事前にプロビジョニングされています。 電子メールチャネル設定を作成する際に、IP プールを割り当てます。

1. **[!UICONTROL 管理]** → **[!UICONTROL チャネル]** → **[!UICONTROL 電子メール設定]** → **[!UICONTROL IP プール]**&#x200B;に移動します。
1. ステータスが&#x200B;**[!UICONTROL Active]**&#x200B;のIP プールが組織で使用可能であることを確認します。
1. プールにカーソルを合わせると、IP アドレスとそのPTR レコード（逆引きDNS）が表示されます。
1. 組織に複数の事業部またはブランドがある場合は、チャネル設定を作成する前に、IP プール（マーケティングプールとウェビナープールなど）の使用方法を計画します。

>[!IMPORTANT]
>
>共有プールが利用可能な場合でも、同じIP プール上でマーケティングトラフィックとトランザクショントラフィックを混在させないでください。 チャネル設定（マーケティングとトランザクション）の「電子メールの種類」設定は、抑制の動作を制御しますが、チャネル設定では可能な限り異なるプールを使用する必要があります。

## メールチャネル設定 {#email-channel-configurations}

チャネル設定とは、送信者ID、サブドメイン、IP プール、トラッキングの設定を結びつける中心的なオブジェクトのことです。 ジャーニーのメールアクションは、チャネル設定を参照して、メッセージの送信方法を把握します。

* **チャネル：**&#x200B;電子メール。
* **メールの種類：** マーケティングまたはトランザクション。 この設定は、抑制ルールが適用されるかどうかを決定します（マーケティング部門が適用します。トランザクションメッセージは、デフォルトでスパム苦情の抑制を回避し、正当なトランザクションメッセージを表示します）。
* **ヘッダーのパラメーター：**&#x200B;名前から、電子メールから、返信先の名前、電子メールに返信、電子メールでエラーが発生しました。
* **サブドメイン：**&#x200B;送信に使用されるデリゲートされたサブドメイン。 差出人メールでは、このサブドメインを使用する必要があります。
* **IP プール：** メッセージの配信に使用されるIP プール。
* **URL トラッキング：** クリックとオープンのトラッキングを有効または無効にします。トラッキングドメインを設定します。
* 組織と検索用の&#x200B;**タグ：** タグ。

### メールチャネル設定の作成 {#create-email-channel-configuration}

>[!PREREQUISITES]
>
>* 少なくとも1つのサブドメインをデリゲートしてアクティブにする必要があります。
>* 少なくとも1つのIP プールを組織に割り当てる必要があります。
>* 管理者の役割が必要です。

1. **[!UICONTROL チャネル]** → **[!UICONTROL 一般設定]** → **[!UICONTROL チャネル設定]**&#x200B;に移動します。
1. 「**[!UICONTROL チャネル設定を作成]**」をクリックします。
1. 名前（例：「Contoso B2B Marketing — North America」）とオプションの説明を入力します。
1. **[!UICONTROL メール]**&#x200B;チャネルの選択
1. オプションで「タグ」を選択して、設定を分類します。
1. 「**[!UICONTROL メールの種類]**」セクションで、「マーケティング」または「トランザクション」を選択します。
1. 「**[!UICONTROL サブドメイン]**」セクションで、以前にデリゲートされたサブドメインを選択します。
1. 「**[!UICONTROL IP プール]**」セクションで、アクティブ IP プールを選択します。 IPにカーソルを合わせると、PTR レコードを表示できます。
1. **[!UICONTROL ヘッダーパラメーター]**&#x200B;を設定します。
   * 名前から（例：「Contoso Marketing」）。
   * 電子メールから – 選択したサブドメインを使用する必要があります（例：`marketing@mail.contoso.com`）。
   * Reply-To Name and Reply-To Email — デフォルトはFrom if blankです。
   * Error Email – 配信以外の通知を受信するアドレス。
1. **[!UICONTROL URL トラッキング]**&#x200B;を有効にし、トラッキングドメインを選択します。
1. 「**[!UICONTROL 送信]**」をクリックします。
1. Primeは、サブドメインステータス、MX レコード、SPF/DKIM/DMARCの整合性、IP プールの準備状況、FBL登録の検証を実行します。 設定はドラフト→処理→アクティブを通じて移動します。

>[!NOTE]
>
>検証が失敗した場合、設定は&#x200B;**[!UICONTROL 失敗]** ステータスに移動します。 エラーの理由を表示するには、コンフィギュレーションを開きます。一般的な原因は、MX レコードの検証エラー、プール内のIPがコンフィギュレーションと一致しない、またはDMARCの不整合です。 解決して再送信。

### チャネル設定の編集または削除 {#edit-channel-configuration}

チャンネル設定は作成後に編集できますが、次の重要な制約があります。

* **チャネルを変更できません。** 設定はそのチャネルにバインドされます。

使用中の設定を編集する場合：

* **公開されたジャーニー：**&#x200B;の場合、変更は次の繰り返しまたは次の実行に適用されます。 実行中の実行は、以前の設定に続きます。
* **トランザクションメッセージまたはリアルタイムメッセージの場合：**&#x200B;件の変更が約5分以内に反映されます。

設定を削除するには、最初に設定を参照するすべてのメールアクションを削除または更新します。[!DNL Journey Optimizer B2B Edition] Primeは、アクティブなジャーニーで現在使用されている設定を削除しません。

### 複数のチャネル設定 {#multiple-channel-configurations}

多くのB2B企業では、複数のチャネル構成を使用して、ブランド、地域、送信タイプを分けています。 共通パターン：

* 事業部門ごとに個別のマーケティング設定（例：*BU-A Marketing*、*BU-B Marketing*）。
* 専用のトランザクション設定で、メールタイプ =製品または契約通知のトランザクションタイプを指定します。
* 地域のISPとコンプライアンスに合わせて、地域固有のサブドメイン（例：`mail.eu.contoso.com`、`mail.us.contoso.com`）を使用する地域固有の設定。

>[!TIP]
>
>明確で構造化された規則で設定に名前を付けます。例：*[ブランド ] - [地域] - [種類]*。 設定が12種類以上ある場合、これは非常に重要になります。

### 既知の制限事項 {#known-limitations}

* サブドメインのデリゲーション用の&#x200B;**カスタム デリゲーション メソッド**&#x200B;はまだ使用できません。完全委任またはCNAMEを使用してください。 カスタム委任はGAをターゲットにしています。
* **専用IP プール**&#x200B;は、Alphaでは利用できません。 共有IP プールは唯一のオプションです。 専用IPは、IP ウォームアッププランニングやPTR レコード管理など、GAに搭載されます。
* **Alphaでは、.htmlまたは.zip アップロード**&#x200B;を介したHTMLの読み込みが制限されています。 Betaには、コードエディターとビジュアルキャンバスのデュアルビュー、検証、インライン CSSの自動変換など、HTMLの包括的な読み込み機能が搭載されています。
* Primeの&#x200B;**ネイティブ画像のアップロードとDAM** （アップロード、整理、編集）は、Beta ロードマップに掲載されています。 このリリースでは、Marketo Design Studio アセットを使用します。 Marketoでの再アップロードは、Primeには反映されません。
* **テストプロファイル、コンテンツのシミュレート、プルーフの送信**&#x200B;は、このリリースでは使用できません。 LitmusのレンダリングとSpamAssassin ベースのスパムレポートは、Betaのロードマップに掲載されています。
* **アカウントレベルのパーソナライゼーションとカスタムオブジェクトデータ**&#x200B;は、このリリースでは使用できません。 プロファイル属性の利用：
* 既存のMarketo テンプレートの&#x200B;**Velocity-to-Handlebars自動移行**&#x200B;は、一般公開されます。
* **電子メールに関するコメントと共同作業** （インラインコメント、@mentions、リクエストとレビューのワークフロー）は、高速フォローアップリリースに含まれます。
* **AEM Assets、AEM コンテンツフラグメント、Adobe Express**&#x200B;の統合は、高速フォローアップロードマップに載っています。

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
