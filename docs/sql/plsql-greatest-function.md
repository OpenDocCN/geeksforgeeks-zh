# PLSQL |最大功能

> 原文:[https://www.geeksforgeeks.org/plsql-greatest-function/](https://www.geeksforgeeks.org/plsql-greatest-function/)

**最大值**是 PLSQL 中内置的[函数，用于从给定的一些表达式列表中返回最大值。这些表达可以是数字、字母等。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
GREATEST(exp1, exp2, ... exp_n)
```

**使用的参数:**
该函数接受一些参数，如 **exp1、exp2、… exp_n** 。这些表达式可以是数字或字母，在其上调用 MARSATE()函数。

**返回值:**
这个函数从给定的表达式列表中返回最大值。

**支持的 Oracle/PLSQL 版本如下:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些例子来说明最大的功能:

**示例-1:**

```sql
DECLARE 
   Test_Number number1 := 1;
   Test_Number number2 := 2;
   Test_Number number3 := 5;
   Test_Number number4 := 30;

BEGIN 
   dbms_output.put_line(GREATEST(Test_Number number1, 
                                 Test_Number number2, 
                                 Test_Number number3, 
                                 Test_Number number4)); 

END; 
```

**输出:**

```sql
30
```

在上面的例子中，一些数字列表被作为参数，其中最大的数字作为输出返回。例如，1、2、5 和 30 被作为参数，其中 30 被返回，因为它是最大的数字。

**示例-2:**

```sql
DECLARE 
   Test_Number number1 := 'a';
   Test_Number number2 := 'b';
   Test_Number number3 := 'c';

BEGIN 
   dbms_output.put_line(GREATEST(Test_Number number1, 
                                 Test_Number number2, 
                                 Test_Number number3)); 

END;
```

**输出:**

```sql
c
```

在上面的例子中，一些字母列表被作为参数，其中计数最大的字母作为输出返回。例如，将 a、b 和 c 作为参数，从中返回 c，因为它是计数中最大的。

**示例-3:**

```sql
DECLARE 
   Test_Number number1 := 0;
   Test_Number number2 := -4;
   Test_Number number3 := 0.6;

BEGIN 
   dbms_output.put_line(GREATEST(Test_Number number1, 
                                 Test_Number number2, 
                                 Test_Number number3)); 

END; 
```

**输出:**

```sql
0.6
```

在上面的例子中，一些数字列表被作为参数，其中最大的数字作为输出返回。例如，0，-4 和 0.6 被作为参数，其中 0.6 被返回，因为它是最大的数字。

**优势:**
这个函数用来从给定的输入表达式中找出最大的表达式。这个表达式可以是任何数字或字母。