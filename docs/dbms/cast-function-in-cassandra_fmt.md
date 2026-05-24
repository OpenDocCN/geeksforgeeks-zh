# 卡珊德拉中的 CAST 功能

> 原文: [https://www.geeksforgeeks.org/cast-function-in-cassandra/](https://www.geeksforgeeks.org/cast-function-in-cassandra/)

`CAST`功能在[卡珊德拉](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)中帮助将数据从一种数据类型转换为另一种数据类型。

在 Cassandra `CAST` 中，`SELECT`语句支持函数。让我们看看如何在`select`语句中使用`CAST`函数。

```
SELECT CAST([fieldname] AS [data type]) 
FROM [table name] 
```

## CAST 的基本功能

*   它从任何本机数据类型转换为`ASCII`和`UTF-8`等格式的文本数据类型。
*   它在数字数据类型之间进行转换，例如从`int`到`smallint`、`smallint`到`int`等。
*   通过使用`CAST`函数，我们可以转换最常见的用例。
*   在我们需要频繁地从一种数据类型更改到另一种数据类型的优化情况下，这非常有帮助。
*   通过使用`CAST`函数，我们可以将时间戳转换为文本，以便在 Cassandra 中显示。

这是一个供参考的表，其中所有的本机数据类型都可以从一种数据类型转换为另一种数据类型。

### 表: CAST 转换表

下表描述了`CAST`函数支持的转换。Cassandra 会默默忽略任何将数据类型转换为自己的数据类型的转换。

| 从 | 到 |
| --- | --- |
| `ASCII` | `text`，`varchar` |
| `bigint` | `tinyint`，`smallint`，`int`，`float`，`double`，`decimal`，`varint`，`text`，`varchar` |
| `boolean` | `text`，`varchar` |
| `counter` | `tinyint`、`smallint`、`int`、`bigint`、`float`、`double`、`decimal`、`varint`、`text`、`varchar` |
| `date` | `timestamp` |
| `decimal` | `tinyint`，`smallint`，`int`，`bigint`，`float`，`double`，`varint`，`text`，`varchar` |
| `double` | `tinyint`，`smallint`，`int`，`bigint`，`float`，`decimal`，`varint`，`text`，`varchar` |
| `float` | `tinyint`、`smallint`、`int`、`bigint`、`double`、`decimal`、`varint`、`text`、`varchar` |
| `inet` | `text`，`varchar` |
| `int` | `tinyint`、`smallint`、`bigint`、`float`、`double`、`decimal`、`varint`、`text`、`varchar` |
| `smallint` | `tinyint`，`int`，`bigint`，`float`，`double`，`decimal`，`varint`，`text`，`varchar` |
| `time` | `text`，`varchar` |
| `timestamp` | `date`、`text`、`varchar` |
| `timeuuid` | `timestamp`、`date`、`text`、`varchar` |
| `tinyint` | `tinyint`、`smallint`、`int`、`bigint`、`float`、`double`、`decimal`、`varint`、`text`、`varchar` |
| `uuid` | `text`，`varchar` |
| `varint` | `tinyint`、`smallint`、`int`、`bigint`、`float`、`double`、`decimal`、`text`、`varchar` |

**来源–** [Cassandra.Apache.org](http://cassandra.apache.org/doc/latest/cql/functions.html#aggregate-functions)

## CQL 查询 CAST 函数

我们来举个例子: `movies`是一个表名，我们要在其中更改它的原生数据类型，这样`movie_date`就是有`timestamp`数据类型的字段名，如果我们要将其转换成另一个原生数据类型，这样在`text`数据类型中。

要创建表，请使用以下 CQL 查询。

```
CREATE TABLE movies
 (
  movie_id int,
  movie_date timestamp,
  PRIMARY KEY (movie_id)
 ); 
```

将以下数据插入表中:

```
INSERT INTO movies (movie_id, movie_date) 
       VALUES (7c3cffb8-0dc4-1d27-af24-c007b5fc5643, 
                 '2019-10-15 01:11:50.000000+0000 '); 
```

因此，下面是我们如何使用`CAST`函数从一种数据类型转换到另一种数据类型的格式。下面给出的语句意味着我们要将`movie_date`时间戳转换为`movie_date`文本。

```
SELECT CAST(movie_date AS text) 
```

*   **Result:** Without CAST

```
    SELECT movie_date
    FROM movies
    WHERE movie_id = 7c3cffb8-0dc4-1d27-af24-c007b5fc5643; 
    ```

**输出:**

```
    2019-10-15 01:11:50.000000+0000 (time stamp format) 
    ```

*   **Result:** With CAST

```
    SELECT CAST(movie_date AS text)
    FROM movies
    WHERE movie_id = 7c3cffb8-0dc4-1d27-af24-c007b5fc5643; 
    ```

**输出:**

```
    2019-10-15 01:11:50.000Z (Coordinated Universal Time, or UTC) 
    ```