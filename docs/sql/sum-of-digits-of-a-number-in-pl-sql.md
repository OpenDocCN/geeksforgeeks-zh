# PL/SQL 中一个数字的位数之和

> 原文:[https://www . geesforgeks . org/pl-SQL 中数字的总和/](https://www.geeksforgeeks.org/sum-of-digits-of-a-number-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个数字，任务是找出这个数字的位数之和。
**例:**

```sql
Input: 123456
Output: 21

Input: 9874
Output: 28

```

**逼近**就是取一个数字，用 MOD 函数得到每个数字，然后求和。

以下是所需的实现:

```sql
DECLARE 

    --Declare variable n, temp_sum  
    -- and r of datatype number 
    n        INTEGER; 
    temp_sum INTEGER; 
    r        INTEGER; 
BEGIN 
    n := 123456; 
    temp_sum := 0; 

    -- here we check condition with the help of while loop 
    -- here <> symbol represent for not null 
    WHILE n <> 0 LOOP 
        r := MOD(n, 10); 
        temp_sum := temp_sum + r; 
        n := Trunc(n / 10); 
    END LOOP; 
    dbms_output.Put_line('sum of digits = ' 
                         || temp_sum); 
END; 
-- Program End 
```

**输出:**

```sql
sum of digits = 21

```