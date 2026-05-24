# SQL |字符串函数

> 原文:[https://www.geeksforgeeks.org/sql-string-functions/](https://www.geeksforgeeks.org/sql-string-functions/)

**字符串函数**
用于对输入字符串执行操作并返回输出字符串。
以下是 SQL 中定义的字符串函数:

1.  **ASCII():** This function is used to find the ASCII value of a character.

    ```sql
    Syntax: SELECT ascii('t');
    Output: 116
    ```

2.  **CHAR_LENGTH():** 不适用于 SQL Server。对 SQL Server 使用 LEN()。这个函数用来查找单词的长度。

    ```sql
    Syntax: SELECT char_length('Hello!');
    Output: 6
    ```

3.  **字符长度():**不适用于 SQL Server。对 SQL Server 使用 LEN()。这个函数用来求一条线的长度。

    ```sql
    Syntax: SELECT CHARACTER_LENGTH('geeks for geeks');
    Output: 15
    ```

4.  **CONCAT():** 此函数用于添加两个单词或字符串。

    ```sql
    Syntax: SELECT 'Geeks' || ' ' || 'forGeeks' FROM dual;
    Output: ‘GeeksforGeeks’
    ```

5.  **CONCAT_WS():** 该函数用于添加两个单词或字符串，其中一个符号作为连接符号。

    ```sql
    Syntax: SELECT CONCAT_WS('_', 'geeks', 'for', 'geeks');
    Output: geeks_for_geeks
    ```

6.  **FIND_IN_SET():** 此函数用于从一组符号中查找一个符号。

    ```sql
    Syntax: SELECT FIND_IN_SET('b', 'a, b, c, d, e, f');
    Output: 2
    ```

7.  **FORMAT():** 该功能用于显示给定格式的数字。

    ```sql
    Syntax: Format("0.981", "Percent");
    Output: ‘98.10%’
    ```

8.  **INSERT():** 该函数用于将数据插入数据库。

    ```sql
    Syntax: INSERT INTO database (geek_id, geek_name) VALUES (5000, 'abc');
    Output: successfully updated
    ```

9.  **INSTR():** 这个函数用来查找一个字母表的出现。

    ```sql
    Syntax: INSTR('geeks for geeks', 'e');
    Output: 2 (the first occurrence of ‘e’)
    ```

    ```sql
    Syntax: INSTR('geeks for geeks', 'e', 1, 2 );
    Output: 3 (the second occurrence of ‘e’)
    ```

10.  **LCASE():** 此函数用于将给定字符串转换为小写。

    ```sql
    Syntax: LCASE ("GeeksFor Geeks To Learn");
    Output: geeksforgeeks to learn
    ```

11.  **LEFT():** 该函数用于从给定大小或字符的左边选择子字符串。

    ```sql
    Syntax: SELECT LEFT('geeksforgeeks.org', 5);
    Output: geeks
    ```

12.  **LENGTH():** 这个函数用来求一个单词的长度。

    ```sql
    Syntax: LENGTH('GeeksForGeeks');
    Output: 13
    ```

13.  **LOCATE():** 这个函数用来查找给定单词在字符串中的第 n 个位置。

    ```sql
    Syntax: SELECT LOCATE('for', 'geeksforgeeks', 1);
    Output: 6
    ```

14.  **LOWER():** 此函数用于将大写字符串转换为小写。

    ```sql
    Syntax: SELECT LOWER('GEEKSFORGEEKS.ORG');
    Output: geeksforgeeks.org
    ```

15.  **LPAD():** 这个函数通过给定的符号相加，使给定的字符串具有给定的大小。

    ```sql
    Syntax: LPAD('geeks', 8, '0');
    Output:
    000geeks
    ```

16.  **LTRIM():** 此函数用于从原始字符串中剪切给定的子字符串。

    ```sql
    Syntax: LTRIM('123123geeks', '123');
    Output: geeks
    ```

17.  **MID():** 这个功能是从给定的位置找到给定大小的单词。

    ```sql
    Syntax: Mid ("geeksforgeeks", 6, 2);
    Output: for
    ```

18.  **POSITION():** 该函数用于查找给定字母表中第一个出现的位置。

    ```sql
    Syntax: SELECT POSITION('e' IN 'geeksforgeeks');
    Output: 2
    ```

19.  **REPEAT():** 这个函数用来反复写给定的字符串，直到提到的次数。

    ```sql
    Syntax: SELECT REPEAT('geeks', 2);
    Output: geeksgeeks
    ```

20.  **REPLACE():** 该函数用于通过移除给定的子字符串来切割给定的字符串。

    ```sql
    Syntax: REPLACE('123geeks123', '123');
    Output: geeks
    ```

21.  **REVERSE():** 此函数用于反转字符串。

    ```sql
    Syntax: SELECT REVERSE('geeksforgeeks.org');
    Output: ‘gro.skeegrofskeeg’
    ```

22.  **RIGHT():** 该函数用于从给定大小的右端选择子字符串。

    ```sql
    Syntax: SELECT RIGHT('geeksforgeeks.org', 4);
    Output: ‘.org’
    ```

23.  **RPAD():** 这个函数是通过在右边加上给定的符号，让给定的字符串和给定的大小一样长。

    ```sql
    Syntax: RPAD('geeks', 8, '0');
    Output: ‘geeks000’
    ```

24.  **RTRIM():** This function is used to cut the given sub string from the original string.

    ```sql
    Syntax: RTRIM('geeksxyxzyyy', 'xyz');
    Output: ‘geeks’
    ```

25.  **SPACE():** 这个函数用来写给定的空格数。

    ```sql
    Syntax: SELECT SPACE(7);
    Output: ‘       ‘
    ```

26.  **STRCMP():** 此函数用于比较 2 个字符串。

    ```sql
    Syntax: SELECT STRCMP('google.com', 'geeksforgeeks.com');
    Output: -1
    ```

    *   如果 string1 和 string2 相同，STRCMP 函数将返回 0。
    *   如果 string1 小于 string2，STRCMP 函数将返回-1。
    *   如果 string1 大于 string2，STRCMP 函数将返回 1。
27.  **SUBSTR():** 这个函数用于从给定位置的字符串中找到一个子字符串。

    ```sql
    Syntax:SUBSTR('geeksforgeeks', 1, 5);
    Output: ‘geeks’
    ```

28.  **SUBSTRING():** 这个函数用于从提到的大小和给定的字符串中找到一个字母表。

    ```sql
    Syntax: SELECT SUBSTRING('GeeksForGeeks.org', 9, 1);
    Output: ‘G’
    ```

29.  **SUBSTRING_INDEX():** 这个函数用来在给定的符号前查找一个子字符串。

    ```sql
    Syntax: SELECT SUBSTRING_INDEX('www.geeksforgeeks.org', '.', 1);
    Output: ‘www’
    ```

30.  **TRIM():** 该功能用于从字符串中剪切给定的符号。

    ```sql
    Syntax: TRIM(LEADING '0' FROM '000123');
    Output: 123
    ```

31.  **UCASE():** 此功能用于使字符串大写。

    ```sql
    Syntax: UCASE ("GeeksForGeeks");
    Output:
    GEEKSFORGEEKS
    ```