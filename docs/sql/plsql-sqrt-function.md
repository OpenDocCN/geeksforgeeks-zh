# PLSQL | SQRT 功能

> 原文:[https://www.geeksforgeeks.org/plsql-sqrt-function/](https://www.geeksforgeeks.org/plsql-sqrt-function/)

**SQRT** 函数是 PLSQL 中内置的[函数，用于返回给定输入数的平方根。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
SQRT( number )
```

**使用的参数:**
该函数接受如下所示的参数:

**数字–**这是将要计算平方根的输入数字。

**返回值:**
该函数返回一个数字，该数字是给定输入数的平方根。

**支持的 Oracle/PLSQL 版本如下:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些说明 SQRT 函数的例子:

**示例-1:**

```sql
DECLARE 
   Test_Number number := 25;

BEGIN 
   dbms_output.put_line(SQRT(Test_Number number)); 

END; 
```

**输出:**

```sql
5
```

在上面的例子中，5 是 25 的平方根。

**示例-2:**

```sql
DECLARE 
   Test_Number number := 5.617;

BEGIN 
   dbms_output.put_line(SQRT(Test_Number number)); 

END; 
```

**输出:**

```sql
2.37002109695251
```

在上面的例子中，2.37002109695251 是 5.617 的平方根

**示例-3:**

```sql
DECLARE 
   Test_Number number := 9;

BEGIN 
   dbms_output.put_line(SQRT(Test_Number number)); 

END; 
```

**输出:**

```sql
3
```

在上面的例子中，3 是 9 的平方根

**优势:**
该函数用于计算给定输入数的平方根。