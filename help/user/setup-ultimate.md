---
title: チェックリストを設定
description: Journey Optimizer B2B Editionを設定します。 XDM スキーマ、メール/SMS チャネル、Marketo Engage ジャーニーのアクション、ユーザーを設定します。
feature: Setup, Administration
role: Admin, Developer
exl-id: 81232976-09d6-4e10-a034-5c193a63b7df
source-git-commit: 944d2616fa21e7f8d2f8c439eaa2f5e529dacb84
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 83%

---

# チェックリストを設定

Adobe Journey Optimizer B2B Editionは、Adobe Experience Platform上に構築されています。 この実装では、Journey Optimizer B2B EditionとMarketo Engageは同じシステムと同じデータストア上にありません。 Journey Optimizer B2B Editionは、Adobe Experience Platformからデータを受け取ります。 ただし、システムのプロビジョニングと設定には、Marketo Engageの使用権限と、メール配信などのバックエンド機能が引き続き使用されます。

<!-- 
>>[!NOTE]
>
>Earlier documentation referred to this deployment as the *simplified architecture*. That model is now the Journey Optimizer B2B Edition Ultimate implementation. 
-->

この導入は、Journey Optimizer B2B Editionの能力を引き出す基盤となります。

* **データを容易に統合および拡張できます。** プラットフォームは、カスタムオブジェクト、購買グループ、アカウントイベントなどの複雑なデータモデルをサポートしています。

* **複数のAdobe Marketo Engage インスタンスへの接続：** 複数のMarketo Engage環境のデータを 1 か所で管理および統合します。

* **データを安全に保つ：**&#x200B;顧客情報の保護に役立つ高度なプライバシー機能とセキュリティ機能。 （_準備中_）

* **将来を見据えて構築：**&#x200B;この設定は、継続的な改善とイノベーションをサポートします。

設定には、次のガイドラインを使用します。

Journey Optimizer B2B Editionの設定を完了するには、このチェックリストを使用します。

## &#x200B;1. B2B 名前空間とスキーマの生成

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>環境設定：</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>GitHub から名前空間とスキーマの自動生成ユーティリティをダウンロードします。</td>
<td><a href="./data/namespaces-schemas.md#set-up-the-auto-generation-utility">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Experience Platform API 資格情報と必要なヘッダーを収集します。</td>
<td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/landing/platform-apis/api-guide">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>環境の値をPostman環境に適用します。</td>
<td><a href="./data/namespaces-schemas.md#environment-values">詳細情報</a></td>
</tr>
<tr>
<td colspan="2"><strong>スクリプトを実行します。</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Postmanで <em> 名前空間とスキーマ </em> 生成ユーティリティを実行し、名前空間とスキーマが作成されたことを確認します。</td>
<td><a href="./data/namespaces-schemas.md#run-the-scripts">詳細情報</a></td>
</tr>
</tbody>
</table>

## &#x200B;2. XDM フィールドとイベントの設定

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong> 標準 XDM クラス </strong>:XDM 個人プロファイルと XDM ビジネスアカウントのクラスを設定します。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>ジャーニー、購入グループおよびメールのパーソナライゼーション用に公開する管理フィールドを選択します。</td>
<td><a href="./admin/xdm-field-management.md#standard-classes">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>スキーマの更新可能なフィールドを編集します。</td>
<td><a href="./admin/xdm-field-management.md#updatable-fields">詳細情報</a></td>
</tr>
<tr>
<td colspan="2"><strong> リレーショナルスキーマ </strong>: リレーショナル XDM クラス（アカウントの多対 1 カスタムオブジェクト）を選択します。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>スキーマに必要な設定値が含まれていることを確認します。</td>
<td><a href="./admin/xdm-field-management.md#relational-schemas">詳細情報</a></td>
</tr>
<tr>
<td colspan="2"><strong> イベント </strong>:Experience Platformのイベントタイプとフィールドを設定します。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>ジャーニー決定/分割パスでサポートされるフィールドを含んだExperience Platform イベントタイプを設定します。</td>
<td><a href="./admin/configure-aep-events.md">詳細情報</a></td>
</tr>
</tbody>
</table>

## &#x200B;3. トラッキングと E メール配信の設定

[!DNL Journey Optimizer B2B Edition]からメールを送信するには、添付の[!DNL Marketo Engage]実稼動インスタンスと[!DNL Journey Optimizer B2B Edition] アプリでメールの追跡と配信品質を設定します。

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">接続されたMarketo Engage インスタンスの <strong> 初期設定 </strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>DNS レコードのトラッキングリンク用の新しい CNAME の設定</td>
<td><a href="./start/email-protocols.md#create-dns-records-for-landing-pages-and-email">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>接続されたMarketo Engage インスタンスのブランディングドメインの設定</td>
<td><a href="./start/branding-domains.md">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>接続されたMarketo Engage インスタンスへのDKIMと SPF の設定</td>
<td><a href="./start/email-protocols.md#set-up-spf-and-dkim">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>DMARC を設定</td>
<td><a href="./start/email-protocols.md#set-up-dmarc">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>ドメインの MX レコードを設定</td>
<td><a href="./start/email-protocols.md#set-up-mx-records-for-your-domain">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>許可リストに加えるへの送信 IP アドレスの追加</td>
<td><a href="./start/email-protocols.md#outbound-ip-addresses">詳細情報</a></td>
</tr>
<tr>
<td colspan="2">添付されたMarketo Engage インスタンスの <strong> メール設定 </strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td><em>From Email</em> および <em>From Label</em> の設定（オプション）</td>
<td><a href="./start/email-setup.md#from-email-and-label">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td><em>HTMLの登録解除 </em> および <em> テキストの登録解除 </em> を設定します</td>
<td><a href="./start/email-setup.md#unsubscribe-messaging">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td><em>Web ページとして表示HTML</em> および <em>Web ページテキストとして表示 </em> を設定します</td>
<td><a href="./start/email-setup.md#view-as-web-page">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td><em> カスタム・オブジェクトの取得制限 </em> の構成</td>
<td><a href="./start/email-setup.md#custom-object-retrieval-limits">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td><em> カスタムヘッダーオプション </em> を設定する</td>
<td><a href="./start/email-setup.md#custom-header-options">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td><em> ボットアクティビティ </em> フィルタリングの設定</td>
<td><a href="./start/email-setup.md#filter-email-bots">詳細情報</a></td>
</tr>
<tr>
<td colspan="2">Journey Optimizer B2B editionの <strong> メールチャネル設定 </strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Journey Optimizer B2B editionでの <em> 通信制限 </em> の設定</td>
<td><a href="./admin/configure-channels-emails.md#communication-limits">詳細情報</a></td>
</tr>
</tbody>
</table>

<!--
 TBD for later

<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Email CC Settings</em></td>
<td>[Learn more](TBD)</td>
</tr>

<tr>
<td colspan="2"><strong>Additional configurations</strong></td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Configure <em>Location Settings</em> for the attached Marketo Engage instance</td>
<td>< [Learn more](TBD)</td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Define and configure which Binding Groups / IPs to move over</td>
<td>[Learn more](TBD)</td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="Checkbox"/></td>
<td>Test Email Send</td>
<td>[Learn more](TBD)</td>
</tr>
-->

## &#x200B;4. 追加のコンテンツチャネルの設定

マーケターがジャーニーに他のチャネルを含めるのをサポートするには、追加のチャネルを設定します。

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2">Journey Optimizer B2B edition用の <strong>SMS</strong> チャネル設定。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>サポートする各 SMS アカウントを設定します。</td>
<td><a href="./admin/configure-channels-sms.md">詳細情報</a></td>
</tr>
<tr>
<td colspan="2"><strong> ランディングページ </strong> （Beta）Journey Optimizer B2B editionのチャネル設定。</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>ランディングページの設定を完了して、これらのページを作成および公開するマーケターをサポートします</td>
<td><a href="./admin/landing-page-settings.md">詳細情報</a></td>
</tr>
<tr>
<td colspan="2">Journey Optimizer B2B edition用の <strong>Web</strong> （Beta）チャネル設定</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Adobe Experience Platform Web SDKをサポートするようにビジネス web サイトを設定します。</td>
<td><a href="https://experienceleague.adobe.com/ja/docs/experience-platform/collection/js/js-overview">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>コンテンツが配信される URL で web プロパティを追加します。</td>
<td><a href="./admin/configure-channels-web.md">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Web エクスペリエンス作成者に、Adobe Experience Cloud Visual Editing Helper ブラウザー拡張機能をインストールするように指示します。</td>
<td><a href="./content/web-experiences.md#install-the-visual-editing-helper-extension">詳細情報</a></td>
</tr>
</tbody>
</table>

## &#x200B;5. ジャーニーアクションをサポートするMarketo Engage インスタンスの接続（オプション）

Marketo EngageのキャンペーンやプログラムでJourney Optimizer B2B editionの機能を補完する予定がある場合は、Marketo Engage アクションのサポートを設定します。 これらのアクションにより、マーケティングチームは、Journey Optimizer B2B editionでの _アカウントベース_ のマーケティングと、Marketo Engageでの _リードベース_ のマーケティングの取り組みを調整できます。

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong>Marketo Engage インスタンスごとに </strong> ジャーニーアクションをサポートします</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Marketo Engage カスタムサービスの作成</td>
<td><a href="./admin/marketo-actions-connect.md#create-the-marketo-engage-custom-service">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Journey Optimizer B2B editionへの統合の追加</td>
<td><a href="./admin/marketo-actions-connect.md#add-the-integration">詳細情報</a></td>
</tr>
</tbody>
</table>

## &#x200B;6. ユーザーアクセスを有効にする

プロビジョニングが完了すると、サンドボックスがバインドされ、初期設定タスクが完了します。チームとユーザーに対して、Journey Optimizer B2B editionとMarketo Engageのアクセスを設定します。

<table>
<thead>
<tr>
<th colspan="2">タスク</th>
<th>詳細と手順</th>
</tr>
</thead>
<tbody>
<tr>
<td colspan="2"><strong> 製品へのアクセスおよび権限の提供 </strong> ユーザーの場合</td>
<td></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>Adobe Admin ConsoleでMarketo Engage製品プロファイルを作成する（新しいMarketo Engage インスタンスのみ）</td>
<td><a href="./admin/user-management.md#marketo-engage-profile">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>プロファイル用のユーザーグループの追加</td>
<td><a href="./admin/user-management.md#add-user-group">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>B2B ユーザーの役割の設定</td>
<td><a href="./admin/user-management.md#b2b-built-in-roles">詳細情報</a></td>
</tr>
<tr>
<td><img src="../assets/do-not-localize/icon-checkbox.svg" width="25" alt="チェックボックス"/></td>
<td>役割にユーザーまたはグループを追加</td>
<td><a href="./admin/user-management.md#add-users-to-a-role">詳細情報</a></td>
</tr>
</tbody>
</table>
