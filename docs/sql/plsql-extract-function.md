# PLSQL | EXTRACT 函数

> 原文:[https://www.geeksforgeeks.org/plsql-extract-function/](https://www.geeksforgeeks.org/plsql-extract-function/)

**PLSQL EXTRACT 函数**用于从日期或区间值中提取年、月、日或小时等特定值。

**语法:**

```sql
EXTRACT(field FROM source)
```

**使用的参数:**
EXTRACT 函数接受两个参数:

*   **字段–**用于指定需要提取的组件。
*   **source–**用于指定从中提取字段的日期、间隔或时间戳值。

可以从各种值类型中提取的字段有:

*   **日期:**年、月、日。
*   **间隔年至月:**年和月
*   **间隔日至秒:**日、时、分、秒。
*   **时间戳:**年、月、日、时、分、秒

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 从日期值中提取年份字段的值。

```sql
SELECT
  EXTRACT(YEAR FROM DATE '2019-10-26')
FROM
  DUAL; 
```

**输出:**

```sql
2019 
```

**示例-2:** 从日期值中提取月份字段的值。

```sql
SELECT
  EXTRACT(YEAR FROM DATE '2019-10-26')
FROM
  DUAL; 
```

**输出:**

```sql
10 
```

**示例-3:** 从日期值中提取日字段的值。

```sql
SELECT
  EXTRACT(YEAR FROM DATE '2019-10-26')
FROM
  DUAL; 
```

**输出:**

```sql
26 
```

**示例-4:** 从间隔年到月提取年字段的值。

```sql
SELECT
  EXTRACT( YEAR FROM INTERVAL '7-3' YEAR TO MONTH )
FROM
  DUAL; 
```

**输出:**

```sql
7 
```

在上面的例子中，提到的参数‘7-3’表示 7 年零 3 个月。

**示例-5:** 从间隔日到秒提取日字段的值。

```sql
SELECT
  EXTRACT( DAY FROM INTERVAL '26 10:32:29.53' DAY TO SECOND )
FROM
  dual; 
```

**输出:**

```sql
26 
```

在上面的例子中，提到的参数‘26 10:32:29.53’表示 26 天 10 小时 32 分 29 秒。

**示例-6:** 从时间戳中提取年份字段的值。

```sql
SELECT
  EXTRACT( YEAR FROM TIMESTAMP '2019-10-26 12:57:34.10' )
FROM
  dual; 
```

**输出:**

```sql
2019 
```