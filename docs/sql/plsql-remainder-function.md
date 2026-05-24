# PLSQL |余数函数

> 原文:[https://www.geeksforgeeks.org/plsql-remainder-function/](https://www.geeksforgeeks.org/plsql-remainder-function/)

**余数**函数是 PLSQL 中内置的[函数，用于返回 **a** 除以 **b** 的余数。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
REMAINDER(a, b)
```

**参数使用:**
该函数接受两个参数 **a** 和 **b** ，用于计算 a 除以 b 后的余数

**返回值:**
当输入数字 **a** 除以 **b** 时，该函数返回一个数值。

**支持的 Oracle/PLSQL 版本如下:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些例子来说明余数函数:

**示例-1:**

```sql
DECLARE 
   Test_Number number1 := 15;
   Test_Number number2 := 5;

BEGIN 
   dbms_output.put_line(REMAINDER(Test_Number number1, 
                                  Test_Number number2)); 

END; 
```

**输出:**

```sql
0
```

在上面的例子中，当 15 除以 5 时，它返回 0 的余数。

**示例-2:**

```sql
DECLARE 
   Test_Number number1 := 11.6;
   Test_Number number2 := 2;

BEGIN 
   dbms_output.put_line(REMAINDER(Test_Number number1, 
                                  Test_Number number2)); 

END; 
```

**输出:**

```sql
-0.4
```

在上面的例子中，当 11.6 除以 2 时，它返回-0.4 的余数

**示例-3:**

```sql
DECLARE 
   Test_Number number1 := -15;
   Test_Number number2 := 4;

BEGIN 
   dbms_output.put_line(REMAINDER(Test_Number number1, 
                                  Test_Number number2)); 

END; 
```

**输出:**

```sql
1
```

在上面的例子中，当-15 除以 4 时，它返回 1 的余数。

**优势:**
该功能用于 **a** 除以 **b** 时求余数。