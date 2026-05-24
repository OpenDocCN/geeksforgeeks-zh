# 统计 PL/SQL 中一个字符串的字符数和字数

> 原文:[https://www . geesforgeks . org/count-no-of-characters-in-string-in-pl-SQL/](https://www.geeksforgeeks.org/count-no-of-characters-and-words-in-a-string-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个字符串，任务是计算给定字符串中字符和单词的数量。
**例:**

```sql
Input: str = 'Geeks for geeks '
Output: Characters = 13 , Words = 3

Input: str = 'A Computer science portal'
Output: Characters = 22, Words = 4

```

**方法**是保持两个计数器变量，即一个用于字符，另一个用于单词。开始逐个遍历字符并增加计数，当有空格时，增加字数。
**下面是需要的实现:**

```sql
DECLARE 
    -- Declare required variables 
    str       VARCHAR2(40) := 'Geeks for Geeks'; 
    noofchars NUMBER(4) := 0; 
    noofwords NUMBER(4) := 1; 
    s         CHAR; 
BEGIN 
    FOR i IN 1..Length(str) LOOP 
        s := Substr(str, i, 1); 

        -- Count no. of characters 
        noofchars := noofchars + 1; 

        -- Count no. of words 
        IF s = ' ' THEN 
          noofwords := noofwords + 1; 
        END IF; 
    END LOOP; 

    dbms_output.Put_line('No. of characters:' 
                         ||noofchars); 

    dbms_output.Put_line('No. of words: ' 
                         ||noofwords); 
END; 
-- Program End  
```

**输出:**

```sql
No. of characters:15
No. of words: 3

```