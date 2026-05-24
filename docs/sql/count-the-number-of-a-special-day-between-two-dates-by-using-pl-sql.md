# 用 PL/SQL

统计两个日期之间特殊的一天的次数

> 原文:[https://www . geeksforgeeks . org/通过使用-pl-sql/](https://www.geeksforgeeks.org/count-the-number-of-a-special-day-between-two-dates-by-using-pl-sql/) 计算两个日期之间的特殊天数

前提–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)、[PL/SQL 中的决策](https://www.geeksforgeeks.org/decision-making-plsql-else-nested-elsif-else/)

编写一个 pl/sql 程序来输入两个日期，并打印这两个日期之间的星期日数。

**解释:**
在循环的每次迭代之前，评估条件。如果评估为**真**，则执行语句序列。如果条件评估为**假**或**空**，循环结束，控制在**结束循环**语句后恢复。

**注意:**
简单循环和 while 循环唯一的区别就是简单先执行然后检查条件，所以简单循环至少执行一次，在 while 循环中先检查条件再执行。

**示例-1:**

```sql
Input: Enter value for date1: 01-SEP-19 
      Enter value for date2: 29-SEP-19

Output: no of Sundays : 5 
```

**示例-2:**

```sql
Input: Enter value for date1: 01-SEP-19
      Enter value for date2: 15-SEP-19

Output: no of Sundays: 3 
```

**代码:**

```sql
--declare the variables D1 and D2.
--type of variable is Date.
SQL> DECLARE
        D1 Date;
        D2 Date;
        Cnt Number:=0;
    BEGIN 
        D1:='&Date1';
        D2:='&Date2';
        D1:=next_day(D1-1, 'SUNDAY');
   --check the condition by using while loop.
        while(D1<=D2)
    LOOP
        Cnt:=Cnt+1;
        D1:=D1+7;
    END LOOP;
        dbms_output.put_line('no of Sundays:'||Cnt);
    END;
    /
--end of program
```

**输出:**

```sql
Enter value for date1: 01-SEP-19
old 5: Begin D1:='&Date1';
new 5: Begin D1:='01-SEP-19';

Enter value for date2: 29-SEP-19
old   6:  D2:='&Date2';
new   6:  D2:='29-SEP-19';
no of Sundays:5 
```

PL/SQL 过程已成功完成。

**优点:-**
通过使用 while 循环，它首先检查条件，然后执行，因此我们可以轻松地计算两个日期之间某个特殊日子的数量。