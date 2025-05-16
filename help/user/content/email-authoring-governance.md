---
title: 管理テンプレートからのオーサリング
description: ロックされたコンテンツコンポーネントを含む管理済みテンプレートでメールオーサリングを使用する方法を説明します。
feature: Email Authoring, Content
role: User
exl-id: 1af996a6-a010-4899-96e9-bad76f93865c
source-git-commit: 4a54548ad061fc778fae3bc4b8499f3716850e4a
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 1%

---

# 管理されたテンプレートからのオーサリング

コンテンツデザイナーは、メールテンプレートの作成時に [ ガバナンス（_コンテンツロック_） ](./template-content-governance.md) を有効にできます。 ガバナンス機能を使用すると、アカウントジャーニーで使用した場合に変更できないデザインの部分を指定できます。 メールを作成するために [ 保存済みのテンプレートを選択 ](./email-authoring.md#select-a-template) すると、ビジュアルデザイナーがテンプレートを読み込み、メールの基礎として使用できるようになります。

テンプレートでガバナンスが有効になっている場合、右側のプロパティパネルにアラートが表示されます。 キャンバスの上部にある **[!UICONTROL 編集可能な領域をハイライト]** をオンにすると、ジャーニーで編集可能なコンポーネントとコンテンツ要素が表示されます。

![ 編集可能な領域を管理テンプレートに表示する ](./assets/email-designer-governed-highlight.png){width="800" zoomable="yes"}

また、_ナビゲーションツリー_ を使用して、ロックされている要素や編集可能な要素を決定することもできます。 キャンバスの左側にある _ナビゲーションツリー_ アイコン ![ リンクアイコン ](../assets/do-not-localize/icon-navigation-tree.svg)）をクリックして、ツリーを表示します。

![ 編集可能な領域を管理テンプレートに表示する ](./assets/email-designer-governed-tree.png){width="600" zoomable="yes"}

アイコンは、適用されたコンテンツのロック設定を示します。

| アイコン | 名前 | 説明 |
|------|------|-------------|
| ![ 読み取り専用アイコン ](../assets/do-not-localize/icon-tree-lock.svg) | 読み取り専用 | コンポーネントはロックされており、編集できません。 ルート（_[!UICONTROL 本文]_）レベルで適用すると、すべての子コンポーネントがロックされ、編集できなくなります。 |
| ![ コンテンツ編集アイコン ](../assets/do-not-localize/icon-tree-content-lock.svg) | コンテンツのロック | コンテンツのロックは、コンポーネントレベルで適用されます。 |
| ![ 編集可能アイコン ](../assets/do-not-localize/icon-edit.svg) | 編集可能 | このコンポーネントは完全に編集可能です。 ただし、要素を削除できない場合があります。 |
| ![ コンテンツ編集アイコン ](../assets/do-not-localize/icon-tree-edit-text.svg) | 編集可能 – コンテンツのみ | コンポーネントとスタイル設定は静的ですが、コンテンツ（テキストや画像など）を変更できます。 |
