# 不使用 temp

在 PL/SQL 中交换两个数字

> 原文:[https://www . geesforgeks . org/swap-two-numbers-pl SQL-不使用-temp/](https://www.geeksforgeeks.org/swap-two-numbers-plsql-without-using-temp/)

在 PL/SQL 代码中，命令组排列在一个块中。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

给定两个数字 num1 和 num2，任务是交换给定数字的值。

示例:

```sql
Input : num1  = 1000, num2 = 2000
Output : num1  = 2000, num2 = 1000

Input : num1  = 40, num2 = 20
Output : num1  = 20, num2 = 40

```

**方法 1** (使用算术运算符)
想法是在两个给定的数字中的一个中得到和。然后，可以使用求和和从求和中减去来交换数字。

```sql
DECLARE 
    -- declare variable num1, num2  
    -- of datatype number 
    num1 NUMBER; 
    num2 NUMBER; 
BEGIN 
    num1 := 1000; 

    num2 := 2000; 

    -- print result before swapping 
    dbms_output.Put_line('Before'); 

    dbms_output.Put_line('num1 = ' 
                         || num1 
                         ||' num2 = ' 
                         || num2); 

    -- swapping of numbers num1 and num2 
    num1 := num1 + num2; 

    num2 := num1 - num2; 

    num1 := num1 - num2; 

    -- print result after swapping 
    dbms_output.Put_line('After'); 

    dbms_output.Put_line('num1 = ' 
                         || num1 
                         ||' num2 = ' 
                         || num2); 
END; 
-- Program End 
```

**输出:**

```sql
Before
num1 = 1000 num2 = 2000
After
num1 = 2000 num2 = 1000

```

**方法二**乘除也可以用于对换。

```sql
DECLARE 
    -- declare variable num1, num2  
    -- of datatype number 
    num1 NUMBER; 
    num2 NUMBER; 
BEGIN 
    num1 := 1000; 

    num2 := 2000; 

    -- print result before swapping 
    dbms_output.Put_line('Before'); 

    dbms_output.Put_line('num1 = ' 
                         || num1 
                         ||' num2 = ' 
                         || num2); 

    -- swapping of numbers num1 and num2 
    num1 := num1 * num2; -- num1 now becomes 15 (1111) 

    num2 := num1 / num2; -- num2 becomes 10 (1010) 

    num1 := num1 / num2; -- num1 becomes 5 (0101) 
    -- print result after swapping 
    dbms_output.Put_line('After'); 

    dbms_output.Put_line('num1 = ' 
                         || num1 
                         ||' num2 = ' 
                         || num2); 
END; 

-- Program End 
```

**输出:**

```sql
Before
num1 = 1000 num2 = 2000
After
num1 = 2000 num2 = 1000

```