# PLSQL | CEIL 功能

> 原文:[https://www.geeksforgeeks.org/plsql-ceil-function/](https://www.geeksforgeeks.org/plsql-ceil-function/)

**CEIL** 是 PLSQL 中内置的[函数，用于返回大于或等于给定输入数的最小整数值。该输入数字可以是分数或整数。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
CEIL(number)
```

**使用的参数:**
这里参数**数字**是将要调用 CEIL 函数的输入数字。

**返回值:**
该函数返回大于或等于给定输入数的最小整数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些说明 CEIL 功能的例子:

**示例-1:**

```sql
DECLARE 
   Test_Number number := 2.6;

BEGIN 
   dbms_output.put_line(CEIL(Test_Number number)); 

END;  
```

**输出:**

```sql
3
```

在上面的例子中，2.6 作为参数，返回 3，因为 3 是大于 2.6 的最小整数

**示例-2:**

```sql
DECLARE 
   Test_Number number := -2.6;

BEGIN 
   dbms_output.put_line(CEIL(Test_Number number)); 

END; 
```

**输出:**

```sql
-2
```

在上面的例子中，-2.6 作为参数，返回-2，因为-2 是大于-2.6 的最小整数

**优势:**
该函数用于找出大于或等于给定输入数的最小整数值。该输入数字可以是分数或整数。