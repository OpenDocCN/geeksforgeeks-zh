# 检查 PL/SQL 中给定的数字是偶数还是奇数

> 原文:[https://www . geesforgeks . org/check-给定的数字是 pl-sql 中的偶数还是奇数/](https://www.geeksforgeeks.org/check-whether-a-given-number-is-even-or-odd-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。

示例:

```sql
Input: 2 
Output: even

Input: 5
Output: odd

```

方法是将给定的数除以 2，如果余数为 0，则给定的数为偶数，否则为奇数。

以下是所需的实现:

```sql
DECLARE
    -- Declare variable n, s, r, len
    -- and m of datatype number
    n NUMBER := 1634;
    r NUMBER;
BEGIN
    -- Calculating modulo
    r := MOD(n, 2);

    IF r = 0 THEN
      dbms_output.Put_line('Even');
    ELSE
      dbms_output.Put_line('Odd');
    END IF;
END;
--End program 
```

**输出:**

```sql
Even

```