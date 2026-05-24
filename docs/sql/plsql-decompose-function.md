# PLSQL |分解函数

> 原文:[https://www.geeksforgeeks.org/plsql-decompose-function/](https://www.geeksforgeeks.org/plsql-decompose-function/)

PLSQL 中的分解函数用于接受字符串并返回其 Unicode 字符串。
分解函数通常与合成函数相反。
DEFAULT 函数仅对 Unicode 字符有效，它在与输入相同的字符集内分解后返回一个 Unicode 字符串。
根据所用操作系统的字符集，所用输入的结果可能会有所不同。

**语法:**

```sql
DECOMPOSE( string )
```

**使用的参数:**

**字符串–**用于指定需要分解的字符串。

**返回值:**
分解函数返回一个 Unicode 字符串。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版

**示例:**

```sql
DECLARE 
   Test_String2 varchar(5) := 'â';
   Test_String varchar(20) := 'Gèèksforgèèks';

BEGIN 
   dbms_output.put_line(DECOMPOSE(Test_String)); 
   dbms_output.put_line(DECOMPOSE(Test_String2)); 

END;  
```

**输出:**

```sql
a^
Ge´e´ksforge´e´ks 
```