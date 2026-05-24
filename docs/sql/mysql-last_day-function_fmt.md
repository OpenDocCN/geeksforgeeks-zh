# MySQL | LAST_DAY()函数

> 原文:[https://www.geeksforgeeks.org/mysql-last_day-function/](https://www.geeksforgeeks.org/mysql-last_day-function/)

MySQL 中的 `LAST_DAY()`函数可以用来知道给定日期或日期时间的一个月的最后一天。`LAST_DAY()`函数以`日期`值为参数，返回该`日期`中的最后一天。`日期`参数表示有效的日期或日期时间。

## 语法

```sql
LAST_DAY( Date );
```

如果日期或日期时间值无效，函数将返回空值。

## 参数

`日期`：`LAST_DAY()`函数采用单个参数 `Date`。它是要提取该月最后一天的日期或日期时间值。

## 返回值

`LAST_DAY()`函数为有效的`日期`参数返回一个月的最后一天。如果参数`日期`无效或为空，则函数也将返回空。

以下是 `LAST_DAY()`函数的一些常见示例或用法：

### 示例1: 从给定日期提取最后一天

要了解2017年12月的最后一天，可以按以下方式执行 `LAST_DAY()`函数：

**语法：**

```sql
SELECT LAST_DAY('2017-12-01') AS LastDay;
```

**输出：**

```sql
'2017-12-31'
```

### 示例2: 从给定的日期时间提取最后一天

要使用日期时间格式了解2017年12月的最后一天，可以按以下方式执行 `LAST_DAY()`函数：

**语法：**

```sql
SELECT LAST_DAY('2017-12-01 10:10:10') AS LastDay;
```

**输出：**

```sql
'2017-12-31'
```

### 示例3: 检查是否为闰年

要知道某年是否为闰年，我们可以使用 `LAST_DAY()`函数来检查该年二月份的最后一天。如果是29号，则该年是闰年，否则不是。

**语法：**

```sql
SELECT LAST_DAY('2016-02-01') AS LastDay;
```

**输出：**

```sql
'2016-02-29'
```

### 示例4: 提取当前月份的最后一天

要知道当前月份的最后一天，`LAST_DAY()`函数可以与 `NOW()`或 `CURDATE()`函数结合使用。

**使用 `NOW()`函数**：`NOW()`函数在MySQL中返回当前日期时间戳。

**语法：**

```sql
SELECT LAST_DAY(NOW()) AS LastDay;
```

**输出：**

```sql
'2017-12-31'
```

### 示例5: 使用 `CURDATE()`函数

`CURDATE()`函数在MySQL中以日期格式返回当前日期。

**语法：**

```sql
SELECT LAST_DAY(CURDATE()) AS LastDay;
```

**输出：**

```sql
'2017-12-31'
```

### 示例6: 提取次月最后一天

要知道次月最后一天，可以通过以下方式执行 `LAST_DAY()`函数：

**语法：**

```sql
SELECT LAST_DAY('2017-12-01') + INTERVAL 1 MONTH AS LastDay;
```

**输出：**

```sql
'2018-01-31'
```