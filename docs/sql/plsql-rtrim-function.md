# PLSQL | RTRIM 功能

> 原文:[https://www.geeksforgeeks.org/plsql-rtrim-function/](https://www.geeksforgeeks.org/plsql-rtrim-function/)

PLSQL RTRIM 函数用于删除字符串右侧的所有指定字符。PLSQL RTRIM 函数接受两个参数，即输入字符串和修剪字符串。

*   If the user does not specify trim_string, it defaults to single blank.
*   If char is a character literal, it must be enclosed in single quotation marks.

Oracle 数据库从字符的第一个字符开始扫描字符，并删除出现在 trim_string 中的所有字符，直到到达不在 trim_string 中的字符，然后返回结果。

**语法:**

```sql
RTRIM( input_string [, trim_string] )
```

**使用的参数:**

1.  **input _ string–**用于指定需要从右侧修剪字符的字符串。
2.  **trim _ string–**这是一个可选参数，用于指定将从 input_string 右侧移除的字符串。如果省略此参数，RTRIM 函数将从 input_string 中删除所有前导空格。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g

4.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks    ';

BEGIN 
   dbms_output.put_line(RTRIM(Test_String)); 

END;   
```

**输出:**

```sql
Geeksforgeeks 
```

**示例-2:**

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks      ';

BEGIN 
   dbms_output.put_line(RTRIM(Test_String, ' ')); 

END;   
```

**输出:**

```sql
Geeksforgeeks 
```

**示例-3:**

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks123';

BEGIN 
   dbms_output.put_line(RTRIM(Test_String, '123')); 

END; 
```

**输出:**

```sql
Geeksforgeeks 
```

**示例-4:**

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks123123';

BEGIN 
   dbms_output.put_line(RTRIM(Test_String, '123')); 

END;   
```

**输出:**

```sql
Geeksforgeeks 
```

**示例-5:**

```sql
DECLARE 
   Test_String string(25) := 'Geeks123forgeeks123';

BEGIN 
   dbms_output.put_line(RTRIM(Test_String, '123')); 

END;    
```

**输出:**

```sql
Geeks123forgeeks 
```