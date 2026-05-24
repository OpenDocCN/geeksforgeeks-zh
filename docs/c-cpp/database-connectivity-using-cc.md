# 使用 C/C++

的数据库连接

> 原文:[https://www . geesforgeks . org/database-connectivity-use-cc/](https://www.geeksforgeeks.org/database-connectivity-using-cc/)

SQL(结构化查询语言)是第四代语言(4GL)，用于定义、操作和控制关系数据库管理系统。

在开始主要文章之前，让我们熟悉一下所使用的工具。

1.  **编译器:**代码::用 MinGW 编译器阻塞 IDE

    **下载链接:** [二进制下载](http://www.codeblocks.org/downloads/5)
    代码::Blocks 是交叉编译器(可以在 Windows、Linux、Mac 等任何平台上运行)，可以免费下载。这个 IDE 是专门为 C 和 C++ 设计的，使用方便。

2.  **API:** 我们将使用 SQLAPI++ 库

    **下载链接:** [SQLAPI 下载](http://www.sqlapi.com/Download/index.html)

    SQLAPI++ 是一个 C++ 库(基本上是一组头文件)，用于访问多个 SQL 数据库(Oracle、SQL Server、DB2、Sybase、Informix、InterBase、SQLBase、MySQL、PostgreSQL、SQLite、SQL Anywhere 和 ODBC)。它易于实现且简单。

3.  **OCCI:** Oracle C++ 调用接口

    **下载链接:** [OCCI C++ 下载](http://www.oracle.com/technetwork/database/features/oci/index-090820.html)
    OCCI 是一个由数据库公司 Oracle 定义的接口，它为 C++ 程序员定义了一个舒适的接口，使他们可以使用类似于 SQL 语句的参数访问带有类的 ORACLE 数据库。该接口适用于 ORACLE 9i、ORACLE 10 和 ORACLE。

我们必须下载并安装以上三个(如果我们没有的话)。现在我们几乎准备好开始了。

**<u>开始前的一些设置:</u>**

->打开代码::blocks IDE，转到或点击**设置** - > **编译器和调试器设置**(您现在将看到全局编译器设置)

->现在点击**链接器设置**，在链接器设置中点击添加按钮并添加以下内容

对于 **Windows 操作系统**:

**代码:**

C:\SQLAPI\lib\libsqlapiddll.a

c:\程序文件\代码块\ MinGW \库\库用户 32

c:\程序文件\代码块\ MinGW \库\库版本

c:\程序文件\代码块\MinGW\lib\liboleaut32.a

c:\程序文件\代码块\ MinGW \库\库文件 32

这些将会在你的 SQLAPI++ 中找到(如果你没有在 C: drive 中提取，那么选择适当的位置，并将提到的文件添加到链接器设置中)。

以上代码用于添加库文件，将 C/C++ 程序与 SQLAPI 连接起来。

基本上有 2 个步骤:

1.  **<u>Connecting to database (and error handling)</u>**
    **Code:**

    ```cpp
    // C++ pgroram for connecting to database (and error handling)
    #include<stdio.h>
    #include<SQLAPI.h>         // main SQLAPI++ header

    int main(int argc, char* argv[])
    {
        // create connection object to connect to database
        SAConnection con;
        try
        {
            // connect to database
            // in this example, it is Oracle,
            // but can also be Sybase, Informix, DB2
            // SQLServer, InterBase, SQLBase and ODBC
            con.Connect ("test",    // database name
                         "tester",  // user name
                         "tester",  // password
                         SA_Oracle_Client); //Oracle Client
            printf("We are connected!\n");

            // Disconnect is optional
            // autodisconnect will occur in destructor if needed
            con.Disconnect();
            printf("We are disconnected!\n");
        }

        catch(SAException & x)
        {
            // SAConnection::Rollback()
            // can also throw an exception
            // (if a network error for example),
            // we will be ready
            try
            {
                // on error rollback changes
                con.Rollback ();
            }
            catch(SAException &)
            {
            }
            // print error message
            printf("%s\n", (const char*)x.ErrText());
        }
        return 0;
    }
    ```

    **输出:**

    ```cpp
    We are Connected!
    We are Disconnected!

    ```

1.  **<u>Executing a simple SQL Command</u>**
    Now, we will look out to execute a simple SQL query.Firstly, creating a table for the database:

    创建表 tb1(id 号，名称 varchar(20)；

    现在，在您的 con.connect 之后，建立与数据库的连接；方法您应该使用 cmd.setCommandText 方法将查询传递给数据库，如下所示:

    ```cpp
    con.Connect("test", "tester", "tester", SA_Oracle_Client);
    cmd.setCommandText("create table tb1(id number, name varchar(20));”);
    ```

    现在，要执行查询，我们必须使用以下命令:

    cmd。execute()；

    **完整代码:**

    ```cpp
    #include<stdio.h>
    #include <SQLAPI.h> // main SQLAPI++ header
    int main(int argc, char* argv[])
    {
        SAConnection con; // connection object to connect to database
        SACommandcmd;    // create command object
        try
        {
            // connect to database (Oracle in our example)
            con.Connect("test", "tester", "tester", SA_Oracle_Client);

            // associate a command with connection
            // connection can also be specified in SACommand constructor
            cmd.setConnection(&con);

            // create table
            cmd.setCommandText("create table tbl(id number, name varchar(20));");
            cmd.Execute();

            // insert value
            cmd.setCommandText("Insert into tbl(id, name) values (1,”Vinay”)");
            cmd.setCommandText("Insert into tbl(id, name) values (2,”Kushal”)");
            cmd.setCommandText("Insert into tbl(id, name) values (3,”Saransh”)");
            cmd.Execute();

            // commit changes on success
            con.Commit();
            printf("Table created, row inserted!\n");
        }

        catch(SAException &x)
        {
            // SAConnection::Rollback()
            // can also throw an exception
            // (if a network error for example),
            // we will be ready
            try
            {
                // on error rollback changes
                con.Rollback();
            }
            catch(SAException &)
            {
            }
            // print error message

            printf("%s\n", (const char*)x.ErrText());
        }
        return 0;
    }
    ```

正如我们所知，Oracle 不是自动提交的(提交是对数据库中数据的永久反映)，所以我们必须提交它。

```cpp
con.Commit();
```

同样，当异常发生时，我们可以回滚事务，为此，我们使用:

```cpp
con.Rollback();
```

为了删除一行，我们使用这个命令。

```cpp
cmd.setCommandText("delete from tb1 where id= 2");
```

因此，到本文结束时，我们已经学习了如何将 C/C++ 程序连接到数据库并执行操作。

本文由**维奈·加尔格**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论