# PLSQL | SUBSTR 函数

> 原文:[https://www.geeksforgeeks.org/plsql-substr-function/](https://www.geeksforgeeks.org/plsql-substr-function/)

PLSQL SUBSTR 函数用于从字符串中提取子字符串。
SUBSTR 函数接受三个参数，分别是 input_string、start_position、length。
SUBSTR 使用输入字符集定义的字符计算长度。SUBSTRB 使用字节而不是字符。

**注:**

*   如果位置为 0，则视为 1。
*   如果位置为正，则 Oracle 数据库从字符的开头开始计数，以找到第一个字符。
*   如果位置为负，则 Oracle 从字符末尾向后计数。
*   如果省略 substring_length，则 Oracle 将返回字符末尾的所有字符。如果 substring_length 小于 1，则 Oracle 返回 null。

**语法:**

```sql
SUBSTR( input_string, start_position, length)
```

**使用的参数:**

1.  **input _ string–**用于指定源字符串。
2.  **起始位置–**用于指定提取的起始位置。
3.  **长度–**是可选参数，用于指定要提取的字符数。

**返回值:**
PLSQL 中的 SUBSTR 函数返回一个字符串值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 传递 SUBSTR 函数中的所有三个参数。

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(SUBSTR(Test_String, '6', '3')); 

END;      
```

**输出:**

```sql
for
```

**示例-2:** 在将参数传递给 SUBSTR 函数时，省略了长度参数。

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(SUBSTR(Test_String, '6')); 

END;    
```

**输出:**

```sql
forgeeks 
```

**示例-3:** 在将参数传递给 SUBSTR 函数时，在 starting _ position 参数中传递负值。

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(SUBSTR(Test_String, '-6', '3')); 

END;     
```

**输出:**

```sql
rge 
```

SUBSTR 函数从字符串的末尾开始，如果起始位置参数为负值，则向后计数。

**示例-4:** 在 starting _ position 参数中传递一个大于 input_string 中字符数的值。

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(SUBSTR(Test_String, '-16', '3')); 

END; 
```

**输出:**

```sql
NULL 
```

SUBSTR 函数返回空值，因为 input_string 中的字符数小于起始位置参数中传递的值。

**优势:**
作为参数传递给 SUBSTR 的浮点数会自动转换为整数。