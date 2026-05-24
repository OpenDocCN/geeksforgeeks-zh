# 在 PL/SQL 中统计一个数字的奇数和偶数

> 原文:[https://www . geesforgeks . org/count-奇数和偶数-in-number-in-pl-SQL/](https://www.geeksforgeeks.org/count-odd-and-even-digits-in-a-number-in-pl-sql/)

**先决条件**–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，命令的代码组排列在一个块内。一组相关的声明或语句。在声明部分，我们声明变量，在开始和结束部分之间，我们执行操作。
给定一个数字，任务是找出数字中出现的奇数和偶数位数。

**示例:**

```sql
Input: 123456
Output: Odd digits = 3
        Even digits = 3

Input: 246
Output: Odd digits = 0
        Even digits = 3
```

**进场**是取一个数字，逐个检查其位数，是奇数还是偶数。
**下面是需要的实现:**

## 结构化查询语言

```sql
--Odd and Even digits in a number
--in PL/SQL
DECLARE
  --num variable declared
  --num assign with a number
  num NUMBER := 123456;

  --len variable char declared
  len VARCHAR2(20);

  --cntvariable declared
  cnt1 NUMBER(5) := 0;
  cnt2 NUMBER(5) := 0;
BEGIN

  --for loop go from 1 to length of the number
  FOR i IN 1..Length(num)
  LOOP
    len := Substr(num, i, 1);
    IF mod(len, 2) != 0 THEN
      cnt1 := cnt1 + 1;
    ELSE
      cnt2:=cnt2+1;
    END IF;
  END LOOP;
  --end loop

  dbms_output.Put_line('Odd Digits: '
  || cnt1);
  dbms_output.Put_line('Even Digits: '
  || cnt2);
  --display result
END;
--end program
```

**输出:**

```sql
Odd Digits: 3
Even Digits: 3
```