# SQL |字符函数示例

> 原文:[https://www . geesforgeks . org/SQL-character-functions-examples/](https://www.geeksforgeeks.org/sql-character-functions-examples/)

字符函数接受字符输入，并可以返回字符或数字值作为输出。SQL 提供了许多不同的字符数据类型，包括–CHAR、VARCHAR、VARCHAR2、LONG、RAW 和 LONG RAW。各种数据类型分为三种不同的数据类型:

1.  **varchar 2**–一种可变长度的字符数据类型，其数据由关系数据库管理系统转换。
2.  **CHAR**–固定长度的数据类型。
3.  **原始数据**–一种可变长度数据类型，其数据不被关系数据库管理系统转换，而是以“原始”形式保留。

**注意:**当一个字符函数返回一个字符值时，该值总是 VARCHAR2(可变长度)类型，有以下两个例外:UPPER 和 LOWER。这些函数分别转换为大写和小写，如果它们被调用转换的字符串是**固定长度** CHAR 参数，则返回 CHAR 值(固定长度)。

**字符功能**

SQL 提供了一组丰富的字符函数，允许您获取关于字符串的信息，并以多种方式修改这些字符串的内容。字符函数有以下两种类型:
1。案例控制功能(下限、上限和上限)
2。字符控制功能(多联、长度、子字符串、内部字符串、LPAD、RPAD、微调和替换)

**案例操纵功能**

1.  **LOWER :** 此函数将字母字符值转换为小写。如果传入的字符串是固定长度的，LOWER 实际上会返回一个固定长度的字符串。LOWER 不会更改字符串中非字母的任何字符，因为大小写与数字和特殊字符无关，例如美元符号($)或模数(%)。
    **语法:**

    ```sql
    LOWER(SQL course)
    ```

    ```sql
    Input1: SELECT LOWER('GEEKSFORGEEKS') FROM DUAL;
    Output1: geeksforgeeks

    Input2: SELECT LOWER('DATABASE@456') FROM DUAL;
    Output2: database@456
    ```

2.  **UPPER :** 该函数将字母字符值转换为大写。如果传入的字符串是固定长度的，那么 UPPER 函数实际上会返回一个固定长度的字符串。UPPER 不会更改字符串中非字母的任何字符，因为大小写与数字和特殊字符无关，例如美元符号($)或模数(%)。
    **语法:**

    ```sql
    UPPER(SQL course)
    ```

    ```sql
    Input1: SELECT UPPER('geeksforgeeks') FROM DUAL;
    Output1: GEEKSFORGEEKS

    Input2: SELECT UPPER('dbms$508%7') FROM DUAL;
    Output2: DBMS$508%7
    ```

3.  **INITCAP :** 该函数将每个单词的第一个字母的字母字符值转换为大写，所有其他字符值转换为小写。字符串 is 中的单词必须用#或 _ 或空格分隔。
    **语法:**

    ```sql
    INITCAP(SQL course)
    ```

    ```sql
    Input1: SELECT INITCAP('geeksforgeeks is a computer science portal for geeks') FROM DUAL;
    Output1: Geeksforgeeks Is A Computer Science Portal For Geeks 

    Input2: SELECT INITCAP('PRACTICE_CODING_FOR_EFFICIENCY') FROM DUAL;
    Output2: Practice_Coding_For_Efficiency
    ```

**字符控制功能**

1.  **CONCAT :** 这个函数总是在 string1 的末尾追加(连接)string2。如果任一字符串为空，CONCAT 函数返回非空参数。如果两个字符串都为空，CONCAT 将返回空值。
    **语法:**

    ```sql
     CONCAT('String1', 'String2')
    ```

    ```sql
    Input1: SELECT CONCAT('computer' ,'science') FROM DUAL;
    Output1: computerscience

    Input2: SELECT CONCAT( NULL ,'Android') FROM DUAL;
    Output2: Android 

    Input3: SELECT CONCAT( NULL ,NULL ) FROM DUAL;
    Output3: - 
    ```

2.  **长度:**该函数返回输入字符串的长度。如果输入字符串为空，那么 LENGTH 函数返回空值而不是零。此外，如果输入字符串在开头、中间或结尾包含额外的空格，那么 LENGTH 函数也会包含额外的空格，并返回字符串的完整长度。
    **语法:**

    ```sql
    LENGTH(Column|Expression)
    ```

    ```sql
    Input1: SELECT LENGTH('Learning Is Fun') FROM DUAL;
    Output1: 15 

    Input2: SELECT LENGTH('   Write an Interview  Experience ') FROM DUAL;
    Output2: 34

    Input3: SELECT LENGTH('') FROM DUAL; or SELECT LENGTH( NULL ) FROM DUAL;
    Output3: - 
    ```

3.  **SUBSTR :** 这个函数返回一个字符串从给定的起点到终点的一部分。如果没有给定子字符串长度，那么 SUBSTR 将返回直到字符串末尾(从指定的起始位置)的所有字符。
    **语法:**

    ```sql
    SUBSTR('String',start-index,length_of_extracted_string)
    ```

    ```sql
    Input1: SELECT SUBSTR('Database Management System', 9) FROM DUAL;
    Output1: Management System

    Input2: SELECT SUBSTR('Database Management System', 9, 7) FROM DUAL;
    Output2: Manage 
    ```

4.  **INSTR :** 该函数返回给定字符串中字符或字符串的数字位置。或者，你可以提供一个位置 *m* 开始搜索，字符串的出现 *n* 。此外，如果没有给出起始位置，默认情况下，它会从索引 1 开始搜索。如果在字符串中搜索后，没有找到匹配，则 INSTR 函数返回 0。

    ```sql
    Syntax: INSTR(Column|Expression, 'String', [,m], [n])
    ```

    ```sql
    Input: SELECT INSTR('Google apps are great applications','app',1,2) FROM DUAL;
    Output: 23 
    ```

5.  **LPAD 和 RPAD :** 这些功能将填充的字符串返回到左侧或右侧(根据使用情况)；于是有了“LPAD”中的“L”和“RPAD”中的“R”；到指定的长度，并使用指定的填充字符串。如果没有指定填充字符串，那么给定的字符串在左边或右边(根据使用情况)用空格填充。
    **语法:**

    ```sql
    LPAD(Column|Expression, n, 'String')
    Syntax: RPAD(Column|Expression, n, 'String')
    ```

    ```sql
    LPAD Input1: SELECT LPAD('100',5,'*') FROM DUAL;
    LPAD Output1: **100

    LPAD Input2: SELECT LPAD('hello', 21, 'geek') FROM DUAL;
    LPAD Output2: geekgeekgeekgeekhello

    RPAD Input1: SELECT RPAD('5000',7,'*') FROM DUAL;
    RPAD Output1: 5000*** 

    RPAD Input1: SELECT RPAD('earn', 19, 'money') FROM DUAL;
    RPAD Output1: earnmoneymoneymoney
    ```

6.  **修剪:**该功能从开始或结束(或两者)修剪字符串输入。如果没有指定要从字符串中修剪的字符串或字符，并且在字符串的开头或结尾存在一些额外的空间，那么这些额外的空间将被修剪掉。

    ```sql
    Syntax: 

    ```
    TRIM(Leading|Trailing|Both, trim_character FROM trim_source)
    ```sql

    ```
    Input1: SELECT TRIM('G' FROM 'GEEKS') FROM DUAL;
    Output1: EEKS

    Input2: SELECT TRIM('        geeksforgeeks   ') FROM DUAL; 
    Output2:geeksforgeeks
    ```sql

    ```

7.  **REPLACE :** This function searches for a character string and, if found, replaces it with a given replacement string at all the occurrences of the string. REPLACE is useful for searching patterns of characters and then changing all instances of that pattern in a single function call.
    If a replacement string is not given, then REPLACE function removes all the occurrences of that character string in the input string. If neither a match string nor a replacement string is specified, then REPLACE returns NULL.

    **语法:**

    ```sql
     REPLACE(Text, search_string, replacement_string)
    ```

    ```sql
    Input1: SELECT REPLACE('DATA MANAGEMENT', 'DATA','DATABASE') FROM DUAL;
    Output1: DATABASE MANAGEMENT 

    Input2: SELECT REPLACE('abcdeabcccabdddeeabcc', 'abc') FROM DUAL;            
    Output2: deccabdddeec
    ```

本文由**安西卡·戈亚尔供稿。**如果你喜欢 GeeksforGeeks 并且愿意投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。