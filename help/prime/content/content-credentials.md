---
title: Content Credentials
description: Adobe Journey Optimizer B2B Primeが、生成AIで生成された画像にContent Credentialsを自動的に適用する方法と、これがコンテンツにもたらす意味をご紹介します。
feature: Assets, Content
role: User
badgeBeta: label="ベータ版" type="informative" tooltip="この機能は、限定的なベータ版リリースの一部です。"
autotag-review: '2026-07-31T22:31:06.899Z'
TQID: 'https://experienceleague.adobe.com/fBPnAmupve3xMSw5fZPQBDTUfr-rwiH2-R3wbKvox-E'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a65c8aea-b21a-41ce-9ed7-6b517a69fd0b
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
  - id: aed878b8-11d0-487c-828b-d23b2051ec37
subfeature_v2:
  - id: d270a788-eb1d-40ed-b74e-9158ed975b1f
  - id: c8402946-ff35-44c5-ab98-74c1bba0975f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: edb796d131c2b058215b73519b845125432d84f8
workflow-type: tm+mt
source-wordcount: 562
ht-degree: 1%

---

# Content Credentials

マーケティング部門は、コンテンツの透明性、AIによる情報開示、アセットの改ざん防止にこれまで以上に懸念しています。 AdobeのContent Authenticity Initiative（CAI）は、[Coalition for Content Provenance and Authenticity](https://c2pa.org/specifications/specifications/1.1/specs/C2PA_Specification.html#_trust_model) （C2PA）技術標準に準拠したツールを構築しています。 _Content Credentials_&#x200B;は、暗号化された改ざん防止のメタデータのセットで、視聴者がコンテンツの系統を理解し、ブランドアセットの整合性を確保するのに役立ちます。 こうした情報には、次のものが含まれます。

* 発行者または署名者 – アセットを認証または署名するためにデジタル署名を発行したエンティティまたは会社に関する情報。
* イシュー日 – Content Credentialがアセットに適用された日付。
* クレジットと利用状況：名前、ソーシャルメディアのハンドル、その他のID関連情報など、アセットの制作者に関する情報。
* プロセス – アセットに対して行われた編集または変更の記録。
* デバイスの詳細 – アセットの作成または編集に使用したアプリまたはデバイスに関する情報。
* 使用されているAI ツール：アセットの作成に生成AIを使用した場合、使用されているモデルの名前を含めることができます。
* その他の関連情報 – アセットの履歴に関するより多くのコンテキストを提供するのに役立つ追加データも含まれています。

アセット履歴の詳細については、Adobe Content Authenticity [&#x200B; インスペクションツール &#x200B;](https://contentauthenticity.adobe.com/inspect)を使用してください。

Content Credentialsは画像ファイルで保持されます。 生成AIで生成または編集された画像が[!DNL Adobe Journey Optimizer B2B Prime]にアップロードされるか、またはから書き出されると、そのContent Credentialsは保持されます。

>[!NOTE]
>
>PDFや埋め込み（base64）ソースから画像を抽出するなど、画像をコンテンツに読み込む方法によっては、元のContent Credentialsが保持されない場合があります。 この場合、Content Credentialsはソースから読み取ることができず、結果に対して作成されません。

>[!BEGINSHADEBOX]

## チャネルを通じたContent Credentialsの永続性 {#channels}

メールまたはWhatsApp メッセージに画像を含めると、配信された画像のContent Credentialsも保持されます。

* **電子メール** - _電子メールを送信_ ジャーニーアクションを使用する場合、_Assets_ ライブラリから電子メールコンテンツに画像を追加します。 電子メールが配信されると、受信者はメッセージから画像をダウンロードでき、Content Credentialsはそのまま維持されます。
* **WhatsApp** - Meta Business アカウントのWhatsApp メッセージテンプレートに画像を追加します。 システムから直接追加することも、_Assets_ ライブラリから画像ファイルをダウンロードすることもできます。 _WhatsAppを送信_ ジャーニーアクションにテンプレートを使用します。 WhatsApp メッセージが配信されると、受信者はメッセージから画像をダウンロードでき、Content Credentialsはそのまま残ります。

>[!ENDSHADEBOX]

## 画像生成 {#generate}

>[!INFO]
>
>生成AIの透明性に関する新たな法律が制定されつつあり、Adobeでは、さまざまな地域で適用される要件を満たすために取り組んでいます。 Content Credentialsは、Adobeがこれらの法律の要件を満たすために使用する出所ツールです。

生成AIを使用して[!DNL Journey Optimizer B2B Prime]で電子メールコンテンツ用の画像を作成すると、Content Credentialsが生成された画像に自動的に添付され、ユーザー側での操作は必要ありません。 生成AI ツールは、元のソースを含む既存の認証情報を持つ画像のバリエーションに対して、Content Credentials要素を組み合わせて生成します。

>[!NOTE]
>
>[!DNL Journey Optimizer B2B Prime]は現在、手動画像編集アクションをサポートしていません。 これらのアクションのContent Credentials ワークフローは、現時点では適用できません。
