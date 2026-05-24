# SQL |从多个表中选择数据

> 原文:[https://www . geesforgeks . org/SQL-select-data-from-multi-tables/](https://www.geeksforgeeks.org/sql-select-data-from-multiple-tables/)

下面的语句可以用来从多个表中获取数据，所以，我们需要使用 join 来从多个表中获取数据。

**语法:**

```sql
SELECT tablenmae1.colunmname, tablename2.columnnmae    
FROM tablenmae1  
JOIN tablename2  
ON tablenmae1.colunmnam = tablename2.columnnmae
ORDER BY columnname;  

```

让我们拿三张桌子来说，两张桌子的顾客分别是极客 1、极客 2 和极客 3。

**极客 1 表:**

<center>

| 身份证明 | 西方人名的第一个字 |
| --- | --- |
| one | Nisha |
| Two | Manoj |
| three | Pujia |

</center>

**极客 2 表:**

<center>

| 身份证明 | surname |
| --- | --- |
| one | Puta |
| Two | Desai |
| three | Living goddess |

</center>

**极客 3 表:**

| 【GID】 | 【PID】 | [assets] |
| --- | --- | --- |
|  | 【P1】 |
| --- | --- |

从多个表中选择的示例:

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

**输出:**

【GID】【last name】

| 【PID】 | [assets] | 【名字】 |
| --- | --- | --- |