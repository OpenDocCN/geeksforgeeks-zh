# Derby 和 PostgreSQL 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-derby-and-postgresql/](https://www.geeksforgeeks.org/difference-between-derby-and-postgresql/)

**1. Derby:**
Derby 是一个用 `Java` 实现的全功能、开源的关系数据库管理系统（`RDBMS`），顾名思义，它是由 `Apache Software Foundations` 开发的。它基于 `Java`、`JDBC` 和 `SQL` 标准。Derby 易于安装、部署和使用。它要么嵌入到 `Java` 应用程序中，要么用作数据库服务器。

**2. PostgreSQL:**
PostgreSQL 是一个强大的开源对象关系数据库系统。由于其高稳定性，它以低维护工作量提供了良好的性能。PostgreSQL 是第一个实现多版本并发控制（`MVCC`）功能的数据库管理系统。

## Derby 和 PostgreSQL 的区别

| 序号 | Derby | PostgreSQL |
| :--- | :--- | :--- |
| 1 | 它是由 `Apache` 软件基金会在 1997 年开发的。 | 它是由 `PostgreSQL` 全球开发集团于 1989 年开发的。 |
| 2 | 它是用 `Java` 语言编写的。 | 它是用 `C` 语言写的。 |
| 3 | Derby 的主要数据库模型是关系数据库管理系统。 | PostgreSQL 的主要数据库模型是关系数据库管理系统。 |
| 4 | Derby 的服务器操作系统有 `Windows`、`macOs`、`Linux`、`Unix`、`BSD` 和 `z/OS`。 | PostgreSQL 服务器操作系统有 `FreeBSD`、`HP-UX`、`Linux`、`NetBSD`、`OpenBSD`、`OS X`、`Solaris`、`Unix` 和 `Windows`。 |
| 5 | 它只支持 `Java` 编程语言。 | 它支持 `C`、`.Net`、`C++`、`Java`、`JavaScript`、`PHP`、`Python`、`Ruby`。 |
| 6 | Derby 使用的 `API` 和其他访问方法是 `JDBC`。 | 它使用 `ADO.NET`、`JDBC`、原生 `C` 库、`ODBC`、流 `API` 对大对象作为 `API`。 |
| 7 | 它根据 `SQL` 标准提供细粒度的访问权限。 | 它为用户和角色提供访问权限。 |
| 8 | 它有服务器端脚本的 `Java` 存储过程。 | 它有用户定义的服务器端脚本函数。 |
| 9 | 它支持内存功能。 | 它不支持内存功能。 |
| 10 | 它支持二级索引。 | 它还支持二级索引。 |