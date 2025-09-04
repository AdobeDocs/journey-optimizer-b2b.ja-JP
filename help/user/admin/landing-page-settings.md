---
title: ランディングページの設定
description: マーケティングチームがキャンペーンをサポートする web ページを作成および公開できるようにランディングページ設定にアクセスして設定する方法を説明します。
feature: Setup, Landing Pages, Content
role: Admin
hide: true
hidefromtoc: true
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、現在、限定ベータ版リリース中です"
exl-id: 54b812cb-0129-4253-8e9e-538c25fc4709
source-git-commit: 8bd3d696a52a813b88de9e3b58145b1cbfb3fa32
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 27%

---

# ランディングページの設定

管理者は、ランディングページの設定が、これらのページを作成および公開するマーケター向けに設定されていることを確認する必要があります。

## 設定

ランディングページの設定を確認するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL ランディングページ]_ の下で **[!UICONTROL 設定]** を選択します。

![ ランディングページの設定 ](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

### アカウント文字列 {#account-string}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_account_string"
>title="ランディングページのアカウント文字列"
>abstract="アカウント文字列は、ランディングページをホストしている Adobe Journey Optimizer B2B エディションインスタンスを識別します。"

アカウント文字列は、ランディングページをホストしているAdobe Journey Optimizer B2B edition インスタンスを識別します。 システムチームが DNS エントリを追加および設定していることを確認します。

### フォームの事前入力 {#form-prefill}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_form_prefill"
>title="ランディングページのフォームの事前入力設定"
>abstract="フォームの事前入力オプションを有効にすると、ランディングページ内のフォームで既知のユーザーに対して事前入力済みの情報を使用できます。"

「**[!UICONTROL フォームの事前入力]**」オプションを有効にすると、ランディングページ内のフォームで、既知のユーザーに対して事前入力済みの情報を使用できるようになります。 このオプションを無効にすると、ランディングページの作成者には、事前入力されたフォームフィールドを含めることができません。

### データストリーム {#datastream}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_datastream"
>title="データストリーム要件"
>abstract="このドメインのランディングページからページイベントを収集するには、データストリームが必要です。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_missing_datastream"
>title="データストリーム ID がありません"
>abstract="サブドメインにデータストリーム ID がありません。これは適切なルーティングに必要です。 設定で設定して続行します"

**[!UICONTROL Datastream]** オプションを設定して、ランディングページイベント収集用のデータストリームを設定します。

## サブドメイン {#add-subdomain}

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_add_subdomain"
>title="ランディングページのサブドメインの追加"
>abstract="最大 50 個のサブドメインを追加できます。Adobe Journey Optimizer B2B エディションでホストする一意のブランド URL 別に新しいサブドメインを設定します。"

>[!CONTEXTUALHELP]
>id="ajo-b2b_landing_pages_configure_subdomain"
>title="ランディングページのサブドメインの設定"
>abstract="ランディングページを公開するには、設定済みのサブドメインが必要です。既にアドビにデリゲートされているサブドメインを使用するか、新しいサブドメインを作成できます。"

ランディングページのサブドメインは、コンテンツタイプ、製品名またはキャンペーンを識別し、ページの信頼性を強化するのに役立ちます。 サブドメインを設定する前に、ランディングページに使用する 1 つ以上の CNAME を定義します。 例：

* **product**.[CompanyDomain].com
* **移動**.[CompanyDomain].com
* **登録**.[CompanyDomain].com

これらの例では、最初の部分（太字）は `LandingPageCNAME` です。

Adobe Journey Optimizer B2B editionでホストする一意のブランド URL ごとに新しいサブドメインを追加します。 最大 50 個のサブドメインを追加できます。

>[!IMPORTANT]
>
>無効なサブドメインをアドビにデリゲートすることはできません。組織が所有する有効なサブドメイン（_marketing.yourcompany.com_ など）を入力してください。

サブドメインを確認して新しいサブドメインを追加するには、**[!UICONTROL 管理]**/**[!UICONTROL チャネル]** に移動します。 ナビゲーションパネルの _[!UICONTROL ランディングページ]_ の下で **[!UICONTROL サブドメイン]** を選択します。

![ ランディングページのサブドメイン ](./assets/config-landing-pages-settings.png){width="800" zoomable="yes"}

ランディングページのサブドメインを追加するには（_T） :_

1. 右上の **[!UICONTROL サブドメインを追加]** をクリックします。

1. _[!UICONTROL サブドメインの詳細]_ に、サブドメイン情報を入力します。

   * **[!UICONTROL サブドメイン]** - `marketing.yourcompany.com` など、使用するサブドメイン URL
   * **[!UICONTROL デフォルトページ]** - デフォルトのサブドメインページの URL （`marketing.yourcompany.com/products` など）
   * **[!UICONTROL フォールバックページ]** - サブドメイン上のランディングページがアクティブでない場合に使用されるフォールバックページの URL （例：`marketing.yourcompany.com/expired`）

   ![ ランディングページのサブドメインを追加 ](./assets/config-landing-pages-add-subdomain.png){width="700" zoomable="yes"}

1. 「**[!UICONTROL 保存]**」をクリックします。
