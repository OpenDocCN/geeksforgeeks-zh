# PLSQL | TAN 函数

> 原文:[https://www.geeksforgeeks.org/plsql-tan-function/](https://www.geeksforgeeks.org/plsql-tan-function/)

**TAN** 函数是 PLSQL 中内置的[函数，用于返回输入数字的正切值。切线是角度的三角函数，这里输入的数字是以弧度表示的角度。180 度等于π弧度。](https://www.geeksforgeeks.org/functions-in-plsql/)

**语法:**

```sql
TAN( number )
```

**使用的参数:**
该函数接受如下所示的参数:

**数字–**这是输入的数字，是用弧度表示的角度。

**返回值:**
该函数返回一个与输入角度相切的数值。

**支持的 Oracle/PLSQL 版本如下:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

让我们看一些说明 TAN 函数的例子:

**示例-1:**

```sql
DECLARE 
   Test_Number number := 3;

BEGIN 
   dbms_output.put_line(TAN(Test_Number number)); 

END; 
```

**输出:**

```sql
-0.142546543074278
```

在上面的例子中，3 的正切值是-0.142546543074278

**示例-2:**

```sql
DECLARE 
   Test_Number number := 5.2;

BEGIN 
   dbms_output.put_line(TAN(Test_Number number)); 

END; 
```

**输出:**

```sql
-1.88564187751976
```

在上面的例子中，5.2 的正切值是-1。58860 . 88888888861

**示例-3:**

```sql
DECLARE 
   Test_Number number := -5.2;

BEGIN 
   dbms_output.put_line(TAN(Test_Number number)); 

END; 
```

**输出:**

```sql
1.88564187751976
```

在上面的例子中，-5.2 的正切值是 1。58860 . 88888888861

**优势:**
这个函数用来计算一个输入数的正切值。