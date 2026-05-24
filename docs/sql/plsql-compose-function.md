# PLSQL | COMPOSE 函数

> 原文:[https://www.geeksforgeeks.org/plsql-compose-function/](https://www.geeksforgeeks.org/plsql-compose-function/)

[PL/SQL](https://www.geeksforgeeks.org/plsql-introduction/) 中的字符串实际上是一个可选大小规格的字符序列。
字符可以是数字、字母、空格、特殊字符或所有字符的组合。
PLSQL 中的 Compose 函数用于返回一个 Unicode 字符串。

在组合函数中可以与其他字符组合的 unistring 值有:

1.  **unistr(' \ 0300 ')-**严重重音( ` )
2.  **unistr(' \ 0301 ')–**锐音符( )
3.  **unistr(' \ 0302 ')-**电路(^)
4.  **unistr(' \ 0303 ')-**波浪符号(~)
5.  **unistr(' \ 0308 ')-**UML()

**语法:**

```sql
COMPOSE( string )
```

**使用的参数:**

**字符串–**用于指定需要创建 Unicode 字符串的输入值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版

**示例:**

```sql
DECLARE 
   Test_Char char := 'a';
   Test_Char2 char := 'e';

BEGIN 
   dbms_output.put_line(COMPOSE(Test_Char || unistr('\0308' ))); 
   dbms_output.put_line(COMPOSE(Test_Char || unistr('\0301' )));
   dbms_output.put_line(COMPOSE(Test_Char || unistr('\0303' ))); 
   dbms_output.put_line(COMPOSE(Test_Char2 || unistr('\0302' ))); 

END;  
```

**输出:**

```sql
ä
á
ã
ê
```