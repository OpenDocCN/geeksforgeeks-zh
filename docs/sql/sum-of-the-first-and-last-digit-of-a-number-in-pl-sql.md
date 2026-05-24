# PL/SQL 中一个数字的第一个和最后一个数字的和

> 原文:[https://www . geesforgeks . org/pl-SQL 中数字的第一位和最后一位之和/](https://www.geeksforgeeks.org/sum-of-the-first-and-last-digit-of-a-number-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个数字 n，任务是找出它的第一个和最后一个数字的和。
**例:**

```sql
Input: 14598.
Output: Sum of the first and last digit is 9.

Input: 987456.
Output: Sum of the first and last digit is 15.

```

**方法**是使用 substr()函数，存储第一个和最后一个数字，然后打印它们的和。

以下是所需的实现:

```sql
DECLARE 
    -- declare variables are A, B,  C and S
    -- these are same datatype integer
    a INTEGER := 14598; 
    b INTEGER := 0; 
    C INTEGER := 0; 
    s INTEGER; 
BEGIN 
    IF a > 9 THEN 
      c := Substr(a, 1, 1); 

      b := Substr(a, Length(a), 1); 

      s := b + c; 
    ELSE 
      s := a; 
    END IF; 

    dbms_output.Put_line('Sum of the first and last digit is ' 
                         ||s); 
END; 
-- Program End 
```

**输出:**

```sql
Sum of the first and last digit is 9

```