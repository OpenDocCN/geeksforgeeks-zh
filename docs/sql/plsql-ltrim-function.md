# PLSQL | LTRIM 功能

> 原文:[https://www.geeksforgeeks.org/plsql-ltrim-function/](https://www.geeksforgeeks.org/plsql-ltrim-function/)

PLSQL LTRIM 函数用于删除字符串左侧的所有指定字符。PLSQL LTRIM 函数接受两个参数，即输入字符串和修剪字符串。

*   如果用户没有指定 trim_string，则默认为一个空格。
*   如果 char 是一个字符文字，那么您必须用单引号将它括起来。

Oracle 数据库从字符的第一个字符开始扫描字符，并删除出现在 trim_string 中的所有字符，直到到达不在 trim_string 中的字符，然后返回结果。

**语法:**

```sql
LTRIM( input_string [, trim_string] )
```

**使用的参数:**

*   **input _ string–**用于指定需要从左侧修剪字符的字符串。
*   **trim _ string–**这是一个可选参数，用于指定将从 string1 左侧移除的字符串。如果省略此参数，LTRIM 函数将从 input_string 中删除所有前导空格。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_String string(25) := '    Geeksforgeeks';

BEGIN 
   dbms_output.put_line(LTRIM(Test_String)); 

END; 
```

**输出:**

```sql
Geeksforgeeks 
```

**例-2:**

```sql
DECLARE 
   Test_String string(25) := '    Geeksforgeeks';

BEGIN 
   dbms_output.put_line(LTRIM(Test_String, ' ')); 

END; 
```

**输出:**

```sql
Geeksforgeeks 
```

**例-3:**

```sql
DECLARE 
   Test_String string(25) := '123Geeksforgeeks';

BEGIN 
   dbms_output.put_line(LTRIM(Test_String, '123')); 

END; 
```

**输出:**

```sql
Geeksforgeeks 
```

**例-4:**

```sql
DECLARE 
   Test_String string(25) := '123123Geeksforgeeks';

BEGIN 
   dbms_output.put_line(LTRIM(Test_String, '123')); 

END; 
```

**输出:**

```sql
Geeksforgeeks 
```

**例-5:**

```sql
DECLARE 
   Test_String string(25) := '123Geeks123forgeeks';

BEGIN 
   dbms_output.put_line(LTRIM(Test_String, '123')); 

END; 
```

**输出:**

```sql
Geeks123forgeeks 
```