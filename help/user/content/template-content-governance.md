---
title: テンプレートコンテンツガバナンス
description: アカウントジャーニーで使用するためにメールテンプレートのコンテンツ要素をどのように変更できるかを制御できるように、コンテンツ要素をロックする方法を説明します。
feature: Templates, Email Authoring, Content
role: User
exl-id: 0cf852cd-491c-4478-8d5e-51fd2cc2625a
source-git-commit: 4905346d8160147f7d71b7b1131ea33f26d3bba0
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 0%

---

# テンプレートコンテンツガバナンス

多くのマーケティング組織には、メールキャンペーンを設計するコンテンツ専門家がいます。 特定のデザインは、組織全体のカスタムアカウントジャーニーの基盤として使用できます。 承認済みのコンテンツデザインに確実に準拠するには、コンテンツガバナンス機能を使用してテンプレートコンポーネントをロックします。 メールテンプレートでコンテンツのロックをアクティブ化すると、マーケターは、許可された要素のみを変更して、コンテンツ戦略に合わせることができます。

例えば、ブランド通信の継続性を確保するために設計されたヘッダーとフッターをロックできます。 また、本文セクションを含む列をロックすることもできますが、作成者は、アカウントジャーニーのデザイン内での目的を満たすようにテキストを変更できます。

## テンプレートのコンテンツガバナンスの有効化

ビジュアルデザイナーを使用してメールテンプレートの [ 構造コンポーネントとコンテンツコンポーネントのオーサリング ](./email-template-authoring.md) を行ったら、ガバナンスを有効にし、必要に応じて特定のコンテンツロックを適用します。

1. ビジュアルデザイナーで、_ナビゲーションツリー_ を使用して、レイヤー/コンテナおよび要素にアクセスします。

   キャンバスの左側にある _ナビゲーションツリー_ アイコン ![ リンクアイコン ](../assets/do-not-localize/icon-navigation-tree.svg)）をクリックして、ツリーを表示します。

1. ツリー内で、ルートの **[!UICONTROL 本文]** コンポーネントを選択します。

   キャンバスの右側にあるプロパティパネルには、デフォルトで _[!UICONTROL 設定]_ タブが表示されます。

1. 「**[!UICONTROL ガバナンス]**」オプションを有効にします。

   ![ メールテンプレートのガバナンスの有効化 ](./assets/governance-template-enable.png){width="800" zoomable="yes"}

   このオプションを有効にすると、デフォルトの _[!UICONTROL モード]_ は **[!UICONTROL 読み取り専用]** になります。 このモードをルートレベルで設定すると、テンプレート内のすべての要素がロックされます。 左側のツリー構造では、ルートおよびすべての子要素の横に _読み取り専用_ アイコン（![ 読み取り専用アイコン ](../assets/do-not-localize/icon-tree-lock.svg)）が表示されます。

1. テンプレート内で特定のコンテンツのロックを有効にするには、**[!UICONTROL モード]** を **[!UICONTROL コンテンツのロック]** に変更します。

   このモードをルートレベルで設定すると、テンプレート内のすべての要素のロックが解除されます。 左側のツリー構造では、ルート要素の横に _コンテンツロック_ アイコン（![ コンテンツロックアイコン ](../assets/do-not-localize/icon-tree-content-lock.svg)）が表示されます。 必要に応じて、コンテンツを含む（構造）コンポーネントと個々のコンテンツコンポーネントにコンテンツロックを適用します。

   ジャーニーのメール作成者が構造要素やコンテンツ要素を追加できるようにするには、**[!UICONTROL コンテンツ追加を有効にする]** をオンにします。 許可する追加のタイプを選択します。

   * **[!UICONTROL 構造およびコンテンツの追加を許可]** – 作成者が構造要素とコンテンツ要素の両方を追加できるようにする場合は、このオプションを選択します。

   * **[!UICONTROL コンテンツの追加のみを許可]** – 作成者にコンテンツ要素の追加のみを許可する場合は、このオプションを選択します。

   ![ コンテンツの追加を有効にする ](./assets/governance-template-content-additions.png){width="600" zoomable="yes"}

   このモードをルートレベルで設定すると、テンプレート内のすべての要素がロックされます。 左側のツリー構造では、ルートおよびすべての子要素の横に _読み取り専用_ アイコン（![ 読み取り専用アイコン ](../assets/do-not-localize/icon-tree-lock.svg)）が表示されます。
<!-- 

   
- ![Link icon](../assets/do-not-localize/icon-navigation-tree.svg)
- ![Read only icon](../assets/do-not-localize/icon-tree-lock.svg)
- ![Content edit icon](../assets/do-not-localize/icon-tree-content-lock.svg)
- ![Content edit icon](../assets/do-not-localize/icon-tree-edit-text.svg)
- ![Edit element](../assets/do-not-localize/icon-edit.svg) -->

## 構造へのロックの適用

構造継承モデルを使用し、適用するガバナンスに従って、メールテンプレートのレイアウトと構造を計画します。 構造コンポーネントをコンテナとして使用し、ロックまたは編集可能として簡単に指定できる方法で項目をグループ化します。 メールテンプレートデザインが行われたら、構造を確認し、計画に従ってロック機能を適用します。

構造レベルでロックタイプを適用すると、その子コンポーネントのデフォルト設定が指定されます。 その後、必要に応じて、列またはコンテンツ要素レベルで特定のロック設定を適用できます。

1. キャンバスの左側にある _ナビゲーションツリー_ アイコン ![ リンクアイコン ](../assets/do-not-localize/icon-navigation-tree.svg)）をクリックして、ツリーを表示します。

1. ツリー内の構造を選択します。

   キャンバスの右側にあるプロパティパネルには、デフォルトで _[!UICONTROL 設定]_ タブが表示されます。

1. **[!UICONTROL ロックタイプ]** を設定します。

   * **[!UICONTROL ロック済み]** – この設定では、すべての子コンポーネントがデフォルトでロックされます。 左側のツリー構造では、すべての子コンポーネントの横に _読み取り専用_ アイコン（![ 読み取り専用アイコン ](../assets/do-not-localize/icon-tree-lock.svg)）が表示されます。

   * **[!UICONTROL 編集可能]** – この設定を使用すると、デフォルトですべての子コンポーネントを編集できます。 左側のツリー構造には、子コンポーネントの横にアイコンは表示されません。

   ![ 構造コンポーネントにコンテンツロックを適用する ](./assets/governance-template-structure-locking.png){width="800" zoomable="yes"}

## 子コンポーネントのロックの設定

1. ツリーでコンポーネントを選択します。

   キャンバスの右側にあるプロパティパネルには、デフォルトで _[!UICONTROL 設定]_ タブが表示されます。

1. 「**[!UICONTROL 特定のロックを使用]** オプションを有効にします。

1. 適用するガバナンスのタイプを選択します。

   * **[!UICONTROL 編集可能]** - メールのオーサリング中に、コンポーネントの完全なエディトリアルコントロールを可能にします。
   * **[!UICONTROL 編集可能なコンテンツのみ]** - メール作成者がコンテンツを変更できますが、コンポーネント自体は変更できません。
   * **[!UICONTROL ロック済み]** - メールのオーサリング中にコンポーネントに変更が加えられるのを防ぎます。

     コンポーネントがロックされている場合は、「削除を許可 **[!UICONTROL オプションをオンにすることで、メールのオーサリング中にコンポーネントを削除でき]** す。

   ![ 子コンポーネントへのコンテンツロックの適用 ](./assets/governance-template-component-locking.png){width="800" zoomable="yes"}
