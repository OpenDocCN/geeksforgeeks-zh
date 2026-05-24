# PL/SQL 中给定字符串中元音和辅音的个数

> 原文:[https://www . geesforgeks . org/给定字符串中元音和辅音的数量-pl-sql/](https://www.geeksforgeeks.org/no-of-vowels-and-consonants-in-a-given-string-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个字符串，任务是找出字符串中元音和辅音的数量。
**例:**

```sql
Input: str = 'Ramesh'
Output: Vowels = 2, Consonants = 4

Input: str = 'Ramesh is a Geek'
Output: Vowels = 6, Consonants = 7

```

**方法**是逐个考虑一个字符，并保持元音和辅音的单独计数。

以下是所需的实现:

```sql
DECLARE 
    -- Here variable V is varchar datatype  
    -- and  flag variable is number datatype   
    -- variable c is char datatype .  
    v              VARCHAR2(400) := 'Ramesh is a Geek'; 
    noofvowels     NUMBER := 0; 
    noofconsonants NUMBER := 0; 
    C              CHAR; 
BEGIN 
    FOR i IN 1..Length(v) LOOP 
        c := Substr(v, i, 1); 

        -- Check if the current character is vowel 
        IF c IN ( 'A', 'E', 'I', 'O', 'U' ) 
            OR c IN ( 'a', 'e', 'i', 'o', 'u' ) THEN 
          noofvowels := noofvowels + 1; 

        -- Else current character is a consonant except space 
        ELSE 
          IF c NOT IN ( ' ' ) THEN 
            noofconsonants := noofconsonants + 1; 
          END IF; 
        END IF; 
    END LOOP; 

    dbms_output.Put_line('No. of Vowels: ' 
                         || noofvowels); 

    dbms_output.Put_line('No. of Consonants: ' 
                         || noofconsonants); 
END; 
-- Program End  
```

**输出:**

```sql
No. of Vowels: 6
No. of Consonants: 7

```