# SQL Server 中的孤立用户

> 原文:[https://www.geeksforgeeks.org/orphan-user-in-sql-server/](https://www.geeksforgeeks.org/orphan-user-in-sql-server/)

**孤立用户**是指在数据库级别可用但其映射登录在服务器级别不可用的用户。**当数据库从一台服务器的备份恢复到另一台服务器时，会创建孤立用户**。

要获取 SQL Server 中任何数据库中的孤立用户，请使用以下命令:

**语法:**

```sql
USE DATABASENAME
EXEC sp_change_users_login report
GO
```

**示例–**
让我们假设已经使用 Server2 中的以下命令将 **GeeksDb** 从 Server1 恢复到 Server2。

```sql
USE GeeksDb
EXEC sp_change_users_login report
GO 
```

**输出–**

<center>

| 用户名 | 用户标识 |
| --- | --- |
| 极客 1 | 0x7a 4x 871 C3 exx7c 42x 67 b5 F3 Cd2 c35 fxx |
| 极客 2 | 0x 7 a4 e 871 C3 Exxon 27c 42 b67 xxf 3 cc 4c 35 fxx |
| 极客 3 | 0x 7 a5 e 871 x3 Exxon 27c 42 f 57 xxf 3 cc 4c 35 fxx |
| 极客 4 | 0x7a5e 871 C3 eff 27 c 32d 67 xf3c 4c 45 fxx |

</center>

以下方法可用于修复孤立用户。

1.  **USING WITH ORPHANED USER SID :**
    To fix any orphaned users, use create login by using SID.

    **语法:**

    ```sql
    USE MASTER
    CREATE LOGIN [LoginName] 
    WITH PASSWORD = 'Password',
    SID = 0x7A4X871C3EXX7C42X67B5F3CD2C35FXX 
    ```

    **示例–**

    ```sql
    USE MASTER
    CREATE LOGIN [Geek1] WITH PASSWORD = 'Pa$W0rd1', 
    SID = 0x7A4X871C3EXX7C42X67B5F3CD2C35FXX 

    ```

2.  **使用 UPDATE_ONE :**
    即使登录名和用户名不同，UPDATE_ONE 也可用于映射，或者可用于使用登录名 SID 更改用户的 SID。

首先，创建新的登录。

```sql
USE MASTER
CREATE LOGIN [LoginName] WITH PASSWORD = 'Password'
```

创建登录后，使用 UPDATE_ONE 修复孤立用户。

**语法:**

```sql
USE DATABASENAME
sp_change_users_login UPDATE_ONE, 'UserName', 'LoginName'
GO
```

**示例–**

```sql
USE MASTER
CREATE LOGIN [Geek2] WITH PASSWORD = 'Pa$W0rd2'
USE GeekDb
sp_change_users_login UPDATE_ONE, 'Geek2', 'Geek2'
GO

```

12.  **USING AUTO_FIX –**
    **TYPE 1 :** When Login Name and User Name are same.

    首先创建登录名，然后将登录名 SID 分配给孤立用户。

    **语法:**

    ```sql
    USE master
    CREATE LOGIN [LoginName] WITH PASSWORD = 'Password'

    USE DATABASENAME
    sp_change_users_login AUTO_FIX, 'LoginName/UserName'
    Go
    ```

    **示例:**

    ```sql
    USE master
    CREATE LOGIN [Geek3] WITH PASSWORD = 'Pa$W0rd3'
    USE GeekDB
    sp_change_users_login AUTO_FIX, 'Geek3/Geek3'
    Go 
    ```

    **类型 2 :** 不创建登录。

    **语法:**

    ```sql
    USE DATABASENAME
    sp_change_users_login AUTO_FIX, 'UserName', NULL, 'Password'
    GO
    ```

    **示例:**

    ```sql
    USE GeekDb
    sp_change_users_login AUTO_FIX, 'Geek4', NULL, 'Pa$W0rd4'
    GO 
    ```

    **使用上述方法后获取任意数据库中的孤儿用户:**

    ```sql
    USE GeeksDb
    EXEC sp_change_users_login report
    GO 
    ```

    **输出–**

    | 1.用户名 | 2\. 用户编号 |
    | --- | --- |

    一旦孤立用户被成功修复，将不会有任何孤立用户(用户名和用户标识号)作为上述命令的结果。