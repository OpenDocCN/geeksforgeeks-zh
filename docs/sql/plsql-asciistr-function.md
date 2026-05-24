# PLSQL | ASCIISTR 函数

> 原文:[https://www.geeksforgeeks.org/plsql-asciistr-function/](https://www.geeksforgeeks.org/plsql-asciistr-function/)

PL/SQL 中的字符串实际上是具有可选大小规格的字符序列。
字符可以是数字、字母、空白、特殊字符或所有字符的组合。
PLSQL 中的 ASCIISTR 函数用于使用数据库字符集将任意字符集的字符串转换为 ASCII 字符串。

**语法:**

```sql
ASCIISTR( string )
```

**使用的参数:**

**字符串–**用于指定数据库字符集中要转换为 ASCII 字符串的字符集。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版

**示例:**

```sql
DECLARE 
   Test_Char char := 'E';
   Test_Char2 varchar2(5) := 'Ê';
   Test_Char3 char := 'H';
   Test_String varchar2(20) := 'H Ê l l Õ';

   BEGIN 
   dbms_output.put_line(ASCIISTR(Test_Char)); 
   dbms_output.put_line(ASCIISTR(Test_Char2)); 
   dbms_output.put_line(ASCIISTR(Test_Char3)); 
   dbms_output.put_line(ASCIISTR(Test_String)); 

END;  
```

**输出:**

```sql
E
\00CA
H
H \00CA l l \00D5 
```