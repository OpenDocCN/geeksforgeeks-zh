# PL/SQL 事务

> 原文:[https://www.geeksforgeeks.org/pl-sql-transactions/](https://www.geeksforgeeks.org/pl-sql-transactions/)

先决条件–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)、 [PL/SQL |用户输入](https://www.geeksforgeeks.org/pl-sql-user-input/)
编写一个接受用户账号的 PL/SQL 代码。检查用户余额是否少于最低余额，仅从余额中扣除 100 卢比。该进程在 acct_mstr 上触发。

**示例–**考虑以下场景:

```sql
acct_master (acct_no number(5) primary key, 
                         acct_name varchar2(10), 
                            balance number(10)); 
```

首先，您需要创建 acct_master 表，

```sql
# CREATING table acct_master 
create table acct_master(acct_no number(5) primary key, 
                                acct_name varchar2(10), 
                                   balance number(10)); 
```

将这些数据插入表中，

```sql
# INSERTING data in acct_mstr
insert into acct_master values(1, 'aaa', 1000)
insert into acct_master values(2, 'bbb', 100)
insert into acct_master values(3, 'ccc', 1100)
insert into acct_master values(4, 'ddd', 700)
insert into acct_master values(5, 'eee', 1700) 
```

**采用的方法–**

*   **步骤-1:** 声明变量，并在其中一个变量中设置最小余额。
*   **第 2 步:**取用户输入的账号。
*   **步骤-3:** 将该用户的余额选择为一个变量。
*   **步骤-4:** 检查余额是否小于最小余额。
*   **步骤-5:** 如果余额较少，则用余额=余额-100 更新表中的余额，并显示从存储余额的变量中扣除 100 后的余额。然后，显示输出。
*   **第 6 步:**否则只需打印数值。

请注意，所有绿色文本都是注释。

以下是所需的实现:

```sql
-- DECLARING VARIABLES
DECLARE 
xacct_no number(5);

-- here, minimum balance is set to 1000;
xmin_bal number(5):=1000; 
xbalance number(5);

BEGIN

-- taking input from user
xacct_no:=&xacct_no; 

-- selecting balance of that user INTO "xbalance";
select balance into xbalance 
from acct_master 
where acct_no=xacct_no; 

-- if condition true, updating balance 
-- with balance = balance - 100 
IF(xbalance < xmin_bal) THEN --condition check
update acct_master 
set balance=balance-100 
where acct_no=xacct_no; 

-- remaining amount                                                                 
xbalance:=xbalance-100; 
dbms_output.put_line('Rs 100 is deducted 
               and current balance is '||xbalance);

-- if condition is false 
ELSE             
dbms_output.put_line('Current balance is '||xbalance);

--ENDING IF 
END IF;    

-- ENDING OF BEGIN
END; 

/     -- FOR DISPLAYING OUTPUT IN SCREEN
```

**输出:**

```sql
Enter value for xacct_no: 2
old 6: xacct_no:=&xacct_no;
new 6: xacct_no:=2;
Rs 100 is deducted and current balance is 0

PL/SQL procedure successfully completed.

SQL> /
Enter value for xacct_no: 3
old   6: xacct_no:=&xacct_no;
new   6: xacct_no:=3;
Current balance is 1100

PL/SQL procedure successfully completed. 
```