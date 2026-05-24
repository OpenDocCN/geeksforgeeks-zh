# 打印 PL/SQL 中所有奇数及其从 1 到 n 的和

> 原文:[https://www . geesforgeks . org/print-all-奇数及其从 1 到 n 的和-in-pl-sql/](https://www.geeksforgeeks.org/print-all-odd-numbers-and-their-sum-from-1-to-n-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个数字 N，任务是显示从 1 到 N 的所有奇数及其总和。

示例:

```sql
Input: 3
Output: 1, 3

Input: 5
Output: 1, 3, 5

```

方法是用 1 初始化一个*数*，用 0 初始化*和*，继续用 2 递增*数*，用*数*递增*数*，直到数< = n。

```sql
-- display all odd number from 1 to n
DECLARE
    -- declare variable num
    num NUMBER(3) := 1;
    sum1 NUMBER(4) := 0;
BEGIN
    WHILE num <= 5 LOOP
        -- display odd number
        dbms_output.Put_line(num);

        -- the sum of all odd numbers
         sum1 := sum1 + num;

        --next odd number
        num := num + 2;

    -- end  loop
    END LOOP;
dbms_output.Put_line('Sum of all odd numbers is '|| sum1);
END;  
```

=>