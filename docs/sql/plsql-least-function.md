# PLSQL |最小函数

> 原文:[https://www.geeksforgeeks.org/plsql-least-function/](https://www.geeksforgeeks.org/plsql-least-function/)

**最小**是 PLSQL 中内置的[函数，用于从给定的一些表达式列表中返回最小的值。这些表达可以是数字、字母等。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
LEAST(exp1, exp2, ... exp_n)
```

**使用的参数:**
该函数接受一些参数，如 **exp1、exp2、… exp_n** 。这些表达式可以是数字或字母，在其上调用最小()函数。

**返回值:**
这个函数从给定的表达式列表中返回最小的值。

**支持的 Oracle/PLSQL 版本如下:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些说明最小函数的例子:

**示例-1:**

```sql
DECLARE 
   Test_Number number1 := 1;
   Test_Number number2 := 2;
   Test_Number number3 := 5;
   Test_Number number4 := 30;

BEGIN 
   dbms_output.put_line(LEAST(Test_Number number1, 
                              Test_Number number2, 
                              Test_Number number3, 
                              Test_Number number4)); 

END; 
```

**输出:**

```sql
1
```

在上面的例子中，一些数字列表被作为参数，其中最小的，即最小的数字被作为输出返回。例如，在第一个示例中，1、2、5 和 30 被作为参数，其中 1 被返回，因为它是最小的数字。

**示例-2:**

```sql
DECLARE 
   Test_Number number1 := 'a';
   Test_Number number2 := 'b';
   Test_Number number3 := 'c';

BEGIN 
   dbms_output.put_line(LEAST(Test_Number number1, 
                              Test_Number number2, 
                              Test_Number number3)); 

END;  
```

**输出:**

```sql
a
```

在上面的例子中，一些字母列表被作为参数，其中最小的，即计数字母中最小的作为输出返回。例如，在示例 2 中，a、b 和 c 被作为参数，从其中返回 a，因为它是计数中最小的。

**例-3:**

```sql
DECLARE 
   Test_Number number1 := 0;
   Test_Number number2 := -4;
   Test_Number number3 := 0.6;

BEGIN 
   dbms_output.put_line(LEAST(Test_Number number1, 
                              Test_Number number2, 
                              Test_Number number3)); 

END; 
```

**输出:**

```sql
-4
```

在上面的例子中，一些数字列表被作为参数，其中最少的，即最小的数字被作为输出返回。例如，在示例 3 中，0，-4 和 0.6 被作为参数，其中-4 被返回，因为它是最小的数字。

**优势:**
该功能用于在给定的一些输入数字中找出最小的数字。