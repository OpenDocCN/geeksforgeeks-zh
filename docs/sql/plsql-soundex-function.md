# PLSQL | SOUNDEX 函数

> 原文:[https://www.geeksforgeeks.org/plsql-soundex-function/](https://www.geeksforgeeks.org/plsql-soundex-function/)

PLSQL SOUNDEX 函数用于返回字符串的语音表示。音标代表字符串的发音方式。PLSQL SOUNDEX 函数有助于比较拼写不同但在英语中听起来相似的单词。

SOUNDEX 函数接受一个参数 input_string，该参数可以是 CHAR、VARCHAR2、NCHAR 或 NVARCHAR2 数据类型中的任何一种。返回值是与 char 相同的数据类型。

**语法:**

```sql
SOUNDEX( input_string )
```

**使用的参数:**

**input _ string–**用于指定想要知道其语音表示的字符串。

**注:**

*   SOUNDEX 函数返回的值总是以 input_string 的第一个字母开始。
*   SOUNDEX 函数只使用前 5 个辅音来确定返回值的 NUMERIC 部分，除非 string1 的第一个字母是元音。
*   SOUNDEX 函数不区分大小写。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_String string(25) := 'geeksforgeeks';

BEGIN 
   dbms_output.put_line(SOUNDEX(Test_String)); 

END;     
```

**输出:**

```sql
G216 
```

**例-2:**

```sql
DECLARE 
   Test_String string(25) := 'GEEKSFORGEEKS';

BEGIN 
   dbms_output.put_line(SOUNDEX(Test_String)); 

END;  
```

**输出:**

```sql
G216 
```

**例-3:**

```sql
DECLARE 
   Test_String string(25) := 'Hello';

BEGIN 
   dbms_output.put_line(SOUNDEX(Test_String)); 

END;  
```

**输出:**

```sql
H400 
```

**例-4:**

```sql
DECLARE 
   Test_String string(25) := 'Hello';

BEGIN 
   dbms_output.put_line(SOUNDEX(Test_String)); 

END;  
```

**输出:**

```sql
H400 
```

**例-5:**

```sql
DECLARE 
   Test_String string(25) := 'Hello User';

BEGIN 
   dbms_output.put_line(SOUNDEX(Test_String)); 

END;  
```

**输出:**

```sql
H426 
```