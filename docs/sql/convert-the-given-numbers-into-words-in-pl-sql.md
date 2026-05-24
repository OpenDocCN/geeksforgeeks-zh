# 将给定的数字转换成 Pl/SQL 中的文字

> 原文:[https://www . geesforgeks . org/convert-the-给定数字-in-pl-sql/](https://www.geeksforgeeks.org/convert-the-given-numbers-into-words-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个数字，任务是将数字的每个数字转换成单词。
**例:**

```sql
Input: 47856
Output: Four Seven Eight Five Six

Input: 123456
Output: one two three four five six

```

**方法**是使用解码功能选择特定数字的对应字。
以下是所需的实施:

```sql
DECLARE 

    -- declare variable are num, num_to_word, str, len, c 
    -- and in above declare variable num, len, c are integer datatype  
    -- and num_to_word and str are varchar datatype 
    num         INTEGER; 
    num_to_word VARCHAR2(100); 
    str         VARCHAR2(100); 
    len         INTEGER; 
    c           INTEGER; 
BEGIN 
    num := 123456; 

    len := Length(num); 

    dbms_output.Put_line('Entered Number is: ' 
                         ||num); 

    FOR i IN 1..len LOOP 
        c := Substr(num, i, 1); 

        SELECT Decode(c, 0, 'Zero ', 
                         1, 'One ', 
                         2, 'Two ', 
                         3, 'Three ', 
                         4, 'Four ', 
                         5, 'Five ', 
                         6, 'Six ', 
                         7, 'Seven ', 
                         8, 'Eight ', 
                         9, 'Nine ') 
        INTO   str 
        FROM   dual; 

        num_to_word := num_to_word 
                       ||str; 
    END LOOP; 

    dbms_output.Put_line('Number to words: ' 
                         ||num_to_word); 
END; 

-- Program End 
```

**输出:**

```sql
Entered Number is: 123456
Number to words: One Two Three Four Five Six 

```