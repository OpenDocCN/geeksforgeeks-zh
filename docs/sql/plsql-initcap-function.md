# PLSQL | INITCAP 函数

> 原文:[https://www.geeksforgeeks.org/plsql-initcap-function/](https://www.geeksforgeeks.org/plsql-initcap-function/)

PLSQl 中的 INITCAP 函数用于将每个单词中的第一个字符设置为大写，其余字符设置为小写。
单词由空格或非字母数字字符分隔。
PLSQL 中的 INITCAP 函数可以接受任何数据类型的 char can，例如 char、VARCHAR2、NCHAR 或 NVARCHAR2。INITCAP 函数返回的值与 char 的数据类型相同。数据库根据为基础字符集定义的二进制映射设置初始字符的大小写。

**语法:**

```sql
INITCAP(string)
```

**使用的参数:**

**字符串:**用于指定每个单词中第一个字符将转换为大写，其余所有字符转换为小写的字符串。

**返回值:**
PLSQL 中的 INITCAP 函数返回一个字符串值。

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例-1:**

```sql
DECLARE 
   Test_String string(20) := 'geeksforgeeks';

BEGIN 
   dbms_output.put_line(INITCAP(Test_String)); 

END; 
```

**输出:**

```sql
Geeksforgeeks 
```

**例-2:**

```sql
DECLARE 
   Test_String string(40) := 'Hello, welcome to geeksforgeeks.';

BEGIN 
   dbms_output.put_line(INITCAP(Test_String)); 

END; 
```

**输出:**

```sql
Hello, Welcome To Geeksforgeeks. 
```