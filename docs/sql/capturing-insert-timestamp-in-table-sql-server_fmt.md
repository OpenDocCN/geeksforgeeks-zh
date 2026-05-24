# 在 SQL 服务器中捕获插入时间戳

> 原文: [https://www.geeksforgeeks.org/capturing-insert-timestamp-in-table-sql-server/](https://www.geeksforgeeks.org/capturing-insert-timestamp-in-table-sql-server/)

在表中插入数据时，有时我们需要在表中捕获插入时间戳。有一种非常简单的方法，我们可以用来捕获表中插入行的时间戳。

## 在 SQL Server 中用 DEFAULT 约束捕获表中插入行的时间戳

创建表时使用 `DEFAULT` 约束:

### 语法

```sql
CREATE TABLE TableName (ColumName INT, ColumnDateTime DATETIME DEFAULT CURRENT_TIMESTAMP)
GO
```

### 示例

让我们创建一个名为“极客标签”的表格。

```sql
CREATE TABLE GeekTab (ID INT, InDtTm DATETIME DEFAULT CURRENT_TIMESTAMP) ;
GO
```

让我们在表中插入几个值。

```sql
INSERT INTO GeekTab (ID) VALUES (1),  (2) ; 
GO
```

```sql
INSERT INTO GeekTab (ID)VALUES (3), (4) ; 
GO
```

现在，让我们从表中选择值。

```sql
SELECT * FROM GeekTab ;
GO
```

**输出:**

| ID | InDtTm |
| --- | --- |
| 1 | 2020-12-30 13:08:54.193 |
| 2 | 2020-12-30 13:08:54.193 |
| 3 | 2020-12-30 13:08:54.193 |
| 4 | 2020-12-30 13:08:54.193 |

### 结论

当我们从表 `GeekTab` 中选择值时，我们可以看到它在 `InDtTm` 列的表中有当前时间戳。这是因为列 `InDtTm` 是用 `DATETIME DEFAULT CURRENT_TIMESTAMP` 创建的。

### 基于场景的示例

让我们假设我们有一个表 `EmployeeTab`，每当有新员工加入公司时，一条新的记录被插入到表中:

```sql
CREATE TABLE EmployeeTab (Name varchar(100), ID INT, Location varchar(100),
InDtTm DATETIME DEFAULT CURRENT_TIMESTAMP); 
```

```sql
SELECT Name, ID, Location FROM EmployeeTab ;
```

| Name | ID | Location |
| --- | --- | --- |
| Ankit | 234 | Delhi |
| Varun | 876 | Noida |

要将每个条目的插入日期和时间作为“加入日期”，可以使用以下查询:

```sql
SELECT Name, ID, Location, InDtTm as JoinDate FROM EmployeeTab ;
```

| Name | ID | Location | JoinDate |
| --- | --- | --- | --- |
| Ankit | 234 | Delhi | 2019-11-24 10:10:53.163 |
| Varun | 876 | Noida | 2019-10-24 10:11:33.163 |

### 注意

使用此功能时有一个例外，如果有人在 `ColumnDateTime` 列中插入显式值，该列将具有新插入的值，而不是默认值。