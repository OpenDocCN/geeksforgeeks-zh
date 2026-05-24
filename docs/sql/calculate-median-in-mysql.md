# 在 MySQL 中计算中位数

> 原文:[https://www.geeksforgeeks.org/calculate-median-in-mysql/](https://www.geeksforgeeks.org/calculate-median-in-mysql/)

**[中值](https://www.geeksforgeeks.org/median/) :**
在统计学和概率论中，中值是将数据样本、总体或概率分布的上半部分与下半部分分开的值。在外行人的语言中，中位数是排序后的值列表的中间值。

**计算在[MySQL](https://www.geeksforgeeks.org/sql-tutorial/#mysql)–**T4 中的中值考虑一个表**演示**其中**名称**是学生姓名**距离**是从他们家到大学的总距离(单位为公里)。

<center>

| 名字 | 距离 |
| 苏米特 | Twenty-five |
| 贾斯基拉特 | Thirty-five |
| 苏克鲁特 | Twenty |
| 希瓦姆 | Twenty |
| 三击即中 | Forty-five |
| 王子 | Thirty-five |
| 凯斯达夫 | Fifteen |
| 漂亮的 | Twenty-five |
| 樱花儿 | Twenty |

</center>

我们根据演示表计算距离的中位数。
**查询–**

```sql
SET @rowindex := -1;

SELECT
   AVG(d.distance) as Median 
FROM
   (SELECT @rowindex:=@rowindex + 1 AS rowindex,
           demo.distance AS distance
    FROM demo
    ORDER BY demo.distance) AS d
WHERE
d.rowindex IN (FLOOR(@rowindex / 2), CEIL(@rowindex / 2));

```

**说明:**

1.  从内部子查询开始–select 将@rowindex 指定为每个选定距离的增量索引，并对距离进行排序。
2.  一旦我们有了距离的排序列表，外部查询将获取数组中的中间项。如果数组包含奇数个项目，则两个值都是单个中间值。
3.  然后，外部查询的 SELECT 子句返回这两个值的平均值作为中间值。

**输出–**

```sql
25.0000
```