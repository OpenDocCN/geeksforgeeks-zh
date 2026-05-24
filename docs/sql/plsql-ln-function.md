# PLSQL | LN 功能

> 原文:[https://www.geeksforgeeks.org/plsql-ln-function/](https://www.geeksforgeeks.org/plsql-ln-function/)

**LN** 函数是 PLSQL 中内置的[函数，用于返回给定输入数的自然对数。一个数的自然对数是该数对基数 e 的对数，其中 e 是近似等于 2.718 的数学常数。这是使用符号 lnx 编写的，有时也称为 logex。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
LN(number) 
```

**使用的参数:**
这个函数接受一个参数**数字**，它是用来计算自然对数的数值。该数字必须大于 0。

**返回值:**
该函数返回给定输入数值的自然对数。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些例子来说明 LN 函数:

**示例-1:**

```sql
DECLARE 
   Test_Number number := 20;

BEGIN 
   dbms_output.put_line(LN(Test_Number number)); 

END;  
```

**输出:**

```sql
2.99573227355399
```

在上面的例子中，20 是一个数值，它的自然对数值是 2.995732273599

**示例-2:**

```sql
DECLARE 
   Test_Number number := 25;

BEGIN 
   dbms_output.put_line(LN(Test_Number number)); 

END; 
```

**输出:**

```sql
3.2188758248682
```

在上面的例子中，25 是自然对数为 3.2188758248682 的数值

**示例-3:**

```sql
DECLARE 
   Test_Number number := 100.5;

BEGIN 
   dbms_output.put_line(LN(Test_Number number)); 

END; 
```

**输出:**

```sql
4.61015772749913
```

在上面的例子中，100.5 是一个数值，它的自然对数值是 4.610157727913

**优势:**
这个函数用来求给定输入数的自然对数。