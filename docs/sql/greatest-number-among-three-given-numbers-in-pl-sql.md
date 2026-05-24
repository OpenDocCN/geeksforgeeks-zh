# PL/SQL 中三个给定数中最大的数

> 原文:[https://www . geesforgeks . org/三个给定数字中的最大数字-pl-sql/](https://www.geeksforgeeks.org/greatest-number-among-three-given-numbers-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。
给定三个数字，任务是找出其中最大的。

**示例:**

```sql
Input: a = 46, b = 67, c = 21
Output: 67

Input: a = 9887, b = 4554, c = 212
Output: 9887
```

**逼近**就是考虑第一个数，与其他两个数进行比较。同样，检查第二个和第三个。
以下是所需的实施:

## 结构化查询语言

```sql
--To find the greatest number
-- among given three numbers
DECLARE
    --a assigning with 46
    a NUMBER := 46;
    --b assigning with 67
    b NUMBER := 67;
    --c assigning with 21
    c NUMBER := 21;
BEGIN
    --block start
    --If condition start
    IF a > b
       AND a > c THEN
      --if a is greater then print a
      dbms_output.Put_line('Greatest number is '
                           ||a);
    ELSIF b > a
          AND b > c THEN
      --if b is greater then print b
      dbms_output.Put_line('Greatest number is '
                           ||b);
    ELSE
      --if c is greater then print c
      dbms_output.Put_line('Greatest number is '
                           ||c);
    END IF;
--end if condition
END;
--End program 
```

**输出:**

```sql
Greatest number is 67
```