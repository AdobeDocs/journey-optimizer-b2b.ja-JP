---
title: データセットクエリ
description: Query ServiceのSQL クエリの例を使用して、Adobe Journey Optimizer B2B Editionによって書き出されたアカウント、購買グループ、人物、ジャーニーのデータを分析する方法を説明します。
feature: Reporting, Data Management
role: Admin, Developer
product_v2:
  - id: aacce07f-424e-489e-8d02-a4fb2f4211bd
    internal-label: Journey Optimizer B2B Edition
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
feature_v2:
  - id: f2da1b69-6919-4386-a5d2-9c7b5c9033db
    internal-label: Data management
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: 6db81a0b993f450a3ff448dcb4c417e3e81ec70a
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 1%
---

# データセットクエリ

[!DNL Adobe Journey Optimizer B2B Edition]が[!DNL Adobe Experience Platform]に書き出すアカウント、人物、購買グループ、ジャーニーのデータを分析するためにすぐに使用できるSQL クエリの例を見つけます。 アカウント、購買グループ、メールエンゲージメント、ジャーニーアクティビティをレポートするには、[!DNL Query Service]でクエリを実行します。

これらのクエリで使用されるデータセットとフィールドについて詳しくは、[書き出されたデータセット ](./aep-exported-datasets.md)を参照してください。

## 前提条件 {#prerequisites}

このページでクエリを実行する前に、次のことを確認してください。

* **[!DNL Query Service]へのアクセス：**&#x200B;あなたは[!DNL Experience Platform] サンドボックス内の[ クエリサービス ](https://experienceleague.adobe.com/ja/docs/experience-platform/query/home){target="_blank"}にアクセスする必要があります。
* **使用可能なデータセット：** クエリは、書き出された[!DNL Journey Optimizer B2B Edition] データセットをターゲットにします。 サンドボックスで、**[!UICONTROL データセット]**&#x200B;に移動し、データセットが存在し、データが含まれていることを確認します。
* **スキーマフィールド値：** クエリのフィールドに、対応するスキーマの値が含まれていることを確認してください。 空のフィールドは結果を返さず、エラーは発生しません。

>[!NOTE]
>
>この例では、`account_table`や`person_activity_table`などの短いテーブル名を使用しています。 各テーブル名を、サンドボックス内の対応するデータセットの名前に置き換えます。 データセット名にハイフンが含まれる場合は、二重引用符で囲みます。 `Example Company`や`PASTE_COMPLETE_JOURNEY_ID_HERE`などのプレースホルダー値を、環境の値に置き換えます。

## クエリの実行 {#run}

このページの任意の例を実行するには：

1. [!DNL Experience Platform]で、**[!UICONTROL クエリサービス]** > **[!UICONTROL クエリ]**&#x200B;を選択します。
1. この例をクエリエディターに貼り付け、テーブル名とプレースホルダー値を置き換えます。
1. **[!UICONTROL 実行]**&#x200B;を選択します。

日付でフィルタリングする例では、過去30日間を使用します。 時間範囲を変更するには、`INTERVAL '30' DAY`値を編集します。

## クエリの選択

次の表を使用して、レポートタスクのクエリを選択します。

| 次に実行したい | 移動先 |
|---|---|
| アカウント名、業種、場所の確認 | [ アカウントの詳細を確認](#account-details) |
| 購買グループのエンゲージメント別比較 | [購買グループのエンゲージメントの比較](#buying-group-engagement) |
| アカウントに関連付けられている人物を検索 | [ アカウント内のユーザーを検索](#account-people) |
| 購買グループのステータスの変更の追跡 | [購買グループのステータスの変更を確認](#buying-group-status-changes) |
| メールをクリックした人物の検索 | [電子メールをクリックしたユーザーを検索](#email-clicks) |
| タイプ別の最近のアクティビティの比較 | [最近のユーザー活動を比較](#person-activity) |
| サイズ別のアカウントジャーニーの比較 | [ ジャーニー別にアカウント数を比較](#account-journey-counts) |
| ジャーニーのアカウントのリスト | [ ジャーニーのアカウントのリスト ](#journey-accounts) |
| 日々のアカウントジャーニー活動の追跡 | [毎日のアカウントアクティビティを追跡](#account-daily-activity) |
| ジャーニーのアカウント履歴の調査 | [ アカウントジャーニーのタイムラインを確認](#account-timeline) |
| サイズとステータス別の個人ジャーニーの比較 | [ ユーザー数をジャーニー別に比較](#person-journey-counts) |
| ジャーニーの人物のリスト | [ ジャーニー内のユーザーを一覧表示](#journey-people) |
| ジャーニーのどの段階にいるのかを把握する | [手順](#person-step-counts)による人数数の比較 |
| 最近の個人ジャーニー活動の追跡 | [最近のジャーニーアクティビティを追跡](#person-journey-activity) |
| ジャーニーにおける人物の履歴の調査 | [個人ジャーニーのタイムラインを確認](#person-timeline) |

## アカウントと購買グループのクエリ

これらのクエリを使用して、レポートに使用できるアカウント、購買グループ、人物を確認します。

### アカウント詳細を見る {#account-details}

アカウント名、業界、場所、企業規模を確認して、レポートに利用できるアカウントを把握します。

```sql
SELECT
a._id AS accountID,
a.accountName,
a.industry,
a.country,
a.numberOfEmployees
FROM account_table a
WHERE a.isDeleted = FALSE
ORDER BY a.accountName
LIMIT 100;
```

### 購買グループのエンゲージメントの比較 {#buying-group-engagement}

記録されたエンゲージメントスコアと、完全性やソリューションへの関心度によって、購買グループを比較します。

```sql
SELECT
bg._id AS buyingGroupID,
bg.buyingGroupName,
bg.engagementScore,
bg.completenessScore,
bg.solutionInterest,
bg.buyingGroupStatus
FROM buying_group_table bg
WHERE bg.isDeleted = FALSE
ORDER BY bg.engagementScore DESC NULLS LAST, bg.buyingGroupName
LIMIT 100;
```

### アカウント内のユーザーを検索 {#account-people}

アカウントに関連付けられている人物と役職を検索して、連絡先を把握します。 `Example Company`をサンドボックスのアカウント名に置き換えます。

```sql
SELECT DISTINCT
a._id AS accountID,
a.accountName,
p._id AS personID,
p.firstName,
p.lastName,
p.email,
p.jobTitle
FROM account_member_table m
JOIN account_table a ON m.accountID = a._id
JOIN person_table p ON m.personID = p._id
WHERE m.isDeleted = FALSE
AND a.isDeleted = FALSE
AND p.isDeleted = FALSE
AND a.accountName = 'Example Company'
ORDER BY p.lastName, p.firstName
LIMIT 100;
```

### 購買グループのステータスの変更の確認 {#buying-group-status-changes}

過去30日間の購買グループのステータスの変化を確認して、グループの経時的な変化を把握します。

```sql
SELECT
bg._id AS buyingGroupID,
bg.buyingGroupName,
e.timestamp AS changedAt,
e.newStatus
FROM buying_group_event_table e
JOIN buying_group_table bg ON e.buyingGroupID = bg._id
WHERE bg.isDeleted = FALSE
AND e.eventType = 'buyingGroup.changeStatus'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```

## 人物エンゲージメントクエリ

これらのクエリを使用して、メールエンゲージメントやその他の記録された人物のアクティビティを確認します。

### メールをクリックした人物の検索 {#email-clicks}

最近の電子メールのエンゲージメントを確認するには、過去30日以内に電子メールのクリック数が記録されている顧客を特定します。

```sql
SELECT DISTINCT
p._id AS personID,
p.firstName,
p.lastName,
p.email
FROM person_activity_table e
JOIN person_table p ON e.personID = p._id
WHERE e.isDeleted = FALSE
AND p.isDeleted = FALSE
AND e.eventType = 'directMarketing.emailClicked'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY p.lastName, p.firstName
LIMIT 100;
```

### 最近の人物アクティビティの比較 {#person-activity}

記録されたアクティビティのタイプと関係者数を比較して、最近のエンゲージメントを把握できます。

```sql
SELECT
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.personID) AS distinctPeople
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.personID IS NOT NULL
AND e.personID <> ''
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY e.eventType
ORDER BY recordedRows DESC
LIMIT 100;
```

## アカウントジャーニークエリ

次のクエリは、アカウントジャーニーの分析に使用できます。 `PASTE_COMPLETE_JOURNEY_ID_HERE`をアカウントジャーニーの`_id`値に、`PASTE_COMPLETE_ACCOUNT_ID_HERE`をアカウントの`_id`値に置き換えます。

### ジャーニー別のアカウント数の比較 {#account-journey-counts}

ステータスと記録されたメンバーシップ数によってアカウントジャーニーを比較し、最もアカウント母集団が多いジャーニーを確認します。

```sql
SELECT
j._id AS journeyID,
j.accountJourneyName,
j.accountJourneyStatus,
COUNT(DISTINCT m.accountID) AS accountsWithRecordedMembership
FROM account_journey_table j
LEFT JOIN account_journey_member_table m
ON m.journeyID = j._id
AND m.isDeleted = FALSE
AND m.accountID <> ''
WHERE j.isDeleted = FALSE
GROUP BY j._id, j.accountJourneyName, j.accountJourneyStatus
ORDER BY accountsWithRecordedMembership DESC, j.accountJourneyName
LIMIT 100;
```

### ジャーニーのアカウントのリスト {#journey-accounts}

業種や国など、特定のジャーニーに関連するアカウントを確認します。

```sql
SELECT DISTINCT
a._id AS accountID,
a.accountName,
a.industry,
a.country
FROM account_journey_member_table m
JOIN account_table a ON m.accountID = a._id
WHERE m.isDeleted = FALSE
AND a.isDeleted = FALSE
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
ORDER BY a.accountName, accountID
LIMIT 100;
```

### 日々のアカウントアクティビティの追跡 {#account-daily-activity}

毎日のアカウント追加、削除、およびステップの変更を追跡して、過去30日間のジャーニーのアクティビティを把握します。

```sql
SELECT
CAST(e.timestamp AS DATE) AS activityDate,
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.accountID) AS distinctAccounts
FROM account_activity_table e
WHERE e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.accountID IS NOT NULL
AND e.accountID <> ''
AND e.eventType IN (
'account.addAccountToJourney',
'account.removeAccountFromJourney',
'account.changeAccountJourneyNode'
)
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY CAST(e.timestamp AS DATE), e.eventType
ORDER BY activityDate DESC, e.eventType
LIMIT 100;
```

### アカウントジャーニーのタイムラインの確認 {#account-timeline}

記録されたイベントとジャーニーのステップを確認して、アカウントの最近のジャーニー履歴を調査します。

```sql
SELECT
e.timestamp AS activityAt,
e.eventType,
e.journeyNodeID,
n.nodeType,
e.previousJourneyNodeID,
e.buyingGroupID
FROM account_activity_table e
LEFT JOIN account_journey_node_table n
ON e.journeyNodeID = n._id
AND e.journeyID = n.accountJourneyID
AND n.isDeleted = FALSE
WHERE e.accountID = 'PASTE_COMPLETE_ACCOUNT_ID_HERE'
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```

## 個人ジャーニークエリ

これらのクエリは、個人のジャーニーを分析するために使用します。 `PASTE_COMPLETE_JOURNEY_ID_HERE`を人物ジャーニーの`_id`値に、`PASTE_COMPLETE_PERSON_ID_HERE`を人物の`_id`値に置き換えます。

### ジャーニー別の人員数の比較 {#person-journey-counts}

記録されたメンバーシップ数、ステータス、日付によって個人のジャーニーを比較し、サイズとライフサイクルを把握します。

```sql
SELECT
j._id AS journeyID,
j.personJourneyName,
j.personJourneyStatus,
j.startDate,
j.endDate,
COUNT(DISTINCT m.personID) AS peopleWithRecordedMembership
FROM person_journey_table j
LEFT JOIN person_journey_member_table m
ON m.journeyID = j._id
AND m.isDeleted = FALSE
AND m.personID <> ''
WHERE j.isDeleted = FALSE
GROUP BY
j._id,
j.personJourneyName,
j.personJourneyStatus,
j.startDate,
j.endDate
ORDER BY peopleWithRecordedMembership DESC, j.personJourneyName
LIMIT 100;
```

### ジャーニー内の人物のリスト {#journey-people}

ジャーニーに関連するユーザー、最後に入力した日時、入力した頻度を確認します。

```sql
SELECT DISTINCT
m.personID,
p.firstName,
p.lastName,
p.email,
m.membershipDate,
m.lastEntryDate,
m.entryCount,
m.reentryOpensAt,
m.journeyNodeID
FROM person_journey_member_table m
LEFT JOIN person_table p
ON m.personID = p._id
AND p.isDeleted = FALSE
WHERE m.isDeleted = FALSE
AND m.personID IS NOT NULL
AND m.personID <> ''
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
ORDER BY m.lastEntryDate DESC NULLS LAST, m.personID
LIMIT 100;
```

### ステップ別の人数比較 {#person-step-counts}

ジャーニーメンバーシップに記録されたステップで、オーディエンスがどのように分配されるかを確認できます。

```sql
SELECT
m.journeyNodeID,
n.nodeType,
COUNT(DISTINCT m.personID) AS peopleWithRecordedStep
FROM person_journey_member_table m
LEFT JOIN person_journey_node_table n
ON m.journeyNodeID = n._id
AND m.journeyID = n.personJourneyID
AND n.isDeleted = FALSE
WHERE m.isDeleted = FALSE
AND m.personID IS NOT NULL
AND m.personID <> ''
AND m.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
GROUP BY m.journeyNodeID, n.nodeType
ORDER BY peopleWithRecordedStep DESC, m.journeyNodeID
LIMIT 100;
```

### 最近のジャーニー活動の追跡 {#person-journey-activity}

記録されたジャーニーの開始、終了、遷移を比較して、過去30日間のジャーニーにおける個人のアクティビティを把握できます。

```sql
SELECT
e.eventType,
COUNT(*) AS recordedRows,
COUNT(DISTINCT e.personID) AS distinctPeople
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.personID IS NOT NULL
AND e.personID <> ''
AND e.eventType IN (
'person.journeyAdd',
'person.journeyRemove',
'person.journeyStart',
'person.journeyEnd',
'person.journeyNodeTransition',
'person.journeySplitNode'
)
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
GROUP BY e.eventType
ORDER BY recordedRows DESC, e.eventType
LIMIT 100;
```

### 個人ジャーニーのタイムラインの確認 {#person-timeline}

ステップの移行、分割選択、ジャーニーに起因するプロファイル更新など、個人の最近のジャーニー履歴を調査します。

```sql
SELECT
e.timestamp AS activityAt,
e.eventType,
e.journeyNodeID,
e.previousJourneyNodeID,
e.newJourneyNodeID,
e.journeyChoiceNumber,
e.journeyEntryCount,
e.attributeName,
e.attributeOldValue,
e.attributeNewValue
FROM person_activity_table e
WHERE e.isDeleted = FALSE
AND e.personID = 'PASTE_COMPLETE_PERSON_ID_HERE'
AND e.journeyID = 'PASTE_COMPLETE_JOURNEY_ID_HERE'
AND e.timestamp >= CURRENT_TIMESTAMP - INTERVAL '30' DAY
AND e.timestamp < CURRENT_TIMESTAMP
ORDER BY e.timestamp DESC
LIMIT 100;
```
