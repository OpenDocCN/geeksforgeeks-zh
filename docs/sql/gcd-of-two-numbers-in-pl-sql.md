# PL/SQL 中两个数的 GCD

> 原文:[https://www.geeksforgeeks.org/gcd-of-two-numbers-in-pl-sql/](https://www.geeksforgeeks.org/gcd-of-two-numbers-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定两个数字，任务是找出数字的最大公约数或最高公约数。
**例:**

```sql
Input:  num1 = 4, num2 = 6
Output: gcd of (num1, num2) = 2

Input: num1 = 8, num2 = 48
Output: gcd of (num1, num2) = 8

```

**逼近**就是取两个数字，用[欧几里德](https://www.geeksforgeeks.org/euclidean-algorithms-basic-and-extended/)算法求出它们的 GCD 值。

以下是所需的实现:

```sql
DECLARE 

    -- declare variable num1, num2 and t 
    -- and these three variables datatype are integer  
    num1 INTEGER; 
    num2 INTEGER; 
    t    INTEGER; 
BEGIN 
    num1 := 8; 

    num2 := 48; 

    WHILE MOD(num2, num1) != 0 LOOP 
        t := MOD(num2, num1); 

        num2 := num1; 

        num1 := t; 
    END LOOP; 

    dbms_output.Put_line('GCD of ' 
                         ||num1 
                         ||' and ' 
                         ||num2 
                         ||' is ' 
                         ||num1); 
END; 

-- Program End 
```

**输出:**

```sql
GCD of 8 and 48 is 8

```