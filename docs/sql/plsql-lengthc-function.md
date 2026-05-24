# PLSQL | LENGTHC 函数

> 原文:[https://www.geeksforgeeks.org/plsql-lengthc-function/](https://www.geeksforgeeks.org/plsql-lengthc-function/)

函数的作用是:使用 UNICODE 完整字符返回指定字符串的长度。
PLSQL 中 LENGTHC 函数接受的 char 可以是任何数据类型，如 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。
length c 函数返回的值是数据类型 NUMBER。
如果参数中发送的 char 具有 CHAR 数据类型，那么长度包括所有尾随空格。如果 char 为 null，那么这个函数返回 null。

**语法:**

```sql
LENGTHC( string )
```

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
   dbms_output.put_line(LENGTHC(Test_String)); 

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
   dbms_output.put_line(LENGTHC(Test_String)); 

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
   dbms_output.put_line(LENGTHC(Test_String)); 

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
   dbms_output.put_line(LENGTHC(Test_String)); 

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
   dbms_output.put_line(LENGTHC(Test_String)); 

END;     
```

**输出:**

```sql
15 
```