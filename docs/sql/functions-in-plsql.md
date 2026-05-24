# PL/SQL 中的函数

> 原文:[https://www.geeksforgeeks.org/functions-in-plsql/](https://www.geeksforgeeks.org/functions-in-plsql/)

函数可以用作 SQL 表达式的一部分，也就是说，我们可以将它们与选择/更新/合并命令一起使用。函数最重要的一个特征是，与过程不同，它必须返回值。

创建函数的语法:

```sql
CREATE [OR REPLACE] FUNCTION function_name 
[(parameter_name  type [, ...])] 

// this statement  is must for functions 
RETURN return_datatype  
{IS | AS} 

BEGIN 
    // program code

[EXCEPTION
   exception_section;

END [function_name];

```

**示例:**

1.  我们必须找到学生在一所学校的不同部分使用函数
    的总强度

```sql
// first lets create a table
create table section(s_id int, s_name varchar(20), strength int );

// Inserting values into table
insert into section values(1, 'computer science', 20);
insert into section values(2, 'portal', 45);
insert into section values(3, 'geeksforgeeks', 60);

// Defining function
create or replace function totalStrength

// Defining return type
return integer
as
total integer:=0;

begin                        

// calculating the sum and storing it in total 
select sum(strength) into total from section;
return total;

// closing function
end totalStrength;

set serveroutput on;

declare
answer integer;

begin
answer:=totalstrength();
   dbms_output.put_line('Total strength of students is  ' || answer);  
end;
```

**输出:**

```sql
Total strength of students is  125

```

*   Now, let’s take an example to demonstrate **Declaring, Defining and Invoking** a simple PL/SQL
    function which will compute and return the reverse of a number.

    ```sql
    set serveroutput on;
    declare

        a int;
        c int;
        n int;
       rev int:=0;
        r int;

    // Defining function 
    function reverse_it( x  IN int) 
    return  int
    as
    z int;

    // function code
    begin
        n := x;

        while (n > 0)
        loop
            r := mod(n, 10);
            rev := (rev * 10) + r;
            n := trunc(n / 10);
        end loop;

        z := rev;
        return z;

    end  ;  

    BEGIN  
       a := 123456789;    

       c := reverse_it(a);  
       dbms_output.put_line('the reverse of number is  ' || c);  

    END;  
    ```

    **输出:**

    ```sql
    the reverse of number is  987654321

    ```

    *   Lets implement a recursive function to calculate the factorial of a number
    **Recursive functions example:**

    ```sql
    DECLARE  
       num int;  
       answer int;  

    // Defining function  
    FUNCTION factorial(x number)  
    RETURN int   
    IS  
       f int;  

    BEGIN  
       IF x = 0 THEN  
          f := 1;  
       ELSE  
          f := x * factorial(x - 1);  
       END IF;  
    RETURN f;  
    END;  

    BEGIN  
       num := 5;  
       answer := factorial(num);  
       dbms_output.put_line(' Factorial of  '|| num || ' is ' || answer);  
    END;  
    ```

    *输出:*

    ```sql
     Factorial of  5 is 120

    ```

    *   Exception handling can be done using exception block in functions but exception handling using *try-catch* block cannot be done.

    示例:

    ```sql
    set serveroutput on;

    declare
    a int;
    b float;
    myexp exception;

    function  sqroot(x int)
    return float

    as
    answer float;

    begin

    if x < 0 then
    raise myexp;

    // pre-defined sqrt()  to 
    // calculate square root 
    else
    answer := SQRT(x); 

    end if;
    return answer;

    exception
    when myexp then
    dbms_output.put_line('square of negative number is  
                         not allowed so returning the same 
                         number');
    return x;
    end;

    begin
    b := sqroot(-2);
    dbms_output.put_line('the value is '|| b);
    end;
    ```

    *输出:*

    ```sql
    square of negative number is  not allowed so returning the same number
    the value is -2

    ```

    **优势:**

    1.  我们可以对数据库进行一次调用来运行一个语句块，这样可以提高多次运行 SQL 的性能。这将减少数据库和应用程序之间的调用次数。
    2.  我们可以将整个工作分成几个小模块，这变得非常容易管理，也增强了代码的可读性。
    3.  它促进了可重用性。
    4.  它是安全的，因为代码留在数据库内部，从而对应用程序(用户)隐藏内部数据库的细节。用户只调用 PL/SQL 函数。因此确保了安全性和数据隐藏。