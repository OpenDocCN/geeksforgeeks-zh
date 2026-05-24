# SQL | listall

> 哎哎哎:# t0]https://www . geeksforgeeks . org/SQL-listagg/

DBMS 中的 LISTAGG 函数用于聚合数据库表中列中数据的字符串。

*   It makes it very easy to concatenate strings. It is similar to concatenation, but uses grouping.
*   The feature of this function is that it also allows the elements in the concatenated list to be sorted.

**语法:**

```sql
LISTAGG (measure_expr [, 'delimiter']) WITHIN GROUP 
(order_by_clause) [OVER query_partition_clause]
measure_expr : The column or expression to concatenate the values.
delimiter : Character in between each measure_expr, which is by default a comma (,) .
order_by_clause : Order of the concatenated values.
```

让我们有一个名为 Gfg 的表，该表有两列，显示每个主题所属的主题名称和主题编号，如下所示:

```sql
SQL> select * from GfG;

SUBNO      SUBNAME
---------- ------------------------------
D20        Algorithm
D30        DataStructure
D30        C
D20        C++
D30        Python
D30        DBMS
D10        LinkedList
D20        Matrix
D10        String
D30        Graph
D20        Tree

11 rows selected.

```

**查询 1:** 使用 LISTAGG 函数编写一个 SQL 查询，以逗号分隔的值在单个字段中输出主题名称。

```sql
SQL> SELECT LISTAGG(SubName, ' , ') WITHIN GROUP (ORDER BY SubName) AS SUBJECTS
  2  FROM   GfG ;

```

输出:

```sql
SUBJECTS
-----------------------------------------------------------------------------------
Algorithm , C , C++ , DBMS , DataStructure , Graph , LinkedList , Matrix , Python ,
String , Tree

```

**查询 2:** 借助 LISTAGG 函数，编写一个 SQL 查询，对每个主题进行分组，并显示每个主题在各自部门中的位置，用逗号分隔。

```sql
SQL> SELECT SubNo, LISTAGG(SubName, ' , ') WITHIN GROUP (ORDER BY SubName) AS SUBJECTS
  2  FROM   GfG
  3  GROUP BY SubNo;

```

输出:

```sql
SUBNO      SUBJECTS
------     --------------------------------------------------------------------------------
D10        LinkedList , String
D20         Algorithm , C++ , Matrix , Tree
D30         C , DBMS , DataStructure , Graph , Python

```

**查询 3:** 借助 LISTAGG 函数，编写一个 SQL 查询，显示按主题号(SUBNO)排序的属于各个部门的主题。

```sql
SQL> SELECT SubNo, LISTAGG(SubName, ',') WITHIN GROUP (ORDER BY SubName) AS SUBJECTS
  2  FROM   GfG
  3  GROUP BY SubNo
  4  ORDER BY SubNo;

```

输出:

```sql
SUBNO        SUBJECTS
-----        --------------------------------
D10          LinkedList, String
D20          Algorithm, C++, Matrix, Tree
D30          C, DBMS, DataStructure, Graph, Python

```

本文由 MAZHAR IMAM KHAN 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。