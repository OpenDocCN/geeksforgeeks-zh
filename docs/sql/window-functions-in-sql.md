# SQL 中的窗口函数

> 原文:[https://www.geeksforgeeks.org/window-functions-in-sql/](https://www.geeksforgeeks.org/window-functions-in-sql/)

窗口函数在特定窗口(一组行)上应用聚合和排名函数。OVER 子句与窗口函数一起使用来定义该窗口。OVER 子句做两件事:

*   将行划分为一组行。(使用了 PARTITION BY 子句)
*   将这些分区中的行按特定顺序排序。(使用 ORDER BY 子句)

**注意–**
如果分区没有完成，那么 ORDER BY 会对表的所有行进行排序。

**基本语法:**

```sql
SELECT coulmn_name1, 
 window_function(cloumn_name2),
 OVER([PARTITION BY column_name1] [ORDER BY column_name3]) AS new_column
FROM table_name;

window_function= any aggregate or ranking function    
column_name1= column to be selected
coulmn_name2= column on which window function is to be applied
column_name3= column on whose basis partition of rows is to be done
new_column= Name of new column
table_name= Name of table
```

**聚合窗口函数:**
应用于特定窗口(一组行)的各种聚合函数，如 SUM()、COUNT()、AVERAGE()、MAX()、MIN()被称为聚合窗口函数。

考虑以下**员工**表:

<figure class="table">

| 名字 | 年龄 | 部门 | 薪水 |
| --- | --- | --- | --- |
| Ramesh | Twenty | 金融 | 50, 000 |
| --- | --- | --- | --- |
| 深的 | Twenty-five | 销售 | 30, 000 |
| 苏雷什 | Twenty-two | 金融 | Fifty thousand |
| 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | Twenty-eight | 金融 | 20, 000 |
| 帕拉德普 | Twenty-two | 销售 | 20, 000 |

</figure>

**示例–**
查找各部门员工的平均工资，并按年龄排序部门内的员工。

```sql
SELECT Name, Age, Department, Salary, 
 AVERAGE(Salary) OVER( PARTITION BY Department ORDER BY Age) AS Avg_Salary
 FROM employee
```

上述查询的输出将是:

<figure class="table">

| 名字 | 年龄 | 部门 | 薪水 | 平均工资 |
| --- | --- | --- | --- | --- |
| Ramesh | Twenty | 金融 | 50, 000 | 40, 000 |
| 苏雷什 | Twenty-two | 金融 | Fifty thousand | 40, 000 |
| 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | Twenty-eight | 金融 | 20, 000 | 40, 000 |
| 帕拉德普 | Twenty-two | 销售 | 20, 000 | 25, 000 |
| 深的 | Twenty-five | 销售 | 30, 000 | 25, 0000 |

</figure>

正如我们在上面的例子中看到的，每个部门内的平均工资是计算出来的，并显示在 Avg_Salary 列中。此外，特定列中的员工按年龄排序。

**排名窗口函数:**
排名函数为，RANK()，DENSE_RANK()，ROW_NUMBER()

*   **RANK() –** 
    As the name suggests, the rank function assigns rank to all the rows within every partition. Rank is assigned such that rank 1 given to the first row and rows having same value are assigned same rank. For the next rank after two same rank values, one rank value will be skipped. 
*   **DENSE_RANK() –** 
    It assigns rank to each row within partition. Just like rank function first row is assigned rank 1 and rows having same value have same rank. The difference between RANK() and DENSE_RANK() is that in DENSE_RANK(), for the next rank after two same rank, consecutive integer is used, no rank is skipped. 
*   **ROW_NUMBER() –** 
    It assigns consecutive integers to all the rows within partition. Within a partition, no two rows can have same row number. 

**注意–**
在使用等级窗口函数时，应强制指定 ORDER BY()。

**例–**
根据各部门内部工资计算员工排号、职级、密级为员工表。

```sql
SELECT 
ROW_NUMBER() OVER (PARTITION BY Department ORDER BY Salary DESC) 
AS emp_row_no, Name,  Department, Salary,
RANK() OVER(PARTITION BY Department 
ORDER BY Salary DESC) AS emp_rank,
DENSE_RANK() OVER(PARTITION BY Department 
                  ORDER BY Salary DESC) 
                  AS emp_dense_rank,
FROM employee 
```

上述查询的输出将是:

<figure class="table">

| emp_row_no | 名字 | 部门 | 薪水 | 电磁脉冲等级 | emp _ 密集 _ 等级 |
| --- | --- | --- | --- | --- | --- |
| one | 苏雷什 | 金融 | 50, 000 | one | one |
| Two | Ramesh | 金融 | 50, 000 | one | one |
| three | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 金融 | 20, 000 | three | Two |
| one | 深的 | 销售 | 30, 000 | one | one |
| Two | 帕拉德普 | 销售 | 20, 000 | Two | Two |

</figure>

因此，我们可以看到，正如 ROW_NUMBER()的定义中所提到的，行号是每个分区内的连续整数。此外，我们可以看到秩和密集秩的区别，在密集秩中，秩值之间没有间隙，而在重复秩之后，秩值之间有间隙。