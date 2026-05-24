# 检查一个字符串在 PL/SQL 中是否是回文

> 原文:[https://www . geesforgeks . org/check-a-string-is-回文-or-not-in-pl-sql/](https://www.geeksforgeeks.org/check-whether-a-string-is-palindrome-or-not-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个字符串，任务是找出它是否是回文。
**例:**

```sql
Input: str = geeksskeeg
Output: geeksskeeg is palindrome

Input: str = geeks
Output: geeks is not palindrome

```

**进场**是取弦，倒弦，检查倒弦是否与原弦相等。如果相等，则是回文，否则不是。

以下是所需的实现:

```sql
DECLARE 

    -- Declared variables are s, l, t . 
    -- These variables are of same data type VARCHAR. 
    s VARCHAR2(10) := 'abccba'; 
    l VARCHAR2(20); 
    t VARCHAR2(10); 
BEGIN 
    FOR i IN REVERSE 1..Length(s) LOOP 
        l := Substr(s, i, 1); 

        -- here || are used for concatenation of string. 
        t := t 
             ||'' 
             ||l; 
    END LOOP; 

    IF t = s THEN 
      dbms_output.Put_line(t 
                           ||'' 
                           ||' is palindrome'); 
    ELSE 
      dbms_output.Put_line(t 
                           ||'' 
                           ||' is not palindrome'); 
    END IF; 
END; 

-- Program End 
```

**输出:**

```sql
abccba is palindrome

```