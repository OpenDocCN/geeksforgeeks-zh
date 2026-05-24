# PL/SQL 中的异常处理

> 原文:[https://www.geeksforgeeks.org/exception-handling-plsql/](https://www.geeksforgeeks.org/exception-handling-plsql/)

异常是指中断程序指令正常流程的错误。PL/SQL 为我们提供了引发异常的异常块，从而帮助程序员发现错误并解决它。

PL/SQL 中定义了两种类型的异常

1.  用户定义的异常。
2.  系统定义的异常。

编写异常的语法

```sql
WHEN exception THEN 
    statement;

```

> 声明
> 声明部分；
> 
> 开始
> 可执行命令；
> 
> 异常
> 当异常 1 时，则
> 陈述 1；
> 当例外 2 然后
> 陈述 2；
> 【当别人接着】
> /*默认异常处理代码*/
> 
> END

**注意:**
**当其他**关键字应该只在异常处理块的末尾使用，因为后面没有异常处理部分将被执行，因为控件将在执行当其他之后退出该块。

*   **系统定义的异常:
    这些异常是在 PL/SQL 中预定义的，当违反某些**数据库规则时会引发。**
    系统定义的异常进一步分为两类:

    ***   命名的系统异常:它们具有系统预定义的名称，如 ACCESS_INTO_NULL、DUP_VAL_ON_INDEX、LOGIN_DENIED 等。名单很大。

        因此,我们将讨论一些最常用的异常:

        让我们创建一个极客表

        ```sql
        create table geeks(g_id int , g_name varchar(20), marks int); 
        insert into geeks values(1, 'Suraj',100);
        insert into geeks values(2, 'Praveen',97);
        insert into geeks values(3, 'Jessie', 99);

        ```

        ![](img/de9090741e3c48cfb883c82cef99a6bc.png)

        1.  **NO _ DATA _ FOUND**:SELECT INTO 语句返回 *no* 行时引发。例如:

            ```sql
            DECLARE
               temp varchar(20);

            BEGIN
               SELECT g_id into temp from geeks where g_name='GeeksforGeeks';

            exception
               WHEN no_data_found THEN
                  dbms_output.put_line('ERROR');
                  dbms_output.put_line('there is no name as');
                  dbms_output.put_line('GeeksforGeeks in geeks table');
            end;
            ```

            输出:

            ```sql
            ERROR
            there is no name as GeeksforGeeks in geeks table

            ```

        2.  **TOO _ multi _ ROWS**:当 SELECT INTO 语句返回的*多于一行时，该语句被引发。

            ```sql
            DECLARE
               temp varchar(20);

            BEGIN

            -- raises an exception as SELECT 
            -- into trying to return too many rows
               SELECT g_name into temp from geeks;
               dbms_output.put_line(temp);

            EXCEPTION
               WHEN too_many_rows THEN
                  dbms_output.put_line('error trying to SELECT too many rows');

            end;
            ```

            输出:

            ```sql
            error trying to SELECT too many rows

            ```* 
        3.  ***VALUE _ ERROR**:当执行导致算术、数值、字符串、转换或约束错误的语句时，会引发此错误。这个错误主要是程序员错误或者数据输入无效造成的。

            输出:

            ```sql
            Error
            Change data type of temp to varchar(20)

            ```* 
        4.  ***ZERO _ DIVIDE**=用零除时引发异常。

            ```sql
            DECLARE
               a int:=10;
               b int:=0;
               answer int;

            BEGIN
               answer:=a/b;
               dbms_output.put_line('the result after division is'||answer);

            exception
               WHEN zero_divide THEN
                  dbms_output.put_line('dividing by zero please check the values again');
                  dbms_output.put_line('the value of a is '||a);
                  dbms_output.put_line('the value of b is '||b);
            END;
            ```

            输出:

            ```sql
            dividing by zero please check the values again
            the value of a is 10
            the value of b is 0

            ```*** 

    1.  ***命名的系统异常。***
    2.  ***未命名的系统异常。***** *   *******Unnamed system exceptions:Oracle doesn’t provide name for some system exceptions called unnamed system exceptions.These exceptions *don’t* occur frequently.These exceptions have two parts *code and an associated message*.
    The way to handle to these exceptions is to *assign name* to them using **Pragma EXCEPTION_INIT**
    Syntax:

    ```sql
    PRAGMA EXCEPTION_INIT(exception_name, -error_number);

    ```

    error_number 是预定义的，其负整数范围为-20000 到-20999。

    **示例:**

    ```sql
    DECLARE
       exp exception;
       pragma exception_init (exp, -20015);
       n int:=10;

    BEGIN 
       FOR i IN 1..n LOOP
          dbms_output.put_line(i*i);
             IF i*i=36 THEN
                RAISE exp;
             END IF;
       END LOOP;

    EXCEPTION
       WHEN exp THEN
          dbms_output.put_line('Welcome to GeeksforGeeks');

    END;
    ```

    输出:

    ```sql
    1
    4
    9
    16
    25
    36
    Welcome to GeeksforGeeks

    ```******* *   *********User defined exceptions:
    This type of users can create their own exceptions according to the need and to raise these exceptions explicitly ***raise*** command is used.

    *示例:*

    *   Divide non-negative integer x by y such that the result is greater than or equal to 1.

        从给定的问题我们可以得出结论，存在两个例外

        *   除法为零。
        *   如果结果大于或等于 1，则表示 y 小于或等于 x。

        ```sql
        DECLARE
           x int:=&x; /*taking value at run time*/
           y int:=&y;
           div_r float;
           exp1 EXCEPTION;
           exp2 EXCEPTION;

        BEGIN
           IF y=0 then
               raise exp1;

           ELSEIF y > x then
              raise exp2;

           ELSE
              div_r:= x / y;
              dbms_output.put_line('the result is '||div_r);

           END IF;

        EXCEPTION
           WHEN exp1 THEN
              dbms_output.put_line('Error');
              dbms_output.put_line('division by zero not allowed');

           WHEN exp2 THEN
              dbms_output.put_line('Error');
              dbms_output.put_line('y is greater than x please check the input');

        END;
        ```

        ```sql
        *Input 1:* x = 20
                 y = 10

        *Output:* the result is 2

        ```

        ```sql
        *Input 2:* x = 20
                 y = 0

        *Output:*
        Error
        division by zero not allowed

        ```

        ```sql
        *Input 3:* x=20
                 y = 30

        *Output:<.em>
        Error
        y is greater than x please check the input* 
        ```

    **RAISE _ APPLICATION _ ERROR**:
    用于显示用户自定义的错误信息，错误号的范围在-20000 到-20999 之间。当 RAISE_APPLICATION_ERROR 执行时，它会返回错误消息和错误代码，看起来**与甲骨文内置错误相同。**

    **示例:**

    ```sql
    DECLARE
        myex EXCEPTION;
        n NUMBER :=10;

    BEGIN
        FOR i IN 1..n LOOP
        dbms_output.put_line(i*i);
            IF i*i=36 THEN
            RAISE myex;
            END IF;
        END LOOP;

    EXCEPTION
        WHEN myex THEN
            RAISE_APPLICATION_ERROR(-20015, 'Welcome to GeeksForGeeks');

    END;
    ```

    输出:

    ```sql
    Error report:
    ORA-20015: Welcome to GeeksForGeeks
    ORA-06512: at line 13

    1
    4
    9
    16
    25
    36

    ```

    **注意:**输出基于 Oracle Sql developer，如果您在其他地方运行这段代码，输出*订单*可能会改变。

    **异常处理中的范围规则**:

    1.  我们不能两次声明一个异常，但是我们可以在**两个不同的街区声明相同的*异常。***
    2.  *一个块内声明的异常是该块的本地*和其所有子块的全局*。***

    ***由于块只能引用局部或全局异常，封闭块不能引用子块中声明的异常。
    如果我们在一个子块中重新声明一个全局异常，局部声明优先，即局部的范围更多。***

    *****示例:*****

    ```sql
    ***DECLARE
       GeeksforGeeks EXCEPTION;
       age NUMBER:=16;
    BEGIN

       --  sub-block BEGINs 
       DECLARE       

          -- this declaration prevails 
          GeeksforGeeks  EXCEPTION;  
          age NUMBER:=22;

       BEGIN
          IF age > 16 THEN
             RAISE GeeksforGeeks; /* this is not handled*/
          END IF;

       END;          
       -- sub-block ends

    EXCEPTION
      -- Does not handle raised exception 
      WHEN GeeksforGeeks THEN
        DBMS_OUTPUT.PUT_LINE
          ('Handling  GeeksforGeeks exception.');

      WHEN OTHERS THEN
        DBMS_OUTPUT.PUT_LINE
          ('Could not recognize exception GeeksforGeeks  in this scope.');
    END;***
    ```

    ***输出:***

    ```sql
    ***Could not recognize exception GeeksforGeeks  in this scope.*** 
    ```

    *****优势:*****

    *   ***Exception handling is very useful for error handling, without it we have to issue the command at every point to check for execution errors:
        **Example:**

        ```sql
        Select ..
        .. check for 'no data found' error
        Select ..
        .. check for 'no data found' error
        Select .. 
        .. check for 'no data found' error

        ```

        这里我们可以看到它不是**健壮的**，因为错误处理没有与正常处理分开，如果我们错过了代码中的某一行，它可能会导致其他类型的错误。*** 
    *   ***通过异常处理，我们无需多次编写语句即可处理错误，甚至可以在一个异常块中处理不同类型的错误:
        **示例:**

        ```sql
        BEGIN
           SELECT ...
           SELECT ...
           SELECT ...
            .
            .
            .
        exception 
           WHEN NO_DATA_FOUND THEN  /* catches all 'no data found' errors */
             ...
           WHEN ZERO_DIVIDE THEN    /* different types of */
           WHEN value_error THEN    /* errors handled in same block */
           ...   

        ```************ 

***********从上面的代码中，我们可以得出异常处理***********

1.  ***********通过让我们隔离错误处理例程来提高可读性，从而提供健壮性。***********
2.  ***********提供**可靠性**，不需要在每个点检查不同类型的错误，我们可以简单地将它们写入异常块，如果存在错误，将会引发异常，从而帮助程序员找出错误类型并最终解决它。***********

*************用途**:其中一个真实 lIFe 用途的异常可以在网上的列车预约系统中找到。
在填写车站代码订票时，如果我们输入了错误的代码，它会向我们显示数据库中不存在该代码的异常。***********

*************参考:**这里可以找到所有预定义异常的列表。
[预定义例外总数](https://stackoverflow.com/questions/1974338/where-can-i-find-a-complete-list-of-predefined-oracle-pl-sql-exceptions?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa)***********