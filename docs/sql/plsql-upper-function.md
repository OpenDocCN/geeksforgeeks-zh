# PLSQL |上位函数

> 原文:[https://www.geeksforgeeks.org/plsql-upper-function/](https://www.geeksforgeeks.org/plsql-upper-function/)

**PLSQL UPPER 函数**用于将指定字符串中的所有字母转换为大写。如果字符串中有不是字母的字符，它们不受此函数的影响。

要转换的 char 可以是任何数据类型，如 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。UPPER 函数返回的值与 char 的数据类型相同。数据库根据为基础字符集定义的二进制映射设置字符的大小写。

**语法:**

```sql
UPPER( string )
```

**使用的参数:**

**字符串–**用于指定需要转换的字符串。

**返回值:**
PLSQL 中的 UPPER 函数返回一个字符串值。

**支持的 Oracle/PLSQL 版本**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:** 将字符串作为参数传递，第一个字符为大写，其余字符为小写。

```sql
DECLARE 
   Test_String string(20) := 'Geeksforgeeks';

BEGIN 
   dbms_output.put_line(UPPER(Test_String)); 

END;  
```

**输出:**

```sql
GEEKSFORGEEKS 
```

**示例-2:** 传递一个字符串作为参数，所有字符都是小写的。

```sql
DECLARE 
   Test_String string(20) := 'geeksforgeeks';

BEGIN 
   dbms_output.put_line(UPPER(Test_String)); 

END;   
```

**输出:**

```sql
GEEKSFORGEEKS 
```

**示例-3:** 将字符串作为参数传递，数值和字符为小写。

```sql
DECLARE 
   Test_String string(20) := '123geeksforgeeks123';

BEGIN 
   dbms_output.put_line(UPPER(Test_String)); 

END; 
```

**输出:**

```sql
123GEEKSFORGEEKS123 
```

**优势:**
UPPER 函数接受 input_string 中的任何数据类型 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。