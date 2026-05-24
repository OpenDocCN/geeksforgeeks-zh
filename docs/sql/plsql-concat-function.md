# PLSQL | CONCAT 函数

> 原文:[https://www.geeksforgeeks.org/plsql-concat-function/](https://www.geeksforgeeks.org/plsql-concat-function/)

PL/SQL 中的字符串实际上是具有可选大小规格的字符序列。
字符可以是数字、字母、空白、特殊字符或所有字符的组合。
CONCAT 函数允许您将两个字符串连接在一起。要连接两个以上的值，我们可以嵌套多个 CONCAT 函数调用。

**语法:**

```sql
CONCAT( string1, string2 )
```

**使用的参数:**

1.  **字符串 1:** 用于指定要连接的第一个字符串。
2.  **字符串 2:** 用于指定要连接的第二个字符串。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_String string(10) := 'Hello ';
   Test_String2 string(10) := 'world!';

BEGIN 
   dbms_output.put_line(CONCAT(Test_String, Test_String2)); 

END; 
```

**输出:**

```sql
Hello world! 
```

**示例-2:**

```sql
DECLARE 
   Test_String string(10) := 'Geeks';
   Test_String2 string(10) := 'For';
   Test_String3 string(10) := 'Geeks';

BEGIN 
   dbms_output.put_line(CONCAT(CONCAT(Test_String, Test_String2), Test_String3)); 

END; 
```

**输出:**

```sql
GeeksForGeeks 
```