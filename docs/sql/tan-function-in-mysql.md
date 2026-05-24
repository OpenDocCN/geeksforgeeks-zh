# MySQL 中的 TAN()函数

> 原文:[https://www.geeksforgeeks.org/tan-function-in-mysql/](https://www.geeksforgeeks.org/tan-function-in-mysql/)

**TAN()函数:**
这个函数在 [MySQL](https://www.geeksforgeeks.org/sql-tutorial/) 中用来返回一个指定数的正切值。在任何直角三角形中，一个角的切线是对边的长度除以邻边的长度。同样，这也可以定义为 x 的正切是 x 的正弦除以 x 的余弦，其中 x 是角度。

**语法:**

```sql
TAN(number)
```

**参数:**
该方法接受如下参数。

*   **数字–**指定的数值。

**返回:**
返回指定数字的正切值。

**例-1:**
1 的正切值是 1.557772464902

```sql
SELECT TAN(1);
```

**输出:**

```sql
1.5574077246549023
```

**例-2:**
0 的正切为 0。

```sql
SELECT TAN(0);
```

**输出:**

```sql
0
```

**例-3 :**
例-3 的切线是 0.1425465430742

```sql
SELECT TAN(-3);
```

**输出:**

```sql
0.1425465430742778
```

**例-4:**
3 的正切值为-0.142546543074

```sql
SELECT TAN(3);
```

**输出:**

```sql
-0.1425465430742778
```

**应用:**
该函数用于返回指定数的正切值。