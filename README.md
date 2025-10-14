---
source-git-commit: 7a08e546a71503e44338e996c597058daaf4c667
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 36%

---
# 記事の投稿

アドビでは、コミュニティに加え、ドキュメントチーム以外のアドビ従業員からの投稿も歓迎します。

## アドビオープンソース行動規範

このプロジェクトでは、[アドビオープンソース行動規範](code-of-conduct.md)または [.NET Foundation 行動規範](https://dotnetfoundation.org/code-of-conduct)を採用しています。詳しくは、[投稿](contributing.md)の記事を参照してください。

## Adobeコンテンツへの投稿方法

**Adobeの従業員でない場合は** 外部のコミュニティ投稿を送信できます。 コミュニティの投稿は社内システムにインポートされ、編集されてパブリックリポジトリにマージされます。 その後、公開リポジトリが最新の変更と同期され、非公開リポジトリに結合されます。

**Adobeの従業員の場合**、プライベート [Adobe GitHub リポジトリに直接投稿できます &#x200B;](https://git.corp.adobe.com/AdobeDocs/)。 詳しくは、Adobeの従業員を対象としたAdobe Experience League オーサリングガイドを参照してください。

## 外部寄稿者

### 軽微な変更

マイナーアップデートに参加している場合：

1. 編集するトピックに移動します。
1. 「このコンテンツは役に立ちましたか？」 ブラウザーウィンドウの下部に表示されるバナーで、「**詳細フィードバックオプション**」をクリックします。
1. 「**編集の提案**」をクリックし、GitHub UI で変更内容を含むプルリクエスト（PR）を送信します。

   詳しくは、一般的な[アドビドキュメントのコントリビューターガイド](https://experienceleague.adobe.com/docs/contributor/contributor-guide/introduction.html?lang=ja&ja-jp)を参照してください。

このリポジトリのドキュメントおよびコード例について送信した軽微な修正または説明には、アドビの利用条件が適用されます。

### コミュニティからの大きな変更または新しいトピック

Adobeコミュニティのメンバーが新しいトピックを作成したり、大きな変更をコントリビューションしたりする場合は、該当する Git リポジトリーの「**イシュー**」タブを使用してイシューを送信し、ドキュメントチームとのやり取りを開始します。 計画が合意されたら、Adobeライターと協力してリビジョンを公開します。

**メモ：** ドキュメントおよびコード例に大幅な変更を加えたプルリクエストを送信すると、プルリクエストにオンライン貢献使用許諾契約（CLA）を送信するように求めるメッセージが表示されます。 プルリクエストを確認する前に、オンラインフォームに記入する必要があります。

### ツール

コミュニティの投稿者は、GitHub UI を使用して、基本的な編集をしたり、リポジトリをフォークしたりして、大きな貢献をすることができます。

詳しくは、[アドビドキュメントのコントリビューターガイド](https://experienceleague.adobe.com/docs/contributor/contributor-guide/introduction.html?lang=ja&ja-jp)を参照してください。

## 内部寄稿者

Adobe Experience Cloud ソリューションの製品チームのテクニカルライター、プログラムマネージャー、または開発者で技術記事の投稿または作成を担当している場合は、[&#x200B; プライベートリポジトリ &#x200B;](https://git.corp.adobe.com/AdobeDocs) を使用します。

## トピックの書式設定

このリポジトリ内の記事はすべて、GitHub 固有の Markdown を使用しています。 Markdown について詳しくは、以下を参照してください。

* [マークダウンの基本](https://help.github.com/ja/articles/getting-started-with-writing-and-formatting-on-github/)
* [印刷用マークダウンチートシート](https://guides.github.com/pdfs/markdown-cheatsheet-online.pdf)

## ラベル

パブリックリポジトリでは、アドビがプル要求のワークフローを管理したり、プル要求の状況を投稿者が把握できるようにしたりするために、プル要求に自動ラベルが割り当てられます。

* **Change sent to author**：保留中のプル要求について作成者に通知されました。
* **ready-to-merge**：プル要求レビューチームによるレビューの準備ができました。
