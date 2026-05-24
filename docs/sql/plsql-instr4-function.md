# PLSQL | INSTR4 功能

> 原文:[https://www.geeksforgeeks.org/plsql-instr4-function/](https://www.geeksforgeeks.org/plsql-instr4-function/)

PLSQL INSTR4 函数用于使用 UCS4 代码点返回字符串中子字符串的位置。UCS-4 代码点是一种字符编码，允许每个值精确地表示为四个字节(一个 32 位字)。UCS-4 表示每个字符在 0 和十六进制 7FFFFFFF 之间的可能值。

PLSQL INSTR4 函数在字符串中搜索用户使用字符指定的子字符串，并返回字符串中指定出现的子字符串的第一个字符的位置。PLSQL INSTR4 函数接受四个参数，即字符串、子字符串、起始位置和第 n 个外观。

字符串和子字符串可以是任何数据类型，如 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。

**语法:**

```sql
INSTR4(string, substring [, start_position [, nth_appearance ]])
```

**参数使用:**

*   **String–** A string used to specify the substring to be searched. It can be any data type CHAR, VARCHAR2, NCHAR, NVARCHAR2, CLOB or NCLOB.
*   **substring–** is used to specify the substring to be searched. It can be any data type CHAR, VARCHAR2, NCHAR, NVARCHAR2, CLOB or NCLOB.
*   **start _ position–** is an optional parameter, which is used to specify the position where the search starts in the string. The default value is 1\. The INSTR4 function counts back from the end of the string to start_position, and searches for the beginning of the string if the inserted value is negative.
*   **nth occurrence–** is an optional parameter to specify the nth occurrence of substring. The default value is 1.

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g

4.  Oracle 8i 发行版

**示例-1:** 使用字符向前搜索来查找子字符串的位置。

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(INSTR4(Test_String, 'e')); 

END;  
```

**输出:**

```sql
2 
```

**示例-2:** 使用字符位置向前搜索来查找子字符串的位置。

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(INSTR4(Test_String, 'e', 1, 1)); 

END;  
```

**输出:**

```sql
2 
```

**示例-3:** 使用字符位置向前搜索来查找子字符串在第三个位置的位置。

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(INSTR4(Test_String, 'e', 1, 3)); 

END; 
```

**输出:**

```sql
10 
```

**示例-4:** 使用字符位置向后搜索来查找子字符串的位置。

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(INSTR4(Test_String, 'e', -2, 1)); 

END; 
```

**输出:**

```sql
11 
```

**示例-5:** 使用三字节字符集来查找子字符串的位置。

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(INSTR4(Test_String, 'for', 1, 1)); 

END;  
```

**输出:**

```sql
6 
```