# PLSQL | LAST_DAY 函数

> 原文:[https://www.geeksforgeeks.org/plsql-last_day-function/](https://www.geeksforgeeks.org/plsql-last_day-function/)

**PLSQL LAST_DAY 函数**用于根据日期值返回一个月的最后一天。一个月的最后一天由会话参数 NLS_CALENDAR 定义。

LAST_DAY 函数接受一个参数，即用于计算一个月最后一天的日期值。函数的作用是:不管日期的数据类型是什么，都返回一个日期数据类型的值。

**语法:**

```sql
LAST_DAY(date)
```

**使用的参数:**

**日期–**用于指定计算一个月最后一天的日期值。

**返回值:**
PLSQL 中的 LAST_DAY 函数返回一个 DATE 类型的值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 获取当月的最后一天。

```sql
SELECT
  LAST_DAY(SYSDATE)
FROM
  dual; 
```

**输出:**

```sql
31.10.19 
```

**示例-2:** 获取特定月份的最后一天。

```sql
SELECT
 LAST_DAY(TO_DATE('2003/02/12', 'yyyy/mm/dd'))
FROM
  dual; 
```

**输出:**

```sql
Feb 28, 2003 
```

**例-3:** 返回当月剩余天数。

```sql
SELECT
  LAST_DAY( SYSDATE ) - SYSDATE
FROM
  dual; 
```

**输出:**

```sql
2 
```

撰写文章时，系统将 2019 年 10 月 29 日视为当前日期。它可能因用户而异。

**例-4:** 返回上月最后一天。

```sql
SELECT
   LAST_DAY(ADD_MONTHS(SYSDATE, -1 ))
FROM
  dual; 
```

**输出:**

```sql
30.09.19 
```

撰写文章时，系统将 2019 年 10 月 29 日视为当前日期。它可能因用户而异。

**例-5:** 返回下个月的最后一天。

```sql
SELECT
   LAST_DAY(ADD_MONTHS(SYSDATE, 1 ))
FROM
  dual; 
```

**输出:**

```sql
30.11.19 
```

撰写文章时，系统将 2019 年 10 月 29 日视为当前日期。它可能因用户而异。