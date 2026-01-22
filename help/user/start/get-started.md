---
title: 管理者およびマーケター向けのオンボーディングガイダンス
description: 管理者およびマーケター向けオンボーディングガイド - Journey Optimizer B2B Edition でサンドボックスの設定、チャネルの設定、購買グループの作成、アカウントジャーニーの設計を行います。
role: Admin, User
level: Beginner
exl-id: 83f8e666-0b31-4323-9902-4fdf4446424c
source-git-commit: 2a676f3cbeb43616a75fa3fa6eb9106230b9fb40
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 93%

---

# オンボーディングガイダンス

Adobe Journey Optimizer B2B Edition で取り扱う機能とツールは、チーム内での役割によって異なります。組織に基づいて、管理者は複数のタイプのユーザーを定義し、ユーザーの権限に応じて特定の機能に対するアクセス権をユーザーに付与できます。

>[!TIP]
>
>また、パフォーマンスガードレールと静的制限について詳しくは、ライセンスの使用権限と対応する[製品説明](https://helpx.adobe.com/jp/legal/product-descriptions/adobe-journey-optimizer-b2b.html){target="_blank"}を参照してください。

>[!BEGINTABS]

>[!TAB 管理者]

チームが Adobe Journey Optimizer B2B Edition 機能の使用を開始する前に、環境の準備にいくつかの手順が必要です。データエンジニアとマーケターが Adobe Journey Optimizer B2B Edition の使用を開始できるように、これらの手順を実行します。

システム管理者は、製品プロファイルを理解し、サンドボックス管理とチャネル設定の権限を割り当てる必要があります。また、使用可能な製品プロファイルに対してサンドボックスを設定し、管理する必要もあります。その後、チームメンバーを製品プロファイルに割り当てることができます。Adobe Admin Console へのアクセス権を持つ製品管理者は、これらの機能を管理できます。[Adobe Admin Console について詳しくは、こちらを参照してください](https://helpx.adobe.com/jp/enterprise/using/admin-console.html)。

アクセス管理については、次のページを参照してください。

1. **サンドボックスを作成**&#x200B;して、インスタンスを個別の独立した仮想環境に分割します。[詳細情報](https://experienceleague.adobe.com/ja/docs/experience-platform/sandbox/home#understanding-sandboxes){target="_blank"}

1. **データエンジニアと協力**&#x200B;して、B2B オーディエンスとプロファイルのアクティベーションを計画および実装します。公開したブループリントを確認し、要件に応じてガイドラインに従います。[詳細情報](https://experienceleague.adobe.com/ja/docs/blueprints-learn/architecture/b2b-activation/overview){target="_blank"}

1. **Marketo Engage統合の計画と実装** を実施して、カスタムスキーマの取り込み、プロファイルとアカウントの取り込み、および購入グループ向けにパーソナライズされたジャーニーのオーケストレーションを組み込みます。 [詳細情報](https://experienceleague.adobe.com/ja/docs/blueprints-learn/architecture/b2b-activation/b2b-journeys-with-marketo){target="_blank"}

1. **製品プロファイルを設定します**。製品プロファイルは、インターフェイス内の特定の機能やオブジェクトにユーザーがアクセスできるようにする、Adobe Experience Platform の単一権限のセットです。[詳細情報](../admin/user-management.md#create-the-marketo-engage-product-profile)

1. サンドボックスを含む製品プロファイルの&#x200B;**ユーザー権限を設定**&#x200B;し、チームメンバーを異なる製品プロファイルに割り当ててアクセス権を付与します。このタスクは、Admin Console で実行します。[詳細情報](../admin/user-management.md#create-a-user-group)

1. **XDM クラスとフィールドを設定** して、journey orchestration およびコンテンツパーソナライゼーションのJourney Optimizer B2B editionで使用できるデータを制御します。 [詳細情報](../admin/xdm-field-management.md)

1. Marketo Engage で&#x200B;**メール配信を設定**&#x200B;すると、チームがアカウントジャーニーからメールコンテンツを送信できます。[詳細情報](../admin/configure-channels-emails.md){target="_blank"}

1. **SMS サービスを設定します**。テキストメッセージサービスを個別に提供する、サポート対象のサードパーティ SMS プロバイダーの 1 つを設定し、Adobe Journey Optimizer B2B Edition でアカウント資格情報を設定します。[詳細情報](../admin/configure-channels-sms.md)

1. 一元的なデジタルアセット管理のために Assets as a Cloud Service を使用するチーム向けに、**Adobe Experience Manager Assets の使用を設定して有効にします**。[詳細情報](../admin/configure-aem-repositories.md)

1. Adobe Experience Platform（AEP）エクスペリエンスイベントをリッスンするアカウントジャーニーの作成を担当するチーム向けに、**AEP エクスペリエンスイベント定義を設定します**。[詳細情報](../admin/configure-aep-events.md)

>[!TAB マーケター]

マーケターまたは&#x200B;_アカウントジャーニー実務担当者_&#x200B;は、ジャーニーの設計とコンテンツの作成を担当します。システム管理者とデータエンジニアが環境を準備し、アクセス権を付与したら、Adobe Journey Optimizer B2B Edition での作業を開始できます。

最初のジャーニーを設定し、アセットを追加し、コンテンツを送信するには、次の節を参照してください。

1. **アカウントオーディエンスを追加します**。Journey Optimizer B2B Edition では、アプリケーションから直接セグメント定義を通じてアカウントオーディエンスを作成し、アカウントジャーニーに活用できます。[詳細情報](../audiences/account-audience-overview.md)

1. **購買グループを作成します**。ビジネスの目標と目的を達成するための主要コンポーネントを定義し、ターゲットアカウントリストのメンバーを識別する購買グループを作成します。[詳細情報](../buying-groups/buying-groups-overview.md)

1. **アセットを作成および管理します**。Adobe Experience Manager Assets は、メッセージの入力に使用できる、アセットの単一の一元的なリポジトリを提供します。[詳細情報](../content/assets-overview.md)

1. **パーソナライズされた動的なメールテンプレートを追加します**。Journey Optimizer B2B Edition のパーソナライゼーションと動的コンテンツ機能を活用して、メッセージをオーディエンスに合わせます。[詳細情報](../content/email-templates.md)

1. **パーソナライズされたコンテキストエクスペリエンスを提供するアカウントジャーニーを設計します**。Journey Optimizer B2B Edition では、イベントやデータソースに保存されたコンテキストデータを使用して、リアルタイムオーケストレーションのユースケースを作成できます。次の機能を活用して、複数ステップの高度なシナリオを設計できます。

   * イベントの受信時にトリガーされるリアルタイムの単一配信を送信するか、Adobe Experience Platform オーディエンスを使用してバッチで送信します。

   * イベントからのコンテキストデータ、Adobe Experience Platform からの情報、サードパーティの API サービスからのデータを使用します。

   * ビルトインのチャネルアクション（メールと SMS）を使用して、Journey Optimizer B2B Edition で設計したメッセージを送信します。

   * ジャーニーマップでは、複数のステップのユースケースを作成し、条件を追加して、パーソナライズされたメッセージを送信します。

[詳細情報](../journeys/journeys-overview.md)

>[!ENDTABS]
