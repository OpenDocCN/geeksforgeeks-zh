# 在 PL/SQL 中反转一个字符串

> 原文:[https://www.geeksforgeeks.org/reverse-a-string-in-pl-sql/](https://www.geeksforgeeks.org/reverse-a-string-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个字符串，任务是使用 PL/SQL 反转一个字符串。

示例:

```sql
Input: skeegrofskeeg
Output: geeksforgeeks

Input: geeks
Output: skeeg

```

**逼近:**

*   Find the length of the string.
*   Then traverse the string in the opposite way.
*   Store characters in another string.
*   Print the final string.

下面是需要的实现:

```sql
DECLARE
    -- declare variable str , len 
    -- and str1 of datatype varchar
    str  VARCHAR(20) := 'skeegrofskeeg';
    len  NUMBER;
    str1 VARCHAR(20);
BEGIN
    -- Here we find the length of string
    len := Length(str);

    -- here we starting a loop from max len to 1
    FOR i IN REVERSE 1.. len LOOP
        -- assigning the reverse string in str1               
        str1 := str1
                || Substr(str, i, 1);
    END LOOP;

    dbms_output.Put_line('Reverse of string is '
                         || str1);
END;
-- Program End 
```

**输出:**

```sql
Reverse of string is geeksforgeeks

```