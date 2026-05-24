# 打印 PL/SQL 中从 1 到 n 的所有偶数

> 原文:[https://www . geesforgeks . org/print-all-偶数-从-1 到-n-in-pl-sql/](https://www.geeksforgeeks.org/print-all-even-numbers-from-1-to-n-in-pl-sql/)

先决条件- [PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)

在 PL/SQL 代码中，命令组排列在一个块中。它将相关的声明或语句组合在一起。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定一个数字 N，任务是显示所有偶数及其从 1 到 N 的和

示例:

```sql
Input: N = 3
Output: 2
Sum = 2

Input: N = 5
Output: 2, 4
Sum = 6

```

**方法**是用 2 初始化一个数*数*，并不断增加 2，直到数为< = n.
下面是它的实现:

```sql
-- Display all even number from 1 to n
DECLARE
    -- Declare variable num
    num NUMBER(3) := 2;
    sum1 NUMBER(4) := 0;
BEGIN
    WHILE num <= 5 LOOP

        -- Display even number
        dbms_output.Put_line(num);

        -- Sum of even numbers
        sum1 := sum1 + num;

        -- Next even number
        num := num + 2;

    -- End  loop
    END LOOP;

    -- Display even number
        dbms_output.Put_line('Sum of even numbers is ' || sum1);
END;
```

输出:

```sql
2
4
Sum of even numbers is 6

```

=>