# 下降功能及其参数

> 原文:[https://www . geesforgeks . org/drop-function-and-its-parameters/](https://www.geeksforgeeks.org/drop-function-and-its-parameters/)

[删除函数](https://www.geeksforgeeks.org/sql-drop-truncate/) :
该语句可用于删除现有的用户定义函数。

**语法**:

```sql
DROP FUNCTION [ IF EXISTS ] schema_name.function_name;

```

**示例–**

让我们考虑极客是你想删除的功能，然后使用如下语法。

```sql
DROP FUNCTION Geeks;
```

**要删除多个用户定义的函数，请使用以下语法:**

```sql
DROP FUNCTION [IF EXISTS]  
 schema_name.function_name1,  
 schema_name.function_name2,
...;

```

**参数:**

*   **IF EXISTS–**
    IF EXISTS 参数是可选的，仅当函数存在时用于删除函数。如果在不使用 IF EXISTS 选项的情况下移除不存在的函数，SQL Server 将抛出一个错误。
*   **schema _ name–**
    schema _ name 是可选参数。schema_name 定义了用户定义函数所属的模式的名称。
*   **函数名–**
    函数名是将要删除的函数的名称。

**备注:**

如果函数中有像 CHECK 或 DEFAULT 这样的约束，DROP FUNCTION 语句将返回错误。

**示例–**

让我们创建一个根据金额、列表和百分比计算折扣的函数:

**创建“极客折扣金额”功能–**

```sql
CREATE FUNCTION Geek.discount_amount (
   @amount INT,
   @list DEC(10,2),
   @percentage DEC(4,2)  
) RETURNS DEC(10,2)  
AS  
BEGIN
   RETURN @quantity * @amount * @percentage
END
```

要删除该函数，可以使用下面给出的 SQL 查询。

```sql
DROP FUNCTION IF EXISTS Geek.discount_amount;
```