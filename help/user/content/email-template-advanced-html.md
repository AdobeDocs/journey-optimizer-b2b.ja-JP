---
title: 電子メールテンプレートデザイン用の高度なHTML モード
description: 高度なHTML モードを使用すると、Journey Optimizer B2B editionの電子メールデザインスペースで、電子メールテンプレートコンテンツの生のHTML ソースを直接表示および編集できます。
feature: Email Authoring, Templates, Content Design Tools
level: Experienced
role: User
source-git-commit: 95dba963e08125370f998cf3960d51ede94c2fb9
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---

# 電子メールテンプレートデザイン用の高度なHTML モード

_高度なHTML モード_&#x200B;では、経験豊富なユーザーがメール テンプレート コンテンツの未加工のソースコードを直接表示および編集できるビューを提供します。 このモードは、コンディショナルロジックなどの高度なエクスプレッションをソースに直接挿入する場合に最適です。 また、ビジュアルデザインツールで表示される範囲を超えた構造調整を行う場合にも便利です。

<!-- We don't have the code editor at this point 
>[!NOTE]
>
>_Advanced HTML mode_ is different from the code editor option that is available when you start a new design. The code editor does not allow you to change to the visual design space. With _advanced HTML mode_, you can toggle back and forth between the HTML source view and the visual design view at any time. -->

>[!AVAILABILITY]
>
>この機能は現在&#x200B;_可用性が制限_&#x200B;されており、すべてのユーザーが利用できるわけではありません。

## 重要な制限事項

[電子メールテンプレートのオーサリング &#x200B;](./email-template-authoring.md)に高度なHTML モードを使用する前に、次の制限事項を理解していることを確認してください。

* **検証なし** — HTML エディターは、構文の確認やレイアウトの検証を行いません。 保存する前に、コードを注意深く確認してください。

* **コンテンツの更新** – 今後のシステムの変更は、高度なHTML モードでデフォルトのマークアップに加えられた変更に影響を与えたり、上書きしたりする可能性があります。 製品の更新後にコンテンツを確認し、期待どおりにレンダリングされるようにします。

* **サポートの制限** – 高度なAdobe モードで行われたカスタムコードの変更に起因するレンダリングの問題やコンテンツエラーをトラブルシューティングできません。

* **プレビューの制限** — コンテンツシミュレーション（プロファイルを使用したプレビュー）は、HTML ソースビューから直接ではなく、デスクトップビューでのみ使用できます。

### 高度なHTML モードへのアクセス

高度なHTML モードは、電子メールテンプレートがカンバスに読み込まれている場合、ビジュアルデザインスペースの上部にあるツールバーからアクセスできます。

1. 電子メールテンプレート [&#128279;](./email-templates.md#create-an-email-template)を開くか作成し、デザインスペースを開いてコンテンツを編集します。

1. デザインスペースで、ツールバーの&#x200B;_[!UICONTROL HTML]_ （![HTML アイコン &#x200B;](../assets/do-not-localize/icon-code.svg)）アイコンをクリックします。

   ![電子メールテンプレートデザインスペースツールバーのHTML アイコンをクリック &#x200B;](./assets/email-template-advanced-html-mode-toolbar.png){width="750" zoomable="yes"}

   初めて高度なHTML モードを開く場合（または1か月以上経過した場合）、警告メッセージが表示されます。 情報を確認し、**[!UICONTROL OK]**&#x200B;をクリックして続行します。

   ![高度なHTML モードの警告を確認し、「OK」をクリックして続行します](./assets/email-template-html-mode-warning.png){width="500"}

   デザインキャンバスは、生のHTML ソースビューに切り替わります。

1. コードを確認し、必要な変更をメールコンテンツに追加します。

   _高度なHTML モード_&#x200B;では、メールテンプレートコンテンツの完全なHTML ソースに直接アクセスできます。

   * 生のHTML マークアップの任意の部分を表示および変更します。
   * 高度な[&#x200B; パーソナライゼーション式](./personalization.md)を直接ソースに挿入します。
   * 式の構文を使用して[条件付きコンテンツ &#x200B;](./conditional-content.md) ロジックを追加します。
   * ビジュアルエディターのコントロールでは使用できない、カスタムのHTML属性、トラッキングタグ、その他のマークアップを追加します。

   ![電子メールコンテンツの生のHTML ソースを使用した高度なHTML モード &#x200B;](./assets/email-template-advanced-html-mode.png){width="800" zoomable="yes"}

   >[!IMPORTANT]
   >
   >正しいHTMLとCSS コードを入力してください。Adobeでは、構文の検証やカスタムコードのサポートは提供されていません。

   コンテンツのシミュレーションと保存は、互換性の理由から、高度なHTML モードでは使用できません。 デスクトップビューに戻って、コンテンツをプレビューし、テンプレートを保存できます。 HTMLのソースビューとビジュアルデザインビューを切り替えると、編集した内容は保持されます。

   高度なHTML モードで右上の&#x200B;**[!UICONTROL 保存]**&#x200B;または&#x200B;**[!UICONTROL 保存して閉じる]**&#x200B;をクリックすると、テンプレートを保存してデザインスペースを終了する前に、高度なHTML モードから切り替える必要があることを知らせる警告ダイアログが表示されます。

   ![高度なHTML モードで保存が無効になっている警告ダイアログ &#x200B;](./assets/email-template-advanced-html-save-disabled-alert.png){width="500"}

1. ツールバーの&#x200B;_[!UICONTROL デスクトップ]_ （![&#x200B; デスクトップアイコン &#x200B;](../assets/do-not-localize/icon-desktop-spectrum-1.svg)）アイコンをクリックして、高度なHTML モード（HTML ソースビュー）からビジュアルデザインキャンバスに切り替えます。

   ビューを切り替えると、編集内容は保持されます。
