---
title: アーキテクチャ設定の簡素化
description: シンプルなアーキテクチャでJourney Optimizer B2B editionを設定します。 XDM スキーマ、メール/SMS チャネル、Marketo Engage ジャーニーのアクション、ユーザーを設定します。
feature: Setup, Administration
role: Admin, Data Engineer
hide: true
hidefromtoc: true
source-git-commit: 8f2cd2a657892b0f776b51776d3056946930df21
workflow-type: tm+mt
source-wordcount: '1423'
ht-degree: 6%

---

# アーキテクチャ設定の簡素化

Adobe Journey Optimizer B2B Edition が、簡素化されたアーキテクチャで使用できるようになりました。この更新されたアーキテクチャにより、同じシステムおよび同じデータストア上に Journey Optimizer B2B Edition と Marketo Engage が存在することはなくなりました。Journey Optimizer B2B Edition は、Adobe Experience Platform からのみデータを受信します。ただし、システムのプロビジョニングと設定には、引き続き Marketo Engage の使用権限と一部の設定機能に依存します。

シンプルなアーキテクチャは、Adobe Journey Optimizer B2B editionの新機能を活用するための基盤となります。

* **データの統合と拡張が簡単：** 新しいプラットフォームは、カスタムオブジェクト、購入グループ、アカウントイベントなどの複雑なデータモデルをサポートしています。 

* **複数のAdobe Marketo Engage インスタンスへの接続：** 複数のAdobe Marketo Engage環境のデータを 1 か所で管理および統合します。

* **データを安全に保持：** お客様の情報を保護するのに役立つ、高度なプライバシーとセキュリティ機能。 （_準備中_）

* **将来を見据えて構築：** このアップグレードにより、継続的な改善とイノベーションに対応できます。 

このアーキテクチャ用にプロビジョニングされた環境の場合は、次のガイドラインを設定に使用します。

## 名前空間とスキーマ

概要については、Experience Platform ドキュメントの [B2B 名前空間とスキーマ &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/sources/connectors/adobe-applications/marketo/marketo-namespaces) を参照してください。

### 環境セットアップ

B2B 名前空間とスキーマ自動生成ユーティリティをサポートするために、Postman環境を設定します。

* 名前空間およびスキーマ自動生成ユーティリティのコレクションと環境は、[GitHub リポジトリ &#x200B;](https://github.com/adobe/experience-platform-postman-samples/tree/master/Postman%20Collections/CDP%20Namespaces%20and%20Schemas%20Utility) からダウンロードできます。

* 必要なヘッダーの値を収集する方法やサンプル API 呼び出しを読み取る方法など、Experience Platform API の使用方法については、[Experience Platform API の概要 &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/platform-apis/api-guide) ガイドを参照してください。

* Experience Platform API の資格情報の生成方法について詳しくは、[Experience Platform API の認証とアクセス &#x200B;](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/platform-apis/api-authentication) に関するチュートリアルを参照してください。

* Experience Platform API 用のPostmanの設定について詳しくは、[Adobe Experience PlatformのPostman](https://experienceleague.adobe.com/ja/docs/experience-platform/landing/platform-apis/postman) を参照してください。

Experience Platform Developer Console とPostmanをセットアップすると、Postman環境に適切な環境値を適用できるようになります。

### スクリプトの実行

Postman コレクションと環境の設定により、Postman インターフェイスを通じてスクリプトを実行できます。

Postman インターフェイスで、自動生成ユーティリティのルートフォルダーを選択し、上部のヘッダーから **実行** を選択します。

Runner インターフェイスが表示されたら、すべてのチェックボックスが選択されていることを確認してから、**名前空間とスキーマ自動生成ユーティリティを実行** を選択します。

リクエストが成功すると、B2B に必要な名前空間とスキーマが作成されます。

## XDM フィールドの選択

Journey Optimizer B2B edition UI では、アプリケーション全体で使用できる XDM フィールドを管理できます。 これらのフィールドは、構築 **_ジャーニー_**、**_購入グループ_** または **_メールのパーソナライゼーション_** に関連するフィールドのみを公開することで、インスタンスを合理化するのに役立ちます。

### XDM クラス

#### 標準クラス

標準の XDM クラスのフィールドを定義するには、次の手順を使用します。

1. **[!UICONTROL 管理 &#x200B;]/[!UICONTROL &#x200B; 設定]** に移動します。

1. ナビゲーションパネルで、「**[!UICONTROL XDM クラス]**」を選択します。

1. **[!UICONTROL 標準]** タブを選択して、使用可能な XDM クラスを表示します。

   * XDM 個人プロファイル

   * XDM ビジネスアカウント

#### 管理フィールド

アプリケーション全体で使用できるフィールドを定義します。

1. _詳細メニュー_ （**...**）アイコンをクリックし、**[!UICONTROL 管理フィールドを編集]** を選択します。

1. 使用可能なフィールドのリストを確認します（フィールドメタデータの場合は _情報_ アイコンをクリック）。

1. 含めるフィールドを選択し、不要なフィールドの選択を解除します。

1. **[!UICONTROL 選択したフィールドのみを表示]** スライダーを使用して、選択を確認します。

1. 「**[!UICONTROL 保存]**」をクリックします。

#### 更新可能なフィールド

**[!UICONTROL アカウントプロファイルを更新]** または **[!UICONTROL 人物プロファイルを更新]** ジャーニーアクションを通じて変更できるフィールドを選択します。

1. _詳細メニュー_ （**...**）アイコンをクリックし、「**[!UICONTROL 更新可能なフィールドを編集]**」を選択します。

1. **[!UICONTROL スキーマ]** を選択し、次に **[!UICONTROL データセット]** を選択します。

   これらのスキーマとデータセットは、組織が提供します。

   更新可能なフィールドのガードレール：

   * スキーマ – スキーマには、XDM Individual Profile クラスのシステム定義のフィールド（`identityMap` や `personID` など）以外の必須フィールドを含めないでください。
   * データセット – 別の目的で既に使用されているデータセットを選択しないでください。 ベストプラクティスとして、更新可能なフィールドを保存するための専用のデータセットを作成します。 XDM クラスごとに個別のデータセットを使用します。

1. 更新可能なフィールドのリストを確認します（メタデータの場合は _情報_ アイコンをクリック）。

   編集できるのは、管理フィールドのみです。

1. ジャーニーから更新できるようにするフィールドを選択します。

1. **[!UICONTROL 保存]**&#x200B;をクリックします。

### リレーショナルスキーマ

[journey decisioning](https://experienceleague.adobe.com/ja/docs/experience-platform/xdm/schema/relational) および **_パーソナライゼーション_** で使用する **_リレーショナルスキーマ_** を選択します。 現在、これらのスキーマは、カスタムオブジェクトのユースケース向けです。 今後、リレーショナルスキーマは他のオブジェクトのユースケースにも使用できます。

1. 「**[!UICONTROL リレーショナル]**」タブを選択します。

1. 「**[!UICONTROL リレーショナル XDM クラスを選択]**」をクリックします。

   現在、アカウントの多対 1 のカスタムオブジェクトのみがサポートされています。

1. スキーマフィールドのリストを確認します（「_情報_ アイコンをクリックしてメタデータを表示）。

1. 含めるフィールドを選択します。

1. **[!UICONTROL 選択したフィールドのみを表示]** スライダーを使用して、選択を確認します。

1. 「**[!UICONTROL 保存]**」をクリックします。

>[!NOTE]
>
>リレーショナルスキーマには、次の設定が必要です。
>
><li>動作：レコード
>&gt; <li>セグメント化：有効
>&gt; <li>関係タイプ：多対 1
>&gt; <li>参照スキーマ：<a href="https://experienceleague.adobe.com/ja/docs/platform-learn/tutorials/schemas/create-schemas-for-b2b-data">B2B アカウント - XDM ビジネスアカウントスキーマ </a>
>&gt; <li>必須フィールド：プライマリキー、外部キー、バージョン記述子
>&gt; <li>関連するデータセット：スキーマに定義およびマッピングされる

### イベント

**_journey decisioning_** で使用するエクスペリエンスイベントを選択します。

1. 「**[!UICONTROL イベント]**」タブを選択します。

1. **[!UICONTROL エクスペリエンスイベントを選択]** をクリックします。

1. **[!UICONTROL イベントタイプを選択]** をクリックし、イベントタイプを選択して、**[!UICONTROL 選択]** をクリックします。

1. 「**[!UICONTROL フィールドを選択]**」をクリックし、必要なフィールドを選択して、「**[!UICONTROL 選択]**」をクリックします。

1. 「**[!UICONTROL 保存]**」をクリックします。

## メール設定

Journey Optimizer B2B editionからメールを送信するには、以下を設定する必要があります。  

[https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/get-started/email-protocols](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/get-started/email-protocols)

### トラッキングとメール配信のプロトコル

1. [&#x200B; メールの DNS レコードの作成 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/get-started/email-protocols#create-dns-records-for-landing-pages-and-email)

1. [SPF とDKIMの設定 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-spf-and-dkim)

1. [DMARCのセットアップ &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-dmarc)

1. [&#x200B; ドメインの MX レコードの設定 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/get-started/email-protocols#set-up-mx-records-for-your-domain)

1. 許可リストに加える [&#x200B; 送信 IP アドレスの追加 &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/get-started/email-protocols#outbound-ip-addresses)

1. 専用 IP プールを共有する必要がある場合は、配信品質チームに連絡して、実現可能性と支援された設定について問い合わせてください。

### メールチャネル設定

シンプルなアーキテクチャでは、メールはMarketo Engage アプリケーションから設定されます。 メール関連の設定手順を完了します。

* [https://experienceleague.adobe.com/ja/docs/marketo/using/getting-started/initial-setup/setup-steps](https://experienceleague.adobe.com/ja/docs/marketo/using/getting-started/initial-setup/setup-steps)

* [https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-emails](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-emails)

### 通信制限

1. 左側のナビゲーションで **[!UICONTROL 管理]**/**[!UICONTROL チャネル]** を選択します。

1. ナビゲーションパネルで、「**[!UICONTROL 通信制限]**」を選択します。

1. グローバル通信制限ルールセットを作成します（このルールセットは、デフォルトですべてのJourney Optimizer B2B edition インスタンスに作成されます）。

   グローバルルールセットが作成されていない場合は、通信の制限はありません。

<!-- In the future, you can also add local communication limit rule sets (AJO B2C doc can be found here [https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/conflict-prioritization/capping-rules/rule-sets](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/conflict-prioritization/capping-rules/rule-sets). We may need a small update for our B2B version.) -->

### 共有コミュニケーションの制限

新しいアーキテクチャ内では、Journey Optimizer B2B editionとMarketo Engageには、デフォルトで独立した通信制限があります。

Journey Optimizer B2B edition インスタンスで設定された通信制限をMarketo Engage インスタンスで共有する場合は、Adobe サポートに連絡して設定をサポートを受けるか、サポートチケットを開きます。 エンジニアリングチームは必要に応じて、Journey Optimizer B2B editionと 1 つ以上のMarketo Engage インスタンスとの間で通信制限の共有を有効にすることができます。

共有通信制限が有効な場合、Journey Optimizer B2B editionでルールを定義し、それらの制限の共有をMarketo Munchkin コードまで拡張することができます。 詳しくは、「通信の制限 [&#x200B; を参照してください &#x200B;](./admin/configure-channels-emails.md#communication-limits)

<!-- internal info only 

Currently, the shared communication limit in the Marketo Engage instance must be set up through an API call.

For example, when:

* The munchkinId of the Journey Optimizer B2B Edition instance is `JKL-567-MNO`.
* The munchkinId of the Marketo Engage instance is `ABC-123-DEF` and it is in the SJ datacenter

The API request should look similar to the following:

```
curl --location --request POST 'http://sjrest2a.marketo.org/rest/v1/fm.json?_munchkinId=ABC-123-DEF&featureName=Mktmail%20Config&paramName=ajoB2bMappingMunchkinId&dataType=string&value=JKL-567-MNO'
```
-->

## SMS チャネルの設定

詳しくは、[_SMS 設定_](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/admin/channels/configure-channels-sms) を参照してください。

## ジャーニーからのMarketo Engage アクション

次のジャーニーアクションで使用するために、1 つ以上のリモート **_Marketo Engage_** インスタンスを設定できます。

* Marketo リストに追加
* Marketo リストから削除
* Marketo リクエストキャンペーンに追加

これらの接続を設定するには、次の手順を実行します。

1. **[!UICONTROL 管理 &#x200B;]/[!UICONTROL &#x200B; 設定]** に移動します。

1. ナビゲーションパネルで、「**[!UICONTROL XDM クラス]**」を選択します。

1. 「**[!UICONTROL 統合]**」タブを選択します。

1. **[!UICONTROL 接続を作成]** をクリックします。

1. **[!UICONTROL 名前]** と **[!UICONTROL 説明]** を入力します。

1. 一致する人物レコードの **[!UICONTROL ポリシーを更新]** を選択します。

1. **[!UICONTROL Munchkin ID]**、**[!UICONTROL クライアント ID]**、**[!UICONTROL クライアントシークレット]** を入力し、**[!UICONTROL Marketoに接続]** をクリックします。

1. 「**[!UICONTROL 作成]**」をクリックします。

## ユーザーのオンボーディング

概要については、[User Management](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/admin/user-management) ページを参照してください。

### 既存のユーザーグループ

既存のJourney Optimizer B2B edition ユーザー全員が新しいアーキテクチャにアクセスする必要がある場合は、既存のJourney Optimizer B2B edition ユーザーグループを使用します。 システム管理者または製品管理者は、次の手順を実行できます。

1. 専用のMarketo Engageで製品プロファイルを作成します。

1. 作成した製品プロファイルに既存のユーザーグループを追加します。

プロファイルは、そのユーザーグループに既に割り当てられているすべての役割と権限を付与します。これらは、ユーザーがJourney Optimizer B2B editionにアクセスできるように既に設定されている必要があります。 ユーザーの一部のみが新しいアーキテクチャにアクセスする必要がある場合は、次に示す手順を実行します。 詳しくは、[&#x200B; 現在のドキュメント &#x200B;](https://experienceleague.adobe.com/ja/docs/journey-optimizer-b2b/user/admin/user-management) を参照してください。

### ユーザーグループの新規作成

1. 専用のMarketo Engage インスタンスに製品プロファイルを作成します。
1. 新規ユーザー用のユーザーグループを作成します。
1. 必要な製品プロファイルを選択してユーザーグループに割り当てます。

   * 作成したMarketo Engage プロファイル
   * Adobe Experience Platform プロファイル
      * AEP-Default-All-Users
      * Adobe Experience Platform のデータ収集
      * データ収集のすべてのアクセス

1. ユーザーグループにユーザーを追加します。
1. Experience PlatformのJourney Optimizer B2B editionの役割に新しいユーザーグループを追加します。
