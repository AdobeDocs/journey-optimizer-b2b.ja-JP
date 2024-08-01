---
title: Journey Optimizer B2B Edition の概要
description: Journey Optimizer B2B Edition の新規ユーザーとして、使用を開始するための主要な領域について説明します。
exl-id: 83f8e666-0b31-4323-9902-4fdf4446424c
source-git-commit: 78d82aa8b3bb8b8d432eeb187d75e2354dbff3ee
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 8%

---

# Journey Optimizer B2B Edition の概要

Adobe Journey Optimizer B2B Edition で取り組みたい機能とツールは、チーム内の役割によって異なります。

管理者は、組織に基づいて、複数のタイプのユーザーを定義し、権限に応じて特定の機能へのアクセス権を付与できます。

>[!BEGINTABS]

>[!TAB  管理者のクイックスタート ]

Adobe Journey Optimizer B2B Edition の機能を使用する前に、環境の準備にいくつかの手順が必要です。 データエンジニアとマーケターがAdobe Journey Optimizer B2B Edition の使用を開始できるように、これらの手順を実行します。

システム管理者は、製品プロファイルを把握し、サンドボックス管理とチャネル設定の権限を割り当てる必要があります。 また、サンドボックスを設定し、使用可能な製品プロファイル用にサンドボックスを管理する必要もあります。 その後、チームメンバーを製品プロファイルに割り当てることができます。 これらの機能は、Adobe Admin Consoleにアクセスできる製品管理者が管理できます。 [Adobe Admin Console の詳細](https://helpx.adobe.com/jp/enterprise/using/admin-console.html)。

アクセス管理については、次のページを参照してください。

1. **サンドボックスを作成**&#x200B;して、インスタンスを個別の独立した仮想環境に分割します。[詳細情報](https://experienceleague.adobe.com/en/docs/experience-platform/sandbox/home#understanding-sandboxes)

1. **製品プロファイルを設定します**。 製品プロファイルは、インターフェイス内の特定の機能やオブジェクトへのアクセスをユーザーに許可する、Adobe Experience Platformの単一権限のセットです。 [詳細情報](../admin/user-management.md#create-the-marketo-engage-product-profile)

1. サンドボックスを含む製品プロファイルの **ユーザー権限の設定** を行い、チームメンバーを様々な製品プロファイルに割り当てることで、それらの製品プロファイルへのアクセス権をチームメンバーに付与します。 このタスクは、Admin Consoleで実行されます。 [詳細情報](../admin/user-management.md#create-a-user-group)

1. Marketo Engageで **メール配信を設定** します。これにより、チームはアカウントジャーニーからメールコンテンツを送信できます。 [詳細情報](https://experienceleague.adobe.com/en/docs/marketo/using/getting-started/initial-setup/setup-steps#ensure-email-deliverability)

1. **SMS サービスを設定** します。 テキストメッセージサービスを個別に提供する、サポートされているサードパーティ SMS プロバイダーの 1 つを設定し、Adobe Journey Optimizer B2B Edition でアカウント資格情報を設定します。 [詳細情報](../content/sms-authoring.md#create-a-new-api-credentials-for-an-sms-service-provider)

1. Adobe Experience Manager Assets as c Cloud Serviceを使用してデジタルアセットの一元管理を行うチームの場合は、**Assetsの使用を設定して有効にします**。 [詳細情報](../admin/configure-aem-repositories.md)

>[!TAB  マーケター向けクイックスタート ]

マーケターつまり _アカウントジャーニー実務担当者_ は、ジャーニーのデザインとコンテンツの作成を担当します。 システム管理者とデータエンジニアが環境を準備してアクセス権を付与したら、Adobe Journey Optimizer B2B Edition での作業を開始できます。

初めてのジャーニーをセットアップし、アセットを追加して、コンテンツを送信するには、以下の節を参照してください。

1. **アカウントオーディエンスを追加**. Journey Optimizer B2B Edition では、アプリケーションから直接セグメント定義を通じてアカウントオーディエンスを作成し、それらをアカウントジャーニーに活用できます。 [詳細情報](../audiences/account-audience-overview.md)

1. **購入グループの作成**。 ビジネス目標とビジネス目標を達成するための主要コンポーネントを定義し、ターゲットアカウントリストのメンバーを識別する購入グループを作成します。 [詳細情報](../buying-groups/buying-groups-overview.md)

1. **アセットを作成し管理**&#x200B;します。Adobe Experience Manager Assetsは、メッセージへの入力に使用できるアセットの一元的な集中リポジトリを提供します。 [詳細情報](../content/assets-overview.md)

1. **パーソナライズされた動的なメールテンプレートを追加** します。 Journey Optimizer B2B Edition のパーソナライズ機能と動的コンテンツ機能を活用して、メッセージをオーディエンスに合わせます。 [詳細情報](../content/email-templates.md)

1. **アカウントジャーニーを設計して、状況に即したパーソナライズされたエクスペリエンスを提供する**。 Journey Optimizer B2B Edition を使用すると、イベントやデータソースに保存されたコンテキストデータを使用して、リアルタイムオーケストレーションの使用例を作成できます。 次の機能を活用して、複数のステップから成る高度なシナリオを設計します。

   * イベントの受信をトリガーにしてリアルタイムに単一配信を送信したり、Adobe Experience Platform オーディエンスを使用してメッセージを一括で送信したりできます。

   * イベント、Adobe Experience Platformの情報、サードパーティの API サービスのデータなどのコンテキストデータを使用できます。

   * 組み込みのチャネルアクション （メールおよび SMS）を使用して、Journey Optimizer B2B Edition でデザインされたメッセージを送信します。

   * ジャーニーデザイナーで、複数ステップのユースケースを作成し、条件を追加して、パーソナライズされたメッセージを送信します。

[詳細情報](../journeys/journey-overview.md)

>[!ENDTABS]
