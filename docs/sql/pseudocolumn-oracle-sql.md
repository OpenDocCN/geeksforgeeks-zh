# Oracle SQL 中的伪列

> 原文:[https://www.geeksforgeeks.org/pseudocolumn-oracle-sql/](https://www.geeksforgeeks.org/pseudocolumn-oracle-sql/)

**伪列**:伪列的行为类似于表列，但实际上并不存储在表中。您可以从伪列中进行选择，但不能插入、更新或删除它们的值。伪列也类似于没有参数的函数。本节描述这些伪列:

*   CURRVAL 和 NEXTVAL
*   水平
*   rowid。rowid
*   罗努姆

**1。CURRVAL 和 NEXTVAL:** 序列是可以生成唯一序列值的模式对象。这些值通常用于主键和唯一键。您可以使用这些伪列来引用 SQL 语句中的序列值:

*   **CURRVAL :** 返回序列的当前值。
*   **NEXVAL:**递增序列并返回下一个值。

举例:
从对偶中选择学生；
插入学生价值观(STUDENT eq . nextval，' BISHAL '，' JAVA '，7902)；

**2。LEVEL:** 对于分层查询返回的每一行，LEVEL 伪列为根节点返回 1，为根的子节点返回 2，依此类推。

**3。ROWNUM:** Oracle 引擎维护用户在表中插入的每条记录的数量。借助 ROWNUM 子句，我们可以根据插入的记录访问数据。

示例:
从电磁脉冲中选择*其中行数<= 3；

**4。对于数据库中的每一行，ROWID 伪列返回一行的地址。ROWID 包含 3 个关于行地址的信息:**

*   **文件号:**文件号表示表号。
*   **DataBlockNo :** DataBlockNo 表示 oracle SQL 引擎为保存记录而分配的空间。
*   **记录号:** Oracle 引擎维护每个记录的记录号。

例:
SELECT ROWID，ename FROM emp WHERE deptno = 20