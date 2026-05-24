# 蜂巢原始数据类型

> 原文:[https://www.geeksforgeeks.org/hive-primitive-datatypes/](https://www.geeksforgeeks.org/hive-primitive-datatypes/)

[Hive](https://www.geeksforgeeks.org/apache-hive/) 是一个建立在 Hadoop 之上的数据仓库工具。Hive 充当 Hadoop 生态系统的接口。这是一个使用 [HDFS(Hadoop 分布式文件系统)](https://www.geeksforgeeks.org/introduction-to-hadoop-distributed-file-systemhdfs/)存储数据，使用[地图缩减](https://www.geeksforgeeks.org/hadoop-reducer-in-map-reduce/)处理数据的框架。因此， [Hadoop](https://www.geeksforgeeks.org/hadoop-ecosystem/) 中的数据由 hive 获取并执行分析活动。在本文中，我们将借助一个示例详细讨论配置单元原语数据类型，以便更好地理解。此外，我们将讨论配置单元数据类型的需求，然后强调基本数据类型，如数值数据类型、日期时间数据类型、复杂数据类型等。我们一个一个来讨论。

**对 Hive 数据类型的需求:**
执行分析活动需要一些数据类型和数据格式来处理和检索数据。

*   通过使用 Hive，我们可以执行数据分析。
*   配置单元提供类似于 SQL 的 HQL(配置单元查询语言)。
*   我们可以通过用数据类型定义表列来创建配置单元表。

**数据类型分类:**
蜂巢的数据类型可以分为两部分。

**原始数据类型:**
原始数据类型也分为以下 3 种类型。

**类型-1 :**
**数值数据类型–**
这些数据类型用于定义带有整数变量的列。

<figure class="table">

| **Data type** | **Size** |
| --- | --- |
| Tinyint–1 byte signed integer | -128 to 127 |
| Small int–2-byte signed integer | -32,768 to 32,767 |
| Int–4-byte signed integer | –2,147,483,648 to 2,147,483,647 |
| BIINT–8-byte signed integer' | 9,223,372,036,854,775,808 to 9,223,372,036,855 |

</figure>

**示例查询–**

**TINYINT Demo :**
在这个蜂巢数据类型中，范围是从-128 到 127。让我们借助一个例子来理解。

```sql
create table geeksportal.geekdata(college_id tinyint);
```

**SMALLINT Demo :**
在这个配置单元数据类型中，大小为 2 字节，范围从-32768 到 32767。让我们借助一个例子来理解。

```sql
create table geeksportal.geekdata(college_id smallint);
```

**INT Demo :**
在这个配置单元数据类型中，大小为 4 字节，范围从–2，147，483，648 到 2，147，483，647。让我们借助一个例子来理解。

```sql
create table geeksportal.geekdata(college_id  int);
```

**BIGINT Demo :**
在这个配置单元数据类型中，大小是 8 字节，范围是从 9，223，372，036，854，775，808 到 9，223，372，036，854，775，807。让我们借助一个例子来理解。

```sql
create table geeksportal.geekdata(phonenumber  bigint);
```

**FLOAT 演示:**
在这个配置单元数据类型中，大小为 Single Precision 浮点，范围为 Single Precision。让我们借助一个例子来理解。

```sql
create table geeksportal.geekdata(percentage float);
```

**Double Demo :**
在这个蜂巢数据类型中，大小是 DOUBLE 精度浮点，范围是 DOUBLE 精度。让我们借助一个例子来理解。

```sql
create table geeksportal.geekdata( percentage double );
```

**DECIMAL 演示:**
在这个配置单元数据类型中，size 是基于 Java BigDecimal Object 的 Precise decimal 类型，范围是 Big Decimal。让我们借助一个例子来理解。

```sql
create table geeksportal.geekdata( percentage decimal);
```

**类型-2 :**
**日期/时间数据类型–**
在这里，我们将讨论 Hive 中的日期/时间数据类型，如下所示。

```sql
TIMESTAMP - 'YYYY-MM-DD HH:MM:SS.fffffffff   = 9 decimal place precision
```

**TIMESTAMP 演示:**
在这个蜂巢数据类型中，你会看到 TIMESTAMP 数据类型的演示如下。

```sql
create table geeksportal.geekdata( time timestamp);
```

**字符串数据类型:**
在这个配置单元数据类型中，您将借助如下示例来理解字符串数据类型数据类型。

```sql
create table geeksportal.geekdata( name string);
```

**Type-3 :**
**复杂数据类型–**
在这里，我们将对 Hive 中的复杂数据类型进行如下讨论。

**数组:**
数组是所有相同数据类型的字段的集合，由一个整数索引。

**语法:**

```sql
ARRAY<TINYINT>
```

**地图:**
地图是键、值对的集合，其中键是基本类型，值可以是任何东西。对于每个映射，为键和值选择的数据类型必须保持相同。

**语法:**

```sql
MAP<STRING,INT>
```

**STRUCT :**
它是一个嵌套的复杂数据结构。

**语法:**

```sql
STRUCT<first : SMALLINT, second : FLOAT, third : STRING>
```

**UNION :**
它是一个复杂的数据类型，可以一次保存一个可能的数据类型。

**语法:**

```sql
UNIONTYPE<INT,FLOAT,STRING>
```

**示例:**
借助示例演示数据类型，以便更好地理解。考虑一个文本文件(Geek.txt)，它包括主题并如下标记记录。

```sql
7058,cse^1,1|2|3,A|50000,3,true
7059,cse^2,1|2,B|40000,good,true
```

**编码/查询:**

```sql
Creating a table t1:
create table t1(id int,class map<string,int>,sections array<int>,hostel
struct<grade:string,fee:double>,rating uniontype<int,string>,exist boolean)
row format delimited
fields terminated by ','
collection items terminated by '|'
map keys terminated by '^'
lines terminated by '\n'
stored as textfile; 
```