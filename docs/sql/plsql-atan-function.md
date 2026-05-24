# PLSQL | ATAN 函数

> 原文:[https://www.geeksforgeeks.org/plsql-atan-function/](https://www.geeksforgeeks.org/plsql-atan-function/)

**PLSQL ATAN 函数**用于返回一个数的反正切。ATAN 函数只接受一个参数，这个参数是一个数字，参数的范围是无限的。

ATAN 函数返回-pi/2 到 pi/2 范围内的值，以弧度表示。此函数将任何数字数据类型以及可以隐式转换为数字数据类型的任何非数字数据类型作为参数。

**语法:**

```sql
ATAN( number )
```

**使用的参数:**

**数字–**用于指定需要计算其反正切的数字。

**返回值:**
PLSQL 中的 ATAN 函数返回一个数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 ATAN 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number number := 0.5;

BEGIN 
   dbms_output.put_line(ATAN(Test_Number)); 

END; 
```

**输出:**

```sql
0.4636476090008061162142562314612144020295 
```

**示例-2:** 在 ATAN 函数中使用负数值作为参数。

```sql
DECLARE 
   Test_Number number := -0.5;

BEGIN 
   dbms_output.put_line(ATAN(Test_Number)); 

END;  
```

**输出:**

```sql
-0.4636476090008061162142562314612144020295 
```

**示例-3:** 在 ATAN 函数中使用一个不在-1 和 1 之间的数值作为参数。

```sql
DECLARE 
   Test_Number number := 2.5;

BEGIN 
   dbms_output.put_line(ATAN(Test_Number)); 

END;  
```

**输出:**

```sql
1.19028994968253173292773377482931773465 
```

**示例-4:** 在选择查询中使用 ATAN 函数。

```sql
SELECT ATAN(.4) FROM dual; 
```

**输出:**

```sql
0.3805063771123649 
```

**示例-5:** 使用 ATAN 函数进行选择查询并返回度数值。

```sql
select (ATAN(.4)) * 57.29  FROM dual; 
```

**输出:**

```sql
21.799210344767385 
```

使用 1 弧度= 57.29 度的转换公式。

**优点:**
ATAN 函数接受任何数字数据类型以及任何非数字数据类型作为参数，可以隐式转换为数字数据类型。