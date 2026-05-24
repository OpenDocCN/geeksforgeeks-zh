# PLSQL | NCHR 函数

> 原文:[https://www.geeksforgeeks.org/plsql-nchr-function/](https://www.geeksforgeeks.org/plsql-nchr-function/)

PLSQL NCHR 函数用于根据国家字符集的数字代码返回字符，或者换句话说，它返回与国家字符集的数字等价的二进制数。NCHR 函数返回的值总是数据类型 NVARCHAR2。

NCHR 函数相当于将 CHR 函数与 USING NCHAR_CS 子句一起使用。传递给 NCHR 函数的参数将数字作为参数，或者任何可以隐式转换为数字的值，并返回一个字符。

**语法:**

```sql
NCHR(number_code)
```

**使用的参数:**

**number _ code–**用于指定检索字符的国家字符集内的 NUMBER 代码。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_value int := 103;

BEGIN 
   dbms_output.put_line(NCHR(Test_value)); 

END;   
```

**输出:**

```sql
g 
```

**例-2:**

```sql
DECLARE 
   Test_value int := 103;

BEGIN 
   dbms_output.put_line(CHR(Test_value USING NCHAR_CS)); 

END;      
```

**输出**

```sql
g

```

**例-3:**

```sql
DECLARE 
   Test_value int := 187;

BEGIN 
   dbms_output.put_line(NCHR(Test_value)); 

END;    
```

**输出:**

```sql
» 
```