# SQL用JOIN更新

> 原文:[https://www.geeksforgeeks.org/sql-update-with-join/](https://www.geeksforgeeks.org/sql-update-with-join/)

`SQL UPDATE JOIN`可用于使用另一个表和连接条件更新一个表。

## 语法

```
UPDATE tablename  
INNER JOIN tablename  
ON tablename.columnname = tablename.columnname  
SET tablenmae.columnnmae = tablenmae.columnname;
```

## 示例

用`JOIN`语句在`SQL UPDATE`中使用多个表。

让我们假设我们有两张表——`Geeks1`和`Geeks2`。检查表格中的内容–

```
SELECT * 
FROM Geeks1;
```

**Table –** Geeks1

| 第 1 栏 | 第 2 栏 | 第 3 栏 |
| --- | --- | --- |
| one | Eleven | 第一 |
| Eleven | Twelve | 第二 |
| Twenty-one | Thirteen | 第三 |
| Thirty-one | Fourteen | 第四 |

```
SELECT * 
FROM Geeks2;
```

**Table –** Geeks2

| 第 1 栏 | 第 2 栏 | 第 3 栏 |
| --- | --- | --- |
| one | Twenty-one | 二合一 |
| Eleven | Twenty-two | 二二 |
| Twenty-one | Twenty-three | 二三 |
| Thirty-one | Twenty-four | 二-四 |

我们有表`Geeks2`，它有两行，其中第 1 列是 21 和 31，我们想为第 1 列是 21 和 31 的行更新表`Geeks2`到表`Geeks1`的值。此外，我们只想更新第 2 列和第 3 列的值。

```
UPDATE Geeks1  
SET col2 = Geeks2.col2,  
col3 = Geeks2.col3  
FROM Geeks1  
INNER JOIN Geeks2 ON Geeks1.col1 = Geeks2.col1  
WHERE Geeks1.col1 IN (21, 31);
```

## 输出

```
(2 row(s) affected)
```

```
SELECT * 
FROM Geeks1;
```

**Table –** Geeks1

| 第 1 栏 | 第 2 栏 | 第 3 栏 |
| --- | --- | --- |
| one | Eleven | 第一 |
| Eleven | Twelve | 第二 |
| Twenty-one | Twenty-three | 二三 |
| Thirty-one | Twenty-four | 二-四 |

```
SELECT * 
FROM Geeks2;
```

**Table –** Geeks2

| 第 1 栏 | 第 2 栏 | 第 3 栏 |
| --- | --- | --- |
| one | Twenty-one | 二合一 |
| Eleven | Twenty-two | 二二 |
| Twenty-one | Twenty-three | 二三 |
| Thirty-one | Twenty-four | 二-四 |