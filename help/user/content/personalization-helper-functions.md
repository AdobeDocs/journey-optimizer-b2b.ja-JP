---
title: ヘルパー関数
description: Journey Optimizer B2B editionのパーソナライゼーションヘルパー関数のリファレンスガイド。 文字列、日付、計算などの構文と例が含まれています。
feature: Personalization, Content Design Tools
topic: Personalization
role: Developer
level: Intermediate
keywords: 式, エディター, 構文, パーソナライゼーション
exl-id: 04f78cdc-af2a-46ad-967d-2e129bd98e06
source-git-commit: 944d2616fa21e7f8d2f8c439eaa2f5e529dacb84
workflow-type: tm+mt
source-wordcount: '4930'
ht-degree: 48%

---

# ヘルパー関数

パーソナライゼーションエディター内のヘルパー関数を使用して、データの操作、計算の実行、コンテンツのフォーマットなどをおこない、パーソナライズされたコンテンツエクスペリエンスを正確かつ効率的に定義します。 これらの機能、オペレーター、ヘルパーがどのように連携するかを探索して実験し、カスタマイズされたデータドリブン型のジャーニーを構築するのに役立つかをご確認ください。

## 集計関数

集計関数を使用して複数の値をグループ化し、単一の概要値を形成します。 また、配列関数とリスト関数を使用して、配列、リスト、文字列の操作を簡単に定義することもできます。

### 平均 {#average}

`average`関数を使用して、配列内で選択したすべての値の算術平均を返します。

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

指定された配列内の要素の数を返すには、`count`関数を使用します。

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

`max`関数を使用して、配列内で選択したすべての値の中で最大の値を返します。

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

`min`関数を使用して、配列内で選択したすべての値の最小値を返します。

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

`sum`関数を使用して、配列内で選択したすべての値の合計を返します。

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

算術関数を使用して、値に関する基本的な計算を実行します。

### 追加 {#add}

`+` （加算）関数を使用して、2つの引数式の合計を検索します。

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

### 乗算 {#multiply}

`*` （乗算）関数を使用して、2つの引数式の積を検索します。

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

`-` （減算）関数を使用して、2つの引数式の違いを見つけます。

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

### 分割 {#divide}

`/` （除算）関数を使用して、2つの引数式の商を検索します。

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

### 残り {#remainder}

`%` （remainder）関数を使用して、2つの引数式を分割した後の残りを検索します。

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

`countOnlyNull`関数を使用して、リスト内のnull値の数をカウントします。

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

`countWithNull`関数を使用して、null値を含むリストのすべての要素をカウントします。

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

`distinct`関数を使用して、重複する値を削除した配列またはリストから値を取得します。

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

リスト内の異なる値の数をnull値を含めてカウントするには、`distinctCountWithNull`関数を使用します。

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

### head {#head}

`head`関数を使用して、配列またはリストの最初の項目を返します。

+++構文

```sql
{%= head(array) %}
```

**例**

次の操作は、最も金額が高い注文の上位 5 件のうち最初の項目を返します。 `topN` 関数の詳細については、[配列の最初の `n`](#first-n)の節を参照してください 。

```sql
{%= head(topN(orders,price, 5)) %}
```

+++

### topN {#first-n}

`topN` 関数は、指定した数値式に基づいて配列を降順に並べ替えて、最初の `N` 個の項目を返します。 配列のサイズが `N` 個未満の場合は、並べ替えられた配列全体を返します。

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

項目が配列またはリストのメンバーであるかどうかを判断するには、`in`関数を使用します。

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

### 含む {#includes}

`includes`関数を使用して、配列またはリストに特定の項目が含まれているかどうかを判断します。

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

### 積集合 {#intersects}

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

<!--

## Intersection{#intersection}

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

`bottomN` 関数は、指定した数値式に基づいて配列を昇順に並べ替えて、最初の `N` 個の項目を返します。 配列のサイズが `N` 個未満の場合は、並べ替えられた配列全体を返します。

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

項目が配列またはリストのメンバーでないかどうかを判断するには、`notIn`関数を使用します。

>[!NOTE]
>
>この`notIn` 関数は&#x200B;*また*、どの値も NULL ではないことを保証します。 したがって、結果は `in` 関数の完全な否定ではありません。

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

`subsetOf`関数を使用して、特定の配列（配列A）が別の配列（配列B）のサブセットであるかどうかを判断します。 つまり、配列 A 内のすべての要素が配列 B の要素であるということです。

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

`supersetOf`関数を使用して、特定の配列（配列A）が別の配列（配列B）のスーパーセットであるかどうかを判断します。 つまり、その配列 Aには配列 B のすべての要素が含まれます。

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

日付と時刻の関数を使用して、値に対して日付と時刻の操作を実行します。

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

### addYears {#add-years}

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

`age`関数を使用して、特定の日付から年齢を取得します。

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

### ageInDays {#age-days}

`ageInDays`関数は、指定された日付から現在の日付までの経過日数を計算します。 将来の日付にはマイナスを使用し、過去の日付にはプラスを使用します。

+++構文

```sql
{%= ageInDays(date) %}
```

**例**

currentDate = 2025-01-07T12:17:10.720122+05:30（アジア／コルカタ）

* 入力：`{%= ageInDays(stringToDate("2025-01-01T17:19:51Z"))%}`
* 出力：`5`

+++

### ageInMonths {#age-months}

`ageInMonths`関数は、指定された日付から現在の日付までの経過月数を計算します。 将来の日付にはマイナスを使用し、過去の日付にはプラスを使用します。

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

`compareDates` 関数は、最初の入力日付を他の入力日付と比較します。 date1がdate2と等しい場合は0を返し、date1がdate2より前の場合は–1、date1がdate2より後の場合は1を返します。

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

`currentTimeInMillis`関数を使用して、現在の時間をエポックミリ秒単位で取得します。

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

`dateDiff`関数を使用して、2つの日付間の日数の差を取得します。

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

### DayOfWeek {#day-week}

`dayOfWeek`関数を使用して、曜日を取得します。

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

### dayOfYear {#day-year}

`dayOfYear`関数を使用して、年の日付を取得します。

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

`formatDate`関数を使用して、日付時刻の値を書式設定します。 形式は、有効なJava `DateTimeFormat` パターンである必要があります。

+++構文

```sql
{%= formatDate(datetime, format) %}
```

ここで、最初の文字列は日付属性で、2番目の値は日付の変換方法と表示方法です。

>[!NOTE]
>
> 日付パターンが無効な場合、日付はISO標準形式にフォールバックします。
>
> [Oracle ドキュメント](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html){_blank}にまとめられている Java 日付書式設定関数を使用できます。

**例**

次の操作は、MM/DD/YYの形式で日付を返します。

```sql
{%= formatDate(profile.timeSeriesEvents._mobile.hotelBookingDetails.bookingDate, "MM/dd/YY") %}
```

+++

#### パターン文字 {#pattern-characters}

一部のパターン文字は似ているかもしれませんが、異なる概念を表しています。

| パターン | 意味 | 例（`2023-12-31T10:15:30Z` の場合） |
|---------|---------|--------------------------------------|
| `y` | 暦年（標準年） | `2023` |
| `Y` | 週ベースの年（ISO 8601）。 年の境界によって異なる場合があります。 | `2024` （2023年12月31日、2024年の最初の週の秋） |
| `M` | 年間通算月（1～12 または `Jan`、`January` のようなテキスト） | `12` または `Dec` |
| `m` | 分（時間）（0～59） | `15` |
| `d` | 月間通算日（1～31） | `31` |
| `D` | 年間通算日（1～366） | `365` |

#### 日付をロケールサポートの形式にします {#format-date-locale}

`formatDate`関数を使用して、日付時刻の値を、目的のロケールなど、対応する言語に依存する表現に書式設定できます。 形式は、有効なJava `DateTimeFormat` パターンである必要があります。

+++構文

```sql
{%= formatDate(datetime, format, locale) %}
```

最初の文字列が日付属性で、2番目の値が日付の変換方法と表示方法で、3番目の値が文字列形式のロケールを表します。

>[!NOTE]
>
> 日付パターンが無効な場合、日付はISO標準形式にフォールバックします。
>
> [Oracle ドキュメント ](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html)に要約されているJava日付書式設定関数を使用できます。
>
> 書式設定と有効なロケールは、[Oracle ドキュメント ](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html)および[ サポートされているロケール ](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html)に要約されて使用できます。

**例**

次の操作は、MM/dd/YYおよびロケール FRANCEの形式で日付を返します。

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

### diffInHours {#hours-difference}

`diffInHours` 関数は、時間数単位で 2 つの日付間の差異を返します。

+++構文

```sql
{%= diffInHours(endDate, startDate) %}
```

**例**

* 入力：`{%= diffInHours(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2024-11-01T07:19:51Z"))%}`
* 出力：`10`

+++

### diffInMinutes {#diff-minutes}

`diffInMinutes`関数は、2つの日付の差を分単位で返します。

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

`setDays`関数を使用して、指定された日時の月の日を設定します。

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

`setHours`関数を使用して、日時の時間を設定します。

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

`toDateTime` 関数は、文字列を日付に変換します。 無効な入力に対する出力として、エポック日付を返します。

+++構文

```sql
{%= toDateTime(string, string) %}
```

**例**

* 入力：`{%=toDateTime("2024-11-01T17:19:51Z")%}`
* 出力：`2024-11-01T17:19:51Z`

+++

### toUTC {#to-utc}

`toUTC`関数を使用して、日時をUTCに変換します。

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

`truncateToStartOfDay`関数を使用して、時刻が00:00の日の先頭に設定することで、指定された日時を変更します。

+++構文

```sql
{%= truncateToStartOfDay(date) %}
```

**例**

* 入力：`{%= truncateToStartOfDay(stringToDate("2024-11-01T17:19:51Z")) %}`
* 出力：`2024-11-01T00:00Z`

+++

### truncateToStartOfQuarter {#truncate-quarter}

`truncateToStartOfQuarter`関数を使用すると、00:00の時点で日時を四半期の最初の日（1月1日、4月1日、7月1日、10月1日など）に切り捨てることができます。

+++構文

```sql
{%= truncateToStartOfQuarter(dateTime) %}
```

**例**

* 入力：`{%=truncateToStartOfQuarter(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`2024-10-01T00:00Z`

+++

### truncateToStartOfWeek {#truncate-week}

`truncateToStartOfWeek`関数は、指定された日時を週の先頭（月曜日の00:00）に設定して変更します。

+++構文

```sql
{%= truncateToStartOfWeek(dateTime) %}
```

**例**

* 入力：`{%= truncateToStartOfWeek(stringToDate("2024-11-19T17:19:51Z"))%} // tuesday`
* 出力：`2024-11-18T00:00Z // monday`

+++

### truncateToStartOfYear {#truncate-year}

`truncateToStartOfYear`関数を使用して、指定された日時を00:00の年の最初の日（1月1日）に切り捨てて変更します。

+++構文

```sql
{%= truncateToStartOfYear(dateTime) %}
```

**例**

* 入力：`{%=truncateToStartOfYear(stringToDate("2024-11-01T17:19:51Z"))%}`
* 出力：`2024-01-01T00:00Z`

+++

### weekOfYear {#week-of-year}

`weekOfYear`関数を使用して、年の週を取得します。

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

`diffInYears`関数を使用して、2つの日付の差を年で返します。

+++構文

```sql
{%= diffInYears(endDate, startDate) %}: int
```

**例**

* 入力：`{%=diffInYears(stringToDate("2024-11-01T17:19:51Z"), stringToDate("2019-10-01T17:19:51Z"))%}`
* 出力：`5`

+++

## 演算子関数 {#operators}

論理評価を実行するには、ブール関数と比較関数を使用します。

### and {#and}

`and` 関数は、論理積を作成するために使用されます。

+++構文

```sql
{%= query1 and query2 %}
```

**例**

次の操作は、母国（フランス）と出生年（1985年）のすべての人を返します。

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

次の操作は、母国（フランス）または出生年（1985年）のすべての人を返します。

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

### 等しくない {#notequal}

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

`>` （より大きい）関数を使用して、最初の値が2番目の値よりも大きいかどうかを確認します。

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

### 以上 {#greaterthanorequal}

`>=` （以上）関数を使用して、最初の値が2番目の値以上かどうかを確認します。

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

`<` （より小さい）比較関数を使用して、最初の値が2番目の値より小さいかどうかを確認します。

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

### 次より小さい値{#lessthanorequal}

`<=` （以下）比較関数を使用して、最初の値が2番目の値以下かどうかを確認します。

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

動的ヘルパー関数を使用して、条件評価、反復、変数の割り当てを使用して動的パーソナライゼーションを実行します。

### デフォルトのフォールバック値 {#default-value}

`Default Fallback Value` ヘルパーは、属性が空または null の場合にデフォルトのフォールバック値を返すために使用されます。 このメカニズムは、プロファイル属性とジャーニーイベントで機能します。

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
`elseif` ステートメントは、最初のステートメントがfalseを返すかどうかをテストするための新しい条件を指定します。


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

### を除く {#unless}

条件付きブロックを定義するには、`unless` ヘルパーを使用します。 `if` ヘルパーとは異なり、式の評価結果が false の場合にブロックがレンダリングされます。

+++構文

```sql
{%#unless unlessCondition%} element_1 {%else%} default_element {%/unless%}
```

**例**

メールアドレスの拡張機能に基づいてコンテンツをレンダリングします。

```sql
{%#unless endsWith(account.accountOrganization.primaryEmailDomain}, ".edu")%}
Some Normal Content
{%else%}
Some edu specific content
{%/unless%}
```

+++

### 各 {#each}

`each` ヘルパーを使用して、配列を繰り返します。

ヘルパー構造は```{{#each ArrayName}}``` YourContent `{{/each}}`です

ブロック内のキーワード `this`を使用して、個々の配列項目を参照できます。 配列の要素のインデックスをレンダリングするには、`{{@index}}`を使用します。

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

`with` ヘルパーを使用して、template-partの評価トークンを変更します。

+++構文

```sql
{{#with profile.person.name}}
{{this.firstName}} {{this.lastName}}
{{/with}}
```

`with` ヘルパーは、ショートカット変数を定義する場合にも使用できます。

**例**

`with`を使用して、長い変数名を短い変数名にエイリアスします。

```sql
{{#with profile.person.name as |name|}}
 Hi {{name.firstName}} {{name.lastName}}!
 Checkout our trending products for today!
{{/with}}
```

+++

### レット {#let}

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
>この機能は、限定提供です。 アクセス権を取得するには、アドビ担当者にお問い合わせください。

`executionMetadata`を使用して、カスタム キーと値のペアを取得し、メッセージ実行コンテキストに動的に保存します。

この関数を使用すると、キャンペーンやジャーニーの任意のネイティブアクションにコンテキスト情報を追加できます。 トラッキング、分析、パーソナライゼーション、下流処理など、様々な目的でリアルタイム配信のコンテキストデータを外部システムに書き出すために使用できます。

>[!NOTE]
>
>カスタムアクションは`executionMetadata`関数をサポートしていません。

例えば、`executionMetadata` ヘルパーを使用して、各プロファイルに送信される各配信に特定のIDを追加できます。 この情報は実行時に生成され、強化された実行メタデータは外部レポートプラットフォームとのダウンストリームの紐付けのためにエクスポートできます。

+++構文

```
{{executionMetadata key="your_key" value="your_value"}}
```

この構文では、`key` はメタデータ名を参照し、`value` は保持するメタデータです。

**仕組み**

キャンペーンまたはジャーニー内のチャネルコンテンツから任意の要素を選択し、パーソナライゼーションエディターを使用して、この要素に `executionMetadata` ヘルパーを追加します。

>[!NOTE]
>
>コンテンツ自体が表示されている場合、`executionMetadata`関数は表示されません。

実行時に、メタデータ値が既存の&#x200B;**[!UICONTROL メッセージフィードバックイベントデータセット]**&#x200B;に追加され、次のスキーマが追加されます。

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
>アクションごとのキーと値のペアには 2 kb の上限があります。 2Kb の制限を超えた場合、メッセージは引き続き配信されますが、キーと値のペアのいずれかが切り捨てられる場合があります。

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

パーソナライゼーションでマップ関数を使用すると、マップとのインタラクションが容易になります。

### get {#get}

指定されたキーのマップの値を取得するには、`get`関数を使用します。

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

`keys`関数を使用して、特定のマップのすべてのキーを取得します。

+++構文

```sql
{%= keys(map) %}
```

**例**

次の操作は、マップ `identityMap`のすべてのキーを取得します。

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

次の操作は、マップ `identityMap`のすべての値を取得します。

```sql
{%= values(identityMap) %}
```

+++

## 数学関数 {#math}

パーソナライゼーションエディターで数学関数を使用する方法を説明します。

### 絶対 {#absolute}

`absolute`関数を使用して、数値を絶対値に変換します。

+++構文

```sql
{%= absolute(int) %}: int
```

+++

### formatNumber {#format-number}

`formatNumber`関数を使用して、任意の数値を言語依存の表現に書式設定します。

ロケールを表す数値および文字列を受け入れて、目的のロケールで書式設定された数値の文字列を返します。

+++構文

```sql
{%= formatNumber(number/double,string) %}: string
```

書式設定と有効なロケールは、[Oracle ドキュメント ](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html)および[ サポートされているロケール ](https://www.oracle.com/java/technologies/javase/jdk11-suported-locales.html){_blank}に要約されて使用できます

**例**

このクエリは、入力番号として123456.789に対応するアラビア語の書式設定された文字列を返します。

```sql
{%= formatNumber(123456.789, "ar_EG") %}
```

+++

### random {#random}

`random`関数を使用して、0 ～ 1のランダムな値を返します。

+++構文

```sql
{%= random() %}: double
```

+++

### roundDown {#round-down}

`roundDown`関数を使用して数値を切り捨てます。

+++構文

```sql
{%= roundDown(double) %}: double
```

+++

### roundUp {#round-up}

`roundUp`関数を使用して数値を切り上げます。

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

このクエリは、158の16進数値を9eとして返します。

```sql
{%= toHexString(158) %}
```

+++

### toInt {#to-int}

`toInt`関数を使用して、型（数値、double、整数、long、float、short、byte、boolean、string）を整数に変換します。

+++構文

```sql
{%= toInt(<valueToConvert>) %}: integer
```

**例**

このクエリは、42.6の整数値を42として返します。

```sql
{%= toInt(42.6) %}: integer
```

+++

### toPercentage {#to-percentage}

`toPercentage`関数を使用して、数値をパーセンテージに変換します。

+++構文

```sql
{%= toPercentage(double) %}: string
```

+++

### toPrecision {#to-precision}

`toPrecision`関数を使用して、数値を必要な精度に変換します。

+++構文

```sql
{%= toPrecision(double,int) %}: string
```

+++

### toString {#to-string}

`toString`関数は、任意の数値を文字列表現に変換します。

+++構文

```sql
{%= toString(string) %}: string
```

**例**

このクエリは`"12"`を返します。

```sql
{%= toString(12) %} 
```

+++

## オブジェクト関数 {#objects}

オブジェクト関数を使用して、オブジェクトのプロパティまたは属性をクエリします。

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

`charCodeAt`関数は、JavaScriptの`charCodeAt`関数のように、文字のASCII値を返します。 文字列と整数（文字の位置を定義）を入力引数として受け取り、対応するASCII値を返します。

+++構文

```sql
{%= charCodeAt(string,int) %}: int
```

**例**

次の関数は、`o` （111）のASCII値を返します。

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

次の関数は、プロファイルの市区町村と国を1つの文字列に組み合わせます。

```sql
{%= concat(profile.homeAddress.city,profile.homeAddress.country) %}
```

+++

### 指定の語を含む {#contains}

文字列に指定された部分文字列が含まれているかどうかを判断するには、`contains`関数を使用します。

+++構文

```sql
{%= contains(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `STRING_1` | チェックの実行対象となる文字列です。 |
| `STRING_2` | 最初の文字列内で検索する文字列です。 |
| `CASE_SENSITIVE` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。 使用可能な値：true（デフォルト）または false。 |

**例**

* 次の関数は、プロファイル名に大文字または小文字のAが含まれているかどうかを確認します。 プロファイルが有効な場合は、`true`が返されます。 そうでない場合は、`false`が返されます。

  ```sql
  {%= contains(profile.person.name.firstName, "A", false) %}
  ```

* 次のクエリでは、大文字と小文字を区別して、ユーザーの電子メールアドレスに文字列`2010@gm`が含まれているかどうかを判断します。

  ```sql
  {%= contains(profile.person.emailAddress,"2010@gm") %}
  ```

+++

### doesNotContain {#doesNotContain}

文字列に指定された部分文字列が含まれていないかどうかを判断するには、`doesNotContain`関数を使用します。

+++構文

```sql
{%= doesNotContain(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `STRING_1` | チェックの実行対象となる文字列です。 |
| `STRING_2` | 最初の文字列内で検索する文字列です。 |
| `CASE_SENSITIVE` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。 使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別して、ユーザーの電子メールアドレスに文字列`2010@gm`が含まれていないかどうかを判断します。

```sql
{%= doesNotContain(profile.person.emailAddress,"2010@gm")%}
```

+++

### doesNotEndWith {#doesNotEndWith}

文字列が指定された部分文字列で終わらないかどうかを判断するには、`doesNotEndWith`関数を使用します。

+++構文

```sql
{%= doesNotEndWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。 使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別して、ユーザーの電子メールアドレスが`.com`で終わらないかどうかを判断します。

```sql
doesNotEndWith(person.emailAddress,".com")
```

+++

### doesNotStartWith {#doesNotStartWith}

文字列が指定された部分文字列で始まらないかどうかを判断するには、`doesNotStartWith`関数を使用します。

+++構文

```sql
{%= doesNotStartWith(STRING_1, STRING_2, CASE_SENSITIVE)%}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。 使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別して、ユーザーの名前が`Joe`で始まらない場合を判断します。

```sql
{%= doesNotStartWith(person.name,"Joe")%}
```

+++

### encode64 {#encode64}

`encode64`関数を使用して、URLに含めるなど、個人情報（PI）を保存する文字列をエンコードします。

+++構文

```sql
{%= encode64(string) %}
```

+++

### endsWith {#endsWith}

文字列が指定された部分文字列で終わるかどうかを判断するには、`endsWith`関数を使用します。

+++構文

```sql
{%= endsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。 使用可能な値：true（デフォルト）または false。 |

**例**

次のクエリでは、大文字と小文字を区別して、ユーザーの電子メールアドレスが`.com`で終わるかどうかを判断します。

```sql
{%= endsWith(person.emailAddress,".com") %}
```

+++

### 等しい {#equals}

`equals`関数を使用して、文字列が指定された文字列と等しいかどうかを判断します。大文字と小文字を区別します。

+++構文

```sql
{%= equals(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリは、大文字と小文字を区別して、ユーザーの名前が`John`かどうかを判断します。

```sql
{%=equals(profile.person.name,"John") %}
```

+++

### equalsIgnoreCase {#equalsIgnoreCase}

`equalsIgnoreCase`関数を使用して、文字列が大文字と小文字を区別せずに、指定された文字列と等しいかどうかを判断します。

+++構文

```sql
{%= equalsIgnoreCase(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリは、大文字と小文字を区別せずに、ユーザーの名前が`John`かどうかを判断します。

```sql
{%= equalsIgnoreCase(profile.person.name,"John") %}
```

+++

### extractEmailDomain {#extractEmailDomain}

`extractEmailDomain`関数を使用して、電子メールアドレスのドメインを抽出します。

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

`formatCurrency`関数を使用して、任意の数値を、2番目の引数で文字列として渡されたロケールに応じて、対応する言語に依存する通貨表現に変換します。

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

`getUrlHost`関数を使用して、URLのホスト名を取得します。

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

`getUrlPath`関数を使用して、URLのドメイン名の後のパスを取得します。

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

`getUrlProtocol`関数を使用して、URLのプロトコルを取得します。

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

`indexOf`関数を使用して、2番目のパラメーターの最初の出現の位置（最初の引数）を返します。 一致するものがない場合は「-1」を返します。

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

文字列が空かどうかを判断するには、`isEmpty`関数を使用します。

+++構文

```sql
{%= isEmpty(string) %}
```

**例**

次の関数は、プロファイルの携帯電話番号が空の場合、「true」を返します。 それ以外の場合は、`false`が返されます。

```sql
{%= isEmpty(profile.mobilePhone.number) %}
```

+++

### isNotEmpty {#is-not-empty}

文字列が空でないかどうかを判断するには、`isNotEmpty`関数を使用します。

+++構文

```sql
{= isNotEmpty(string) %}: boolean
```

**例**

次の関数は、プロファイルの携帯電話番号が空の場合、「true」を返します。 それ以外の場合は、`false`が返されます。

```sql
{%= isNotEmpty(profile.mobilePhone.number) %}
```

+++

### lastIndexOf {#last-index-of}

`lastIndexOf`関数を使用して、2番目のパラメーターの最後の出現の位置（最初の引数）を返します。 一致するものがない場合は「-1」を返します。

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

文字列の先頭から空白を削除するには、`leftTrim`関数を使用します。

+++構文

```sql
{%= leftTrim(string) %}
```

+++

### length {#length}

`length`関数を使用して、文字列または式の文字数を取得します。

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

### いいね！ {#like}

文字列が指定されたパターンと一致するかどうかを判断するには、`like`関数を使用します。

+++構文

```sql
{%= like(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列列と照合される式です。 式の作成に使用できる特殊文字として、`%` と `_` の 2 つがサポートされています。 <ul><li>`%` は、0 個以上の文字を表すために使用されます。</li><li>`_` は、1 文字を表すために使用されます。</li></ul> |

**例**

次のクエリは、パターン `es`を含むプロファイルが存在するすべての都市を取得します。

```sql
{%= like(profile.homeAddress.city, "%es%")%}
```

+++

### lowerCase {#lower}

`lowerCase`関数を使用して、文字列を小文字に変換します。

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

文字列が特定の正規表現に一致するかどうかを判断するには、`matches`関数を使用します。 正規表現でのパターンの一致について詳しくは、[Oracle ドキュメント ](https://docs.oracle.com/javase/8/docs/api/java/util/regex/Pattern.html)を参照してください。

+++構文

```sql
{%= matches(STRING_1, STRING_2) %}
```

**例**

次のクエリでは、大文字と小文字を区別せずに、ユーザーの名前が`John`で始まるかどうかを判断します。

```sql
{%= matches(person.name.,"(?i)^John") %}
```

+++

### マスク {#mask}

`mask`関数を使用して、文字列の一部を「X」文字に置き換えます。

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

`md5`関数を使用して、文字列のmd5 ハッシュを計算して返します。

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

文字列が指定された文字列と等しくないかどうかを判断するには、`notEqualTo`関数を使用します。

+++構文

```sql
{%= notEqualTo(STRING_1, STRING_2) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリは、大文字と小文字を区別して、ユーザーの名前が`John`でない場合を判断します。

```sql
{%= notEqualTo(profile.person.name,"John") %}
```

+++

### notEqualWithIgnoreCase {#not-equal-with-ignore-case}

大文字と小文字を区別せずに2つの文字列を比較するには、`notEqualWithIgnoreCase`関数を使用します。

+++構文

```sql
{= notEqualWithIgnoreCase(STRING_1,STRING_2) %}: boolean
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列と比較する文字列です。 |

**例**

次のクエリは、大文字と小文字を区別せずに、ユーザーの名前が`john`でないかどうかを判断します。

```sql
{%= notEqualTo(profile.person.name,"john") %}
```

+++

### regexGroup {#regexGroup}

指定された正規表現に基づいて、特定の情報を抽出するには、`regexGroup`関数を使用します。

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

次のクエリは、メールアドレスからドメイン名を抽出します。

```sql
{%= regexGroup(emailAddress,"@(\\w+)", 1) %}
```

+++

### replace {#replace}

`replace`関数を使用して、文字列内の特定の部分文字列を別の部分文字列に置き換えます。

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

`replaceAll`関数を使用して、正規表現式と一致するテキストのすべての部分文字列を、指定されたリテラル置換文字列に置き換えます。 Regexは`\`と`+`の特別な処理を行い、すべての正規表現はPQL エスケープ ストラテジーに従います。 文字列の先頭から末尾まで置換が行われます。例えば、文字列`aa`を文字列`aaa`の`b`に置き換えると、`ab`ではなく`ba`になります。

+++構文

```sql
{%= replaceAll(string,string,string) %}
```

>[!NOTE]
>
> 2 番目の引数として使用される式が特殊な正規表現文字である場合は、2 つのバックスラッシュ（`//`）を使用します。  特殊な正規表現文字は次のとおりです：[.、+、*、?、^、$、(、)、[、]、{、}、|、\]
> 
> 詳しくは、[Oracle ドキュメント](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html){_blank}を参照してください。
>

+++

### rightTrim {#rightTrim}

`rightTrim`関数は、文字列の末尾から空白を削除します。

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

`split`関数を使用して、文字列を特定の文字で分割します。

+++構文

```sql
{%= split(string,string) %}
```

+++

### startsWith {#startsWith}

文字列が指定された部分文字列で始まるかどうかを判断するには、`startsWith`関数を使用します。

+++構文

```sql
{%= startsWith(STRING_1, STRING_2, CASE_SENSITIVE) %}
```

| 引数 | 説明 |
| --------- | ----------- |
| `{STRING_1}` | チェックの実行対象となる文字列です。 |
| `{STRING_2}` | 最初の文字列内で検索する文字列です。 |
| `{CASE_SENSITIVE}` | チェックで大文字と小文字が区別されるかどうかを指定するオプションのパラメーターです。 デフォルトでは、trueに設定されています。 |

**例**

次のクエリでは、大文字と小文字を区別して、ユーザーの名前が`Joe`で始まるかどうかを判断します。

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

`string_to_integer`関数を使用して、文字列値を整数値に変換します。

+++構文

```sql
{= string_to_integer(string) %}: int
```

+++

### stringToNumber {#string-to-number}

文字列を数値に変換するには、`stringToNumber`関数を使用します。 無効な入力の出力と同じ文字列を返します。

+++構文

```sql
{%= stringToNumber(string) %}: double
```

+++

### substr {#sub-string}

`substr`関数を使用して、開始インデックスと終了インデックスの間の文字列式のサブ文字列を返します。

+++構文

```sql
{= substr(string, integer, integer) %}: string
```

+++

### titleCase {#titleCase}

`titleCase`関数を使用して、文字列の各単語の最初の文字を大文字にします。

+++構文

```sql
{%= titleCase(string) %}
```

**例**

この人物がワシントンのハイストリートに住んでいる場合、この関数は`Washington High Street`を返します。

```sql
{%= titleCase(profile.person.location.Street) %}
```

+++

### toBool {#to-bool}

引数の値を型に応じてブール値に変換するには、`toBool`関数を使用します。

+++構文

```sql
{= toBool(string) %}: boolean
```

+++

### toDateTime {#to-date-time}

文字列を日付に変換するには、`toDateTime`関数を使用します。 無効な入力に対する出力として、エポック日付を返します。

+++構文

```sql
{%= toDateTime(string, string) %}: date-time
```

+++

### toDateTimeOnly {#to-date-time-only}

`toDateTimeOnly`関数を使用して、引数の値を日付時間のみの値に変換します。 無効な入力に対する出力として、エポック日付を返します。 この関数は、文字列、日付、長さ、整数のフィールドタイプを受け入れます。

+++構文

```sql
{%= toDateTimeOnly(string/date/long/int) %}: date-time
```

+++

### trim {#trim}

`trim`関数は、文字列の先頭と末尾にあるすべての空白を削除します。

+++構文

```sql
{%= trim(string) %}
```

+++

### upperCase {#upper}

`upperCase`関数は、文字列を大文字に変換します。

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

`urlDecode`関数を使用して、URL エンコードされた文字列をデコードします。

+++構文

```sql
{%= urlDecode(string) %}: string
```

+++

### urlEncode {#url-encode}

文字列をURLとしてエンコードするには、`urlEncode`関数を使用します。

+++構文

```sql
{%= urlEncode(string) %}: string
```

+++
