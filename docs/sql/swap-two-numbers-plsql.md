# PL/SQL 中两个数字互换

> 原文:[https://www.geeksforgeeks.org/swap-two-numbers-plsql/](https://www.geeksforgeeks.org/swap-two-numbers-plsql/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。
在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

pl/sql 块的基本结构

```sql
declare
-- declare all the variables

begin  -- for start block
-- make a program here

end -- for end block
```

你已经给了两个数字 num1 和 num2，你的任务是交换给定数字的值。

示例:

```sql
Input : num1  = 1000 num2 = 2000
Output : num1  = 2000 num2 = 1000

Input : num1  = 40 num2 = 20
Output : num1  = 20 num2 = 40

```

```sql
declare

-- declare variable num1, num2 
-- and temp of datatype number
    num1 number;
    num2 number;
    temp number;

begin
    num1:=1000;
    num2:=2000;

    -- print result before swapping
    dbms_output.put_line('before');
    dbms_output.put_line('num1 = '|| num1 ||' num2 = '|| num2);

    -- swapping of numbers num1 and num2
    temp := num1;
    num1 := num2;
    num2 := temp;

   -- print result after swapping
    dbms_output.put_line('after');
    dbms_output.put_line('num1 = '|| num1 ||' num2 = '|| num2);

end;
```

输出:

```sql
before
num1  = 1000 num2 = 2000
after
num1  = 2000 num2 = 1000
```