# PLSQL | EXP 功能

> 原文:[https://www.geeksforgeeks.org/plsql-exp-function/](https://www.geeksforgeeks.org/plsql-exp-function/)

**EXP** 是 PLSQL 中内置的[函数，用于返回一个被 **e 提升到 n 次方**的值。这里的“e”是一个数学常数，其值为 2.7182818，n 是输入数。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
exp(number)
```

**使用的参数:**
这里的参数**数**是输入的数，是“e”的幂。

**返回值:**
该函数返回一个上升到第 n 次方的值 **e。其中 n 是给定的输入数。**

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些例子来说明 EXP 函数:

**示例-1:**

```sql
DECLARE 
   Test_Number number := 3;

BEGIN 
   dbms_output.put_line(EXP(Test_Number number)); 

END;  
```

**输出:**

```sql
20.0855369231877
```

在上面的例子中，取 3 作为参数，该参数被提升到 e，然后它给出了 20 的结果。58860 . 88888888861

**示例-2:**

```sql
DECLARE 
   Test_Number number := 3.1;

BEGIN 
   dbms_output.put_line(EXP(Test_Number number)); 

END;  
```

**输出:**

```sql
22.1979512814416
```

在上面的例子中，3.1 被作为参数，它被提升到 e。然后它给出一个 22 的结果。18860 . 888888888816

**示例-3:**

```sql
DECLARE 
   Test_Number number := -3;

BEGIN 
   dbms_output.put_line(EXP(Test_Number number)); 

END; 
```

**输出:**

```sql
0.0497870683678639
```

在上面的例子中，-3 被作为参数，它被提升到 e，然后它给出了一个 0 的结果。58860 . 88888888861

**优势:**
这个函数用来找出一个 **e 升到第 n 次方**的值。这里的“e”是一个数学常数，其值为 2.7182818，n 是输入数。