# PLSQL | REPLACE 函数

> 原文:[https://www.geeksforgeeks.org/plsql-replace-function/](https://www.geeksforgeeks.org/plsql-replace-function/)

PLSQL REPLACE 函数用于用另一组字符替换字符串中的一系列字符。REPLACE 函数接受三个参数，即输入字符串、字符串到替换和替换字符串。

REPLACE 函数返回 input_string，每次出现 string_to_replace 都被 replacement _ string 替换。如果 replacement_string 被省略或为空，那么所有出现的 string _ to _ replacement 都将被删除。如果 string_to_replace 为空，则返回 input_string。

string_to_replace 和 replacement_string 以及 input_string 都可以是任何数据类型 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。返回的字符串与 char 在同一字符集内。

**语法:**

```sql
REPLACE( input_string, string_to_replace, replacement_string] )
```

**使用的参数:**

1.  **input _ string–**用于指定要用另一组字符替换其字符的字符串。
2.  **string _ to _ replace–**用于指定需要在 input_string 中搜索的字符串。
3.  **replacement_string :** 可选参数，用于指定替换字符串。如果省略了 replacement _ string 参数，REPLACE 函数只需删除所有出现的 string_to_replace，并返回结果字符串。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_String string(25) := '111Geeksforgeeks';

BEGIN 
   dbms_output.put_line(REPLACE(Test_String, '1')); 

END;     
```

**输出:**

```sql
Geeksforgeeks 
```

**例-2:**

```sql
DECLARE 
   Test_String string(25) := '111Geeksforgeeks111';

BEGIN 
   dbms_output.put_line(REPLACE(Test_String, '1')); 

END;     
```

**输出:**

```sql
Geeksforgeeks 
```

**例-3:**

```sql
DECLARE 
   Test_String string(25) := '111Geeksforgeeks111';

BEGIN 
   dbms_output.put_line(REPLACE(Test_String, '1', '2')); 

END;     
```

**输出:**

```sql
222Geeksforgeeks222 
```

**例-4:**

```sql
DECLARE 
   Test_String string(25) := 'Giiksforgiiks';

BEGIN 
   dbms_output.put_line(REPLACE(Test_String, 'i', 'e' )); 

END;    
```

**输出:**

```sql
Geeksforgeeks 
```

**例-5:**

```sql
DECLARE 
   Test_String string(25) := 'Giiksforgiiks';

BEGIN 
   dbms_output.put_line(REPLACE(Test_String, 'i', ' ' )); 

END;     
```

**输出:**

```sql
G  ksforg  ks 
```