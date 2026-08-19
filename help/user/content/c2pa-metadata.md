---
title: C2PA メタデータ
description: Adobe Journey Optimizer B2B editionが、生成AI ツールで生成または編集された画像にC2PA メタデータを自動的に適用する仕組みと、これがコンテンツにもたらす意味をご紹介します。
feature: Assets, Content
hide: true
role: User
autotag-review: '2026-07-31T22:15:54.535Z'
TQID: 'https://experienceleague.adobe.com/9XCqPWz62uDDLFAyxARfD2jErYx2aOiOB5fAOGLLTbo'
product_v2: id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2: id: a65c8aea-b21a-41ce-9ed7-6b517a69fd0bid: bef5003b-cad2-4f40-bdb2-a80426d52ef5id: e666e996-b2cf-4c45-8fc2-1c625212abab
subfeature_v2: id: c8402946-ff35-44c5-ab98-74c1bba0975f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: c1e8e03ccd6f2d132ca1bc1a27c0d9ea18dcdcac
workflow-type: tm+mt
source-wordcount: 913
ht-degree: 0%

---

# C2PA メタデータ

マーケティング部門は、コンテンツの透明性、AIによる情報開示、アセットの改ざん防止にこれまで以上に懸念しています。 AdobeのContent Authenticity Initiative（CAI）は、[Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) （C2PA）技術標準に準拠したツールを構築しています。 _C2PA メタデータ_&#x200B;は暗号化され、改ざんされやすい情報で、視聴者がコンテンツの系統を理解し、ブランドアセットの整合性を確保するのに役立ちます。 こうした情報には、次のものが含まれます。

* 発行者または署名者 – アセットを認証または署名するためにデジタル署名を発行したエンティティまたは会社に関する情報。
* 発行日 – C2PA メタデータがアセットに適用された日付。
* クレジットと使用状況 – 名前、ソーシャルメディアの取り扱い、またはその他のID関連情報を含む、アセットの制作者に関する情報。
* プロセス – アセットに対して行われた編集または変更の記録。
* デバイスの詳細 – アセットの作成または編集に使用するアプリまたはデバイスに関する情報。
* AI ツールの使用 – 生成AIを使用してアセットを編集または作成した場合、使用するモデルの名前が含まれる場合があります。
* その他の関連情報 – アセットの履歴に関するより多くのコンテキストを提供するために、追加のデータも含まれる場合があります。

アセット履歴の詳細については、Adobe Content Authenticity [ インスペクションツール ](https://contentauthenticity.adobe.com/inspect)を使用してください。

C2PA メタデータは画像ファイルに保持されます。 生成AIで生成または編集された画像が[!DNL Adobe Journey Optimizer B2B Edition]にアップロードされるか、またはから書き出されると、そのC2PA メタデータが保持されます。

>[!NOTE]
>
>PDFや埋め込み（base64）ソースから画像を抽出するなど、画像をコンテンツに読み込む方法によっては、元のC2PA メタデータが保持されない場合があります。 このような場合、C2PA メタデータはソースから読み取ることができず、結果に対して作成されません。

>[!BEGINSHADEBOX]

## チャネルを通じたC2PA メタデータの永続性 {#channels}

メールまたはWhatsApp メッセージに画像を含めると、配信された画像のC2PA メタデータも保持されます。

* **電子メール** - _電子メールを送信_ ジャーニーアクションを使用する場合、_Assets_ ライブラリから電子メールコンテンツに画像を追加します。 電子メールが配信されると、受信者はメッセージから画像をダウンロードでき、C2PA メタデータはそのまま維持されます。
* **WhatsApp** - Meta Business アカウントのWhatsApp メッセージテンプレートに画像を追加します。 独自のシステムから直接追加するか、_Assets_ ライブラリから画像ファイルをダウンロードできます。 _WhatsAppを送信_ ジャーニーアクションにテンプレートを使用します。 WhatsApp メッセージが配信されると、受信者はメッセージから画像をダウンロードでき、C2PA メタデータはそのまま維持されます。

>[!ENDSHADEBOX]

## C2PA メタデータに影響するアクション {#cc-workflows}

>[!INFO]
>
>生成AIの透明性に関する新たな法律が制定されつつあり、Adobeでは、さまざまな地域で適用される要件を満たすために取り組んでいます。 C2PA メタデータは、Adobeがこれらの法律の要件を満たすために使用する来歴ツールです。

[!DNL Journey Optimizer B2B Edition]で生成AI ツールを使用して画像を生成または編集すると、C2PA メタデータが自動的にその画像に添付され、ユーザー側での操作は必要ありません。

### 画像を生成 {#generate}

**_Example:_**&#x200B;目的のビジュアルを説明するテキストプロンプトから、メール用のバナー画像を生成します。 生成された画像にはC2PA メタデータが添付されます。

テキストプロンプトから新しい画像を作成する場合、参照画像から作成する場合、または類似の画像を生成する場合、C2PA メタデータは常に添付されます。

### 画像の切り抜き {#crop}

**_Examples:_**

* 生成されたバナー画像をweb ページに合わせて切り抜きます。 C2PA メタデータは、切り抜きを通じて保持されます。
* アップロードしたストック写真をメールの背景として使用し、画面に合わせて切り抜きます。 ストック写真に生成AI情報が含まれていない場合、C2PA メタデータは作成されません。

要求されたサイズに切り抜くなど、画像ファイルに調整を加えた場合、ソースイメージに既に含まれている場合にのみ、C2PA メタデータが保持されます。 切り抜きでは、画像ピクセルが再作成され、通常はC2PA メタデータが削除されるので、AI アシスタントは切り抜く前にソース画像から画像を読み取り、切り抜いた結果に再作成して再添付します。 切り抜き自体は、新しい生成AI アクションを追加するものではなく、既存の生成AI アクションを保持します。

### テキストオーバーレイの追加

**_Example:_** ランディングページ用に生成された背景画像のテキストオーバーレイとして、プロモーション用の見出しを作成します。 背景画像のC2PA メタデータは保持されます。

生成されたテキストを背景画像の上にレンダリングする場合、背景画像に既にC2PA メタデータが含まれている場合にのみ、結果の画像にC2PA メタデータが添付されます。 オーバーレイをレンダリングすると新しい画像が生成されるため、画像編集ツールは背景からC2PA メタデータを読み取り、それを結果に再添付します。 オーバーレイ手順では、新しい生成AI アクションは追加されません。

### 画像のオーバーレイ

**_Examples:_**

* 生成された製品画像と生成された背景を組み合わせて、メールヘッダーを作成します。 その結果、生成AIのソース両方を反映したC2PA メタデータが取得されます。
* アップロードした2枚のブランド写真を1つのコラージュ画像に結合。 どちらのソース画像も生成AI アクションを搭載していないため、C2PA メタデータは作成されません。

2つ以上の画像を合成し、任意のソース画像にC2PA メタデータが含まれている場合、合成された画像はそれを保持し、単一のC2PA メタデータ要素に結合されます。 合成すると、ソースから新しい画像が生成され、通常はそのC2PA メタデータが削除されます。 しかし、画像編集ツールは、合成前にソースメタデータを読み取り、次に生成AI アクションに貢献したすべてのソースをリストする、単一の結合されたC2PA メタデータ要素を構築します。

<!--

In [!DNL Adobe Journey Optimizer B2B Edition], you can see C2PA metadata directly within the _Assets_ library. When you open the asset details, any image with C2PA metadata (such as those created with GenAI services) shows the manifest details in a dedicated panel. If the asset is downloaded, published, or shared, the C2PA metadata remains intact with the asset.

_To access C2PA metadata:_

1. In the left navigation, expand **[!UICONTROL Content Management]** and select **[!UICONTROL Assets]**.

   This action opens a listing page with all the assets listed.

1. Navigate to a folder, and select the desired asset.

1. In the right panel, ??? where is it.

-->
