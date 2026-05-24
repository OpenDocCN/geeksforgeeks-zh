# PLSQL | FLOOR 函数

> 原文:[https://www.geeksforgeeks.org/plsql-floor-function/](https://www.geeksforgeeks.org/plsql-floor-function/)

**FLOOR** 是 PLSQL 中内置的[函数，用于返回等于或小于给定输入数的最大整数值。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
FLOOR(number)
```

**参数使用:**
该函数接受参数**数字**，该数字是调用 FLOOR 函数的输入数字。

**返回值:**
该函数返回最大的整数值，该值等于或小于给定输入数。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些说明 FLOOR 函数的例子:

**示例-1:**

```sql
DECLARE 
   Test_Number number1 := 2.6;

BEGIN 
   dbms_output.put_line(FLOOR(Test_Number number1)); 

END; 
```

**输出:**

```sql
2
```

在上面的例子中，取了一些参数。比如 2.6 作为参数，返回 2，因为 2 是小于 2.6 的最大整数

**示例-2:**

```sql
DECLARE 
   Test_Number number1 := -2.6;

BEGIN 
   dbms_output.put_line(FLOOR(Test_Number number1)); 

END; 
```

**输出:**

```sql
-3
```

在上面的例子中，取了一些参数。在上面的例子中，-2.6 作为参数，返回-3，因为-3 是小于-2.6 的最大整数

**优势:**
该函数用于从给定的输入数中找出等于或小于的最大整数值。