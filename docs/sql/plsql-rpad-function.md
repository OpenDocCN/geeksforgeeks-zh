# PLSQL | RPAD 函数

> 原文:[https://www.geeksforgeeks.org/plsql-rpad-function/](https://www.geeksforgeeks.org/plsql-rpad-function/)

PLSQL RPAD 函数用于用一组特定的字符填充字符串的右侧。这样做的先决条件是字符串不应该为空。PLSQL 中的 RPAD 函数对于格式化查询输出非常有用。RPAD 函数接受三个参数，即输入字符串、填充长度和填充字符串。

input_string 和 pad_string 可以是 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB 中的任何一种数据类型。如果 input_string 是字符数据类型，则返回的字符串是 VARCHAR2 数据类型。

参数 padded_length 必须是一个 NUMBER 整数或一个可以隐式转换为 NUMBER 整数的值。

如果不指定 pad_string，则默认值为一个空格。如果输入字符串比填充长度长，那么这个函数返回输入字符串中适合填充长度的部分。

**语法:**

```sql
RPAD( input_string, padded_length, pad_string)
```

**使用的参数:**

1.  **input _ string–**用于指定需要格式化的字符串。
2.  **string _ to _ replace–**用于指定要返回的字符数。如果填充长度小于原始字符串，RPAD 函数会将字符串截断到填充长度的大小。
3.  **pad _ string–**这是一个可选参数，用于指定将被填充到字符串右侧的输入字符串。如果省略此参数，RPAD 函数将在 input_string 的右侧填充空格。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(RPAD(Test_String, '5')); 

END;     
```

**输出:**

```sql
Geeks 
```

**例-2:**

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(RPAD(Test_String, '17')); 

END;    
```

**输出:**

```sql
Geeksforgeeks  
```

**例-3:**

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(RPAD(Test_String, '17', '0')); 

END;  
```

**输出:**

```sql
Geeksforgeeks0000 
```

**例-4:**

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(RPAD(Test_String, '5')); 

END;     
```

**输出:**

```sql
Geeksforgeek 
```