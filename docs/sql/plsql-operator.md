# PLSQL : ||运算符

> 原文:[https://www.geeksforgeeks.org/plsql-operator/](https://www.geeksforgeeks.org/plsql-operator/)

PL/SQL 中的字符串实际上是具有可选大小规格的字符序列。
字符可以是数字、字母、空白、特殊字符或所有字符的组合。
PLSQL 中的||运算符用于将两个或多个字符串连接在一起。
串联两个字符串的结果是另一个字符串。
结果具有数据类型 CHAR，如果两个字符串都是数据类型 CHAR，则限制为 2000 个字符，而如果任一字符串是数据类型 VARCHAR2，则结果具有数据类型 VARCHAR2，并且限制为 4000 个字符。
对于字符串的连接，CONCAT 字符函数也可以作为 PLSQL 中竖线运算符的替代。

**语法:**

```sql
string1 || string2 [ || string_n ]
```

**使用的参数:**

1.  **字符串 1–**
    用于指定要连接的第一个字符串。
2.  **字符串 2–**
    用于指定要连接的第二个字符串。
3.  **string _ n–**
    用于指定要连接的第 n 个字符串。

**返回类型:**
|运算符返回一个字符串值。

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
   dbms_output.put_line((Test_String || Test_String2)); 

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
   dbms_output.put_line(Test_String || Test_String2 || Test_String3);   
END; 
```

**输出:**

```sql
GeeksForGeeks 
```