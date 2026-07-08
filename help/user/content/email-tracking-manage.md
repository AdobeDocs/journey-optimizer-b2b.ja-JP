---
title: 電子メールの開封トラッキングを管理
description: 個々の電子メールに対して電子メールの開封トラッキングを無効にするか、担当者のトラッキング設定をキャプチャし、分割パスを使用してトラッキングとトラッキング以外の電子メールのバリエーションを送信します。
feature: Account Journeys, Channels
topic: Content Management
role: User
level: Beginner, Intermediate
autotag-review: '2026-07-08T00:02:50.497Z'
TQID: 'https://experienceleague.adobe.com/LIutoajlpVQTeJP2y4i0Wv7H-WqGj-c-LVsOGfin384'
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: a4b836d9-ffdd-4df3-a62a-f78b830cf059
  - id: d6e625c1-468f-4d73-9f32-fd1edb87f96b
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
  - id: f01b5556-e951-40ba-8625-2e3001864f2b
subfeature_v2:
  - id: ff0c35fa-aa7e-4050-a37c-198fcacd09e6
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 61481d57fb8eca805d9a9bc545124aed568b5416
workflow-type: tm+mt
source-wordcount: 860
ht-degree: 0%

---

# 電子メールの開封トラッキングを管理

個々の電子メールに対して開封トラッキングを無効にしたり、Adobe Experience Platformで各個人のトラッキング環境設定を取得したり、分割パスを使用して、トラッキング対象とトラッキング以外の電子メールのバリエーションにユーザーをルーティングしたりできます。

>[!BEGINSHADEBOX &quot;電子メールトラッキングピクセルに関するCNIL ガイダンス&quot;]

2026年4月14日、*Commission Nationale de l&#39;Informatique et des Libertés* （CNIL）は、メール内でのトラッキングピクセルの使用に関する[の推奨事項](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf)を公開しました。 このガイダンスでは、同意が必要なタイミングを明確にし、メールのピクセル追跡における適切な同意管理の重要性を強調しています。 このポリシーは、フランスに拠点を置く購読者にメールを配信するエンティティの送信方法に影響を与える可能性があります。

電子メールトラッキングピクセルは、電子メールのHTMLに埋め込まれた1x1の透明画像です。 受信者のメールクライアントがその画像を読み込むと、ピクセルはタイムスタンプ、デバイスの種類、メールクライアント、場合によってはIP アドレスなどのデータを記録するサーバーにping送信し、おおよその場所を確認します。 その後、そのログは受信者のレコードに関連付けられ、マーケターはメールが開封されたかどうかを確認できます。

ここで説明する[!UICONTROL Journey Optimizer B2B edition]製品の機能は、適切に設定および操作され、コンプライアンスに準拠した実装をサポートできるビルディングブロックです。 各顧客は、適用法に基づく義務を決定し、遵守する責任があります。

>[!ENDSHADEBOX]

## 1通のメールのトラッキングを無効にする {#disable-tracking-single-email}

このオプションは、特定の電子メールを受信したユーザーに関係なく、開封済みのアクティビティを報告しない場合に使用します。

1. 右側のジャーニーノードのプロパティで、メールを開きます。

1. メールプロパティで、「**[!UICONTROL 開封トラッキングを無効にする]**」チェックボックスを選択します。

   ![電子メールの開封トラッキングを無効にする](./assets/email-tracking-disable-all.png){width="500" zoomable="yes"}

   電子メールプロパティの完全なリストについては、[電子メール設定の定義](./add-email.md#define-the-email-settings)を参照してください。

## トラッキング設定で利用者をセグメンテーション {#segment-people-tracking-preference}

各ユーザーに電子メールの開封率を追跡させるかどうかを指定する場合は、その設定をAdobe Experience Platform（AEP）のユーザー属性として取得します。 このフィールドを[&#x200B; ランディングページフォーム &#x200B;](./forms.md)で使用すると、連絡先がメール開封トラッキングをオプトアウトする機会を得ることができます。 その後、ジャーニーで&#x200B;_パスを分割_ ノードを使用して、トラッキングとトラッキング以外のユーザーを様々なメールバリエーションにルーティングできます。 これにより、すべての人に対してオープンなトラッキングを無効にすることなく、個々のオプトアウトを尊重することができます。

このワークフローは、次の3つの部分で構成されています。

1. [AEPで環境設定をトラッキングするためのカスタムフィールドを追加し](#add-custom-field-tracking-preference)、フォームリンクを使用してオプトアウトコミュニケーションを送信します。
1. [&#x200B; ジャーニー内のオプトアウト &#x200B;](#add-split-path-tracking)を追跡するための分割パスを追加します。
1. [各パスに対して、トラッキングとトラッキング以外のメールのバリエーション &#x200B;](#configure-tracking-and-non-tracking-email-variants)を設定します。

### トラッキング環境設定のカスタムフィールドを追加 {#add-custom-field-tracking-preference}

>[!NOTE]
>
>カスタム XDM フィールドの追加とマッピングは、Adobe Experience Platformの管理タスクです。 AEPの管理者またはデータエンジニアリングチームと協力して、この手順を完了します。

1. AEPで、B2B Person プロファイルに使用するスキーマを開きます（例：_B2B Person_）。

1. テナント IDで、組織の同意管理フィールドのフィールドグループを見つけるか、作成します（例：`consents`）。

1. フィールド グループにフィールドを追加します。例えば、`emailTracking`という名前のブール型フィールドを使用して、ユーザーがトラッキングを開くことに同意したかどうかを表します。

1. フィールド名と表示名を入力し、タイプを設定してフィールドグループに割り当て、**[!UICONTROL 適用]**&#x200B;をクリックします。

1. 「**[!UICONTROL 保存]**」をクリックして、スキーマの変更を保存します。

   ![AEP スキーマ同意フィールドグループにemailTracking フィールドを追加](./assets/email-tracking-xdm-field-aep-schema.png){width="800" zoomable="yes"}

1. [XDM フィールド管理](../admin/xdm-field-management.md#managed-fields)の[!UICONTROL XDM Individual Profile] クラスの&#x200B;_Managed field_&#x200B;として選択して、[!DNL Journey Optimizer B2B Edition]でフィールドを利用できるようにします。

   ![XDM フィールド管理の管理フィールドとしてemailTrackingを選択](./assets/email-tracking-xdm-field-select.png){width="450"}

   これにより、フィールドをスプリットパスノードの条件として使用できるようになります。

### オプトアウトを追跡するための分割パスの追加 {#add-split-path-tracking}

ジャーニーに&#x200B;[_人ごとにパスを分割_ ノード &#x200B;](../journeys/split-merge-paths-nodes.md#split-paths-by-people)し、各トラッキング設定値のパスを定義します。

1. **[!UICONTROL パスを分割]** ノードを追加し、分割に&#x200B;**[!UICONTROL 人]**&#x200B;を選択します。

1. 最初のパスでは、カスタムトラッキング環境設定フィールドを使用して条件を適用し（例：`emailTracking` is `true`）、オープントラッキングを許可するユーザーを特定します。

   ![&#x200B; パスを分割する条件 – メールトラッキングフィールドをtrueとして追加](./assets/email-tracking-condition-true.png){width="700" zoomable="yes"}

1. 2つ目のパスを追加し、トラッキングをオプトアウトしたユーザーを識別するために逆条件（`emailTracking` is `false`）を適用します。

   パスの追加、条件の適用、パスの並べ替えについての一般的な手順については、[人物ノードによる分割パスの追加](../journeys/split-merge-paths-nodes.md#add-a-split-path-by-people-node)を参照してください。

   ![&#x200B; パスをユーザー別に分割 – 条件のオンとオフを追跡する電子メール &#x200B;](./assets/email-tracking-split-paths.png){width="500" zoomable="yes"}

### トラッキングとトラッキング以外のメールのバリエーションを設定する {#configure-tracking-and-non-tracking-email-variants}

各パスに[_[!UICONTROL &#x200B; メール送信&#x200B;]_&#x200B;アクションノード &#x200B;](./add-email.md)を追加して、すべてのユーザーがトラッキング設定に一致するメールバリアントを受信できるようにします。

1. トラッキングが有効なパスで、**[!UICONTROL メールを送信]** アクションを追加し、通常どおりメールを選択または作成します。メールのプロパティで&#x200B;**[!UICONTROL 開封トラッキングを無効にする]**&#x200B;がクリアされたままになります。

1. オプトアウトパスで、同じ電子メールまたは重複した電子メールを使用して&#x200B;**[!UICONTROL 電子メールを送信]** アクションを追加し、右側の電子メールプロパティで「**[!UICONTROL 開封トラッキングを無効にする]**」チェックボックスを選択します。

   ![&#x200B; パスをトラッキングするための電子メール – オープン トラッキングを無効にする](./assets/email-tracking-disable.png){width="600" zoomable="yes"}

1. [ジャーニーを公開します](../journeys/create-publish-journey.md#publish-a-journey)。

   ユーザーは、トラッキング環境設定フィールドの値に一致するメールバリエーションに自動的にルーティングされ、ユーザーが設定に加えた更新は、次回ジャーニーにエントリしたときに反映されます。
