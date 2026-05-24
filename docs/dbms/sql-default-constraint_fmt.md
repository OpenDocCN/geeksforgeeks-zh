# SQL 默认约束

> 原文: [https://www.geeksforgeeks.org/sql-default-constraint/](https://www.geeksforgeeks.org/sql-default-constraint/)

**默认约束**用于用默认值和固定值填充列。当没有提供其他值时，该值将被添加到所有新记录中。

## 1. 在创建表格时使用默认值

### 语法

```sql
CREATE TABLE tablename (
    Columnname DEFAULT 'defaultvalue'
);
```

### 示例

创建`Geeks`表时，为`Location`列设置默认值：

```sql
CREATE TABLE Geeks (
    ID int NOT NULL,
    Name varchar(255),
    Age int,
    Location varchar(255) DEFAULT 'Noida'
);
```

```sql
INSERT INTO Geeks VALUES (4, 'Mira', 23, 'Delhi');
INSERT INTO Geeks VALUES (5, 'Hema', 27);
INSERT INTO Geeks VALUES (6, 'Neha', 25, 'Delhi');
INSERT INTO Geeks VALUES (7, 'Khushi', 26);
```

### 输出

```sql
SELECT *
FROM Geeks;
```

```
| ID | Name   | Age | Location |
|----|--------|-----|----------|
| 4  | Mira   | 23  | Delhi    |
| 5  | Hema   | 27  | Noida    |
| 6  | Neha   | 25  | Delhi    |
| 7  | Khushi | 26  | Noida    |
```

## 2. 删除默认约束

### 语法

```sql
ALTER TABLE tablename
ALTER COLUMN columnname
DROP DEFAULT;
```

### 示例

```sql
ALTER TABLE Geeks
ALTER COLUMN Location
DROP DEFAULT;
```

让我们在`Geeks`表中添加 2 个新行：

```sql
INSERT INTO Geeks VALUES (8, 'Komal', 24, 'Delhi');
INSERT INTO Geeks VALUES (9, 'Payal', 26);
```

**注意：** 删除默认约束不会影响表中的当前数据，它只适用于新行。

### 输出

```sql
SELECT *
FROM Geeks;
```

```
| ID | Name   | Age | Location |
|----|--------|-----|----------|
| 4  | Mira   | 23  | Delhi    |
| 5  | Hema   | 27  | Noida    |
| 6  | Neha   | 25  | Delhi    |
| 7  | Khushi | 26  | Noida    |
| 8  | Komal  | 24  | Delhi    |
| 9  | Payal  | 26  | NULL     |
```