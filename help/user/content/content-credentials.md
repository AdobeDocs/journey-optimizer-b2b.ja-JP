---
title: Content Credentials
description: 生成AI ツールを使用して生成または編集された画像に、Adobe Journey Optimizer B2B editionがContent Credentialsを自動的に適用する仕組みと、これがコンテンツにもたらす意味をご紹介します。
feature: Assets, Content
role: User
autotag-review: '2026-07-31T22:15:54.535Z'
TQID: 'https://experienceleague.adobe.com/9XCqPWz62uDDLFAyxARfD2jErYx2aOiOB5fAOGLLTbo'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a65c8aea-b21a-41ce-9ed7-6b517a69fd0b
  - id: bef5003b-cad2-4f40-bdb2-a80426d52ef5
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2:
  - id: c8402946-ff35-44c5-ab98-74c1bba0975f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: ad794b50f6c6f3b59e853e99f7983136ee098e18
workflow-type: tm+mt
source-wordcount: 913
ht-degree: 0%

---

# Content Credentials

マーケティング部門は、コンテンツの透明性、AIによる情報開示、アセットの改ざん防止にこれまで以上に懸念しています。 AdobeのContent Authenticity Initiative（CAI）は、[Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) （C2PA）技術標準に準拠したツールを構築しています。 暗号化された改ざんされやすいメタデータである&#x200B;_Content Credentials_&#x200B;は、視聴者がコンテンツの系統を理解し、ブランドアセットの整合性を確保するのに役立ちます。 こうした情報には、次のものが含まれます。

* 発行者または署名者 – アセットを認証または署名するためにデジタル署名を発行したエンティティまたは会社に関する情報。
* 発行日 – Content Credentialがアセットに適用された日付。
* クレジットと使用状況 – 名前、ソーシャルメディアの取り扱い、またはその他のID関連情報を含む、アセットの制作者に関する情報。
* プロセス – アセットに対して行われた編集または変更の記録。
* デバイスの詳細 – アセットの作成または編集に使用するアプリまたはデバイスに関する情報。
* AI ツールの使用 – 生成AIを使用してアセットを編集または作成した場合、使用するモデルの名前が含まれる場合があります。
* その他の関連情報 – アセットの履歴に関するより多くのコンテキストを提供するために、追加のデータも含まれる場合があります。

アセット履歴の詳細については、Adobe Content Authenticity [&#x200B; インスペクションツール &#x200B;](https://contentauthenticity.adobe.com/inspect)を使用してください。

Content Credentialsは画像ファイルで保持されます。 生成AIで生成または編集された画像が[!DNL Adobe Journey Optimizer B2B Edition]にアップロードされるか、またはから書き出されると、そのContent Credentialsは保持されます。

>[!NOTE]
>
>PDFや埋め込み（base64）ソースから画像を抽出するなど、画像をコンテンツに読み込む方法によっては、元のContent Credentialsが保持されない場合があります。 この場合、Content Credentialsはソースから読み取ることができず、結果に対して作成されません。

>[!BEGINSHADEBOX]

## チャネルを通じたContent Credentialsの永続性 {#channels}

メールまたはWhatsApp メッセージに画像を含めると、配信された画像のContent Credentialsも保持されます。

* **電子メール** - _電子メールを送信_ ジャーニーアクションを使用する場合、_Assets_ ライブラリから電子メールコンテンツに画像を追加します。 電子メールが配信されると、受信者はメッセージから画像をダウンロードでき、Content Credentialsはそのまま維持されます。
* **WhatsApp** - Meta ビジネス アカウントのWhatsApp メッセージ テンプレートに画像を追加します。 独自のシステムから直接追加するか、_Assets_ ライブラリから画像ファイルをダウンロードできます。 _WhatsAppを送信_ ジャーニーアクションにテンプレートを使用します。 WhatsApp メッセージが配信されると、受信者はメッセージから画像をダウンロードでき、Content Credentialsはそのまま残ります。

>[!ENDSHADEBOX]

## Content Credentialsに影響するアクション {#cc-workflows}

>[!INFO]
>
>生成AIの透明性に関する新たな法律が制定されつつあり、Adobeでは、さまざまな地域で適用される要件を満たすために取り組んでいます。 Content Credentialsは、Adobeがこれらの法律の要件を満たすために使用する出所ツールです。

[!DNL Journey Optimizer B2B Edition]で生成AI ツールを使用して画像を生成または編集すると、Content Credentialsがその画像に自動的に添付され、ユーザー側で操作は必要ありません。

### 画像を生成 {#generate}

**_Example:_**&#x200B;目的のビジュアルを説明するテキストプロンプトから、メール用のバナー画像を生成します。 Content Credentialsが生成された画像にアタッチされます。

テキストプロンプトから新しい画像を作成したり、参照画像から新しい画像を作成したり、同様の画像を生成したりすると、Content Credentialsは常にアタッチされます。

### 画像の切り抜き {#crop}

**_Examples:_**

* 生成されたバナー画像をweb ページに合わせて切り抜きます。 Content Credentialsは切り抜きを通して保存されます。
* アップロードしたストック写真をメールの背景として使用し、画面に合わせて切り抜きます。 ストックフォトに生成AI情報が含まれていない場合、Content Credentialsは作成されません。

要求されたサイズに切り抜くなど、画像ファイルに調整を加えた場合、ソースイメージに既に画像が含まれている場合にのみ、Content Credentialsが保持されます。 切り抜きは、画像のピクセルを再作成します。通常、このピクセルはContent Credentialから削除されるので、AI アシスタントは切り抜く前にソースイメージから画像を読み取り、切り抜いた結果に再作成して再び添付します。 切り抜き自体は、新しい生成AI アクションを追加するものではなく、既存の生成AI アクションを保持します。

### テキストオーバーレイの追加

**_Example:_** ランディングページ用に生成された背景画像のテキストオーバーレイとして、プロモーション用の見出しを作成します。 背景画像のContent Credentialsは保持されます。

生成されたテキストを背景画像の上にレンダリングする場合、背景画像にContent Credentialsが既に含まれている場合にのみ、Content Credentialsが生成された画像にアタッチされます。 オーバーレイをレンダリングすると新しい画像が生成されるため、画像編集ツールはContent Credentialsを背景から読み取り、結果に再びアタッチします。 オーバーレイ手順では、新しい生成AI アクションは追加されません。

### 画像のオーバーレイ

**_Examples:_**

* 生成された製品画像と生成された背景を組み合わせて、メールヘッダーを作成します。 その結果、生成AIのソースを反映させたContent Credentialsが生成されました。
* アップロードした2枚のブランド写真を1つのコラージュ画像に結合。 どちらのソース画像も生成AI アクションを搭載していないため、Content Credentialsは作成されません。

2つ以上の画像を合成し、任意のソース画像にContent Credentialsが含まれている場合、結合された画像はそれらを保持し、1つのContent Credentials メタデータ要素に結合されます。 合成すると、ソースから新しい画像が生成され、通常はContent Credentialsが削除されます。 しかし、画像編集ツールは、合成する前にそれぞれを読み取り、次に生成AI アクションに貢献したすべてのソースを一覧表示する、単一の結合されたContent Credentials要素を構築します。

<!--

In [!DNL Adobe Journey Optimizer B2B Edition], you can see Content Credentials directly within the _Assets_ library. When you open the asset details, any image with Content Credentials (such as those created with GenAI services) shows the manifest details in a dedicated panel. If the asset is downloaded, published, or shared, the Content Credentials remain intact with the asset.

_To access Content Credentials:_

1. In the left navigation, expand **[!UICONTROL Content Management]** and select **[!UICONTROL Assets]**.

   This action opens a listing page with all the assets listed.

1. Navigate to a folder, and select the desired asset.

1. In the right panel, ??? where is it.

-->