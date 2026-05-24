# PLSQL | ASCII 函数

> 原文:[https://www.geeksforgeeks.org/plsql-ascii-function/](https://www.geeksforgeeks.org/plsql-ascii-function/)

PL/SQL 中的字符串实际上是具有可选大小规格的字符序列。
字符可以是数字、字母、空白、特殊字符或所有字符的组合。
PLSQL 中的 ASCII 函数用于返回代表指定字符的 NUMBER 代码。

**语法**

```sql
ASCII( single_character )
```

**使用的参数:**

**单个字符–**用于检索指定字符的数字代码。
如果输入了多个字符，ASCII 函数将返回第一个字符的值，并忽略第一个字符之后的所有字符。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例:**

```sql
DECLARE 
   Test_Char char := 'A';
   Test_Char2 char := 'H';
   Test_String varchar2(6) := 'Hello';

BEGIN 
   dbms_output.put_line(ASCII(Test_Char)); 
   dbms_output.put_line(ASCII(Test_Char2)); 
   dbms_output.put_line(ASCII(Test_String)); 

END; 
```

**输出:**

```sql
65
72
72
```