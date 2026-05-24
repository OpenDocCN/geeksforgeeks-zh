# 动态 SQL

> 原文:[https://www.geeksforgeeks.org/dynamic-sql/](https://www.geeksforgeeks.org/dynamic-sql/)

**先决条件–**[静态和动态 SQL 的区别](https://www.geeksforgeeks.org/difference-static-dynamic-sql/)

**动态 SQL** 是一种编程技术，可用于在运行时编写 SQL 查询。动态 SQL 可以用来创建通用和灵活的 SQL 查询。

动态 SQL 的语法如下所示:

```sql
'SELECT statement';
```

要运行动态 SQL 语句，请运行存储过程 **sp_executesql** ，如下所示:

```sql
EXEC sp_executesql N'SELECT statement';
```

使用前缀 N 和 sp_executesql 将动态 sql 用作 Unicode 字符串。

**使用动态 SQL 的步骤:**

1.  声明两个变量，@var1 用于保存表名，@var 2 用于保存动态 SQL :

    ```sql
    DECLARE 
    @var1 NVARCHAR(MAX), 
    @var2 NVARCHAR(MAX);
    ```

2.  将@var1 变量的值设置为 table_name :

    ```sql
    SET @var1 = N'table_name';
    ```

3.  通过将 SELECT 语句添加到表名参数中来创建动态 SQL:

    ```sql
    SET @var2= N'SELECT * 
    FROM ' + @var1;
    ```

4.  使用@var2 参数运行 sp_executesql 存储过程:

    ```sql
    EXEC sp_executesql @var2;
    ```

**示例–**

```sql
SELECT * 
from geek;
```

**表–**极客

| 身份证明 | 名字 | 城市 |
| --- | --- | --- |
| one | 库希 | 斋浦尔 |
| Two | 停止 | 无聊死了 |
| three | 米拉 | 德里 |

**使用动态 SQL :**

```sql
DECLARE 
@tab NVARCHAR(128), 
@st NVARCHAR(MAX);
SET @tab = N'geektable';
SET @st = N'SELECT * 
FROM ' + @tab;
EXEC sp_executesql @st;
```

**表–**极客

| 身份证明 | 名字 | 城市 |
| --- | --- | --- |
| one | 库希 | 斋浦尔 |
| Two | 停止 | 无聊死了 |
| three | 米拉 | 德里 |