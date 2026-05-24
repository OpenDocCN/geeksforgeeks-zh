# PLSQL | TRIM 功能

> 原文:[https://www.geeksforgeeks.org/plsql-trim-function/](https://www.geeksforgeeks.org/plsql-trim-function/)

**PLSQL TRIM 函数**用于从字符串的开头或结尾删除所有指定的字符。
TRIM 函数接受三个参数，其中第一个参数可以有值“LEADING”、“TRAILING”、“Both”和 Trim_character 和 input_string 之一。

*   如果指定了前导，则 Oracle 数据库将删除所有等于 trim_character 的前导字符。
*   如果指定了 TRAING，则甲骨文将删除所有等于 trim_character 的尾随字符。
*   如果三者都指定或都不指定，则 Oracle 将删除等于 trim_character 的前导和尾随字符。
*   如果未指定 trim_character，则默认值为空格。
*   如果只指定了 input_string，则 Oracle 会删除前导空格和尾随空格。
*   如果 trim_source 或 trim_character 为空，则 trim 函数返回空值。

**语法:**

```sql
TRIM( [ [ LEADING | TRAILING | BOTH ] trim_character FROM ] input_string )
```

**使用的参数:**

1.  **LEADING:** 此参数用于从 input_string 前面删除 trim _ 字符。
2.  **training:**此参数用于从 input_string 的末尾移除 trim_character。
3.  **BOTH:** 此参数用于从 input_string 的前端和末端移除 trim_character。
4.  **input_string:** 用于指定源字符串。
5.  **trim_character:** 用于指定将从 input_string 中删除的字符串。

**返回值:**
PLSQL 中的 TRIM 函数返回一个字符串值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 使用 LEADING 参数从 input_string 前面删除 trim _ 字符。

```sql
DECLARE 
   Test_String string(25) := '1Geeksforgeeks1';

BEGIN 
   dbms_output.put_line(TRIM(LEADING '1' FROM Test_String)); 

END;      
```

**输出:**

```sql
Geeksforgeeks1 
```

**示例-2:** 使用 TRAING 参数从 input_string 的末尾移除 trim_character。

```sql
DECLARE 
   Test_String string(25) := '1Geeksforgeeks1';

BEGIN 
   dbms_output.put_line(TRIM(Trailing '1' FROM Test_String)); 

END; 
```

**输出:**

```sql
1Geeksforgeeks 
```

**示例-3:** 使用 BOTH 参数从 input_string 的前面和末尾移除 trim_character。

```sql
DECLARE 
   Test_String string(25) := '1Geeksforgeeks1';

BEGIN 
   dbms_output.put_line(TRIM(Both '1' FROM Test_String)); 

END; 
```

**输出:**

```sql
Geeksforgeeks 
```

**示例-4:** 在 TRIM 函数的第一个参数中不传递任何值。

```sql
DECLARE 
   Test_String string(25) := '  Geeksforgeeks  ';

BEGIN 
   dbms_output.put_line(TRIM(' ' FROM Test_String )); 

END; 
```

**输出:**

```sql
Geeksforgeeks 
```

如果第一个参数中没有传递任何值，trim 函数将从输入字符串的前端和后端删除 TRIM 字符。

**优势:**
参数 trim_character 和 trim_source 都接受任何数据类型中的值，如 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。