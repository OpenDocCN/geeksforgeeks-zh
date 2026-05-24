# PLSQL | SINH 函数

> 原文:[https://www.geeksforgeeks.org/plsql-sinh-function/](https://www.geeksforgeeks.org/plsql-sinh-function/)

PLSQL SINH 函数用于返回数值的双曲正弦值。SINH 函数接受一个参数，即需要计算其双曲正弦值的数字。SINH 函数返回数值数据类型的值。

此函数将任何数字数据类型以及可以隐式转换为数字数据类型的任何非数字数据类型作为参数。如果在任何情况下，参数都是 BINARY_FLOAT，那么 SINH 函数返回 BINARY_DOUBLE。

**语法:**

```sql
SINH(number)
```

**参数使用:**
**数字–**用于指定需要计算双曲正弦的数字。

**返回值:**
PLSQL 中的 SINH 函数返回一个数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 SINH 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number1 number := 0.5;

BEGIN 
   dbms_output.put_line(SINH(Test_Number1)); 

END; 
```

**输出**

```sql
0.5210953054937473616224256264114915591057 
```

**示例-2:** 在 SINH 函数中使用 0 值作为参数。

```sql
DECLARE 
   Test_Number1 number := 0;

BEGIN 
   dbms_output.put_line(SINH(Test_Number1)); 

END; 
```

**输出:**

```sql
0 
```

**示例-3:** 在 SINH 函数中使用 1 值作为参数。

```sql
DECLARE 
   Test_Number1 number := 1;

BEGIN 
   dbms_output.put_line(SINH(Test_Number1)); 

END; 
```

**输出:**

```sql
1.17520119364380145688238185059560081516 
```

**示例-4:** 在 SINH 函数中使用负值作为参数。

```sql
DECLARE 
   Test_Number1 number := -5;

BEGIN 
   dbms_output.put_line(SINH(Test_Number1)); 

END; 
```

**输出:**

```sql
-74.20321057778875897700947199606456559957 
```

**示例-5:** 在选择查询中使用 SINH 函数，并以度为单位返回值。

```sql
select (SINH(5)) * 57.29  FROM dual; 
```

**输出:**

```sql
4251.10193 
```

使用 1 弧度= 57.29 度的转换公式。

**优势:**
SINH 函数接受任何数字数据类型以及任何非数字数据类型作为参数，可以隐式转换为数字数据类型。