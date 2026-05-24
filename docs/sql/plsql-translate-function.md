# PLSQL | TRANSLATE 函数

> 原文:[https://www.geeksforgeeks.org/plsql-translate-function/](https://www.geeksforgeeks.org/plsql-translate-function/)

PLSQL TRANSLATE 函数用于用另一组字符替换字符串中的一系列字符。PLSQL TRANSLATE 函数一次替换一个字符。TRANSLATE 函数将 input_string 的第一个字符替换为 replacement_string 的第一个字符，然后是第二个字符，并对其余字符遵循相同的流程。

TRANSLATE 函数接受三个参数 input_string、string_to_replace 和 replacement_string。如果一个字符在 string_to_replace 中出现多次，则使用对应于第一次出现的 replacement _ string 映射。TRANSLATE 函数返回一个字符串值。

**语法:**

```sql
TRANSLATE( input_string, string_to_replace, replacement_string )
```

**使用的参数:**

1.  **input _ string–**用于指定源字符串。
2.  **string _ to _ replace–**用于指定将在 input_string 中搜索的字符串。
3.  **replacement _ string–**用于指定将被 input_string 中对应字符替换的字符。

**返回值:**
PLSQL 中的 TRANSLATE 函数返回一个字符串值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 将所有三个参数传递给 TRANSLATE 函数，以替换 input_string 中的连续字母。

```sql
DECLARE 
   Test_String string(25) := 'Giiksforgiiks';

BEGIN 
   dbms_output.put_line(TRANSLATE(Test_String, 'ii', 'ee')); 

END;     
```

**输出:**

```sql
Geeksforgeeks 
```

**示例-2:** 将所有三个参数传递给 TRANSLATE 函数，以替换 input_string 中的非连续字母。

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(TRANSLATE(Test_String, 'Gkrs', 'abcd')); 

END; 
```

**输出:**

```sql
aeebdfocgeebd 
```

**示例-3:** 将所有三个参数传递给 TRANSLATE 函数，以替换 input_string 中的大小写字母。

```sql
DECLARE 
   Test_String string(25) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(TRANSLATE(Test_String, 'Gg', 'Aa')); 

END;  
```

**输出:**

```sql
Aeeksforaeeks 
```

**优势:**

*   REPLACE 可用于用一个字符串替换另一个字符串，以及删除字符串。
*   TRANSLATE 可用于在一次操作中进行多个单字符、一对一的替换。