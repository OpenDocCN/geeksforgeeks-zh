# 电影数据库的 SQL 查询

> 原文: [https://www.geeksforgeeks.org/sql-queries-on-film-database/](https://www.geeksforgeeks.org/sql-queries-on-film-database/)

请考虑电影数据库中的以下表格：

```sql
ARTIST (Art_id, Art_Name, Art_Gender) 
PRODUCER (Prod_id, Prod_Name, Prod_Phone)
FILMS (Film_id, Film_Title, Film_Year, Film_Lang, Prod_id) 
CASTING (Art_id, Film_id, Part) 
REVIEW (Film_id, Stars) 
```

这五个表的数据内容如下所示：

```sql
SELECT * FROM ARTIST;
```

| Art_id | 艺术名称 | 艺术_性别 |
| --- | --- | --- |
| 101 | AMIT | M |
| 102 | 普里塔姆 | M |
| 103 | 西娅 | F |
| 104 | -好的 | F |

```sql
SELECT * FROM PRODUCER;
```

| 产品 id | 产品名称 | 产品_电话 |
| --- | --- | --- |
| 200 | 阿迪蒂亚 | 6735835863 |
| 201 | FARAN | 8654297433 |
| 202 | 亚什 | 8765421567 |
| 203 | 尼拉吉 | 7654321986 |

```sql
SELECT * FROM FILMS;
```

| 电影 id | 电影_标题 | 电影年 | 电影_郎 | 产品 id |
| --- | --- | --- | --- | --- |
| 11 | 战争 2 | 2017 | 英语 | 201 |
| 12 | 片刻 | 2015 | 北印度语 | 203 |
| 13 | 五月 | 2019 | 英语 | 201 |
| 14 | BHANUMATI | 2014 | 特拉古语 | 200 |

```sql
SELECT * FROM CASTING;
```

| Art_id | 电影 id | 部分 |
| --- | --- | --- |
| 101 | 12 | 行动者 |
| 101 | 11 | 行动者 |
| 103 | 13 | 女演员 |
| 103 | 12 | 客人 |
| 104 | 14 | 女演员 |

```sql
SELECT * FROM REVIEW;
```

| 电影 id | 明星 |
| --- | --- |
| 11 | 4 |
| 12 | 2 |
| 13 | 5 |
| 14 | 4 |

## 查询-1
找到所有制片人为“NIRAJ”的电影名称。

首先，我们将找到名为“NIRAJ”的生产者的生产者标识，为此我们使用生产者表。

```sql
SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’
```

上面的查询将返回 `Prod_id` “203”。现在我们将找到 `pros_id` 为“203”的电影的标题。为此，我们使用表 `FILMS`，并将上面的查询用作子查询。

```sql
SELECT FILM_TITLE 
FROM FILMS 
WHERE PROD_ID IN (SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’);
```

**输出：**

| 电影_标题 |
| --- |
| 片刻 |

## 查询-2
展示 2016 年至 2018 年间出演某部电影的所有艺人。

为了找到这一点，我们需要使用艺术家表的艺术家名称字段以及电影表的电影年份字段。为了连接这两个表，我们使用第三个表 `CASTING`，使用 `Art_id` 和 `Film_id`。加入后，我们在 2016 年至 2018 年间使用“介于”运算符检查电影年份。

```sql
SELECT A.ART_NAME,  F.FILM_TITLE, F.FILM_YEAR 
FROM ARTIST A, CASTING C, FILMS F
WHERE A.ART_ID=C.ART_ID 
AND C.FILM_ID=F.FILM_ID 
AND F.FILM_YEAR  BETWEEN 2016 AND 2018;
```

**输出：**

| 艺术名称 | 电影_标题 | 电影_年份 |
| --- | --- | --- |
| AMIT | 战争 2 | 2017 |

## 查询-3
显示收到明星的电影名称，并根据明星对结果进行排序。

为此，我们需要电影表的电影标题字段以及评论表的星星字段。为了连接这两个表，我们将使用公共字段，即电影标识。在连接之后，我们使用 `ORDER BY` 子句按照 `STARS` 递增的顺序显示结果。

```sql
SELECT F.FILM_TITLE, R.STARS
FROM FILMS F, REVIEW R
WHERE F.FILM_ID=R.FILM_ID
ORDER BY R.STARS DESC
```

**输出：**

| 电影_标题 | 明星 |
| --- | --- |
| 五月 | 5 |
| BHANUMATI | 4 |
| 战争 2 | 4 |
| 片刻 | 2 |

## 查询-4
将制片人为‘NIRAJ’的所有电影的主演更新为 5。

首先，我们使用以下查询找到名为“NIRAJ”的生产者的生产者标识：

```sql
SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’
```

然后使用这个产品标识从电影表中找到电影标识。

```sql
SELECT FILM_ID FROM FILMS 
WHERE PROD_ID IN (SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’)
```

然后这个电影标识有助于使用更新命令更新评论表中的星星值。

```sql
UPDATE REVIEW 
SET STARS=5 
WHERE FILM_ID IN (SELECT FILM_ID FROM FILMS 
WHERE PROD_ID IN (SELECT PROD_ID 
FROM PRODUCER 
WHERE PROD_NAME = ‘NIRAJ’));
```

**输出：**

```sql
1 row updated.
```

要观察这些变化，我们可以使用 `REVIEW` 表中的 `SELECT *` 命令。

```sql
SELECT * FROM REVIEW;
```

| 电影 id | 明星 |
| --- | --- |
| 11 | 4 |
| 12 | 5 |
| 13 | 5 |
| 14 | 4 |