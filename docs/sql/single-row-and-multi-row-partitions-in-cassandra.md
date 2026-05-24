# 卡珊德拉中的单行和多行分区

> 原文:[https://www . geesforgeks . org/单排多排分区 in-cassandra/](https://www.geeksforgeeks.org/single-row-and-multi-row-partitions-in-cassandra/)

在卡珊德拉中， [CQL(卡珊德拉查询语言)](https://www.geeksforgeeks.org/useful-cql-query-in-cassandra/?ref=rp)有两个分区，如下

*   单行分区
*   多行分区

**单行分区:**
在 Cassandra 中，主键表示唯一的数据分区，聚类列部分也有助于数据排列，用于处理数据排列部分。在单行分区中，单列上只有一个分区键。

**示例–**
让我们看一下 Employee 表，它有 Emp_id、Emp_name、Emp_email 等字段，其中 Emp_id 是主键。

```sql
CREATE table Employee(
Emp_id UUID, 
Emp_name TEXT, 
Emp_email TEXT,
primary key(Emp_id)
);
```

您可以检查上述示例的分区逻辑参考模型，如下所示–

```sql
K - Primary key
C - Clustering column
S - Static column
```

<figure class="table">

| 雇员 |
| --- |
| 字段名称 | 数据类型 | 钥匙 |
| --- | --- | --- |
| Emp_id | UUID | K |
| Emp_name | 文本 |   |
| Emp_email | 文本 |   |

</figure>

在 Cassandra 中，主键是分区键和集群列(如果有)的组合。

```sql
Primary Key = Partition Key + [Clustering Columns]
```

**多行分区:**
在多行分区中，分区键应用于多个单列和聚类列，用于排列或分区数据建模。

**示例–**
我们来看事件表，它有 Event_venue、Event_year、Event_artifact、Events_title、Events_country 这样的字段，其中 Event_venue、Event_year 是主键，Event_artifact 是聚类列键。

```sql
CREATE table Events(
Event_venue TEXT, 
Event_year INT,
Event_artifact TEXT,
Events_title TEXT,
Events_country TEXT STATIC,
primary key((Event_venue, Event_year), Event_artifact)
);
```

您可以检查上述示例的分区逻辑参考模型，如下所示–

```sql
K - Primary key
C - Clustering column
S - Static column
```

<figure class="table">

| 事件 |
| --- |
| 字段名称 | 数据类型 | 钥匙 |
| --- | --- | --- |
| 活动地点 | 文本 | K |
| 事件 _ 年份 | （同 Internationalorganizations）国际组织 | K |
| 事件 _ 工件 | 文本 |   |
| 事件 _ 标题 | 文本 |   |
| 事件 _ 国家 | 文本 | S |

</figure>