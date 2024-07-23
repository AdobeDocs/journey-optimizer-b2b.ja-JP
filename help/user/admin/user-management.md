---
title: ユーザー管理
description: チームメンバーをJourney Optimizer B2B Edition 製品プロファイルに割り当てる方法について説明します。
feature: Setup
roles: Admin
source-git-commit: dcd8ab2820d60654e8970944054142fc296ed54f
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 1%

---

# ユーザー管理

プロビジョニングが完了し、サンドボックスがバインドされたら、次の手順を実行して、チームとユーザーがAdobe Journey Optimizer B2B Edition にアクセスできるようにします。

1. Admin Consoleで [Marketo Engage製品プロファイルを作成 ](#marketo-engage-profile) （新しいMarketo Engageインスタンスのみ）。
1. Admin Consoleで [ ユーザーグループを作成 ](#create-user-group) します。
1. AEP 権限の [ 役割を作成 ](#create-role) します。
1. Admin Consoleの [ ユーザーを追加 ](#add-users) します。

管理者は、Adobe Admin Consoleでこれらのタスクを実行できます。この場所では、Adobeの製品ライセンスとユーザーを一元的に管理および管理できます。 Admin Consoleでは、様々な個別のソリューション内ではなく、1 か所でユーザーを作成および管理できます。 関数と機能について詳しくは、[Admin Consoleの概要 ](https://helpx.adobe.com/jp/enterprise/using/admin-console.html) ページを参照してください。

## Admin Consoleへのアクセス

Admin Consoleを使用してチーム内のユーザーを管理する前に、Admin Consoleにアクセスし、適切な権限を持っていることを確認する必要があります。

1. システム管理者は、オンボーディングプロセスの一環としてAdobeから複数のメールを受け取る必要があります。

   アクセス権が付与された組織名に関する情報を記載したお知らせメールを探します。

1. お知らせメールの **[!UICONTROL 使用を開始]** リンクをクリックして、Admin Consoleに移動します。

   メールが見つからない場合は、ブラウザーを開いてAdmin Console（[https://adminconsole.adobe.com](https://adminconsole.adobe.com)）に直接アクセスします。

1. Adobe IDを使用してログインします。

   ログインに成功すると、Adobe Admin Consoleの概要ページが表示されます。

1. 複数の組織にアクセスできる場合は、正しい組織にログインしていることを確認します。

   組織を変更するには、右上隅の組織名をクリックし、アクセスが必要な組織を選択します。

1. ユーザーカードから「管理者」を選択して、自分がシステム管理者であることを確認します。

1. Adobe IDのメールアドレス、ユーザー名、名、姓を入力して検索します。

   * アクセス権が正しく設定されている場合、検索はレコードを返します。

   * **[!UICONTROL 管理者の役割]** 列の値に `System` が表示されている場合、自分（または表示されているユーザー）がシステム管理者であることがわかります。

## Marketo Engage製品プロファイルの作成 {#marketo-engage-profile}

Adobeソリューションに対するアクセス権をユーザーに付与する場合、必ずしも完全なアクセス権を付与する必要はありません。 製品プロファイルを使用すると、ソリューションごとに独自のユーザー権限を設定できます。 Admin Consoleを使用して、製品プロファイルを割り当てます。

>[!NOTE]
>
>これらの手順は、Admin Consoleシステム管理者またはMarketo Engageプロダクト管理者のみが実行できます。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) にログインします。

1. Products/Marketo Engageを選択します。

1. 「新規プロファイル」をクリックし、製品プロファイル名（「_標準ユーザー_ など）を入力します。

1. 次へ/保存をクリックします。

## ユーザーグループの作成 {#create-user-group}

ユーザーグループは、一連の共有権限が付与されるユーザーの集まりです。 ユーザーグループのユーザーを追加または削除できます。 グループの権限は、グループ内のユーザーが変更されても、同じままです。

>[!NOTE]
>
>これらの手順は、Admin Consoleシステム管理者のみが実行できます。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) にログインします。

1. **[!UICONTROL ユーザー]**/**[!UICONTROL ユーザーグループ]**/**[!UICONTROL 新規ユーザーグループ]** を選択します。

1. _標準ユーザー_ のようにユーザーグループの名前を入力し、「**[!UICONTROL 保存]**」をクリックします。

1. 作成したユーザーグループをクリックします。

1. **[!UICONTROL 割り当てられた製品プロファイル]**/**[!UICONTROL プロファイルを割り当て]** をクリックします。

1. 次の製品を選択します。
   * [!UICONTROL Marketo Engage – 標準ユーザー ]
   * [!UICONTROL Adobe Experience Platform - AEP-Default-All-Users]
   * [!UICONTROL Adobe Experience Platform データ収集 – デフォルト ]
   * [!UICONTROL  データ収集のすべてのアクセス ]

1. 「**[!UICONTROL 保存]**」をクリックします。

## AEP 権限での役割の作成 {#create-role}

権限は、製品プロファイルに割り当てる許可を定義できる単一の権利です。 各権限は、Journey Optimizer B2B Edition のさまざまな機能やオブジェクトに相当する、ジャーニーや購入グループなどの機能の下に収集されます。

_権限_ は、管理者がユーザーの役割およびアクセスポリシーを定義し、製品アプリケーション内の機能およびオブジェクトのアクセス権限を管理できる、Adobe Experience Platformの領域です。 このアプリでは、役割を作成および管理すると共に、それらの役割に対して必要なリソース権限を割り当てることができます。 また、権限では、特定の役割に関連付けられたラベル、サンドボックス、ユーザーを管理することもできます。

>[!NOTE]
>
>次の手順を実行するには、Adobe Experience Platformの製品管理者である必要があります。

1. [experience.adobe.com](https://experience.adobe.com/) に移動します。

1. **[!UICONTROL 権限]** を選択します。

   >[!NOTE]
   >
   >権限が表示されない場合は、「すべて表示」をクリックし、使用可能なアプリケーションから選択する必要がある場合があります。

1. 左側のナビゲーションで「**[!UICONTROL 役割]**」を選択し、「**[!UICONTROL 役割を作成]**」を選択します。

1. _[!UICONTROL 新しい役割の作成]_ ダイアログで、「_標準ユーザー_」などの役割の名前と説明（オプション）を入力します。

1. 「**[!UICONTROL 確認]**」をクリックします。

1. サンドボックスを選択します

1. プロファイル権限を追加します。

   * 左側の _[!UICONTROL リソース]_ リストで「**[!UICONTROL プロファイル管理]**」項目を見つけ、プラス（**+**）アイコンをクリックして属性を追加します。

   * 属性に次の権限を追加します。
      * [!UICONTROL  セグメントの表示 ]
      * [!UICONTROL  セグメントの管理 ]
      * [!UICONTROL  プロファイルの表示 ]
      * [!UICONTROL  プロファイルの管理 ]
      * [!UICONTROL B2B プロファイルの表示 ]
      * [!UICONTROL B2B プロファイルの管理 ]

1. 右上の **[!UICONTROL 保存]** をクリックします。

1. **[!UICONTROL ユーザーグループ]**/**[!UICONTROL グループを追加]** を選択します。

1. Admin Consoleで前に作成したユーザーグループの横にあるチェックボックスをオンにします。

1. 「**[!UICONTROL 保存]**」をクリックします。

## Admin Consoleにユーザーを追加

>[!NOTE]
>
>これらの手順は、Admin Consoleシステム管理者またはプロダクト管理者のみが実行できます。

1. [https://adminconsole.adobe.com](https://adminconsole.adobe.com) に移動します。

1. **[!UICONTROL ユーザーを追加]** をクリックします。

1. 各ユーザーを追加します。

   * ユーザーのメールアドレス、名、姓を入力します。
   * [!UICONTROL  ユーザーグループ ] をクリックします。
   * 前に作成したユーザーグループを選択します。

1. 「**[!UICONTROL 適用]**」をクリックします。

1. 「**[!UICONTROL 保存]**」をクリックします。
