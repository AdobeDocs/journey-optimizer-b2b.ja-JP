---
title: ヘルパー関数
description: Journey Optimizer B2B editionのパーソナライゼーションヘルパー関数のリファレンスガイド。 文字列、日付、数学などの構文と例が含まれます。
feature: Personalization, Content Design Tools
topic: Personalization
role: Developer
level: Intermediate
keywords: 式, エディター, 構文, パーソナライゼーション
source-git-commit: fee5bddcce11b3035da6ab93b18bcc7006b4b554
workflow-type: tm+mt
source-wordcount: '4857'
ht-degree: 44%

---

# ヘルパー関数

パーソナライゼーションエディター内のヘルパー関数を使用して、データの操作、計算の実行、コンテンツの書式設定により、パーソナライズされたコンテンツエクスペリエンスを正確かつ効率的に定義します。 これらの機能、オペレーター、ヘルパーを調べて実験し、連携してカスタマイズされたデータ駆動型ジャーニーを作成する方法を見つけます。

>[!AVAILABILITY]
>
>ヘルパー関数は、[ シンプルなアーキテクチャ ](../simplified-architecture.md) でプロビジョニングされた Journey Optimizer B2B edition環境で使用できます。

## 集計関数

集計関数を使用して、複数の値をグループ化し、単一の要約値を形成します。 また、配列関数とリスト関数を使用すると、配列、リストおよび文字列とのインタラクションを定義しやすくなります。

### 平均 {#average}

配列内の選択された値すべての算術平均を返すには、`average` 関数を使用します。

+++構文

```sql
{%= average(array) %}
```

**例**

次の操作は、すべての注文の平均価格を返します。

```sql
{%=average(orders.order.price)%}
```

+++

### count {#count}

指定された配列内の要素数を返すには、`count` 関数を使用します。

+++構文

```sql
{%= count(array) %}
```

**例**

次の操作は、配列内の注文の数を返します。

```sql
{%= count(orders) %}
```

+++

### max {#max}

配列内の選択された値すべての最大値を返すには、`max` 関数を使用します。

+++構文

```sql
{%= max(array) %}
```

**例**

次の操作は、すべての注文の最高価格を返します。

```sql
{%=max(orders.order.price)%}
```

+++

### min {#min}

配列内の選択された値すべての最小値を返すには、`min` 関数を使用します。

+++構文

```sql
{%= min(array) %}
```

**例**

次の操作は、すべての注文の最低価格を返します。

```sql
{%=min(orders.order.price) %}
```

+++

### sum {#sum}

配列内の選択された値すべての合計を返すには、`sum` 関数を使用します。

+++構文

```sql
{%= sum(array) %}
```

**例**

次の操作は、すべての注文の価格の合計を返します。

```sql
 {%=sum(orders.order.price)%}
```

+++

## 演算関数 {#maths}

演算関数を使用して、値に対する基本的な計算を実行します。

### add {#add}

2 つの引数式の合計を求めるには、`+` （加算）関数を使用します。

+++構文

```sql
{%= double + double %}
```

**例**

次の操作は、2 つの異なる製品の価格を合計します。

```sql
{%= product1.price + product2.price %}
```

+++

### multiple {#multiply}

2 つの引数式の積を求めるには、`*` （乗算）関数を使用します。

+++構文

```sql
{%= double * double %}
```

**例**

次の操作は、在庫製品と製品価格を検索して、製品の総価値を算出します。

```sql
{%= product.inventory * product.price %}
```

+++

### 減算 {#substract}

2 つの引数式の差を求めるには、`-` （減算）関数を使用します。

+++構文

```sql
{%= double - double %}
```

**例**

次の操作は、2 つの異なる製品の価格の違いを見つけます。

```sql
{%= product1.price - product2.price %}
```

+++

### 除算 {#divide}

2 つの引数式の商を求めるには、`/` （除算）関数を使用します。

+++構文

```sql
{%= double / double %}
```

**例**

次の操作は、販売された製品の合計と獲得した合計金額の比率を求めて、品目ごとの平均コストを算出します。

```sql
{%= totalProduct.price / totalProduct.sold %}
```

+++

### remainder {#remainder}

2 つの引数式を除算した後の剰余を求めるには、`%` （remainder）関数を使用します。

+++構文

```sql
{%= double % double %}
```

**例**

次の操作は、年齢が 5 で割り切れるかどうかを確認します。

```sql
{%= person.age % 5 = 0 %}
```

+++

## 配列およびリスト関数 {#arrays}

これらの関数を使用すると、配列、リスト、および文字列の操作が容易になります。

### countOnlyNull {#count-only-null}

`countOnlyNull` 関数を使用すると、リスト内の null 値の数をカウントできます。

+++構文

```sql
{%= countOnlyNull(array) %}
```

**例**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

3 を返します。

+++

### countWithNull {#count-with-null}

`countWithNull` 関数を使用すると、null 値を含むリストのすべての要素をカウントできます。

+++構文

```sql
{%= countWithNull(array) %}
```

**例**

```sql
{%= countOnlyNull([4,0,1,6,0,0]) %}
```

「6」を返します。

+++

### distinct {#distinct}

`distinct` 関数を使用して、重複値を削除して配列またはリストから値を取得します。

+++構文

```sql
{%= distinct(array) %}
```

**例**

次の操作は、複数の店舗で注文した人物を特定します。

```sql
{%= distinct(person.orders.storeId).count() > 1 %}
```

+++

### distinctCountWithNull {#distinct-count-with-null}

`distinctCountWithNull` 関数を使用すると、null 値を含むリスト内の異なる値の数をカウントできます。

+++構文

```sql
{%= distinctCountWithNull(array) %}
```

**例**

```sql
{%= distinctCountWithNull([10,2,10,null]) %}
```

3 を返します。

+++

### ヘッド {#head}

配列またはリスト内の最初の項目を返すには、`head` 関数を使用します。

+++構文

```sql
{%= head(array) %}
```

**例**

次の操作は、最も金額が高い注文の上位 5 件のうち最初の項目を返します。`topN` 関数の詳細については、[配列の最初の `n`](#first-n)の節を参照してください 。

```sql
{%= head(topN(orders,price, 5)) %}
```

+++

### topN {#first-n}

`topN` 関数は、指定された数式に基づいて配列を降順に並べ替え、最初の `N` 項目を返します。 配列のサイズが `N` 未満の場合は、並べ替えられた配列全体を返します。

+++構文

```sql
{%= topN(array, value, amount) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{ARRAY}` | 並べ替える配列またはリスト。 |
| `{VALUE}` | 配列またはリストの並べ替えに使用するプロパティ。 |
| `{AMOUNT}` | 返される項目の数。 |

**例**

次の操作は、最も金額が低い注文の最初の 5 件を返します。

```sql
{%= topN(orders,price, 5) %}
```

+++

### in {#in}

項目が配列またはリストのメンバーであるかどうかを判断するには、`in` 関数を使用します。

+++構文

```sql
{%= in(value, array) %}
```

**例**

次の操作は、誕生日が 3 月、6 月または 9 月の人を定義します。

```sql
{%= in (person.birthMonth, [3, 6, 9]) %}
```

+++

### includes {#includes}

配列またはリストに指定した項目が含まれているかどうかを確認するには、`includes` 関数を使用します。

+++構文

```sql
{%= includes(array,item) %}
```

**例**

次の操作は、お気に入りの色に赤が含まれる人物を定義します。

```sql
{%= includes(person.favoriteColors,"red") %}
```

+++

### 交わり {#intersects}

`intersects` 関数は、2つの配列またはリストに、共通メンバーが 1 つ以上あるかどうかを判断するために使用されます。

+++構文

```sql
{%= intersects(array1, array2) %}
```

**例**

次の操作は、お気に入りの色に赤、青、緑のうち 1 つ以上が含まれる人を定義します。

```sql
{%= intersects(person.favoriteColors,["red", "blue", "green"]) %}
```

+++

<!-- ## Intersection{#intersection}

The `intersection` function is used to determine the common members of two arrays or lists.

**Syntax**

```sql
intersection({ARRAY},{ARRAY})
```

**Example**

The following operation defines if person 1 and person 2 both have favorite colors of red, blue, and green.

```sql
intersection(person1.favoriteColors,person2.favoriteColors) = ["red", "blue", "green"]
```
-->

### bottomN {#last-n}

`bottomN` 関数は、指定された数式に基づいて配列を昇順に並べ替え、最初の `N` 項目を返します。 配列のサイズが `N` 未満の場合は、並べ替えられた配列全体を返します。

+++構文

```sql
{%= bottomN(array, value, amount) %}
```

| 引数 | 説明 |
| --------- | ----------- | 
| `{ARRAY}` | 並べ替える配列またはリスト。 |
| `{VALUE}` | 配列またはリストの並べ替えに使用するプロパティ。 |
| `{AMOUNT}` | 返される項目の数。 |

**例**

次の操作は、最も金額が高い注文の最後の 5 件を返します。

```sql
{%= bottomN(orders,price, 5) %}
```

+++

### notIn {#notin}

項目が配列またはリストのメンバーでないかどうかを判断するには、`notIn` 関数を使用します。

>[!NOTE]
>
>この`notIn` 関数は&#x200B;*また*、どの値も NULL ではないことを保証します。したがって、結果は `in` 関数の完全な否定ではありません。

+++構文

```sql
{%= notIn(value, array) %}
```

**例**

次の操作は、誕生日が 3 月、6 月または 9 月でない人を定義します。

```sql
{%= notIn(person.birthMonth ,[3, 6, 9]) %}
```

+++

### subsetOf {#subset}

特定の配列（配列 A）が別の配列（配列 B）のサブセットであるかどうかを判断するには、`subsetOf` 関数を使用します。 つまり、配列 A 内のすべての要素が配列 B の要素であるということです。

+++構文

```sql
{%= subsetOf(array1, array2) %}
```

**例**

次の操作は、お気に入りの都市をすべて訪問した人を定義します。

```sql
{%= subsetOf(person.favoriteCities,person.visitedCities) %}
```

+++

### スーパーセットの {#superset}

特定の配列（配列 A）が別の配列（配列 B）のスーパーセットであるかどうかを判断するには、`supersetOf` 関数を使用します。 つまり、その配列 Aには配列 B のすべての要素が含まれます。

+++構文

```sql
{%= supersetOf(array1, array2) %}
```

**例**

次の操作は、寿司とピザを 1 回以上食べたことがある人を定義しています。

```sql
{%= supersetOf(person.eatenFoods,["sushi", "pizza"]) %}
```

+++

## 日付および時間関数 {#date-time}

日付と時刻の関数を使用すると、値に対して日付と時刻の操作を実行できます。

### addDays {#add-days}

`addDays` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された日数で調整します。

+++構文

```sql
{%= addDays(date, number) %}
```

**例**

* 入力：`{%= addDays(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* 出力：`2024-11-11T17:19:51Z`

+++

### addHours {#add-hours}

`addHours` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された時間数で調整します。

+++構文

```sql
{%= addHours(date, number) %}
```

**例**

* 入力：`{%= addHours(stringToDate("2024-11-01T17:19:51Z"),1) %}`
* 出力：`2024-11-01T18:19:51Z`

+++

### addMinutes {#add-minutes}

`addMinutes` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された分数で調整します。

+++構文

```sql
{%= addMinutes(date, number) %}
```

**例**

* 入力：`{%= addMinutes(stringToDate("2024-11-01T17:59:51Z"),10) %}`
* 出力：`2024-11-01T18:09:51Z`

+++

### addMonths {#add-months}

`addMonths` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された月数で調整します。

+++構文

```sql
{%= addMonths(date, number) %}
```

**例**

* 入力：`{%= addMonths(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* 出力：`2025-01-01T17:19:51Z`

+++

### addSeconds {#add-seconds}

`addSeconds` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された秒数で調整します。

+++構文

```sql
{%= addSeconds(date, number) %}
```

**例**

* 入力：`{%= addSeconds(stringToDate("2024-11-01T17:19:51Z"),10) %}`
* 出力：`2024-11-01T17:20:01Z`

+++

### addYeers {#add-years}

`addYears` 関数は、増分に正の値を使用し、減分に負の値を使用して、指定された日付を指定された年数で調整します。

+++構文

```sql
{%= addYears(date, number) %}
```

**例**

* 入力：`{%= addYears(stringToDate("2024-11-01T17:19:51Z"),2) %}`
* 出力：`2026-11-01T17:19:51Z`

+++

### 年齢 {#age}

`age` 関数を使用して、指定された日付からの経過時間を取得します。

+++構文

```sql
 {%= age(datetime) %}
```

<!--
**Example**

The following operation gets the value of the identity map for the key `example@example.com`.

```sql
 {%= age(datetime) %}
```
-->

+++

### ageInDay {#age-days}

`ageInDays` 関数は、指定された日付から現在の日付までの経過日数を計算します。 将来の日付には負の値を使用し、過去の日付には正の値を使用します。

+++構文

```sql
{%= ageInDays(date) %}
```

**例**

currentDate = 2025-01-07T12:17:10.720122+05:30（アジア／コルカタ）

* 入力：`{%= ageInDays(stringToDate("2025-01-01T17:19:51Z"))%}`
* 出力：`5`

+++

### ageInMonth {#age-months}

`ageInMonths` 関数は、指定された日付から現在の日付までの経過月数を計算します。 将来の日付には負の値を使用し、過去の日付には正の値を使用します。

+++構文

```sql
{%= ageInMonths(date) %}
```

**例**

currentDate = 2025-01-07T12:22:46.993748+05:30（アジア／コルカタ）

* 入力：`{%=ageInMonths(stringToDate("2024-01-01T00:00:00Z"))%}`
* 出力：`12`

+++

### compareDates {#compare-dates}

`compareDates` 関数は、最初の入力日付を他の入力日付と比較します。date1 が date2 と等しい場合は 0、date1 が date2 より前の場合は–1、date1 が date2 より後の場合は 1 が返されます。

+++構文

```sql
{%= compareDates(date1, date2) %}
```

**例**

* 入力：`{%=compareDates(stringToDate("2024-12-02T00:00:00Z"), stringToDate("2024-12-03T00:00:00Z"))%}`
* 出力：`-1`

+++

### convertZonedDateTime {#convert-zoned-date-time}

`convertZonedDateTime` 関数は、日時を指定されたタイムゾーンに変換します。

+++構文

```sql
{%= convertZonedDateTime(dateTime, timezone) %}
```

**例**

* 入力：`{%=convertZonedDateTime(stringToDate("2019-02-19T08:09:00Z"), "Asia/Tehran")%}`
* 出力：`2019-02-19T11:39+03:30[Asia/Tehran]`

+++

### currentTimeInMillis {#current-time}

`currentTimeInMillis` 関数を使用して、現在の時刻をエポックミリ秒単位で取得します。

+++構文

```sql
{%= currentTimeInMillis() %}
```

<!--
**Example**

The following operation gets all the keys for the map `identityMap`.

```sql
{%= keys(identityMap) %}
```
-->

+++

### dateDiff {#date-diff}

`dateDiff` 関数を使用すると、2 つの日付間の差異を日数単位で取得できます。

+++構文

```sql
{%= dateDiff(datetime,datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### dayOfMonth {#day-month}

`dayOfMonth` は、その月の日付を表す数値を返します。

+++構文

```sql
{%= dayOfMonth(datetime) %}
```

**例**

* 入力：`{%= dayOfMonth(stringToDate("2024-11-05T17:19:51Z")) %}`
* 出力：`5`

+++

### 曜日 {#day-week}

`dayOfWeek` 関数を使用して曜日を取得します。

+++構文

```sql
{%= dayOfWeek(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### dayOyear {#day-year}

`dayOfYear` 関数を使用して通日（1 月 1 日からの通算日数）を取得します。

+++構文

```sql
{%= dayOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### diffInSeconds {#diff-seconds}

`diffInSeconds` 関数は、秒数単位で 2 つの日付間の差異を返します。

+++構文

```sql
{%= diffInSeconds(endDate, startDate) %}
```

**例**

* 入力：`{%=diffInSeconds(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T17:19:01Z"))%}`
* 出力：`50`

+++

### extractHours {#extract-hours}

`extractHours` 関数は、指定されたタイムスタンプから時間コンポーネントを抽出します。

+++構文

```sql
{%= extractHours(date) %}
```

**例**

* 入力：`{%= extractHours(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`17`

+++

### extractMinutes {#extract-minutes}

`extractMinutes` 関数は、指定されたタイムスタンプから分コンポーネントを抽出します。

+++構文

```sql
{%= extractMinutes(date) %}
```

**例**

* 入力：`{%= extractMinutes(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`19`

+++

### extractMonths {#extract-months}

`extractMonth` 関数は、指定されたタイムスタンプから月コンポーネントを抽出します。

+++構文

```sql
{%= extractMonths(date) %}
```

**例**

* 入力：`{%=extractMonth(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`11`

+++

### extractSeconds {#extract-seconds}

`extractSeconds` 関数は、指定されたタイムスタンプから秒コンポーネントを抽出します。

+++構文

```sql
{%= extractSeconds(date) %}
```

**例**

* 入力：`{%=extractSeconds(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`51`

+++

### formatDate {#format-date}

`formatDate` 関数を使用して、日時値を書式設定します。 形式は、有効な Java `DateTimeFormat` パターンである必要があります。

+++構文

```sql
{%= formatDate(datetime, format) %}
```

ここで、最初の文字列は日付属性で、2 番目の値は日付の変換および表示方法です。

>[!NOTE]
>
> 日付パターンが無効な場合、日付は ISO 標準形式にフォールバックします。
>
> [Oracle ドキュメント](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html){_blank}にまとめられている Java 日付書式設定関数を使用できます。

**例**

次の操作を実行すると、MM/DD/YY の形式で日付が返されます。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}
```

+++

#### パターン文字 {#pattern-characters}

一部のパターン文字は似ているように見えるかもしれませんが、異なる概念を表しています。

| パターン | 意味 | 例（`2023-12-31T10:15:30Z`） |
|---------|---------|--------------------------------------|
| `y` | 暦年（標準年） | `2023` |
| `Y` | 週ベースの年（ISO 8601）。 年の境界で異なる場合があります。 | `2024` （2023 年 12 月 31 日は 2024 年の第 1 週です） |
| `M` | 月（1 ～ 12 または `Jan`、`January` などのテキスト） | `12` または `Dec` |
| `m` | 分時（0～59） | `15` |
| `d` | 日（1 ～ 31） | `31` |
| `D` | 年間通算日（1 ～ 366） | `365` |

#### 日付をロケールサポートの形式にする {#format-date-locale}

`formatDate` 関数を使用すると、目的のロケールなど、日付と時刻の値を対応する言語に依存する表現にフォーマットできます。 形式は、有効な Java `DateTimeFormat` パターンである必要があります。

+++構文

```sql
{%= formatDate(datetime, format, locale) %}
```

最初の文字列は日付の属性で、2 番目の値はどのように日付を変換して表示するか、3 番目の値は文字列形式のロケールを表します。

>[!NOTE]
>
> 日付パターンが無効な場合、日付は ISO 標準形式にフォールバックします。
>
> [Oracle ドキュメント ](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html) にまとめられている Java 日付書式設定関数を使用できます。
>
> [Oracle ドキュメントと ](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html) サポートされているロケール [ にまとめられている書式設定と有効なロケールを使用でき ](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html) す。

**例**

次の操作は、MM/dd/YY 形式（ロケール：FRANCE）で日付を返します。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY", "fr_FR") %}
```

+++

### getCurrentZonedDateTime {#get-current-zoned-date-time}

`getCurrentZonedDateTime` 関数は、タイムゾーン情報を含む現在の日時を返します。

+++構文

```sql
{%= getCurrentZonedDateTime() %}
```

**例**

* 入力：`{%= getCurrentZonedDateTime() %}`
* 出力：`2024-12-06T17:22:02.281067+05:30[Asia/Kolkata]`

+++

### diffInHour {#hours-difference}

`diffInHours` 関数は、時間数単位で 2 つの日付間の差異を返します。

+++構文

```sql
{%= diffInHours(endDate, startDate) %}
```

**例**

* 入力：`{%= diffInHours(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T07:19:51Z"))%}`
* 出力：`10`

+++

### diffInMinute {#diff-minutes}

`diffInMinutes` 関数は、2 つの日付間の差異を分単位で返します。

+++構文

```sql
{%= diffInMinutes(endDate, startDate) %}
```

**例**

* 入力：`{%= diffInMinutes(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T16:19:51Z"))%}`
* 出力：`60`

+++

### diffInMonths {#months-difference}

`diffInMonths` 関数は、月数単位で 2 つの日付間の差異を返します

+++構文

```sql
{%= diffInMonths(endDate, startDate) %}
```

**例**

* 入力：`{%=diffInMonths(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-08-01T17:19:51Z"))%}`
* 出力：`3`

+++

### setDays {#set-days}

`setDays` 関数を使用して、指定された日時の日付を設定します。

+++構文

```sql
{%= setDays(datetime, day) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### setHours {#set-hours}

`setHours` 関数を使用して日時の時を設定します。

+++構文

```sql
{%= setHours(datetime, hour) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### toDateTime {#string-to-date-time}

`toDateTime` 関数は、文字列を日付に変換します。無効な入力に対する出力として、エポック日付を返します。

+++構文

```sql
{%= toDateTime(string, string) %}
```

**例**

* 入力：`{%=toDateTime("2024-11-01T17:19:51Z")%}`
* 出力：`2024-11-01T17:19:51Z`

+++

### toUtc {#to-utc}

`toUTC` 関数を使用して日時を UTC に変換します。

+++構文

```sql
{%= toUTC(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### truncateToStartOfDay {#truncate-day}

`truncateToStartOfDay` 関数を使用して、指定された日時を、時刻 00:00 の日の始めに設定して変更します。

+++構文

```sql
{%= truncateToStartOfDay(date) %}
```

**例**

* 入力：`{%= truncateToStartOfDay(stringToDate("2024-11-01T17:19:51Z")) %}`
* 出力：`2024-11-01T00:00Z`

+++

### truncateToStartOfQuarter {#truncate-quarter}

`truncateToStartOfQuarter` 関数を使用すると、日時を四半期の最初の日（1 月 1 日、4 月 1 日、7 月 1 日、10 月 1 日など） :0000 に切り捨てることができます。

+++構文

```sql
{%= truncateToStartOfQuarter(dateTime) %}
```

**例**

* 入力：`{%=truncateToStartOfQuarter(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`2024-10-01T00:00Z`

+++

### truncateToStartOfWeek {#truncate-week}

`truncateToStartOfWeek` 関数は、指定された日時を週の初め（月曜日の 00:00）に設定して変更します。

+++構文

```sql
{%= truncateToStartOfWeek(dateTime) %}
```

**例**

* 入力：`{%= truncateToStartOfWeek(stringToDate("2024-11-19T17:19:51Z"))%} // tuesday`
* 出力：`2024-11-18T00:00Z // monday`

+++

### truncateToStartOfYear {#truncate-year}

`truncateToStartOfYear` 関数を使用すると、指定された日時を年の最初の日（1 月 1 日）の 00:00 に切り捨てて変更できます。

+++構文

```sql
{%= truncateToStartOfYear(dateTime) %}
```

**例**

* 入力：`{%=truncateToStartOfYear(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`2024-01-01T00:00Z`

+++

### 週間/年 {#week-of-year}

`weekOfYear` 関数を使用して、年の週番号（何週目か）を取得します。

+++構文

```sql
{%= weekOfYear(datetime) %}
```

<!--
**Example**

The following operation gets all the values for the map `identityMap`.

```sql
{%= values(identityMap) %}
```
-->

+++

### diffInYears {#diff-years}

2 つの日付間の年単位の差異を返すには、`diffInYears` 関数を使用します。

+++構文

```sql
{%= diffInYears(endDate, startDate) %}: int
```

**例**

* 入力：`{%=diffInYears(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2019-10-01T17:19:51Z"))%}`
* 出力：`5`

+++

## 演算子関数 {#operators}

ブール関数と比較関数を使用して、論理評価を実行します。

### and {#and}

`and` 関数は、論理積を作成するために使用されます。

+++構文

```sql
{%= query1 and query2 %}
```

**例**

次の操作は、母国（フランス）と生年月日（1985 年）を持つすべての人を返します。

```sql
{%= profile.homeAddress.country = "France" and profile.person.birthYear = 1985 %}
```

+++

### または {#or}

`or` 関数は、論理和を作成するために使用されます。

+++構文

```sql
{%= query1 or query2 %}
```

**例**

次の操作は、母国（フランス）または生年月日（1985 年）を持つすべての人を返します。

```sql
{%= profile.homeAddress.country = "France" or profile.person.birthYear = 1985 %}
```

+++

<!--
## Not{#not}

The `not` (or `!`) function is used to create a logical negation.

**Syntax**

```sql
not ({QUERY})
!({QUERY})
```

**Example**

The following operation will return all people who do not have their home country as Canada.

```sql
not (homeAddress.countryISO = "CA")
```
-->

### 等しい {#operator-equals}

`=`（次に等しい）関数は、ある値または式が別の値または式と等しいかどうかを確認します。

+++構文

```sql
{%= expression = value %}
```

**例**

次の操作は、自宅住所の国がフランスかどうかを確認します。

```sql
{%= profile.homeAddress.country = "France" %}
```

+++

### 次と等しくない {#notequal}

`!=`（次と等しくない）関数は、ある値または式が別の値または式と等しく&#x200B;**ない**&#x200B;かどうかを確認します。

+++構文

```sql
{%= expression != value %}
```

**例**

次の操作は、自宅住所の国がフランスでないかどうかを確認します。

```sql
{%= profile.homeAddress.country != "France" %}
```

+++

### 指定の値より大きい {#greaterthan}

`>` （次より大きい）関数を使用すると、最初の値が 2 番目の値より大きいかどうかを確認できます。

+++構文

```sql
{%= expression1 > expression2 %}
```

**例**

次の操作は、1970 年より後（1970 年は含まない）に生まれた人々を定義します。

```sql
{%= profile.person.birthYear > 1970 %}
```

+++

### 次よりも大きいか等しい {#greaterthanorequal}

`>=` （同じかそれ以上）関数を使用すると、最初の値が 2 番目の値以上かどうかを確認できます。

+++構文

```sql
{%= expression1 >= expression2 %}
```

**例**

以下の操作は、1970 年以降に生まれた人々を定義します。

```sql
{%= profile.person.birthYear >= 1970 %}
```

+++

### 指定の値未満 {#lessthan}

`<` （次より小さい）比較関数を使用すると、最初の値が 2 番目の値より小さいかどうかを確認できます。

+++構文

```sql
{%= expression1 < expression2 %}
```

**例**

次の操作は、2000 年より前（2000 年を含まない）に生まれた人々を定義します。

```sql
{%= profile.person.birthYear < 2000 %}
```

+++

### 次よりも小さいか等しい{#lessthanorequal}

`<=` （同じかそれ以下）比較関数を使用すると、最初の値が 2 番目の値以下かどうかを確認できます。

+++構文

```sql
{%= expression1 <= expression2 %}
```

**例**

次の操作は、2000 年以前に生まれた人々を定義します。

```sql
{%= profile.person.birthYear <= 2000 %}
```

+++

## 動的関数 {#dynamic-helpers}

動的ヘルパー関数を使用して、条件付き評価、イテレーション、変数割り当てを動的パーソナライゼーションに使用します。

### デフォルトのフォールバック値 {#default-value}

`Default Fallback Value` ヘルパーは、属性が空または null の場合にデフォルトのフォールバック値を返すために使用されます。このメカニズムは、プロファイル属性とジャーニーイベントで機能します。

+++構文

```sql
Hello {%=profile.personalEmail.name.firstName ?: "there" %}!
```

この例では、このプロファイルの `firstName` 属性が空または null の場合、`there` という値が表示されます。

+++

### if （条件） {#if-function}

`if` ヘルパーを使用して、条件ブロックを定義します。
式の評価結果が true の場合、ブロックはレンダリングされます。true でない場合はスキップされます。

+++構文

```sql
{%#if contains(account.accountOrganization.primaryEmailDomain, ".edu")%}
<a href="https://www.adobe.com/academia">Check out this link</a>
```

`if` ヘルパーの後に、`else` ステートメントを入れて、その条件の結果が false の場合に実行するコードのブロックを指定することもできます。
`elseif` ステートメントは、最初のステートメントが false を返した場合にテストする新しい条件を指定します。


**形式**

```sql
{
    {
        {%#if condition1%} element_1 
        {%else if condition2%} element_2 
        {%else%} default_element 
        {%/if%}
    }
}
```

<!-- 
**Examples**

* **Render different store links based on conditional expressions**

    ```sql
    {%#if profile.homeAddress.countryCode = "FR"%}
    <a href="https://www.somedomain.com/fr">Consultez notre catalogue</a>
    {%else%}
    <a href="https://www.somedomain.com/en">Checkout our catalogue</a>
    {%/if%}
    ```

* **Determine email address extension**

    ```sql
    {%#if contains(profile.personalEmail.address, ".edu")%}
    <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
    {%else if contains(profile.personalEmail.address, ".org")%}
    <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
    {%else%}
    <a href="https://www.adobe.com/users">Checkout our page</a>
    {%/if%}
    ```

* **Add a conditional link**

    The following operation adds a link to the `www.adobe.com/academia` website for profiles with '.edu' email addresses only, the `www.adobe.com/org` website for profiles with '.org' email addresses, and the default URL `www.adobe.com/users` for all other profiles:

    ```sql
    {%#if contains(profile.personalEmail.address, ".edu")%}
    <a href="https://www.adobe.com/academia">Checkout our page for Academia personals</a>
    {%else if contains(profile.personalEmail.address, ".org")%}
    <a href="https://www.adobe.com/orgs">Checkout our page for Non Profits</a>
    {%else%}
    <a href="https://www.adobe.com/users">Checkout our page</a>
    {%/if%}
    ```

* **Conditional content based on audience membership**

    ```sql
    {%#if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8b").status = "existing"%}
    Hi! Esteemed gold member. <a href="https://www.somedomain.com/gold">Checkout your exclusive perks </a>
    {%else if profile.segmentMembership.get("ups").get("5fd513d7-d6cf-4ea2-856a-585150041a8c").status = "existing"%}
    Hi! Esteemed silver member. <a href="https://www.somedomain.com/silver">Checkout your exclusive perks </a>
    {%/if%}
    ```
-->

+++

### unless {#unless}

`unless` ヘルパーを使用して、条件ブロックを定義します。 `if` ヘルパーとは異なり、式の評価結果が false の場合にブロックがレンダリングされます。

+++構文

```sql
{%#unless unlessCondition%} element_1 {%else%} default_element {%/unless%}
```

**例**

メールアドレスの拡張子に基づいてコンテンツをレンダリングする。

```sql
{%#unless endsWith(account.accountOrganization.primaryEmailDomain}, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content
{%/unless%}
```

+++

### それぞれ {#each}

`each` ヘルパーを使用して、配列に対して反復処理を行います。

ヘルパー構造は ```{{#each ArrayName}}``` YourContent `{{/each}}` です

ブロック内でキーワード `this` を使用して、個々の配列項目を参照できます。 `{{@index}}` を使用して、配列の要素のインデックスをレンダリングします。

+++構文

```sql
{{#each profile.productsInCart}}
    <li>{{this.name}}</li>
{{/each}}
```

**例**

```sql
{{#each profile.homeAddress.city}}
  {{@index}} : {{this}}<br>
{{/each}}
```

**例**

ユーザーが買い物かごに入れた商品のリストをレンダリングする。

```sql
{{#each profile.products as |product|}}
    <li>{{product.productName}} {{product.productRating}}</li>
{{/each}}
```

+++

### 次を使用 {#with}

template-part の評価トークンを変更するには、`with` ヘルパーを使用します。

+++構文

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

`with` ヘルパーは、ショートカット変数を定義する場合にも使用できます。

**例**

長い変数名を短い変数名にエイリアシングする場合は、`with` を使用します。

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

+++

### let {#let}

`let` 関数を使用すると、式を変数として保存し、後からクエリで使用できます。

+++構文

```sql
{% let variable = expression %} {{variable}}
```

**例**

次の例では、買い物かご内の価格が 100～1000 の製品の合計価格を計算できます。

```sql
{% let sum = 0%}
    {{#each profile.productsInCart as |p|}}
        {%#if p.price>100 and p.price<1000%}
            {%let sum = sum + p.price %}
        {%/if%}
    {{/each}}
{{sum}}
```

+++

## 実行メタデータ {#execution-metadata}

>[!AVAILABILITY]
>
>この機能は限定提供（LA）です。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

`executionMetadata` を使用して、カスタムのキーと値のペアをキャプチャし、メッセージ実行コンテキストに動的に保存します。

この関数を使用すると、キャンペーンやジャーニーの任意のネイティブアクションにコンテキスト情報を追加できます。これを使用すると、トラッキング、分析、パーソナライゼーション、ダウンストリーム処理など、様々な目的でリアルタイム配信のコンテキストデータを外部システムに書き出すことができます。

>[!NOTE]
>
>カスタムアクションは、`executionMetadata` 関数をサポートしていません。

例えば、`executionMetadata` ヘルパーを使用して、各プロファイルに送信される各配信に特定の ID を追加できます。 この情報は実行時に生成され、強化された実行メタデータは外部レポートプラットフォームとのダウンストリームの紐付けのためにエクスポートできます。

+++構文

```
{{executionMetadata key="your_key" value="your_value"}}
```

この構文では、`key` はメタデータ名を参照し、`value` は保持するメタデータです。

**仕組み**

キャンペーンまたはジャーニー内のチャネルコンテンツから任意の要素を選択し、パーソナライゼーションエディターを使用して、この要素に `executionMetadata` ヘルパーを追加します。

>[!NOTE]
>
>コンテンツ自体が表示されている場合、`executionMetadata` 関数は表示されません。

実行時に、次のスキーマの追加を伴って、メタデータ値が既存の **[!UICONTROL メッセージフィードバックイベントデータセット]** に追加されます。

```
"_experience": {
  "customerJourneyManagement": {
    "messageExecution": {
      "metadata": {
        "your_key": "your_value"
      }
    }
  }
}
```

>[!IMPORTANT]
>
>アクションごとのキーと値のペアの上限は 2 kb です。 2Kb の制限を超えた場合、メッセージは引き続き配信されますが、キーと値のペアのいずれかが切り捨てられる場合があります。

**例**

```
{{executionMetadata key="firstName" value=profile.person.name.firstName}}
```

この例では、`profile.person.name.firstName` = &quot;Alex&quot; と想定すると、結果のエンティティは次のようになります。

```
{
  "key": "firstName",
  "value": "Alex"
}
```

+++

## マップ関数 {#maps}

パーソナライゼーションでマップ関数を使用すると、マップとのやり取りが容易になります。

### get {#get}

`get` 関数を使用して、指定されたキーのマップの値を取得します。

+++構文

```sql
{%= get(map, string) %}
```

**例**

次の操作は、キー `example@example.com` の ID マップの値を取得します。

```sql
{%= get(identityMap,"example@example.com") %}
```

+++

### キー {#keys}

`keys` 関数を使用して、特定のマップのすべてのキーを取得します。

+++構文

```sql
{%= keys(map) %}
```

**例**

次の操作は、マップ `identityMap` のすべてのキーを取得します。

```sql
{%= keys(identityMap) %}
```

+++

### 値 {#values}

`values` 関数は、特定のマップのすべての値を取得するために使用されます。

+++構文

```sql
{%= values(map) %}
```

**例**

次の操作は、マップ `identityMap` のすべての値を取得します。

```sql
{%= values(identityMap) %}
```

+++

## 数学関数 {#math}

パーソナライゼーションエディターで数学関数を使用する方法を説明します。

### 絶対パス {#absolute}

`absolute` 関数を使用して、数値をその絶対値に変換します。

+++構文

```sql
{%= absolute(int) %}: int
```

+++

### formatNumber {#format-number}

`formatNumber` 関数を使用すると、任意の数値を言語依存の表現に書式設定できます。

ロケールを表す数値および文字列を受け入れて、目的のロケールで書式設定された数値の文字列を返します。

+++構文

```sql
{%= formatNumber(number/double,string) %}: string
```

[Oracle ドキュメントと ](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html) サポートされているロケールにまとめられている書式設定と有効なロケールを使用でき [ す ](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html){_blank}

**例**

このクエリは、123456.789 に対応するアラビア語で書式設定された文字列を入力番号として返します。

```sql
{%= formatNumber(123456.789, "ar_EG") %}
```

+++

### random {#random}

`random` 関数を使用すると、0 ～ 1 の間のランダムな値を返します。

+++構文

```sql
{%= random() %}: double
```

+++

### roundDown {#round-down}

`roundDown` 関数を使用すると、数値を切り捨てることができます。

+++構文

```sql
{%= roundDown(double) %}: double
```

+++

### 切り上げ {#round-up}

`roundUp` 関数を使用すると、数値を切り上げることができます。

+++構文

```sql
{%= roundUp(double) %}: double
```

+++

### toHexString {#to-hex-string}

この `toHexString` 関数は、任意の数を 16 進文字列に変換します。

+++構文

```sql
{%= toHexString(number) %}: string
```

**例**

このクエリは、158 の 16 進数値を 9e として返します。

```sql
{%= toHexString(158) %}
```

+++

### toInt {#to-int}

型（number、double、integer、long、float、short、byte、boolean、string）を整数に変換するには、`toInt` 関数を使用します。

+++構文

```sql
{%= toInt(<valueToConvert>) %}: integer
```

**例**

このクエリは、42.6 の整数値を 42 として返します。

```sql
{%= toInt(42.6) %}: integer
```

+++

### toPercentage {#to-percentage}

`toPercentage` 関数を使用して数値をパーセンテージに変換します。

+++構文

```sql
{%= toPercentage(double) %}: string
```

+++

### toPrecision {#to-precision}

`toPrecision` 関数を使用して、数値を必要な精度に変換します。

+++構文

```sql
{%= toPrecision(double,int) %}: string
```

+++

### toString {#to-string}

`toString` 関数は、任意の数値を文字列表現に変換します。

+++構文

```sql
{%= toString(string) %}: string
```

**例**

このクエリは `"12"` を返します。

```sql
{%= toString(12) %} 
```

+++

## オブジェクト関数 {#objects}

オブジェクトのプロパティまたは属性を照会するオブジェクト関数。

### isNull {#isNull}

`isNull` 関数は、オブジェクト参照が存在しないかどうかを判定します。

+++構文

```sql
{%= isNull(object) %}
```

**例**

次の操作は、ユーザーの自宅の住所が存在しないかどうかを確認します。

```sql
{%= isNull(person.homeAddress) %}
```

+++

### isNotNull {#isNotNull}

`isNotNull` 関数は、オブジェクト参照が存在するかどうかを判定します。

+++構文

```sql
{%= isNotNull(object) %}
```

**例**

次の操作は、ユーザーの自宅の住所が存在するかどうかを確認します。

```sql
{%= isNotNull(person.homeAddress) %}
```

+++

## 文字列関数 {#string-functions}

パーソナライゼーションエディターで文字列関数を使用する方法を説明します。

### camelCase {#camelCase}

`camelCase` 関数は、文字列の各単語の最初の文字を大文字にします。

+++構文

```sql
{%= camelCase(string)%}
```

**例**

次の関数は、プロファイルの住所の単語の最初の文字を大文字にします。

```sql
{%= camelCase(profile.homeAddress.street) %}
```

+++

### charCodeAt {#char-code-at}

`charCodeAt` 関数は、JavaScriptの `charCodeAt` 関数と同様に、文字の ASCII 値を返します。 文字列と整数（文字の位置を定義する）を入力引数として受け取り、対応する ASCII 値を返します。

+++構文

```sql
{%= charCodeAt(string,int) %}: int
```

**例**

次の関数は、`o` （111）の ASCII 値を返します。

```sql
{%= charCodeAt("some", 1)%}
```

+++

### concat {#concate}

`concat` 関数は、2 つの文字列を 1 つに結合します。

+++構文

```sql
{%= concat(string,string) %}
```

**例**

次の関数は、プロファイルの市区町村と国を 1 つの文字列に組み合わせます。

```sql
{%= concat(profile.homeAddress.city,profile.homeAddress.country) %}
```

+++

### 指定の語を含む {#contains}

文字列が指定の部分文字列を含んでいるかどうかを判定するには、`contains` 関数を使用します。

+++構文

```sql
{%= contains(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `STRING_1` | チェックの実行対象となる文字列です。 |
| `STRING_2` | 最初の文字列内で検索する文字列です。 |
| `CASE_SENSITIVE` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

* 次の関数は、プロファイルの名に A （大文字または小文字）が含まれているかどうかを確認します。 プロファイルが含む場合は、`true` を返します。 そうでない場合は、`false` を返します。

  ```sql
  {%= contains(profile.person.name.firstName, "A", false) %}
  ```

* 次のクエリでは、大文字と小文字を区別したうえで、人物のメールアドレスが `2010@gm` という文字列を含んでいるかどうかを判定します。

  ```sql
  {%= contains(profile.person.emailAddress,"2010@gm") %}
  ```

+++

### doesNotContain {#doesNotContain}

文字列が指定の部分文字列を含んでいないかどうかを判定するには、`doesNotContain` 関数を使用します。

+++構文

```sql
{%= doesNotContain(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `STRING_1` | チェックの実行対象となる文字列です。 |
| `STRING_2` | 最初の文字列内で検索する文字列です。 |
| `CASE_SENSITIVE` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物のメールアドレスが `2010@gm` という文字列を含んでいないかどうかを判定します。

```sql
{%= doesNotContain(profile.person.emailAddress,"2010@gm")%}
```

+++

### doesNotEndWith {#doesNotEndWith}

文字列の末尾が指定の部分文字列になっていないかどうかを判定するには、`doesNotEndWith` 関数を使用します。

+++構文

```sql
{%= doesNotEndWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物のメールアドレスが `.com` で終わらないかどうかを判定します。

```sql
doesNotEndWith(person.emailAddress,".com")
```

+++

### doesNotStartWith {#doesNotStartWith}

文字列の先頭が指定の部分文字列になっていないかどうかを判定するには、`doesNotStartWith` 関数を使用します。

+++構文

```sql
{%= doesNotStartWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物の名前が `Joe` で始まらないかどうかを判定します。

```sql
{%= doesNotStartWith(person.name,"Joe")%}
```

+++

### encode64 {#encode64}

`encode64` 関数を使用して、個人情報（PI）を URL に含めるなどの個人情報を保持する文字列をエンコードします。

+++構文

```sql
{%= encode64(string) %}
```

+++

### endsWith {#endsWith}

文字列が指定の部分文字列で終わることを判別するには、`endsWith` 関数を使用します。

+++構文

```sql
{%= endsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物のメールアドレスが `.com` で終わるかどうかを判定します。

```sql
{%= endsWith(person.emailAddress,".com") %}
```

+++

### 等しい {#equals}

文字列が指定の文字列に等しいかどうかを判定するには、`equals` 関数を使用します。

+++構文

```sql
{%= equals(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物の名前が `John` かどうかを判定します。

```sql
{%=equals(profile.person.name,"John") %}
```

+++

### equalsIgnoreCase {#equalsIgnoreCase}

大文字と小文字を区別せずに、文字列が指定の文字列に等しいかどうかを判定するには、`equalsIgnoreCase` 関数を使用します。

+++構文

```sql
{%= equalsIgnoreCase(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、大文字と小文字を区別せずに、人物の名前が `John` かどうかを判定します。

```sql
{%= equalsIgnoreCase(profile.person.name,"John") %}
```

+++

### extractEmailDomain {#extractEmailDomain}

`extractEmailDomain` 関数を使用して、メールアドレスのドメインを抽出します。

+++構文

```sql
{%= extractEmailDomain(string) %}
```

**例**

次のクエリは、個人のメールアドレスのメールドメインを抽出します。

```sql
{%= extractEmailDomain(profile.personalEmail.address) %}
```

+++

### formatCurrency {#format-currency}

`formatCurrency` 関数を使用すると、2 番目の引数で文字列として渡されたロケールに応じて、任意の数値を対応する言語に依存する通貨表現に変換できます。

+++構文

```sql
{%= formatCurrency(number/double,string) %}: string
```

**例**

このクエリは £56.00 を返します

```sql
{%= formatCurrency(56L,"en_GB") %}
```

+++

### getUrlHost {#get-url-host}

`getUrlHost` 関数を使用して、URL のホスト名を取得します。

+++構文

```sql
{%= getUrlHost(string) %}: string
```

**例**

```sql
{%= getUrlHost("https://www.myurl.com/contact") %}
```

「www.myurl.com」を返します

+++

### getUrlPath {#get-url-path}

`getUrlPath` 関数を使用して、URL のドメイン名の後のパスを取得します。

+++構文

```sql
{%= getUrlPath(string) %}: string
```

**例**

```sql
{%= getUrlPath("https://www.myurl.com/contact.html") %}
```

「/contact.html」を返します

+++

### getUrlProtocol {#get-url-protocol}

`getUrlProtocol` 関数を使用して、URL のプロトコルを取得します。

+++構文

```sql
{%= getUrlProtocol(string) %}: string
```

**例**

```sql
{%= getUrlProtocol("https://www.myurl.com/contact.html") %}
```

「http」を返します

+++

### indexOf {#index-of}

`indexOf` 関数を使用すると、2 番目のパラメーターが最初に現れる（最初の引数内の）位置を返します。 一致するものがない場合は「-1」を返します。

+++構文

```sql
{%= indexOf(STRING_1, STRING_2) %}: integer
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初のパラメーターで検索する文字列 |

**例**

```sql
{%= indexOf("hello world","world" ) %}
```

「6」を返します。

+++

### isEmpty {#isEmpty}

`isEmpty` 関数を使用すると、文字列が空かどうかを判断できます。

+++構文

```sql
{%= isEmpty(string) %}
```

**例**

次の関数は、プロファイルの携帯電話番号が空の場合、「true」を返します。それ以外の場合は、`false` を返します。

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

+++

### isNotEmpty {#is-not-empty}

`isNotEmpty` 関数を使用すると、文字列が空でないかどうかを判定できます。

+++構文

```sql
{= isNotEmpty(string) %}: boolean
```

**例**

次の関数は、プロファイルの携帯電話番号が空の場合、「true」を返します。それ以外の場合は、`false` を返します。

```sql
{%= isNotEmpty(profile.mobilePhone.number) %}
```

+++

### lastIndexOf {#last-index-of}

`lastIndexOf` 関数を使用して、2 番目のパラメーターが最後に現れる（最初の引数内の）位置を返します。 一致するものがない場合は「-1」を返します。

+++構文

```sql
{= lastIndexOf(STRING_1, STRING_2) %}: integer
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初のパラメーターで検索する文字列 |

**例**

```sql
{%= lastIndexOf("hello world","o" ) %}
```

「7」を返します。

+++

### leftTrim {#leftTrim}

文字列の先頭から空白を削除するには、`leftTrim` 関数を使用します。

+++構文

```sql
{%= leftTrim(string) %}
```

+++

### length {#length}

文字列または式の文字数を取得するには、`length` 関数を使用します。

+++構文

```sql
{%= length(string) %}
```

**例**

次の関数は、プロファイルの市区町村名の長さを返します。

```sql
{%= length(profile.homeAddress.city) %}
```

+++

### like {#like}

文字列が指定のパターンと一致するかどうかを判定するには、`like` 関数を使用します。

+++構文

```sql
{%= like(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列列と照合される式です。式の作成に使用できる特殊文字として、`%` と `_` の 2 つがサポートされています。 <ul><li>`%` は、0 個以上の文字を表すために使用されます。</li><li>`_` は、1 文字を表すために使用されます。</li></ul> |

**例**

次のクエリでは、パターン `es` を含むプロファイルが住んでいるすべての都市を取得します。

```sql
{%= like(profile.homeAddress.city, "%es%")%}
```

+++

### lowercase {#lower}

文字列を小文字に変換するには、`lowerCase` 関数を使用します。

+++構文

```sql
{%= lowerCase(string) %}
```

**例**

この関数は、プロファイルの名を小文字に変換します。

```sql
{%= lowerCase(profile.person.name.firstName) %}
```

+++

### 一致する {#matches}

`matches` 関数を使用すると、文字列が特定の正規表現に一致することを判別できます。 正規表現のマッチングパターンについて詳しくは、[Oracleのドキュメント ](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html) を参照してください。

+++構文

```sql
{%= matches(STRING_1, STRING_2) %}
```

**例**

次のクエリでは、大文字と小文字を区別せずに、人物の名前が `John` で始まるかどうかを判定します。

```sql
{%= matches(person.name.,"(?i)^John") %}
```

+++

### マスク {#mask}

`mask` 関数を使用すると、文字列の一部を「X」の文字に置き換えることができます。

+++構文

```sql
{%= mask(string,integer,integer) %}
```

**例**

次のクエリでは、「123456789」文字列を「X」の文字に置き換えます（最初と最後の 2 文字を除きます）。

```sql
{%= mask("123456789",1,2) %}
```

このクエリは `1XXXXXX89` を返します。

+++

### md5 {#md5}

`md5` 関数を使用して、文字列の md5 ハッシュを計算して返します。

+++構文

```sql
{%= md5(string) %}: string
```

**例**

```sql
{%= md5("hello world") %}
```

「5eb63bbbe01eeed093cb22bb8f5acdc3」を返します。

+++

### notEqualTo {#notEqualTo}

文字列が指定の文字列に等しくないかどうかを判定するには、`notEqualTo` 関数を使用します。

+++構文

```sql
{%= notEqualTo(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物の名前が `John` でないかどうかを判定します。

```sql
{%= notEqualTo(profile.person.name,"John") %}
```

+++

### notEqualWithIgnoreCase {#not-equal-with-ignore-case}

`notEqualWithIgnoreCase` 関数を使用すると、大文字と小文字を区別せずに、2 つの文字列を比較できます。

+++構文

```sql
{= notEqualWithIgnoreCase(STRING_1,STRING_2) %}: boolean
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリでは、大文字と小文字を区別せずに、ユーザーの名前が `john` でないかどうかを判定します。

```sql
{%= notEqualTo(profile.person.name,"john") %}
```

+++

### regexGroup {#regexGroup}

`regexGroup` 関数を使用して、指定された正規表現に基づいて特定の情報を抽出します。

+++構文

```sql
{%= regexGroup(STRING, EXPRESSION, GROUP) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING}` | チェックの実行対象となる文字列です。 |
| `{EXPRESSION}` | 最初の文字列列と照合する正規表現です。 |
| `{GROUP}` | 照合する式のグループです。 |

**例**

次のクエリでは、メールアドレスからドメイン名を抽出します。

```sql
{%= regexGroup(emailAddress,"@(\\w+)", 1) %}
```

+++

### replace {#replace}

文字列内の特定の部分文字列を別の部分文字列で置き換えるには、`replace` 関数を使用します。

+++構文

```sql
{%= replace(STRING_1,STRING_2,STRING_3) %}:string
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | 部分文字列を置き換える必要がある文字列です。 |
| `{STRING_2}` | 置き換える部分文字列。 |
| `{STRING_3}` | 置換する部分文字列。 |

**例**

```sql
{%= replace("Hello John, here is your monthly newsletter!","John","Mark") %}
```

`Hello Mark, here is your monthly newsletter!` を返します。

+++

### replaceAll {#replaceAll}

`replaceAll` 関数を使用すると、正規表現式に一致するテキストのすべてのサブ文字列を、指定されたリテラル置換文字列に置き換えることができます。 正規表現には `\` と `+` の特別な処理があり、すべての正規表現はPQL エスケープ戦略に従います。 置換は、文字列の先頭から末尾に向かって行われます。例えば、文字列内の `aa` を `b` に置き換えると `aaa``ba` ではなく `ab` になります。

+++構文

```sql
{%= replaceAll(string,string,string) %}
```

>[!NOTE]
>
> 2 番目の引数として使用される式が特殊な正規表現文字である場合は、2 つのバックスラッシュ（`//`）を使用します。特殊な正規表現文字は次のとおりです：[.、+、*、?、^、$、(、)、[、]、{、}、|、\]
> 
> 詳しくは、[Oracle ドキュメント](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html){_blank}を参照してください。
>

+++

### rightTrim {#rightTrim}

`rightTrim` 関数は、文字列の末尾から空白を削除します。

+++構文

```sql
{%= rightTrim(string) %}
```

+++

### sha256 {#sha256}

`sha256` 関数は、文字列の sha256 ハッシュを計算して返します。

+++構文

```sql
{%= sha256(string) %} : string
```

**例**

```sql
{%= sha256("Eliechxh")%}
```

`0b0b207880b999adaad6231026abf87caa30760b6f326b21727b61139332257d` を返します。

+++

### split {#split}

文字列を特定の文字で分割するには、`split` 関数を使用します。

+++構文

```sql
{%= split(string,string) %}
```

+++

### startsWith {#startsWith}

`startsWith` 関数を使用すると、文字列が指定の部分文字列で始まるかどうかを判定できます。

+++構文

```sql
{%= startsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。デフォルトでは true に設定されています。 |

**例**

次のクエリでは、大文字と小文字を区別したうえで、人物の名前が `Joe` で始まるかどうかを判定します。

```sql
{%= startsWith(person.name,"Joe") %}
```

+++

### stringToDate {#string-to-date}

`stringToDate` 関数は、文字列値を日時値に変換します。 日時の文字列表現とフォーマッターの文字列表現の 2 つの引数を取ります。

+++構文

```sql
{= stringToDate("date-time value","formatter" %}
```

**例**

```sql
{= stringToDate("2023-01-10 23:13:26", "yyyy-MM-dd HH:mm:ss") %}
```

+++

### string_to_integer {#string-to-integer}

文字列値を整数値に変換するには、`string_to_integer` 関数を使用します。

+++構文

```sql
{= string_to_integer(string) %}: int
```

+++

### stringToNumber {#string-to-number}

文字列を数値に変換するには、`stringToNumber` 関数を使用します。 無効な入力の出力と同じ文字列を返します。

+++構文

```sql
{%= stringToNumber(string) %}: double
```

+++

### substr {#sub-string}

開始インデックスと終了インデックスの間の文字列式の部分文字列を返すには、`substr` 関数を使用します。

+++構文

```sql
{= substr(string, integer, integer) %}: string
```

+++

### titleCase {#titleCase}

`titleCase` 関数を使用すると、文字列の各単語の最初の文字を大文字にすることができます。

+++構文

```sql
{%= titleCase(string) %}
```

**例**

人物が Washington high street に住んでいる場合、この関数は `Washington High Street` を返します。

```sql
{%= titleCase(profile.person.location.Street) %}
```

+++

### toBool {#to-bool}

`toBool` 関数を使用して、引数の値を、型に応じてブール値に変換します。

+++構文

```sql
{= toBool(string) %}: boolean
```

+++

### toDateTime {#to-date-time}

`toDateTime` 関数を使用して、文字列を日付に変換します。 無効な入力に対する出力として、エポック日付を返します。

+++構文

```sql
{%= toDateTime(string, string) %}: date-time
```

+++

### toDateTimeOnly {#to-date-time-only}

`toDateTimeOnly` 関数を使用して、引数の値を日時のみの値に変換します。 無効な入力に対する出力として、エポック日付を返します。この関数は、文字列、日付、長さおよび整数のフィールドタイプを受け入れます。

+++構文

```sql
{%= toDateTimeOnly(string/date/long/int) %}: date-time
```

+++

### trim {#trim}

`trim` 関数は、文字列の先頭と末尾にあるすべての空白を削除します。

+++構文

```sql
{%= trim(string) %}
```

+++

### uppercase {#upper}

`upperCase` 関数は、文字列を大文字に変換します。

+++構文

```sql
{%= upperCase(string) %}
```

**例**

この関数は、プロファイルの姓を大文字に変換します。

```sql
{%= upperCase(profile.person.name.lastName) %}
```

+++

### urlDecode {#url-decode}

`urlDecode` 関数を使用して、URL エンコードされた文字列をデコードします。

+++構文

```sql
{%= urlDecode(string) %}: string
```

+++

### urlEncode {#url-encode}

`urlEncode` 関数を使用して、文字列を URL としてエンコードします。

+++構文

```sql
{%= urlEncode(string) %}: string
```

+++
