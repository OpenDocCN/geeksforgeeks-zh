# 不同类型的数据库用户

> 原文：[https://www.geeksforgeeks.org/different-types-of-database-users/](https://www.geeksforgeeks.org/different-types-of-database-users/)

数据库用户根据他们与数据库的交互进行分类。

这是数据库管理系统中七种类型的数据库用户。

## 1. Database Administrator (DBA)

`Database Administrator (DBA)` 是一个定义模式并控制数据库三个级别的人/团队。
DBA 将为需要访问数据库的用户创建新的账户 ID 和密码。
DBA 还负责为数据库提供安全性，只允许授权用户访问/修改数据库。
*   数据库管理员还监控恢复和备份，并提供技术支持。
*   数据库管理员在数据库管理系统中有一个数据库管理员帐户，称为系统或超级用户帐户。
*   数据库管理员修复由于硬件和/或软件故障造成的损坏。

## 2. Naive / Parametric End Users

`Parametric End Users` 是那些不具备任何 `DBMS` 知识，但经常在日常生活中使用数据库应用程序以获得所需结果的非专业用户。

比如铁路的订票用户就是幼稚用户。任何银行的职员都是天真的用户，因为他们没有任何数据库管理系统的知识，但他们仍然使用数据库并执行他们给定的任务。

## 3. System Analyst

`System Analyst` 是分析 `Parametric End Users` 需求的用户。他们检查终端用户的所有需求是否得到满足。

## 4. Sophisticated Users

`Sophisticated Users` 可以是工程师、科学家、业务分析师，他们熟悉数据库。他们可以根据自己的需求开发自己的数据库应用程序。他们不编写程序代码，而是通过查询处理器直接编写 `SQL queries` 来与数据库交互。

## 5. Data Base Designers

`Data Base Designers` 是设计数据库结构的用户，包括表、索引、视图、约束、触发器、存储过程。他/她控制必须存储哪些数据以及数据项如何关联。

## 6. Application Program

`Application Program` 是为应用程序编写代码的后端程序员。他们是计算机专业人士。这些程序可以用 `Visual Basic`、`Developer`、`C`、`FORTRAN`、`COBOL` 等编程语言编写。

## 7. Casual Users / Temporary Users

`Casual Users` 或 `Temporary Users` 是偶尔使用/访问数据库但每次访问数据库时都需要新信息的用户，例如中层或更高层管理人员。

```
if (condVar > someVal) {console.log("xxx")}
```