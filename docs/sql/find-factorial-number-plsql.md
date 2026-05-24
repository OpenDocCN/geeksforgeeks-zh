# 求 pl/sql 中一个数的阶乘

> 原文:[https://www.geeksforgeeks.org/find-factorial-number-plsql/](https://www.geeksforgeeks.org/find-factorial-number-plsql/)

给定一个数字，你的任务是用 pl/sql 打印这个数字的阶乘。

**示例:**

```sql
Input : 5
Output : 120

```

**解说:**
5！= 5 * 4 * 3 * 2 * 1 = 120

```sql
Input : 4
Output : 24

```

**pl/SQL 块的基本结构**

```sql
declare
-- declare all the variables

begin  -- for start block
-- make a program here

end -- for end block

```

pl/sql 中一个数的阶乘程序如下:

```sql
declare 
-- it gives the final answer after computation
fac number :=1;   

-- given number n
-- taking input from user
n number := &1;   

-- start block
begin         

-- start while loop    
while n > 0 loop  

-- multiple with n and decrease n's value
fac:=n*fac;        
n:=n-1;           
end loop;         
-- end loop

-- print result of fac
dbms_output.put_line(fac);  

-- end the begin block
end;              
```

**输出:**(如果给定输入为 5)

```sql
120

```