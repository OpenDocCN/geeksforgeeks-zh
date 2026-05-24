# 在 MySQL 中重复密钥更新时插入

> 原文:[https://www . geesforgeks . org/insert-on-reply-key-update-in-MySQL/](https://www.geeksforgeeks.org/insert-on-duplicate-key-update-in-mysql/)

在 MySQL 中，重复键更新语句可以作为插入语句的扩展。每当一个新的行被插入到一个表中，以防该行在 UNIQUE 索引或 PRIMARY KEY 中引起重复条目，MySQL 将抛出一个错误。

当在 INSERT 语句中定义了 ON DUPLICATE KEY UPDATE 选项时，现有行将改为用新值更新。

**语法:**

```sql
INSERT INTO table (column_names)
VALUES (values)
ON DUPLICATE KEY UPDATE
  col1 = val1,  
  col2 = val2 ;

```

除了 INSERT 语句，ON DUPLICATE KEY UPDATE 语句还定义了一个列和值分配的列表，以防重复。

**工作原理:**
该语句首先尝试在表中插入一个新行。当出现重复条目时，MySQL 将使用在 ON DUPLICATE KEY UPDATE 子句中指定的值更新现有行。

**示例–**
让我们创建一个名为‘geek _ demo’的表，如下所示。

```sql
CREATE TABLE geek_demo
(
id INT AUTO_INCREMENT PRIMARY KEY, 
name VARCHAR(100) 
);

```

**将数据插入 geek_demo :**

```sql
INSERT INTO geek_demo (name)
VALUES('Neha'), ('Nisha'), ('Sara') ;

```

**从表中读取数据:**

```sql
SELECT id, name
FROM geek_demo;
```

**输出:**

| 身份证明（identification） | 名字 |
| --- | --- |
| one | 停止 |
| Two | 妮莎 |
| three | 莎拉 |

现在，一行将插入到表中。

```sql
INSERT INTO geek_demo(name) 
VALUES ('Sneha') 
ON DUPLICATE KEY UPDATE name = 'Sneha';

```

由于没有重复，MySQL 在表中插入了一个新行。上面语句的输出类似于下面语句的输出，如下所示。

```sql
INSERT INTO geek_demo(name)
VALUES ('Sneha');

```

**读取数据:**

```sql
SELECT id, name
FROM geek_demo; 

```

**输出:**

| 身份证明（identification） | 名字 |
| --- | --- |
| one | 停止 |
| Two | 妮莎 |
| three | 莎拉 |
| four | 雪 |

让我们在 id 列中插入一个具有重复值的行，如下所示。

```sql
INSERT INTO geek_demo (id, name) 
VALUES (4, 'Mona')
ON DUPLICATE KEY UPDATE name = 'Mona';

```

**下面是输出:**

```sql
2 row(s) affected

```

因为 geek_demo 表中已经存在 id 为 4 的行，所以该语句将名称从 Sneha 更新为 Mona。
**读取数据:**

```sql
SELECT id, name
FROM geek_demo;

```

**输出:**

| 身份证明（identification） | 名字 |
| --- | --- |
| one | 停止 |
| Two | 妮莎 |
| three | 莎拉 |
| four | 白腹长尾猴 |