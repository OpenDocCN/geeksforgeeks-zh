# MS 接入中的年()函数

> 原文:[https://www.geeksforgeeks.org/year-function-in-ms-access/](https://www.geeksforgeeks.org/year-function-in-ms-access/)

**Year():**Microsoft Access 中的函数用于返回给定日期的年份部分。

**语法:**

```sql
Year (date)
```

**参数:**此方法接受一个参数，如上所述，如下所述:

*   **Date:** It is any variable, numerical expression, string expression or any combination thereof that can represent a date.

**返回:**返回指定日期的年份部分。如果日期包含空值，则返回空值。

**示例-1 :** 从指定日期开始查找年份:

```sql
SELECT Year(#05/17/2017#);

```

**输出:**

```sql
2017 

```

**示例-2 :** 查找今天的年份部分:

```sql
SELECT Year(Date());

```

**输出:**

```sql
2020

```

**示例-3 :** 查找员工入职年份:

```sql
SELECT Year(JoiningDate) FROM Employees;

```

**输出:**

```sql
1990
2004
1992

```

**注意:**员工数据库中应有“加入日期”列。这里，雇员数据库只包含 3 条记录。