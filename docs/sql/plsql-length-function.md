# PLSQL | LENGTH 函数

> 原文:[https://www.geeksforgeeks.org/plsql-length-function/](https://www.geeksforgeeks.org/plsql-length-function/)

PLSQL LENGTH 函数用于返回指定字符串的长度，换句话说，它返回字符的长度。PLSQL 中 LENGTH 函数接受的 char 可以是任何数据类型，如 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。

LENGTH 函数返回的值是数据类型 NUMBER。如果在参数中发送的 char 具有数据类型 CHAR，则长度包括所有尾随空格。如果 char 为 null，那么这个函数返回 null。

**语法:**

```sql
LENGTH( string )
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
   dbms_output.put_line(LENGTH(Test_String)); 

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
   dbms_output.put_line(LENGTH(Test_String)); 

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
   dbms_output.put_line(LENGTH(Test_String)); 

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
   dbms_output.put_line(LENGTH(Test_String)); 

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
   dbms_output.put_line(LENGTH(Test_String)); 

END;     
```

**输出:**

```sql
15 
```