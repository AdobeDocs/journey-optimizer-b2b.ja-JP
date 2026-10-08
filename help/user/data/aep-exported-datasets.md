---
title: 書き出されたExperience Platform データセット
description: Adobe Journey Optimizer B2B Editionによって書き出されるAdobe Experience Platform データセット名とキーフィールドパスのリファレンス。
feature: Setup, Data Management
role: Admin
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
  - id: c8f3fb27-3167-48ac-a66a-fa4bc3f58dda
    internal-label: Integrations
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
autotag-review: '2026-09-29T00:00:00.000Z'
source-git-commit: 801025ee02617d56fc8ab933b59385bca38f5097
workflow-type: tm+mt
source-wordcount: '4845'
ht-degree: 7%
---

# [!DNL Experience Platform]個のデータセットをエクスポートしました

[!DNL Adobe Journey Optimizer B2B Edition]は、アカウント、人物、購買グループ、ジャーニーの情報を[!DNL Adobe Experience Platform]で利用できるようにします。 データセットは、関連するレコードのコレクションです。 たとえば、人物データセットは人物を記述し、メンバーシップデータセットは人物をアカウントやジャーニーに接続し、イベントデータセットはメールを開くなどのアクションを記録します。

このガイドでは、各データセットの内容、フィールドの意味、関連レコードの接続方法を説明します。 データセット名は次のパターンに従います。

**`AJOB2B-<datasetVersion>-<entity>`**

ここでは、`<entity>`は、`person`、`account_relational`、`person_event`などの情報について説明します。 `<datasetVersion>`は、データセットのフィールド定義のバージョンを識別します。 セクションの見出しに文書化された名前が表示されます。[!DNL Experience Platform]環境に古いバージョンが含まれている場合もあります。

これらの書き出しをサポートする名前空間とスキーマの設定については、[B2B名前空間とスキーマ ](./namespaces-schemas.md)を参照してください。

>[!NOTE]
>
>Adobeでは、既存の使用を妨げないように、古いデータセットのバージョンを保持します。 その結果、サンドボックスに同じデータセットの複数のバージョンが表示される場合があります。 古いデータセットを使用しなくなった場合は、Adobeにそのデータセットの削除をリクエストできます。 削除を要求する前に、データセットが使用されていないことを確認します。

## このガイドを読む

- **フィールド名：**&#x200B;は、[!DNL Experience Platform]に表示されている正確な名前です。 `consents.marketing.email.val`など、フィールド内のレベルを個別にドット付けします。
- **レコード ID:**&#x200B;は、そのデータセット内のレコードを識別します。
- **関係：**&#x200B;は、識別子が一致するデータセットとフィールドに名前を付けます。 例えば、`Matches AJOB2B-1_5_4-buying_group (_id)`は、フィールドが購買グループの`_id`を参照することを意味します。 完全なIDを一致させます。このIDを短くしたり、再構築したりしないでください。
- **標準Adobe形式：**&#x200B;は、Adobeの共有フィールド定義を使用します。
- **関連レコード形式：**&#x200B;は、一致する識別子を使用して接続できるレコードとして情報を整理します。

例えば、`buying_group_member.buyingGroupID`は`buying_group._id`に一致し、その`personID`は`person_relational._id`または人物データセットの`personKey.sourceKey`に一致します。 これらのリンクは、購買グループに誰が属するのかを把握するのに役立ちます。 [!DNL Experience Platform]は、リンクのみからレポートまたはオーディエンスを自動的に作成しません。

一部の識別子は、マーケティングプログラムなど、このガイドで個別のデータセットを持たない情報を参照します。 「関係」列では、ここに存在しないデータセットに名前を付ける代わりにこの点をメモします。

レコードが削除済みとしてマークされている場合、`isDeleted`は`true`であり、そうでない場合は`false`です。 一般的なアクティブメンバーまたは同意指標として扱わないでください。 `lastUpdatedDate`は、レコードの最新のデータ更新を説明します。イベントの場合は、`timestamp`を使用して、アクティビティがいつ発生したかを把握します。 空白のフィールドは、情報が利用できないか、そのレコードに適用されないことを意味します。

関連レコードデータセットはバージョン `1_5_4`を使用しています。 フィールドが現在入力されていない場合、または特別な処理が必要な場合は、関連するセクションで顧客に表示される制限について説明します。

オーディエンスとは、選択した基準を満たす人のグループのことです。 オーディエンス作成の可用性は、情報を個人プロファイルに組み合わせるための[!DNL Experience Platform]設定によって異なります。 [!DNL Experience Platform]にデータセットが存在する場合、それ自体ではセグメント化に使用できません。

## データセットの選択

| 把握したいデータ | 探すべきデータセット |
|---|---|
| 人物とそのメール設定 | `person` |
| アカウントの詳細と個人の連絡先の詳細 | `account_relational`, `person_relational` |
| アカウントに関連付けられている人物 | `account_member`, `account_person` |
| 購買グループとそのメンバー、ステータスの変更 | `buying_group`, `buying_group_member`, `buying_group_event` |
| アカウントジャーニーと参加アカウント | `account_journey`, `account_journey_member`, `account_event` |
| 人物ジャーニーと参加人物 | `person_journey`, `person_journey_member` |
| ジャーニー内のステップ | `account_journey_node`, `person_journey_node`, `journey_node` |
| 電子メール、web、その他のサポート対象のアクティビティ | `person_event`, `person_event_relational` |

次の節では、完全なデータセット名とフィールドの詳細を示します。 ジャーニーは、全体的な体験を表します。メンバーシップは、個人またはアカウントをそのジャーニーに結び付けます。イベントは、何かが起こったことを表します。

+++エンティティ関係図

[!DNL Adobe Experience Platform]](./assets/ajo-b2b-data-model.svg)に書き出されたデータセットの![ エンティティ関係ダイアグラム

+++

## `AJOB2B-1_5_1-person`

各レコードは、個人、そのID、メールマーケティングの好みについて説明します。 個人レベルのレポートに使用し、プロファイルを設定してオーディエンスを構築するのに役立ちます。

**書式：**&#x200B;標準Adobe書式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `personID` | レコード ID | 個人の識別子。 完全値を使用して、関連するレコードを一致させます。 |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `identityMap` |  | 接続されたデータ全体で[!DNL Experience Platform]が同じ人物を認識するのに役立つその他のID。 |
| `consents.marketing.email.val` |  | メールマーケティング設定：`n`はオプトアウトを示します。`y`はこのフィールドにオプトアウトが記録されていないことを示します。 このフィールドだけでは、マーケティングメールを送信する権限を確立できません。 |
| `consents.marketing.email.time` |  | メール設定が最後に更新された日時。 |
| `consents.marketing.email.reason` |  | オプトアウトの理由が指定された場合（登録解除の場合のみ）。 |
| `isDeleted` |  | この人物レコードが削除済みとしてマークされているかどうか。 |

>[!NOTE]
>
>組織には、ここに記載されている以外の追加の個人フィールドがある場合があります。

組織が独自に設定されたアカウントまたは人物のデータセットを使用する場合、これらのレコードには`isDeleted`も含めることができます。 [顧客所有データセット ](#customer-owned-datasets)を参照してください。

## `AJOB2B-1_5_4-account_member`

各レコードは、1つのアカウントを1人にリンクします。 このデータセットを使用して、各アカウントに関連付けられている人物をレポートします。どちらのプロファイルではなく、関係を記述します。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | 関係レコード ID。 |
| `accountID` | `AJOB2B-1_5_4-account_relational`に一致します（`_id`） | アカウント ID: |
| `personID` | `AJOB2B-1_5_4-person_relational`に一致します（`_id`） | 個人ID: |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-buying_group`

各レコードは、アカウントに関連付けられた購買グループを表し、名前、ステータス、ソリューションへの興味、エンゲージメントと完全性のスコアが含まれます。 購買グループステージは現在入力されていません。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | 購買グループ レコード ID （完全な値を使用）。 |
| `buyingGroupName` |  | 購買グループ名： |
| `engagementScore` |  | エンゲージメントスコア： |
| `completenessScore` |  | 完全性スコア： |
| `accountID` | `AJOB2B-1_5_4-account_relational`に一致します（`_id`） | 関連するアカウント ID。 |
| `solutionInterest` |  | ソリューションへの興味ラベル： |
| `buyingGroupStatus` |  | ステータス： |
| `buyingGroupStage` |  | 購買グループのステージ名。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

>[!NOTE]
>
>**可用性に関するメモ：** `buyingGroupStage`は現在空白です。 購買グループをステージ別にフィルタリングしたりグループ化したりするために使用しないでください。

## `AJOB2B-1_5_4-buying_group_member`

各レコードは、ある人物を購買グループにリンクし、その人物の役割を記録します。 購買グループの構成と役割のカバー範囲をレポートするために使用します。

`isDeleted`は、ユーザーが購買グループから削除されたかどうかを必ずしも示しません。 現在のメンバーシップを判断する場合は、このフィールドのみを使用しないでください。 役割の情報がない場合は、役割の名前を空白にすることができます。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | メンバーシップ レコード ID。 |
| `buyingGroupID` | `AJOB2B-1_5_4-buying_group`に一致します（`_id`） | 購買グループのID: |
| `personID` | `AJOB2B-1_5_4-person_relational`に一致します（`_id`） | 個人ID: |
| `buyingGroupMemberRole` |  | ロール名（使用可能な場合）。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-account_journey`

各レコードは、名前、ステータス、開始日と終了日を含むアカウントジャーニーを記述します。 アカウントのジャーニーのライフサイクルとステータスをレポートするために使用します。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | ジャーニーレコード id （完全な値を使用）。 |
| `accountJourneyName` |  | ジャーニー名： |
| `accountJourneyStatus` |  | ステータス（ドラフト、ライブ、完了など）。 |
| `startDate` |  | 開始タイムスタンプ。 |
| `endDate` |  | 終了タイムスタンプ： |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-account_journey_member`

各レコードは、アカウントをアカウントジャーニーに接続します。 各ジャーニーに参加しているアカウントを特定し、レポートするために使用します。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | メンバーシップ レコード ID。 |
| `accountID` | `AJOB2B-1_5_4-account_relational`に一致します（`_id`） | アカウント ID: |
| `journeyID` | `AJOB2B-1_5_4-account_journey`に一致します（`_id`） | アカウントジャーニーのID。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-person_journey`

各レコードは、名前、ステータス、開始日と終了日が記載された個人ジャーニーを記述します。 個人に焦点を当てたジャーニーのライフサイクルとステータスをレポートできます。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | ジャーニーレコード id （完全な値を使用）。 |
| `personJourneyName` |  | ジャーニー名： |
| `personJourneyStatus` |  | ステータス（ドラフト、ライブ、完了など）。 |
| `startDate` |  | 開始タイムスタンプ。 |
| `endDate` |  | 終了タイムスタンプ： |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-person_journey_member`

各レコードには、現在のジャーニーノード、メンバーシップとエントリ日、エントリ数など、ジャーニーにおける個人のメンバーシップが記述されます。 このツールを使用して、登録、再入力、ジャーニーの進捗状況を報告できます。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | メンバーシップ レコード ID。 |
| `marketingProgramID` |  | ジャーニーが属するマーケティングプログラムの識別子。 |
| `personID` | `AJOB2B-1_5_4-person_relational`に一致します（`_id`） | 個人ID: |
| `journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | 人物が現在所属するジャーニーノードの識別子。 |
| `membershipDate` |  | その人がマーケティングプログラムのメンバーになると。 |
| `lastEntryDate` |  | オーディエンスがジャーニーに最後にエントリした際。 |
| `reentryOpensAt` |  | ジャーニーに再度入れることができるとき。 |
| `entryCount` |  | ユーザーがジャーニーにエントリした回数。 |
| `createdDate` |  | レコードが作成された日付。 |
| `updatedDate` |  | レコードが最後に変更された日時。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-account_journey_node`

各レコードは、ステップの種類や属するジャーニーなど、ジャーニーのステップを表します。 ジャーニーノードは、開始、待機、決定などのステップです。 `person_journey_node`でも同じ手順が表示されます。ステップをアカウント固有として処理する前に、`accountJourneyID`とアカウントジャーニーを一致させてください。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | ノードレコード ID （完全な値を使用）。 |
| `accountJourneyID` | `AJOB2B-1_5_4-account_journey`に一致します（`_id`） | 親ジャーニーのID。 |
| `uuid` |  | ジャーニーステップの追加ID。 |
| `journeyNodeTypeID` |  | ジャーニーステップの種類を特定する番号。 |
| `nodeType` |  | ジャーニーステップの種類を特定するラベル。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `createdDate` |  | レコードが作成された日付。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-person_journey_node`

各レコードは、ステップの種類や属するジャーニーなど、ジャーニーのステップを表します。 `account_journey_node`にも同じステップが表示されます。ステップを個人に固有として扱う前に、`personJourneyID`と個人ジャーニーを一致させてください。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | ノードレコード ID （完全な値を使用）。 |
| `personJourneyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | 親ジャーニーのID。 |
| `uuid` |  | ジャーニーステップの追加ID。 |
| `journeyNodeTypeID` |  | ジャーニーステップの種類を特定する番号。 |
| `nodeType` |  | ジャーニーステップの種類を特定するラベル。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `createdDate` |  | レコードが作成された日付。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-account_event`

各レコードは、アカウント ジャーニーイベント（ジャーニーに追加または削除されるアカウント、ジャーニーノード間を移動するアカウント）をキャプチャします。 `eventType`と`timestamp`を使用してアカウントアクティビティタイムラインを構築します。イベントが購買グループに属している場合は、`buyingGroupID`を利用できます。

**形式：**&#x200B;関連レコード形式

`eventType`は、何が起こったのかに関する情報を提供します。 次の表に、アクティビティの種類ごとのフィールドを示します。

`lastUpdatedDate`は現在、これらのイベントに入力されていません。 アクティビティ日に`timestamp`を使用します。

### ジャーニーに追加されたアカウント （`account.addAccountToJourney`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `account.addAccountToJourney`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `accountID` | `AJOB2B-1_5_4-account_relational`に一致します（`_id`） | アカウント ID: |
| `journeyID` | `AJOB2B-1_5_4-account_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-account_journey_node`に一致します（`_id`） | ジャーニーノード ID。 |
| `buyingGroupID` | `AJOB2B-1_5_4-buying_group`に一致します（`_id`） | ジャーニーの追加が購買グループの属性である場合の購買グループの識別子。 |
| `lastUpdatedDate` |  | 更新時間を記録します。 現在空白です。アクティビティの日付にタイムスタンプを使用します。 |

### ジャーニーからアカウントが削除されました（`account.removeAccountFromJourney`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `account.removeAccountFromJourney`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `accountID` | `AJOB2B-1_5_4-account_relational`に一致します（`_id`） | アカウント ID: |
| `journeyID` | `AJOB2B-1_5_4-account_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-account_journey_node`に一致します（`_id`） | ジャーニーノード ID。 |
| `buyingGroupID` | `AJOB2B-1_5_4-buying_group`に一致します（`_id`） | ジャーニーの削除が購買グループの帰属である場合の購買グループのID。 |
| `lastUpdatedDate` |  | 更新時間を記録します。 現在空白です。アクティビティの日付にタイムスタンプを使用します。 |

### ジャーニーステップ （`account.changeAccountJourneyNode`）の間でアカウントが移動しました

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `account.changeAccountJourneyNode`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `accountID` | `AJOB2B-1_5_4-account_relational`に一致します（`_id`） | アカウント ID: |
| `journeyID` | `AJOB2B-1_5_4-account_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-account_journey_node`に一致します（`_id`） | ジャーニーノード ID。 |
| `previousJourneyNodeID` | `AJOB2B-1_5_4-account_journey_node` （`_id`）を参照します。値が一致しない可能性があります | 前のジャーニーステップの識別子。 この値は、対応するステップレコードと一致しない可能性があります。レコードの接続に単独で依存しないでください。 |
| `buyingGroupID` | `AJOB2B-1_5_4-buying_group`に一致します（`_id`） | ノードの変更が購買グループの属性である場合の購買グループの識別子。 |
| `lastUpdatedDate` |  | 更新時間を記録します。 現在空白です。アクティビティの日付にタイムスタンプを使用します。 |

## `AJOB2B-1_5_4-buying_group_event`

各レコードは、新しいステータスや変更されたタイミングなど、購買グループのステータスに対する変更を記録します。 新しいステージのフィールドは現在入力されていません。

**形式：**&#x200B;関連レコード形式

### 購買グループの状態が変更されました（`buyingGroup.changeStatus`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `buyingGroup.changeStatus`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `buyingGroupID` | `AJOB2B-1_5_4-buying_group`に一致します（`_id`） | 購買グループのID: |
| `newStatus` |  | 新しいステータス値 |
| `newStage` |  | 新しい購買グループのステージ： 現在空白です。 |
| `lastUpdatedDate` |  | 更新時間を記録します。 |

>[!NOTE]
>
>**可用性に関するメモ：**&#x200B;は`newStatus`を使用してステータスの変更を報告します。 `newStage`は現在空白なので、ステージの変更をレポートするには使用しないでください。

## `AJOB2B-1_5-person_event`

各レコードは、個人レベルのweb、電子メール、その他のサポートされているアクティビティイベントを表します。 `eventType`と`timestamp`を使用して、時間の経過に伴う動作を分析します。イベント固有の詳細は、一致するイベントタイプにのみ入力されます。

**書式：**&#x200B;標準Adobe書式

`eventType`が何が起こったか教えてくれます。 次の表に、アクティビティの種類ごとのフィールドを示します。 イベントに適用されない詳細は空白です。

### 送信された電子メール （`directMarketing.emailSent`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `directMarketing.emailSent`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `directMarketing.emailSent.mailingKey.sourceID` |  | メーリングアセット id。 |
| `directMarketing.emailSent.mailingKey.sourceType` |  | 接続されている製品の名前。 |
| `directMarketing.emailSent.mailingKey.sourceInstanceID` |  | インスタンス ID。 |
| `directMarketing.emailSent.mailingKey.sourceKey` |  | メールコンテンツの完全なID。 |
| `directMarketing.emailSent.mailingName` |  | 郵送先名。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーid （帰属する場合）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード id （帰属する場合）。 |

### 電子メールが配信されました（`directMarketing.emailDelivered`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `directMarketing.emailDelivered`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `directMarketing.mailingKey.sourceID` |  | メーリングアセット id。 |
| `directMarketing.mailingKey.sourceType` |  | 接続されている製品の名前。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | インスタンス ID。 |
| `directMarketing.mailingKey.sourceKey` |  | メールコンテンツの完全なID。 |
| `directMarketing.mailingName` |  | 郵送先名。 |
| `directMarketing.email` |  | メールアドレス： |
| `_experience.journeyOrchestration.stepEvents.journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーid （帰属する場合）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード id （帰属する場合）。 |

### メールの購読解除（`directMarketing.emailUnsubscribed`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `directMarketing.emailUnsubscribed`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `directMarketing.mailingKey.sourceID` |  | メーリングアセット id。 |
| `directMarketing.mailingKey.sourceType` |  | 接続されている製品の名前。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | インスタンス ID。 |
| `directMarketing.mailingKey.sourceKey` |  | メールコンテンツの完全なID。 |
| `directMarketing.mailingName` |  | 郵送先名。 |
| `directMarketing.email` |  | メールアドレス： |
| `_experience.journeyOrchestration.stepEvents.journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーid （帰属する場合）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード id （帰属する場合）。 |

### 開封された電子メール （`directMarketing.emailOpened`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `directMarketing.emailOpened`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `directMarketing.mailingKey.sourceID` |  | メーリングアセット id。 |
| `directMarketing.mailingKey.sourceType` |  | 接続されている製品の名前。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | インスタンス ID。 |
| `directMarketing.mailingKey.sourceKey` |  | メールコンテンツの完全なID。 |
| `directMarketing.mailingName` |  | 郵送先名。 |
| `directMarketing.email` |  | メールアドレス： |
| `_experience.journeyOrchestration.stepEvents.journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーid （帰属する場合）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード id （帰属する場合）。 |
| `device.isMobileDevice` |  | アクティビティ用にモバイルデバイスが記録されたかどうか。 |
| `device.model` |  | デバイスまたは電子メールクライアントの情報： |
| `environment.browserDetails.userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `environment.operatingSystem` |  | オペレーティングシステム： |

### クリックされた電子メールリンク （`directMarketing.emailClicked`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `directMarketing.emailClicked`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `directMarketing.mailingKey.sourceID` |  | メーリングアセット id。 |
| `directMarketing.mailingKey.sourceType` |  | 接続されている製品の名前。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | インスタンス ID。 |
| `directMarketing.mailingKey.sourceKey` |  | メールコンテンツの完全なID。 |
| `directMarketing.mailingName` |  | 郵送先名。 |
| `directMarketing.email` |  | メールアドレス： |
| `directMarketing.linkURL` |  | リンク URLをクリックしました。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーid （帰属する場合）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード id （帰属する場合）。 |
| `device.isMobileDevice` |  | アクティビティ用にモバイルデバイスが記録されたかどうか。 |
| `device.model` |  | デバイスまたは電子メールクライアントの情報： |
| `environment.browserDetails.userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `environment.operatingSystem` |  | オペレーティングシステム： |

### 電子メールのバウンス （`directMarketing.emailBounced`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `directMarketing.emailBounced`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `directMarketing.mailingKey.sourceID` |  | メーリングアセット id。 |
| `directMarketing.mailingKey.sourceType` |  | 接続されている製品の名前。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | インスタンス ID。 |
| `directMarketing.mailingKey.sourceKey` |  | メールコンテンツの完全なID。 |
| `directMarketing.mailingName` |  | 郵送先名。 |
| `directMarketing.email` |  | メールアドレス： |
| `directMarketing.emailBouncedCode` |  | バウンスのカテゴリ/コード。 |
| `directMarketing.emailBouncedDetails` |  | 詳細テキスト： |
| `_experience.journeyOrchestration.stepEvents.journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーid （帰属する場合）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード id （帰属する場合）。 |

### 電子メールのソフトバウンス （`directMarketing.emailBouncedSoft`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `directMarketing.emailBouncedSoft`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `directMarketing.mailingKey.sourceID` |  | メーリングアセット id。 |
| `directMarketing.mailingKey.sourceType` |  | 接続されている製品の名前。 |
| `directMarketing.mailingKey.sourceInstanceID` |  | インスタンス ID。 |
| `directMarketing.mailingKey.sourceKey` |  | メールコンテンツの完全なID。 |
| `directMarketing.mailingName` |  | 郵送先名。 |
| `directMarketing.email` |  | メールアドレス： |
| `directMarketing.emailBouncedCode` |  | バウンスのカテゴリ/コード。 |
| `directMarketing.emailBouncedDetails` |  | 詳細テキスト： |
| `_experience.journeyOrchestration.stepEvents.journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーid （帰属する場合）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード id （帰属する場合）。 |

### 閲覧されたWeb ページ （`web.webpagedetails.pageViews`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `web.webpagedetails.pageViews`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `web.webPageDetails.webPageKey.sourceID` |  | ページアセット ID。 |
| `web.webPageDetails.webPageKey.sourceType` |  | 接続されている製品の名前。 |
| `web.webPageDetails.webPageKey.sourceInstanceID` |  | インスタンス ID。 |
| `web.webPageDetails.webPageKey.sourceKey` |  | 完全なページ ID。 |
| `web.webPageDetails.name` |  | ページ名： |
| `web.webPageDetails.URL` |  | ページ URL。 |
| `web.webPageDetails.queryParameters` |  | Web アドレスに含まれる追加情報。 |
| `web.webPageDetails.webPageID` |  | ページ ID。 |
| `environment.browserDetails.userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `web.webReferrer.URL` |  | リファラーURL: |

### クリックされたWeb リンク （`web.webinteraction.linkClicks`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `web.webinteraction.linkClicks`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `web.webInteraction.webInteractionKey.sourceID` |  | インタラクションアセット ID。 |
| `web.webInteraction.webInteractionKey.sourceType` |  | 接続されている製品の名前。 |
| `web.webInteraction.webInteractionKey.sourceInstanceID` |  | インスタンス ID。 |
| `web.webInteraction.webInteractionKey.sourceKey` |  | 完全なインタラクション ID: |
| `web.webInteraction.linkID` |  | リンク ID。 |
| `web.webInteraction.linkURL` |  | 宛先 URL |
| `web.webPageDetails.queryParameters` |  | Web アドレスに含まれる追加情報。 |
| `web.webPageDetails.webPageID` |  | ページ ID。 |
| `environment.browserDetails.userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `web.webReferrer.URL` |  | リファラーURL: |

### 送信されたフォーム （`web.formFilledOut`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `web.formFilledOut`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `web.fillOutForm.webFormKey.sourceID` |  | フォームアセット ID。 |
| `web.fillOutForm.webFormKey.sourceType` |  | 接続されている製品の名前。 |
| `web.fillOutForm.webFormKey.sourceInstanceID` |  | インスタンス ID。 |
| `web.fillOutForm.webFormKey.sourceKey` |  | 完全なフォーム ID: |
| `web.fillOutForm.webFormID` |  | フォーム ID。 |
| `web.fillOutForm.webFormName` |  | フォーム名： |
| `web.webPageDetails.queryParameters` |  | Web アドレスに含まれる追加情報。 |
| `web.webPageDetails.webPageID` |  | ページ ID。 |
| `environment.browserDetails.userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `web.webReferrer.URL` |  | リファラーURL: |

### 注目のアクションが記録されました（`leadOperation.interestingMoment`）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティ ID: |
| `eventType` |  | `leadOperation.interestingMoment`. |
| `timestamp` |  | アクティビティが発生した場合。 |
| `personID` | `AJOB2B-1_5_1-person`に一致します（`personID`） | 個人ID: |
| `personKey.sourceID` |  | 接続されたシステムにおける人物ID。 |
| `personKey.sourceType` |  | 接続されている製品の名前。 |
| `personKey.sourceInstanceID` |  | [!DNL Experience Platform]環境または接続されたアカウントの識別子。 |
| `personKey.sourceKey` |  | 関連するレコードを照合するために使用される完全な個人ID。 |
| `leadOperation.interestingMoment.date` |  | モーメントの日時。 |
| `leadOperation.interestingMoment.description` |  | 説明 |
| `leadOperation.interestingMoment.source` |  | 関連製品またはキャンペーンの名前。 |
| `leadOperation.interestingMoment.type` |  | ラベルを入力します。 |
| `_experience.journeyOrchestration.stepEvents.journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーid （帰属する場合）。 |
| `_experience.journeyOrchestration.stepEvents.nodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード id （帰属する場合）。 |

## `AJOB2B-1_5_4-journey_node`

各レコードは、ジャーニーステップ、属するジャーニー、ステップの種類を表します。 同じステップが、アカウントと個人ジャーニーのステップデータセットにも表示されます。 `journeyID`を適切なジャーニーに一致させます。複数のデータセットに表示されるため、ステップを複数回カウントしないでください。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | ノードレコード ID （完全な値を使用）。 |
| `journeyID` | `AJOB2B-1_5_4-account_journey`または`AJOB2B-1_5_4-person_journey`に一致（`_id`） | 親ジャーニーのID。 |
| `nodeType` |  | 開始、終了、待機、決定など、ジャーニーステップの一種。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-account_relational`

各レコードは、組織の詳細、場所、サイズ、収益、カスタムフィールドなど、アカウントを記述します。 この情報を使用して、購買グループおよびジャーニーレポートにアカウントコンテキストを追加します。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アカウントレコード ID （完了値を使用）。 |
| `accountName` |  | アカウント名： |
| `industry` |  | 業界分類。 |
| `country` |  | 国： |
| `sicCode` |  | 標準工業分類コード。 |
| `domainName` |  | プライマリ web ドメイン。 |
| `primaryEmailDomain` |  | プライマリのメールドメイン： |
| `street` |  | 住所： |
| `city` |  | 都市： |
| `state` |  | 都道府県または地域： |
| `postalCode` |  | 郵便番号/郵便番号。 |
| `region` |  | 地域： |
| `phoneNumber` |  | 電話番号： |
| `logoUrl` |  | アカウントのロゴのURL。 |
| `annualRevenue` |  | 年間収益： |
| `numberOfEmployees` |  | 従業員数： |
| `createdDate` |  | レコードが作成された日付。 |
| `sourceType` |  | アカウントを識別する接続システムの名前。 |
| `sourceInstanceID` |  | 接続されたシステム内の組織またはアカウントの識別子。 |
| `sourceID` |  | 接続されたシステムにおけるアカウント ID。 |
| `customAttributes` |  | カスタムフィールド名と値がテキストとして一緒に保存されます。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-person_relational`

各レコードには、連絡先情報、役職の詳細、識別子、カスタムフィールドなど、個人が記載されています。 メンバーシップ、ジャーニー、アクティビティレポートに人物情報を追加するために使用します。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | 関連するレコードを照合するために使用される完全な個人ID。 |
| `email` |  | メールアドレス： |
| `firstName` |  | 名。 |
| `middleName` |  | ミドルネーム。 |
| `lastName` |  | 姓： |
| `jobTitle` |  | 役職： |
| `personType` |  | 人物タイプ：連絡先、見込み客、保留中のリード |
| `isLead` |  | 人物がリードであるかどうか。 |
| `isAnonymous` |  | 個人が匿名かどうか。 |
| `salutation` |  | 敬礼や敬礼。 |
| `phone` |  | プライマリの電話番号。 |
| `mobile` |  | 携帯電話番号。 |
| `sourceType` |  | ユーザーを識別する接続システムの名前（例：[!DNL Marketo Engage]）。 |
| `sourceInstanceID` |  | 接続されたシステム内の組織またはアカウントの識別子。 |
| `sourceID` |  | 接続されたシステムにおける個人ID。 |
| `identityNamespace` |  | 追加のユーザーIDの種類を識別するラベル。 |
| `identityValue` |  | セカンダリ IDの値。 |
| `customAttributes` |  | カスタムフィールド名と値がテキストとして一緒に保存されます。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-account_person`

各レコードは、アカウントプロファイルを人物プロファイルにリンクします。 アカウントと個人のプロファイルデータセットをまたいで関係をレポートするために使用できます。

**形式：**&#x200B;関連レコード形式

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アカウントと個人の関係レコード ID （完了値を使用）。 |
| `accountID` | `AJOB2B-1_5_4-account_relational`に一致します（`_id`） | 完全なアカウント ID （参照`account_relational._id`）。 |
| `personID` | `AJOB2B-1_5_4-person_relational`に一致します（`_id`） | 完全な個人ID （参照`person_relational._id`）。 |
| `createdDate` |  | アカウントと個人の関係が作成されたとき。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

## `AJOB2B-1_5_4-person_event_relational`

各レコードは、web ページの表示、メールの操作、ジャーニーの移動など、サポートされている個人のアクティビティを表します。 `eventType`と`activityTypeID`を使用して、何が起こったのかを把握します。 その種類のアクティビティに関連する詳細のみが入力されます。

**形式：**&#x200B;関連レコード形式

次のフィールドリストは、サポートされているすべてのアクティビティタイプを網羅しています。 個々のレコードには、そのアクティビティに適用される詳細のみが含まれます。

>[!NOTE]
>
>**可用性：**&#x200B;一部のアクティビティに空の`_id`がある場合があります。 すべてのアクティビティに使用可能なレコード識別子があると仮定しないでください。 データセットは、完全なアクティビティ履歴を保証するものではありません。

ジャーニーアクティビティ （`person.journeyAdd`、`person.journeyRemove`、`person.journeyStart`、`person.journeyEnd`、`person.journeyNodeTransition`、`person.journeySplitNode`）および「人物ジャーニーを更新」ジャーニーステップに関連付けられた`person.attributeChanged` アクティビティに対しては、プロファイルの詳細（`journeyID`、`journeyNodeID`、`journeyStepID`および同様のフィールド）が提供されます。

属性変更フィールド （`attributeName`, `attributeID`, `attributeNewValue`, `attributeOldValue`, `attributeChangeReason`）は、`person.attributeChanged`にのみ入力されます。

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id` | レコード ID | アクティビティの識別子（使用可能な場合）。 |
| `timestamp` |  | アクティビティが発生した場合。 |
| `eventType` |  | アクティビティラベル： 値：`web.webpagedetails.pageViews`, `web.formFilledOut`, `web.webinteraction.linkClicks`, `directMarketing.emailSent`, `directMarketing.emailDelivered`, `directMarketing.emailBounced`, `directMarketing.emailBouncedSoft`, `directMarketing.emailUnsubscribed`, `directMarketing.emailOpened`, `directMarketing.emailClicked`, `leadOperation.interestingMoment`, `person.attributeChanged`, `person.journeyAdd`, `person.journeyRemove`, `person.journeyStart`, `person.journeyEnd`, `person.journeyNodeTransition`, `person.journeySplitNode`。 |
| `activityTypeID` |  | アクティビティコード： `eventType`と共に使用すると、同じイベントラベルを共有するアクティビティを区別できます。 |
| `personID` | `AJOB2B-1_5_4-person_relational`に一致します（`_id`） | アクティビティと人物レコードの照合に使用される完全な人物ID。 |
| `journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーの完全なID。 ジャーニーに関連付けられていないアクティビティの場合は空白になります。 |
| `journeyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーの完全なステップ ID: ジャーニーに関連付けられていないアクティビティの場合は空白になります。 |
| `previousJourneyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | 以前のジャーニーノード （`person.journeyNodeTransition`および`person.journeySplitNode`に設定）。 |
| `newJourneyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | 宛先ジャーニーノード ID （`person.journeyNodeTransition`および`person.journeySplitNode`）。 通常は`journeyNodeID`に等しくなります。 |
| `journeyStepID` |  | アクティビティに関連付けられているジャーニーステップの識別子。 |
| `journeyChoiceNumber` |  | `person.journeySplitNode`の分割選択番号。 整数として記録されます。 |
| `journeyEntryCount` |  | このユーザーがジャーニーにエントリした回数（ジャーニーの追加/開始イベントに入力）。 整数として記録されます。 |
| `journeyProgramID` | このガイドには、マーケティング施策に関するデータセットは含まれていません | ジャーニーアクティビティに関連付けられたマーケティングプログラムの識別子。 |
| `activitySource` |  | アクティビティに関連付けられている製品またはアクションの名前。 |
| `campaignID` |  | アクティビティがキャンペーンに関連付けられている場合の[!DNL Marketo Engage] キャンペーン id。 |
| `attributeName` |  | 変更されたフィールドの名前（`person.attributeChanged`のみ）。 |
| `attributeID` |  | 変更されたフィールドの識別子（`person.attributeChanged`のみ）。 |
| `attributeNewValue` |  | 新しいフィールド値がテキストとして記録されました（`person.attributeChanged`のみ）。 |
| `attributeOldValue` |  | 以前のフィールド値。テキストとして記録されます（`person.attributeChanged`のみ）。 |
| `attributeChangeReason` |  | 変更の理由ラベル （`person.attributeChanged`のみ）。 |
| `assetID` |  | 関連するメールコンテンツ、ページ、フォームの識別子。 |
| `assetName` |  | 関連するコンテンツの名前。 |
| `recipientEmail` |  | 受信者のメールアドレス（使用可能な場合）。 アクティビティコード **27** （ソフトバウンス）および&#x200B;**48** （セールスメールのソフトバウンス）に対してのみ入力されました。他のメールアクティビティでは空白です。 これらのアクティビティについては、`personID`を使用して個人レコードを検索します。 `assetName`は、受信者のアドレスではなく、メール コンテンツを識別します。 |
| `bouncedCode` |  | バウンスのカテゴリーコード （emailBounced / emailBouncedSoftのみ）。 |
| `bouncedDetails` |  | バウンスの理由の詳細（emailBounced / emailBouncedSoftのみ）。 |
| `isMobileDevice` |  | モバイルデバイスがメールの開封率またはクリック率に応じて記録されたかどうか。 |
| `deviceModel` |  | デバイスモデル（emailOpened / emailClickedのみ）。 |
| `operatingSystem` |  | オペレーティングシステム（emailOpened / emailClickedのみ）。 |
| `userAgent` |  | 電子メールの開封、電子メールのクリック、web アクティビティに関するブラウザーまたは電子メールクライアントの情報。 |
| `clickedLinkUrl` |  | クリックしたメールリンク URL （emailClickedのみ）。 |
| `webPageUrl` |  | Web ページ URL （`web.webpagedetails.pageViews`のみ）。 |
| `queryParameters` |  | ページビュー、フォーム送信、またはweb リンククリックに関するweb アドレスの追加情報。 |
| `webPageID` |  | [!DNL Marketo Engage] web ページ ID （pageViews、formFilledOut、linkClicks）。 |
| `referrerUrl` |  | リファラーURL （pageViews、formFilledOut、linkClicks）: |
| `formID` |  | [!DNL Marketo Engage] フォーム id （`web.formFilledOut`のみ）。 |
| `linkID` |  | [!DNL Marketo Engage] リンク id （`web.webinteraction.linkClicks`のみ）。 |
| `interestingMomentDate` |  | モーメント日付（`leadOperation.interestingMoment`のみ）。 |
| `interestingMomentDescription` |  | フリーテキストの説明（interestingMomentのみ）。 |
| `interestingMomentSource` |  | 関連製品またはキャンペーン（interestingMomentのみ）。 |
| `interestingMomentType` |  | カテゴリ / タイプ （interestingMomentのみ）。 |
| `isDeleted` |  | このレコードが削除済みとしてマークされているかどうか。 |
| `lastUpdatedDate` |  | 最終変更時刻。 |

### アクティビティタイプ別のフィールド参照

次の表に、各アクティビティに適用される詳細を示します。 その他の詳細は空白です。 一部のアクティビティは、同じ`eventType` ラベルを共有しています。コード 8とコード 48はどちらも`directMarketing.emailBounced`を使用しています。 `activityTypeID`を使用して区別します。

#### 閲覧したWeb ページ （`web.webpagedetails.pageViews`） （アクティビティの種類1）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | ページ ID。 |
| `assetName` |  | ページ名： |
| `webPageUrl` |  | ページ URL。 |
| `queryParameters` |  | Web アドレスに含まれる追加情報。 |
| `webPageID` |  | [!DNL Marketo Engage] web ページ id。 |
| `referrerUrl` |  | リファラーURL: |
| `userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### 送信されたフォーム （`web.formFilledOut`） （アクティビティの種類2）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | フォーム ID。 |
| `assetName` |  | フォーム名： |
| `formID` |  | [!DNL Marketo Engage] フォーム id。 |
| `queryParameters` |  | Web アドレスに含まれる追加情報。 |
| `webPageID` |  | [!DNL Marketo Engage] web ページ id。 |
| `referrerUrl` |  | リファラーURL: |
| `userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### クリックされたWeb リンク （`web.webinteraction.linkClicks`） （アクティビティの種類3）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | インタラクション / リンク ID。 |
| `assetName` |  | 宛先 URL |
| `linkID` |  | [!DNL Marketo Engage] リンク id。 |
| `queryParameters` |  | Web アドレスに含まれる追加情報。 |
| `webPageID` |  | [!DNL Marketo Engage] web ページ id。 |
| `referrerUrl` |  | リファラーURL: |
| `userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### 送信された電子メール （`directMarketing.emailSent`） （アクティビティの種類6、39）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | メーリング ID。 |
| `assetName` |  | 郵送先名。 |
| `campaignID` |  | キャンペーンに起因する場合の[!DNL Marketo Engage] キャンペーン id。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### 配信された電子メール （`directMarketing.emailDelivered`） （アクティビティの種類7、45）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | メーリング ID。 |
| `assetName` |  | 郵送先名。 |
| `campaignID` |  | キャンペーンに起因する場合の[!DNL Marketo Engage] キャンペーン id。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### メールの購読解除（`directMarketing.emailUnsubscribed`） （アクティビティ タイプ 9）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | メーリング ID。 |
| `assetName` |  | 郵送先名。 |
| `campaignID` |  | キャンペーンに起因する場合の[!DNL Marketo Engage] キャンペーン id。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### 開封された電子メール （`directMarketing.emailOpened`） （アクティビティ タイプ 10、40）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | メーリング ID。 |
| `assetName` |  | 郵送先名。 |
| `isMobileDevice` |  | アクティビティ用にモバイルデバイスが記録されたかどうか。 |
| `deviceModel` |  | デバイスモデル： |
| `operatingSystem` |  | オペレーティングシステム： |
| `userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `campaignID` |  | キャンペーンに起因する場合の[!DNL Marketo Engage] キャンペーン id。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### メールリンクをクリックしました（`directMarketing.emailClicked`） （アクティビティタイプ 11、41）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | メーリング ID。 |
| `assetName` |  | 郵送先名。 |
| `clickedLinkUrl` |  | リンク URLをクリックしました。 |
| `isMobileDevice` |  | アクティビティ用にモバイルデバイスが記録されたかどうか。 |
| `deviceModel` |  | デバイスモデル： |
| `operatingSystem` |  | オペレーティングシステム： |
| `userAgent` |  | ブラウザーまたは電子メールクライアントの情報： |
| `campaignID` |  | キャンペーンに起因する場合の[!DNL Marketo Engage] キャンペーン id。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### 電子メールバウンス （`directMarketing.emailBounced`）: ハードバウンス （アクティビティの種類8）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | メーリング ID。 |
| `assetName` |  | 郵送先名。 |
| `bouncedCode` |  | バウンスのカテゴリーコード。 |
| `bouncedDetails` |  | バウンスの理由の詳細。 |
| `campaignID` |  | キャンペーンに起因する場合の[!DNL Marketo Engage] キャンペーン id。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

このアクティビティは`directMarketing.emailBounced` ラベルをアクティビティ コード 48と共有していますが、`recipientEmail`はコード 8に対して空白です。 `activityTypeID`を使用して2つを区別します。

#### 電子メールのバウンス （`directMarketing.emailBounced`）：販売電子メールのソフトバウンス （アクティビティの種類48）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | メーリング ID。 |
| `assetName` |  | 郵送先名。 |
| `recipientEmail` |  | 受信者のメールアドレス。 |
| `bouncedCode` |  | バウンスのカテゴリーコード。 |
| `bouncedDetails` |  | バウンスの理由の詳細。 |
| `campaignID` |  | キャンペーンに起因する場合の[!DNL Marketo Engage] キャンペーン id。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### 電子メールのソフトバウンス （`directMarketing.emailBouncedSoft`） （アクティビティの種類27）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `assetID` |  | メーリング ID。 |
| `assetName` |  | 郵送先名。 |
| `recipientEmail` |  | 受信者のメールアドレス。 |
| `bouncedCode` |  | バウンスのカテゴリーコード。 |
| `bouncedDetails` |  | バウンスの理由の詳細。 |
| `campaignID` |  | キャンペーンに起因する場合の[!DNL Marketo Engage] キャンペーン id。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### 興味深い瞬間を記録しました（`leadOperation.interestingMoment`） （アクティビティ タイプ 46）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `interestingMomentDate` |  | モーメントの日時。 |
| `interestingMomentDescription` |  | フリーテキストの説明： |
| `interestingMomentSource` |  | 関連製品またはキャンペーンの名前。 |
| `interestingMomentType` |  | ラベルを入力します。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

`assetID`と`assetName`は、このアクティビティタイプに入力されていません。

#### ユーザーのフィールドが変更されました（`person.attributeChanged`） （アクティビティの種類13）

「人物プロファイルを更新」ステップなど、変更がジャーニーに関連付けられている場合にのみ含まれます。 ジャーニー以外の変更は含まれません。

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `attributeName` |  | 変更されたフィールドの名前。 |
| `attributeID` |  | 変更されたフィールドの識別子。 |
| `attributeNewValue` |  | 新しいフィールド値をテキストとして記録します。 |
| `attributeOldValue` |  | 以前のフィールド値、テキストとして記録。 |
| `attributeChangeReason` |  | 変更の理由ラベル。 |
| `journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード ID。 |
| `journeyStepID` |  | ジャーニーステップの識別子。 |
| `journeyProgramID` | このガイドには、マーケティング施策に関するデータセットは含まれていません | ジャーニープログラム id。 |
| `activitySource` |  | アクティビティに関連付けられた製品またはアクション。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### ユーザーがジャーニー（`person.journeyAdd`、`person.journeyStart`）に追加または開始しました（アクティビティ タイプ 182、184）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード ID。 |
| `journeyStepID` |  | ジャーニーステップの識別子。 |
| `journeyEntryCount` |  | このユーザーがジャーニーにエントリした回数。 |
| `journeyProgramID` | このガイドには、マーケティング施策に関するデータセットは含まれていません | ジャーニープログラム id。 |
| `activitySource` |  | アクティビティに関連付けられた製品またはアクション。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### ジャーニーから削除された人物、またはジャーニーを終了した人物（`person.journeyRemove`, `person.journeyEnd`） （アクティビティタイプ 183, 185）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード ID。 |
| `journeyStepID` |  | ジャーニーステップの識別子。 |
| `journeyProgramID` | このガイドには、マーケティング施策に関するデータセットは含まれていません | ジャーニープログラム id。 |
| `activitySource` |  | アクティビティに関連付けられた製品またはアクション。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### ユーザーがジャーニー分岐（`person.journeySplitNode`） （アクティビティ タイプ 186）に続きました

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | ジャーニーノード ID （分割ノード）。 |
| `previousJourneyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | 分割の前に人物が所属していたノード。 |
| `newJourneyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | 移動先のノード（通常は`journeyNodeID`に等しい）。 |
| `journeyStepID` |  | ジャーニーステップの識別子。 |
| `journeyChoiceNumber` |  | どの分岐が取られたか。 |
| `journeyProgramID` | このガイドには、マーケティング施策に関するデータセットは含まれていません | ジャーニープログラム id。 |
| `activitySource` |  | アクティビティに関連付けられた製品またはアクション。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

#### ジャーニーステップ （`person.journeyNodeTransition`）の間でユーザーが移動しました（アクティビティ タイプ 600）

| フィールド名 | 関係 | データの意味 |
|------------|-------------|-------------|
| `_id`, `timestamp`, `eventType`, `activityTypeID`, `personID` | レコード ID: `_id`、`personID`が`AJOB2B-1_5_4-person_relational`と一致します（`_id`） | 共通フィールド： |
| `journeyID` | `AJOB2B-1_5_4-person_journey`に一致します（`_id`） | ジャーニーID: |
| `journeyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | 現在のジャーニーノード ID。 |
| `previousJourneyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | 移行元の人物をノード化します。 |
| `newJourneyNodeID` | `AJOB2B-1_5_4-person_journey_node`に一致します（`_id`） | 移行先の人物をノード化します（通常は`journeyNodeID`に等しい）。 |
| `journeyStepID` |  | ジャーニーステップの識別子。 |
| `journeyProgramID` | このガイドには、マーケティング施策に関するデータセットは含まれていません | ジャーニープログラム id。 |
| `activitySource` |  | アクティビティに関連付けられた製品またはアクション。 |
| `isDeleted`, `lastUpdatedDate` |  | 共通フィールド： |

## 顧客所有データセット {#customer-owned-datasets}

組織は、アカウントまたはユーザーに対して独自の[!DNL Experience Platform] データセットを使用できます。 設定すると、[!DNL Adobe Journey Optimizer B2B Edition]は、別のアカウントまたは人物のデータセットを作成する代わりに、これらのデータセットに情報を追加できます。

名前と使用可能なフィールドは、組織の設定によって異なります。 設定したアカウントまたは人物のIDを使用して、一致するレコードを認識します。 これらのデータセットにレコードを含めると、オーディエンスでレコードを自動的に使用できるようになります。使用できるかどうかは、[!DNL Experience Platform]設定によって異なります。
