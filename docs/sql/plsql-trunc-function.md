# PLSQL | TRUNC 函数

> 原文:[https://www.geeksforgeeks.org/plsql-trunc-function/](https://www.geeksforgeeks.org/plsql-trunc-function/)

**TRUNC** 函数是 PLSQL 中内置的[函数，用于返回被截断到特定小数位数的数字。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
TRUNC( number, decimal_places )
```

**使用的参数:**
该函数接受两个参数，如下所示:-

*   **数字–**这是将要被截断为某个数字的输入数字。
*   **小数位数–**这也是一个输入数，指定小数点后最多有多少个数字是该函数的输出。

**返回值:**
这个函数返回一个被截断到特定小数位数的数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些说明 TRUNC 函数的例子:

**示例-1:**

```sql
DECLARE 
   Test_Number number := 5.5;

BEGIN 
   dbms_output.put_line(TRUNC(Test_Number number)); 

END;  
```

**输出:**

```sql
5
```

在上面的示例中，截断值 5.5 是 5

**示例-2:**

```sql
DECLARE 
   Test_Number number1 := 5;
   Test_Number number2 := 0;

BEGIN 
   dbms_output.put_line(TRUNC(Test_Number number1, 
                              Test_Number number2)); 

END;  
```

**输出:**

```sql
5
```

在上面的例子中，(5，0)的截断值是 5，因为 5 没有任何小数点，因此它返回 5 作为输出。

**示例-3:**

```sql
DECLARE 
   Test_Number number1 := 15.3123;
   Test_Number number2 := 2;

BEGIN 
   dbms_output.put_line(TRUNC(Test_Number number1, 
                              Test_Number number2)); 

END;  
```

**输出:**

```sql
15.31
```

在上面的示例中，截断值 15.3123 是 15.31，因为这里 2 位于 decimal_place 参数的位置，并且它显示输出值必须在小数点后包含 2 个小数。

**优势:**
该函数用于返回被截断到特定小数位数的数字。