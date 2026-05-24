# MySQL | CONNECTION_ID()函数

> 原文:[https://www.geeksforgeeks.org/mysql-connection_id-function/](https://www.geeksforgeeks.org/mysql-connection_id-function/)

MySQL**CONNECT _ ID()**函数用于返回 MySQL 中当前连接的连接标识。用于建立数据库连接的连接标识对于连接的客户端之间的每个连接都是唯一的。CONNECTION_ID()函数不需要任何参数或自变量。

CONNECTION_ID()函数返回的值与信息模式的标识列中显示的值类型相同。PROCESSLIST 表。

**语法:**

```sql
CONNECTION_ID()
```

**使用的参数:**
CONNECTION _ ID()函数不需要任何参数或自变量。

**返回值:**
MySQL CONNECTION _ ID()函数返回一个整数值，代表当前唯一的连接标识。

**支持的 MySQL 版本:**

*   MySQL 5.7
*   MySQL 5.6
*   MySQL 5.5
*   MySQL 5.1
*   MySQL 5.0
*   MySQL 4.1
*   MySQL 4.0
*   MySQL 3.23

**示例:**实现 CONNECTION_ID()函数。

```sql
SELECT CONNECTION_ID(); 
```

**输出:**

```sql
1196078 
```