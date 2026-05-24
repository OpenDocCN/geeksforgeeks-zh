# PLSQL | COSH 功能

> 原文:[https://www.geeksforgeeks.org/plsql-cosh-function/](https://www.geeksforgeeks.org/plsql-cosh-function/)

PLSQL COSH 函数用于返回数值的双曲余弦值。COSH 函数接受一个参数，即需要计算双曲余弦的数字。COSH 函数返回数值数据类型的值。

此函数将任何数字数据类型以及可以隐式转换为数字数据类型的任何非数字数据类型作为参数。如果在任何情况下，参数都是 BINARY_FLOAT，那么 COSH 函数返回 BINARY_DOUBLE。

**语法:**

```sql
COSH(number)
```

**使用的参数:**

**数字–**用于指定需要计算双曲余弦的数字。

**返回值:**
PLSQL 中的 COSH 函数返回一个数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 COSH 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number1 number := 0.5;

BEGIN 
   dbms_output.put_line(COSH(Test_Number1)); 

END; 
```

**输出:**

```sql
1.12762596520638078522622516140267201257 
```

**示例-2:** 在 COSH 函数中使用 0 值作为参数。

```sql
DECLARE 
   Test_Number1 number := 0;

BEGIN 
   dbms_output.put_line(COSH(Test_Number1)); 

END; 
```

**输出:**

```sql
1 
```

**示例-3:** 在 COSH 函数中使用 1 值作为参数。

```sql
DECLARE 
   Test_Number1 number := 1;

BEGIN 
   dbms_output.put_line(COSH(Test_Number1)); 

END;
```

**输出:**

```sql
1.5430806348152437784779056207570616826 
```

**示例-4:** 在 COSH 函数中使用负值作为参数。

```sql
DECLARE 
   Test_Number1 number := -5;

BEGIN 
   dbms_output.put_line(COSH(Test_Number1)); 

END; 
```

**输出:**

```sql
74.20994852478784444410610804448771402388 
```

**示例-5:** 使用带有选择查询的 COSH 函数，并以度为单位返回值。

```sql
select (COSH(5)) * 57.29  FROM dual; 
```

**输出:**

```sql
4251.48795 
```

使用 1 弧度= 57.29 度的转换公式。

**优点:**
COSH 函数接受任何数字数据类型以及任何非数字数据类型作为参数，可以隐式转换为数字数据类型。