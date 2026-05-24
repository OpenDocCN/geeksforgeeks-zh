# PLSQL |电源功能

> 原文:[https://www.geeksforgeeks.org/plsql-power-function/](https://www.geeksforgeeks.org/plsql-power-function/)

**POWER** 函数是 PLSQL 中内置的[函数，用于在 **a** 升至 **b** 次幂时返回计算值。如果 a 是负数，那么 b 必须是整数。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
POWER(a, b)
```

**参数使用:**
该功能接受两个参数 **a** 和 **b** 。如果 a 是负数，那么 b 必须是整数。

**返回值:**
该功能将 **a** 升至 **b** 次幂。

**支持的 Oracle/PLSQL 版本如下:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些例子来说明 POWER 函数:

**示例-1:**

```sql
DECLARE 
   Test_Number number1 := 3;
   Test_Number number2 := 2;

BEGIN 
   dbms_output.put_line(POWER(Test_Number number1, 
                              Test_Number number2)); 

END; 
```

**输出:**

```sql
9
```

在上面的例子中，3 被提升到 2 次幂，并返回 9 作为输出。

**示例-2:**

```sql
DECLARE 
   Test_Number number1 := -5;
   Test_Number number2 := 3;

BEGIN 
   dbms_output.put_line(POWER(Test_Number number1, 
                              Test_Number number2)); 

END; 
```

**输出:**

```sql
-125
```

在上面的例子中，-5 被提升到 3 次方，并返回-125 作为输出。

**示例-3:**

```sql
DECLARE 
   Test_Number number1 := 6.2;
   Test_Number number2 := 3.5;

BEGIN 
   dbms_output.put_line(POWER(Test_Number number1, 
                              Test_Number number2)); 

END; 
```

**输出:**

```sql
593.431934277892
```

在上面的例子中，6.2 被提升到 3.5 次方，并返回 593.43193427892 作为输出。

**优势:**
该功能用于计算 **a** 升至 **b** 次幂时的数值。