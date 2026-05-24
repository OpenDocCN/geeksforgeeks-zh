# PLSQL | LENGTH4 功能

> 原文:[https://www.geeksforgeeks.org/plsql-length4-function/](https://www.geeksforgeeks.org/plsql-length4-function/)

PLSQL LENGTH4 函数用于使用 UCS4 代码点返回指定字符串的长度。
UCS-4 代码点是一种字符编码，允许将每个值精确地表示为四个字节(一个 32 位字)。
UCS-4 表示每个字符在 0 和十六进制 7FFFFFFF 之间的可能值。

PLSQL 中的 LENGTH4 函数接受的 char 可以是任何数据类型，如 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。

LENGTH4 函数返回的值是数据类型 NUMBER。
如果参数中发送的 char 具有 CHAR 数据类型，则长度包括所有尾随空格。如果 char 为 null，那么这个函数返回 null。

**语法:**

```sql
LENGTH4( string )
```

**使用的参数:**

**字符串–**用于指定要查找长度的字符串。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_String string(20) := NULL;

BEGIN 
   dbms_output.put_line(LENGTH4(Test_String)); 

END;    
```

**输出:**

```sql
NULL 
```

**示例-2:**

```sql
DECLARE 
   Test_String string(20) := '';

BEGIN 
   dbms_output.put_line(LENGTH4(Test_String)); 

END;    
```

**输出:**

```sql
NULL 
```

**示例-3:**

```sql
DECLARE 
   Test_String string(20) := ' ';

BEGIN 
   dbms_output.put_line(LENGTH4(Test_String)); 

END;    
```

**输出:**

```sql
1 
```

**示例-4:**

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(LENGTH4(Test_String)); 

END;     
```

**输出:**

```sql
13 
```

**示例-5:**

```sql
DECLARE 
   Test_String string(20) := ' Geeksforgeeks ';

BEGIN 
   dbms_output.put_line(LENGTH4(Test_String)); 

END;     
```

**输出:**

```sql
15 
```