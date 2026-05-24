# PLSQL | COS 函数

> 原文:[https://www.geeksforgeeks.org/plsql-cos-function/](https://www.geeksforgeeks.org/plsql-cos-function/)

**PLSQL COS 函数**用于返回数值的余弦值。COS 函数接受一个参数，即需要计算余弦的数字。COS 函数返回数值数据类型的值。

此函数将任何数字数据类型以及可以隐式转换为数字数据类型的任何非数字数据类型作为参数。如果在任何情况下，参数都是 BINARY_FLOAT，那么 COS 函数返回 BINARY_DOUBLE。

**语法:**

```sql
COS(number)
```

**使用的参数:**

**数字–**用于指定需要计算余弦的数字。

**返回值:**
PLSQL 中的 COS 函数返回一个数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 COS 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number1 number := 0.5;

BEGIN 
   dbms_output.put_line(COS(Test_Number1)); 

END; 
```

**输出:**

```sql
0.8775825618903727161162815826038296520119 
```

**示例-2:** 在 COS 函数中使用 0 值作为参数。

```sql
DECLARE 
   Test_Number1 number := 0;

BEGIN 
   dbms_output.put_line(COS(Test_Number1)); 

END; 
```

**输出:**

```sql
1 
```

**示例-3:** 在 COS 函数中使用 1 个值作为参数。

```sql
DECLARE 
   Test_Number1 number := 1;

BEGIN 
   dbms_output.put_line(COS(Test_Number1)); 

END; 
```

**输出:**

```sql
0.5403023058681397174009366074429766037354 
```

**示例-4:** 在 COS 函数中使用负值作为参数。

```sql
DECLARE 
   Test_Number1 number := -5;

BEGIN 
   dbms_output.put_line(COS(Test_Number1)); 

END; 
```

**输出:**
<re>0.28366218546326264466391715135573083265</re>

**示例-5:** 使用 COS 函数进行选择查询并返回度数值。

```sql
select (COS(5)) * 57.29  FROM dual; 
```

**输出:**

```sql
16.25100660518823 
```

使用 1 弧度= 57.29 度的转换公式。

**优点:**
COS 函数接受任何数字数据类型以及任何非数字数据类型作为参数，可以隐式转换为数字数据类型。