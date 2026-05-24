# PLSQL | ABS 功能

> 原文:[https://www.geeksforgeeks.org/plsql-abs-function/](https://www.geeksforgeeks.org/plsql-abs-function/)

PLSQL ABS 函数用于返回一个数字的绝对值。绝对值用于描述数字线上的数字与 0 之间的距离。不考虑数字从零开始的方向，因为数字的绝对值从来不是负数。

PLSQL 函数中的 ABS 将任何数字数据类型或任何可以隐式转换为数字数据类型的非数字数据类型作为参数。PLSQL ABS 函数返回的值的数据类型与参数的数值数据类型相同。

**语法:**

```sql
ABS( number )
```

**使用的参数:**

**数字–**用来指定你想知道其绝对值的数字。

**返回值:**
PLSQL 中的 ABS 函数返回一个数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 ABS 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number int := 20;

BEGIN 
   dbms_output.put_line(ABS(Test_Number)); 

END; 
```

**输出:**

```sql
20 
```

**示例-2:** 在 ABS 函数中使用负数值作为参数。

```sql
DECLARE 
   Test_Number int := -12;

BEGIN 
   dbms_output.put_line(ABS(Test_Number)); 

END; 
```

**输出:**

```sql
12 
```

**示例-3:** 在 ABS 函数中使用带小数的负数值作为参数。

```sql
DECLARE 
   Test_Number decimal(7, 2) := -12.23;

BEGIN 
   dbms_output.put_line(ABS(Test_Number)); 

END;  
```

**输出:**

```sql
12.23 
```

**示例-4:** 在 ABS 函数中使用表达式作为参数。

```sql
DECLARE 
   Test_Number decimal(11, 2) := (-20.45 * 2);

BEGIN 
   dbms_output.put_line(ABS(Test_Number)); 

END;   
```

**输出:**

```sql
40.9 
```

**示例-5:** 使用带选择查询的 ABS 功能。

```sql
SELECT ABS(-20.45 * 1) FROM dual; 
```

**输出:**

```sql
20.45 
```

**优点:**
ABS 函数接受任何数字数据类型以及任何非数字数据类型作为参数，可以隐式转换为数字数据类型。