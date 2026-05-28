---
title: 管理されたテンプレートからのオーサー
description: ロックされたコンテンツを持つ管理されたテンプレートからメールを作成する – Journey Optimizer B2B editionで編集可能な領域を特定し、ガバナンス制約の範囲内で作業します。
feature: Email Authoring, Content
role: User
exl-id: 1af996a6-a010-4899-96e9-bad76f93865c
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
feature_v2:
  - id: e666e996-b2cf-4c45-8fc2-1c625212abab
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f5c2a4bb-71ca-4d7e-8efd-442250e6ba48
autotag-review: 2026-03-30T22:35:16.900Z
TQID: https://experienceleague.adobe.com/iwVl-dwU9oGG0rHQ9-J3EO5r3B778jQCe6XK742ArEo
source-git-commit: 9baf03a1ddc1733385b0398ffadde8f548c431cc
workflow-type: tm+mt
source-wordcount: 277
ht-degree: 1%

---

# 管理されたテンプレートからのオーサー

コンテンツデザイナーは、メールテンプレートの作成時に[&#x200B; ガバナンス（_コンテンツロック_） &#x200B;](./template-content-governance.md)を有効にできます。 ガバナンス機能を使用すると、アカウントジャーニーで使用する際に変更できないデザインの部分を指定できます。 [保存済みのテンプレート &#x200B;](./email-authoring.md#select-a-template)を選択して電子メールを作成すると、ビジュアルデザインスペースにテンプレートが読み込まれ、電子メールのベースとして使用できるようになります。

テンプレートでガバナンスが有効になっている場合、右側のプロパティパネルにアラートが表示されます。 キャンバスの上部にある「**[!UICONTROL 編集可能な領域をハイライト表示]**」をオンにすると、ジャーニーで使用できるコンポーネントとコンテンツ要素を確認できます。

![管理されたテンプレートで編集可能な領域を表示](./assets/email-designer-governed-highlight.png){width="800" zoomable="yes"}

_ナビゲーションツリー_&#x200B;を使用して、ロックまたは編集可能な要素を特定することもできます。 キャンバスの左側にある&#x200B;_ナビゲーションツリー_ アイコン（![&#x200B; リンクアイコン &#x200B;](../assets/do-not-localize/icon-navigation-tree.svg)）をクリックして、ツリーを表示します。

![管理されたテンプレートで編集可能な領域を表示](./assets/email-designer-governed-tree.png){width="600" zoomable="yes"}

アイコンは、適用されたコンテンツロック設定を示します。

| アイコン | 名前 | 説明 |
|------|------|-------------|
| ![読み取り専用アイコン &#x200B;](../assets/do-not-localize/icon-tree-lock.svg) | 読み取り専用 | コンポーネントはロックされており、編集できません。 ルート （_[!UICONTROL Body]_）レベルで適用すると、すべての子コンポーネントがロックされ、編集できません。 |
| ![&#x200B; コンテンツ編集アイコン &#x200B;](../assets/do-not-localize/icon-tree-content-lock.svg) | コンテンツロック | コンテンツロックは、コンポーネントレベルで適用されます。 |
| ![編集可能なアイコン &#x200B;](../assets/do-not-localize/icon-edit.svg) | 編集可能 | コンポーネントは完全に編集可能です。 ただし、要素を削除できない場合があります。 |
| ![&#x200B; コンテンツ編集アイコン &#x200B;](../assets/do-not-localize/icon-tree-edit-text.svg) | 編集可能 – コンテンツのみ | コンポーネントとスタイル設定は静的ですが、コンテンツ（テキストや画像など）を変更できます。 |
