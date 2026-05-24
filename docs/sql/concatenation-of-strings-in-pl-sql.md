# PL/SQL 中字符串的串联

> 原文:[https://www . geesforgeks . org/pl-SQL 字符串串联/](https://www.geeksforgeeks.org/concatenation-of-strings-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定两个字符串，任务是连接它们并将其存储在另一个字符串中。

**示例:**

```sql
Input: str1 = ' RAMESH', str2 = 'SURESH'
Output: RAMESH SURESH

Input: str1 = ' Ramesh is a good boy', str3 = 'and',
       str2 = 'Suresh is a brilliant student'.
Output: Ramesh is a good boy and Suresh is a brilliant student

```

**方法**是使用[串联](https://docs.oracle.com/cd/B19306_01/server.102/b14200/operators003.htm)运算符，即||。

下面是需要的实现:

```sql
DECLARE
    --Here variables are str, str1, str2 and v
    str  VARCHAR2(40) := 'Ramesh is a good boy';
    str1 VARCHAR2(40) := 'Suresh is a brilliant student';
    str2 VARCHAR2(40) := 'and';
    v    VARCHAR2(100);
BEGIN
    v := str
         ||' '
         || str2
         ||' '
         ||str1;

    dbms_output.Put_line(v);
END;
-- Program End  
```

**输出:**

```sql
Ramesh is a good boy and Suresh is a brilliant student

```