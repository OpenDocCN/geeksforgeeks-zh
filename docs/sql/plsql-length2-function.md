# PLSQL | LENGTH2 功能

> 原文:[https://www.geeksforgeeks.org/plsql-length2-function/](https://www.geeksforgeeks.org/plsql-length2-function/)

PLSQL LENGTH2 函数用于返回指定字符串的长度，换句话说，它返回字符的长度。UCS-2 代码点是一种字符编码标准，其中字符由固定长度的 16 位(2 字节)表示。UCS-2 表示可能的最大长度为 65，536 个字符，或者从 0000h–FFFFh(2 字节)开始的十六进制数。

PLSQL 中的 LENGTH2 函数接受的 char 可以是任何数据类型，如 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。LENGTH2 函数返回的值是数据类型 NUMBER。如果在参数中发送的 char 具有数据类型 CHAR，则长度包括所有尾随空格。如果 char 为 null，那么这个函数返回 null。

**语法:**

```sql
LENGTH2( string )
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
   dbms_output.put_line(LENGTH2(Test_String)); 

END;    
```

**输出:**

```sql
NULL 
```

**例-2:**

```sql
DECLARE 
   Test_String string(20) := '';

BEGIN 
   dbms_output.put_line(LENGTH2(Test_String)); 

END;    
```

**输出:**

```sql
NULL 
```

**例-3:**

```sql
DECLARE 
   Test_String string(20) := ' ';

BEGIN 
   dbms_output.put_line(LENGTH2(Test_String)); 

END;    
```

**输出:**

```sql
1 
```

**例-4:**

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(LENGTH2(Test_String)); 

END;     
```

**输出:**

```sql
13 
```

**例-5:**

```sql
DECLARE 
   Test_String string(20) := ' Geeksforgeeks ';

BEGIN 
   dbms_output.put_line(LENGTH2(Test_String)); 

END;     
```

**输出:**

```sql
15 
```