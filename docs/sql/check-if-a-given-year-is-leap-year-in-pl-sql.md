# 检查 PL/SQL 中给定的年份是否为闰年

> 原文:[https://www . geesforgeks . org/check-if-a-year-in-pl-SQL/](https://www.geeksforgeeks.org/check-if-a-given-year-is-leap-year-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一年，任务是检查给定的一年是否是[闰年](https://www.geeksforgeeks.org/program-check-given-year-leap-year/)。

示例:

```sql
Input: 1500
Output: 1500 is not leap year.

Input: 1600
Output: 1600 is a leap year

```

如果满足以下条件，一年就是闰年:
1)年是 400 的倍数
2)年是 4 的倍数而不是 100 的倍数

```sql
-- To check if a
-- given year is leap year or not
DECLARE
  year NUMBER := 1600;
BEGIN
  --  true if the year is a multiple
  -- of 4 and not multiple of 100.
  -- OR year is multiple of 400.
  IF MOD(year, 4)=0
    AND
    MOD(year, 100)!=0
    OR
    MOD(year, 400)=0 THEN
    dbms_output.Put_line(year
    || ' is a leap year ');
  ELSE
    dbms_output.Put_line(year
    || ' is not a leap year.');
  END IF;
END; 
```

输出:

```sql
1600 is a leap year.

```