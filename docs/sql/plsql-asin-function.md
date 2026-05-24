# PLSQL | ASIN 函数

> 原文:[https://www.geeksforgeeks.org/plsql-asin-function/](https://www.geeksforgeeks.org/plsql-asin-function/)

**PLSQL ASIN 函数**用于返回一个数的反正弦。ASIN 函数只有一个参数，这个参数是一个数字，参数个数必须在 **-1** 到 **1** 的范围内，函数返回一个在-pi/2 到 pi/2 范围内的值，用弧度表示。

此函数将可以隐式转换为数字数据类型的任何数字数据类型或非数字数据类型作为参数。

**语法:**

```sql
ASIN( number )
```

**使用的参数:**

**数字–**用于指定需要计算的反正弦数。

**返回值:**
PLSQL 中的 ASIN 函数返回一个数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 ASIN 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number number := 0.5;

BEGIN 
   dbms_output.put_line(ASIN(Test_Number)); 

END; 
```

**输出:**

```sql
0.52359877559829887307710723054658381405 
```

**示例-2:** 在 ASIN 函数中使用负数值作为参数。

```sql
DECLARE 
   Test_Number number := -0.5;

BEGIN 
   dbms_output.put_line(ASIN(Test_Number)); 

END;  
```

**输出:**

```sql
-0.52359877559829887307710723054658381405 
```

**示例-3:** 在 ASIN 函数中使用一个不在-1 和 1 之间的数值作为参数。

```sql
DECLARE 
   Test_Number number := 2.5;

BEGIN 
   dbms_output.put_line(ASIN(Test_Number)); 

END;  
```

**输出:**

```sql
ERROR
ORA-01428: argument '2.5' is out of range 
```

上面的程序抛出了一个错误，因为传递的参数超出了可接受的范围。

**示例-4:** 在选择查询中使用 ASIN 函数。

```sql
SELECT ASIN(.4) FROM dual; 
```

**输出:**

```sql
0.41151684606748806 
```

**示例-5:** 使用带有选择查询的 ASIN 函数并返回度数值。

```sql
select (ASIN(.4)) * 57.29  FROM dual; 
```

**输出:**

```sql
23.57580011120639 
```

使用 1 弧度= 57.29 度的转换公式。

**优点:**
ASIN 函数接受任何数字数据类型或非数字数据类型作为参数，可以隐式转换为数字数据类型。