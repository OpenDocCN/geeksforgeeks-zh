# PLSQL | CONVERT 函数

> 原文:[https://www.geeksforgeeks.org/plsql-convert-function/](https://www.geeksforgeeks.org/plsql-convert-function/)

PL/SQL 中的字符串实际上是具有可选大小规格的字符序列。
字符可以是数字、字母、空白、特殊字符或所有字符的组合。
PLSQL 中的 CONVERT 函数用于将字符串从一个字符集转换为另一个字符集。
通常，目标字符集包含源字符集定义的所有字符的表示。
如果在任何情况下，目标字符集中不存在字符，则会出现替换字符。这些替换字符可以被定义为字符集定义的一部分。

**语法:**

```sql
CONVERT( string1, char_set_to [, char_set_from] )
```

**使用的参数–**

1.  **字符串 1–**
    用于指定要转换的字符串。它可以是任何数据类型 CHAR、VARCHAR2、NCHAR、NVARCHAR2、CLOB 或 NCLOB。
2.  **char _ set _ to–**
    用于指定字符串需要转换到的字符集。
3.  **char _ set _ from–**
    这是一个可选参数，用于指定字符串需要转换的字符集。

**注意–**目标和源字符集参数可以是文字，也可以是包含字符集名称的列。

**可用字符集:**

*   美国 7 位 ASCII 字符集
*   WE8DEC:西欧 8 位字符集
*   WE8HP:惠普西欧激光打印机 8 位字符集
*   F7DEC : DEC 法语 7 位字符集
*   WE8EBCDIC500 : IBM 西欧 EBCDIC 代码页 500
*   WE8PC850 : IBM 个人电脑代码页 850
*   WE8ISO8859P1 : ISO 8859-1 西欧 8 位字符集

**支持的 Oracle/PLSQL 版本:**

1.  Oracle 12c
2.  Oracle 11g
3.  Oracle 10g
4.  Oracle 9i 发行版
5.  Oracle 8i 发行版

**示例:**

```sql
DECLARE 
   Test_String string(10) := 'A B C D';
   Test_String2 string(20) := 'E Ä Ê Í';

BEGIN 
   dbms_output.put_line(CONVERT(Test_String, 'US7ASCII', 'WE8ISO8859P1')); 
   dbms_output.put_line(CONVERT(Test_String2, 'US7ASCII')); 

END;  
```

**输出:**

```sql
A B C D
E A E I
```