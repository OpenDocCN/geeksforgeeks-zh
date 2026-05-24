# 微软 Access 和 dBASE 的区别

> 原文：[https://www.geeksforgeeks.org/difference-between-microsoft-access-and-dbase/](https://www.geeksforgeeks.org/difference-between-microsoft-access-and-dbase/)

## 微软 Access

微软 Access 是一个数据库程序，它使用唯一的身份证号码和一个可编辑的数据列表来存储大量项目的详细信息，也就是说，你可以使用这个程序来存储。

- Access 旨在让多个用户在同一个数据库文件中工作，并提供各种安全预防措施，以帮助保护数据，如记录级锁定。
- 在 Access 中创建的数据库以 `mdb` 扩展名保存。
- 数据存储在表中。
- 表中的每个字段都可以与某些约束相关联，例如只允许字母数字值。
- 像任何其他关系数据库一样，它基于表、字段和关系的原理工作。它支持不同种类的数字、日期、文本等。

## dBASE

dBASE 是最成功的微型计算机数据库管理系统之一。这是第一个商业上成功的个人电脑数据库系统。它用于创建和操作关系数据库。dBASE 使用类似于 `BASIC` 语言的过程函数和命令。它使用简单的命令进行数据操作，如 `use`、`GO TOP` 等。

## dBASE 和微软 Access 的区别

| 序号 | Microsoft Access | dBASE |
| :--- | :--- | :--- |
| 1. | 它是由微软在 1992 年开发的。 | 它是由阿什顿·泰特在 1979 年开发的。 |
| 2. | Windows 只是服务器操作系统使用微软 Access。 | DOS 和 Windows 都是服务器操作系统使用 dBASE。 |
| 3. | 微软 Access 支持标准查询语言。 | dBASE 不支持 `SQL`。 |
| 4. | 使用 `ADO.NET`、`JDBC`、`ODBC` 等作为 API 等访问方式。 | 不支持任何 API 和访问方法。 |
| 5. | 事务的 `ACID` 属性（原子性、一致性、隔离性和持久性）后面是微软 Access。 | dBASE 内部数据没有事务概念，但是 IDE 在访问外部 `DBMS` 时确实支持事务。 |
| 6. | 微软访问允许服务器端脚本。 | dBASE 中不允许服务器端脚本。 |
| 7. | 微软访问权限中的用户没有访问权限。 | 用户和角色的访问权限在 dBASE 中。 |
| 8. | 触发器可以在微软访问中使用。 | 触发器不能在 dBASE 中使用。 |