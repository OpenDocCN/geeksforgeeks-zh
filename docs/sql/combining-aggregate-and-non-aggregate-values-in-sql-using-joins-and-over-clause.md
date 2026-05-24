# 使用连接和 Over 子句结合 SQL 中的聚合值和非聚合值

> 原文:[https://www . geesforgeks . org/combining-aggregate-and-non-aggregate-values-in-SQL-use-joins-and-over-子句/](https://www.geeksforgeeks.org/combining-aggregate-and-non-aggregate-values-in-sql-using-joins-and-over-clause/)

先决条件–[SQL 中的聚合函数](https://www.geeksforgeeks.org/database-management-system-aggregate-functions/)、[SQL 中的联接](https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/)、
聚合函数对一组值执行计算并返回单个值。现在，考虑一个员工表 EMP 和一个部门表 DEPT，其结构如下:

**表─**员工表

<figure class="table">

| (full) name | 【无效】 |  |
| --- | --- | --- |
| 【高龄】 |  | [date] |
| 【萨尔】 |  |

</figure>

**表─**系表

<figure class="table">型

| 【 name 】 | 【无效】 |
| --- | --- |

</figure>

需要以下结果:

1.  显示名称、SAL、EMP 的工作以及完成相同工作的 EMP 的最大、最小、AVG、总 SAL。
2.  显示在其中工作的电磁脉冲数量的 DEPTNAME。

聚合值不能直接与非聚合值一起使用以获得结果。因此，可以使用以下概念:

**1。使用连接–**

1.  创建包含聚合值结果的子表。
2.  使用连接，使用子表的结果以非聚合值显示它们。

使用 JOIN 解决问题 1:

```sql
SELECT ENAME, SAL, EMP.JOB, 
            SUBTABLE.MAXSAL, SUBTABLE.MINSAL, 
            SUBTABLE.AVGSAL, SUBTABLE.SUMSAL
FROM EMP
INNER JOIN
        (SELECT JOB, MAX(SAL) MAXSAL, MIN(SAL) 
                MINSAL, AVG(SAL) AVGSAL, SUM(SAL) SUMSAL 
         FROM EMP 
          GROUP BY JOB) SUBTABLE
                  ON EMP.JOB = SUBTABLE.JOB; 
```

输出为样本数据:

<figure class="table">T14】AvgSalT16】SumSalT20T28】3300T30】1920 T68

| Ename | Sal | homework | 马萨尔 | 最小数量 |
| --- | --- | --- | --- | --- |
| 斯科特 | Three thousand three hundred | 分析家 | Three thousand three hundred | 分析家 | Three thousand three hundred | One thousand nine hundred and twenty-five | Two thousand eight hundred and forty-one point six seven | Eight thousand five hundred and twenty-five |
| 史密斯 | Three thousand three hundred | （轮船、飞机等上面的）全体工作人员 | Three thousand three hundred |

</figure>

**2。使用“Over”子句–**

1.  OVER 子句和 PARTITION BY 一起用于将数据分成多个分区。
2.  特定功能对每个分区起作用。

使用 OVER 子句解决问题 2:

```sql
SELECT DISTINCT(DNAME),
COUNT(ENAME) OVER (PARTITION BY EMP.DEPTNO) EMP
FROM EMP
RIGHT OUTER JOIN DEPT
ON EMP.DEPTNO=DEPT.DEPTNO
ORDER BY EMP DESC; 
```

<figure class="table">

| Dname | 电磁脉冲 |
| --- | --- |
| 销售 | six |
| 研究 | five |
| 会计 | three |
| 操作 | Zero |
| 其他人 | Zero |

</figure>