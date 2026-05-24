# SQL：从多个表中选择数据

> 原文：[https://www.geeksforgeeks.org/sql-select-data-from-multiple-tables/](https://www.geeksforgeeks.org/sql-select-data-from-multiple-tables/)

下面的语句可以用来从多个表中获取数据，所以，我们需要使用 `JOIN` 来从多个表中获取数据。

## 语法

```sql
SELECT tablenmae1.colunmname, tablename2.columnnmae    
FROM tablenmae1  
JOIN tablename2  
ON tablenmae1.colunmnam = tablename2.columnnmae
ORDER BY columnname;
```

让我们拿三张表来说，两张表的顾客分别是极客 1、极客 2 和极客 3。

## 极客 1 表

| ID | FirstName |
| --- | --- |
| one | Nisha |
| Two | Manoj |
| three | Pujia |

## 极客 2 表

| ID | LastName |
| --- | --- |
| one | Puta |
| Two | Desai |
| three | Living goddess |

## 极客 3 表

| GID | PID | Asset |
| --- | --- | --- |
| 1 | P1 | Gold |
| 2 | P2 | Silver |
| 3 | P3 | Bronze |

## 从多个表中选择的示例

```sql
SELECT Geeks3.GID, Geeks3.PID, 
       Geeks3.Asset, Geeks1.FirstName, 
       Geeks2.LastName  
FROM Geeks3
LEFT JOIN Geeks1 
ON Geeks3.GID = Geeks1.ID
LEFT JOIN Geeks2 
ON Geeks3.GID = Geeks2.ID  
```

## 输出

| GID | PID | Asset | FirstName | LastName |
| --- | --- | --- | --- | --- |
| 1 | P1 | Gold | Nisha | Puta |
| 2 | P2 | Silver | Manoj | Desai |
| 3 | P3 | Bronze | Pujia | Living goddess |