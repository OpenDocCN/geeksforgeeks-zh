# PLSQL | LOG 函数

> 原文:[https://www.geeksforgeeks.org/plsql-log-function/](https://www.geeksforgeeks.org/plsql-log-function/)

PLSQL LOG 函数用于返回以 n 为底的 m 的对数。LOG 函数接受两个参数，用于计算对数值。LOG 函数返回数值数据类型的值。

此函数将任何数字数据类型以及可以隐式转换为数字数据类型的任何非数字数据类型作为参数。如果在任何情况下，参数是 BINARY_FLOAT 或 BINARY_DOUBLE，那么 LOG 函数返回 BINARY_DOUBLE，否则返回 number。

**语法:**

```sql
LOG( m, n )
```

**使用的参数:**

**m–**用于指定基数。它应该是除 0 和 1 之外的任何正数。

**n–**用于指定需要用特定基数计算其对数值的数字。它应该是一个正数。

**返回值:**
PLSQL 中的 LOG 函数返回一个数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 LOG 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number1 number := 9;
   Test_Number2 number := 3;

BEGIN 
   dbms_output.put_line(LOG(Test_Number1, 
                            Test_Number2)); 

END; 
```

**输出:**

```sql
0.5 
```

**示例-2:** 在 LOG 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number1 number := 3;
   Test_Number2 number := 9;

BEGIN 
   dbms_output.put_line(LOG(Test_Number1, 
                            Test_Number2)); 

END; 
```

**输出:**

```sql
2 
```

**示例-3:** 在 LOG 函数的两个参数中使用相同的正数值。

```sql
DECLARE 
   Test_Number1 number := 3;
   Test_Number2 number := 3;

BEGIN 
   dbms_output.put_line(LOG(Test_Number1, 
                            Test_Number2)); 

END; 
```

**输出:**

```sql
1 
```

**示例-4:** 在 LOG 函数的基值参数中使用零。

```sql
DECLARE 
   Test_Number1 number := 0;
   Test_Number2 number := 3;

BEGIN 
   dbms_output.put_line(LOG(Test_Number1, 
                            Test_Number2)); 

END; 
```

**输出:**

```sql
numeric or value error 
```

上面的例子抛出了一个错误，因为 LOG 函数没有将 0 和 1 作为参数中的基值。

**示例-5:** 在选择查询中使用日志功能。

```sql
SELECT LOG(2, 8) "Log base 2 of 8" FROM DUAL; 
```

**输出:**

```sql
3 
```

**优点:**
LOG 函数接受任何数字数据类型以及任何非数字数据类型作为参数，可以隐式转换为数字数据类型。