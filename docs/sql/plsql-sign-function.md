# PLSQL | SIGN 函数

> 原文:[https://www.geeksforgeeks.org/plsql-sign-function/](https://www.geeksforgeeks.org/plsql-sign-function/)

PLSQL SIGN 函数用于返回一个指示数字符号的值。SIGN 函数接受一个参数，即需要知道其符号的数字。SIGN 函数返回数值数据类型的值。此函数将任何数字数据类型以及可以隐式转换为数字数据类型的任何非数字数据类型作为参数。

SIGN 函数返回的可能值有:

*   如果数字小于 0，SIGN 函数返回-1。
*   如果数字等于 0，SIGN 函数返回 0。
*   如果数字大于 0，SIGN 函数返回 1。

**语法:**

```sql
SIGN (number)
```

**使用的参数:**

**数字–**用于指定需要测试符号的数字。

**返回值:**
PLSQL 中的 SIGN 函数返回一个数值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 在 SIGN 函数中使用正数值作为参数。

```sql
DECLARE 
   Test_Number1 number := 5;

BEGIN 
   dbms_output.put_line(SIGN(Test_Number1)); 

END; 
```

**输出:**

```sql
1 
```

**示例-2:** 在 SIGN 函数中使用负数值作为参数。

```sql
DECLARE 
   Test_Number1 number := -5;

BEGIN 
   dbms_output.put_line(SIGN(Test_Number1)); 

END;

```

**输出:**

```sql
-1 
```

**示例-3:** 在 SIGN 函数中使用零作为参数。

```sql
DECLARE 
   Test_Number1 number := 0;

BEGIN 
   dbms_output.put_line(SIGN(Test_Number1)); 

END; 
```

**输出:**

```sql
0 
```

**示例-4:** 在 SIGN 函数中使用带十进制值的正数作为参数。

```sql
DECLARE 
   Test_Number1 number := 0.0032;

BEGIN 
   dbms_output.put_line(SIGN(Test_Number1)); 

END; 
```

**输出:**

```sql
1 
```

**示例-5:** 在 SIGN 函数中使用带十进制值的负数作为参数。

```sql
DECLARE 
   Test_Number1 number := - 0.0032;

BEGIN 
   dbms_output.put_line(SIGN(Test_Number1)); 

END; 
```

**示例-6:** 在选择查询中使用 SIGN 函数。

```sql
SELECT SIGN(-5) "Sign" FROM DUAL; 
```

**输出:**

```sql
Sign
-1 
```

**优点:**
SIGN 函数接受任何数字数据类型以及任何非数字数据类型作为参数，可以隐式转换为数字数据类型。