# 更新卡珊德拉中的设置

> 原文: [https://www.geeksforgeeks.org/updating-set-in-cassandra/](https://www.geeksforgeeks.org/updating-set-in-cassandra/)

在本文中，我们将讨论如何以不同的方式更新集合[集合数据类型](https://www.geeksforgeeks.org/collection-data-type-in-apache-cassandra/)。我们还将讨论如何使用 `update` 子句插入行，如果我们不想要任何集合元素，那么我们也可以使用带有`(-)`运算符的 `UPDATE` 子句移除。

## 创建表

首先，我们将创建一个食品菜单表，其中 `Cafe_id`、`Order_Date`、`total_cost`、`Menu_items` 是下面给定表格中的字段。让我们看看。

```sql
Create Table Food_menu 
(
 Cafe_id int Primary Key,
 Order_Date Date,
 total_cost int,    
 Menu_items Set<text>
);
```

## 插入数据

现在，我们将使用下面给出的[卡珊德拉查询语言(CQL)](https://www.geeksforgeeks.org/additional-functions-in-cql-cassandra-query-language/) 查询向 `Food_menu` 表中插入一些数据。让我们看看。

```sql
INSERT INTO Food_menu (Cafe_id,  Order_Date, total_cost, Menu_items)
VALUES (7801, '2019-02-13', 500, {'Banana', 'Mango', 'Apple'});

INSERT INTO Food_menu (Cafe_id,  Order_Date, total_cost, Menu_items)
VALUES (7802, '2019-02-15', 600, {'Banana', 'Mango', 'Apple'});

INSERT INTO Food_menu (Cafe_id,  Order_Date, total_cost, Menu_items)
VALUES (7803, '2019-02-19', 800, {'grapes', 'papaya', 'pomegranate'}); 
```

让我们看看插入数据的输出。

```sql
select * 
from Food_menu; 
```

`输出:`

![](img/28d5ffc1e926de117df44891776dca1f.png)

## 更新集合数据类型

现在，这里我们将讨论更新集合数据类型。让我们看看。

### 1. 添加元素

我们可以使用 `(+)` 运算符在集合数据类型中添加一个元素。

```sql
UPDATE Food_menu
SET Menu_items = Menu_items + {'mango shake'}  
WHERE Cafe_id = 7802; 
```

让我们看看上面 CQL 查询的输出。

```sql
select * 
from Food_menu; 
```

`输出:`

![](img/3b73c2ec16dee8e7024c049602b1a1b9.png)

### 2. 移除元素

我们可以使用减法 `(-)` 运算符从集合中移除一个元素。

```sql
UPDATE Food_menu
SET Menu_items = Menu_items - { 'Banana'} 
WHERE Cafe_id = 7801; 
```

让我们看看上面 CQL 查询的输出。

```sql
select * 
from Food_menu; 
```

`输出:`

![](img/0c537aad80179704d0b2665c0c8255a5.png)

### 3. 移除所有元素

现在，如果我们想从集合中移除所有元素，则使用下面给出的 CQL 查询。

```sql
UPDATE Food_menu
SET Menu_items = {''} 
WHERE Cafe_id = 7803;
```

```sql
select * 
from Food_menu; 
```

`输出:`

![](img/165d605bb651d4ccf366a103da68273e.png)