# PLSQL | LOWER 函数

> 原文:[https://www.geeksforgeeks.org/plsql-lower-function/](https://www.geeksforgeeks.org/plsql-lower-function/)

PLSQL LOWER 函数用于将指定字符串中的所有字母转换为小写。如果字符串中有不是字母的字符，它们不受此函数的影响。

要转换的 char 可以是任何数据类型，如 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。LOWER 函数返回的值与 char 的数据类型相同。数据库根据为基础字符集定义的二进制映射设置字符的大小写。

**语法:**

```sql
LOWER( string )
```

**使用的参数:**

**字符串–**用于指定需要转换的字符串。

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
   dbms_output.put_line(LOWER(Test_String)); 

END;  
```

**输出:**

```sql
geeksforgeeks 
```

**例-2:**

```sql
DECLARE 
   Test_String string(20) := 'GEEKSFORGEEKS';

BEGIN 
   dbms_output.put_line(LOWER(Test_String)); 

END; 
```

**输出:**

```sql
geeksforgeeks 
```

**例-3:**

```sql
DECLARE 
   Test_String varchar2(30) := 'GEEKSFORGEEKS12345';

BEGIN 
   dbms_output.put_line(LOWER(Test_String)); 

END; 
```

**输出:**

```sql
geeksforgeeks12345 
```