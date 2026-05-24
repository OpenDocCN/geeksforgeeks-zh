# PLSQL | CHR 功能

> 原文:[https://www.geeksforgeeks.org/plsql-chr-function/](https://www.geeksforgeeks.org/plsql-chr-function/)

PL/SQL 中的字符串实际上是具有可选大小规格的字符序列。
字符可以是数字、字母、空白、特殊字符或所有字符的组合。
PLSQL 中的 CHR 函数与 ASCII 函数相反，用于根据 NUMBER 代码返回字符。

**语法:**

```sql
CHR( number_code )
```

**使用的参数:**

**number _ code–**用于检索指定数字代码的字符。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例:**

```sql
DECLARE 
   Test_Char varchar2(4) := '69';
   Test_Char1 varchar2(4) := '72';

   BEGIN 
   dbms_output.put_line(CHR(Test_Char)); 
   dbms_output.put_line(CHR(Test_Char1)); 

END; 
```

**输出:**

```sql
E
H
```