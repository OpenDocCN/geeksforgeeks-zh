# PLSQL | VSIZE 函数

> 原文:[https://www.geeksforgeeks.org/plsql-vsize-function/](https://www.geeksforgeeks.org/plsql-vsize-function/)

PLSQL VSIZE 函数用于返回表达式内部表示中的字节数。PLSQL 只接受一个指定表达式的参数。

通常，VSIZE 函数返回一个数值，但是如果表达式为空，则该函数返回空值。该函数不直接支持 CLOB 数据。但是，CLOBs 可以通过隐式数据转换作为参数传入。

**语法:**

```sql
VSIZE( expression )
```

**使用的参数:**

**表达式–**用于指定需要求值的字符串。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**返回值:**
PLSQL 中的 VSIZE 函数返回一个数值。

**示例-1:** 传递仅包含字符的输入字符串。

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(VSIZE(Test_String)); 

END;  
```

**输出:**

```sql
13 
```

**示例-2:** 传递带有字符和空格的输入字符串。

```sql
DECLARE 
   Test_String string(20) := ' Geeksforgeeks ';

BEGIN 
   dbms_output.put_line(VSIZE(Test_String)); 

END;  
```

**输出:**

```sql
15 
```

**示例-3:** 传递空参数。

```sql
DECLARE 
   Test_String string(20) := '';

BEGIN 
   dbms_output.put_line(VSIZE(Test_String)); 

END;  
```

**输出:**

```sql
NULL 
```

**示例-4:** 传递空格作为参数。

```sql
DECLARE 
   Test_String string(20) := ' ';

BEGIN 
   dbms_output.put_line(VSIZE(Test_String)); 

END;  
```

**输出:**

```sql
1 
```