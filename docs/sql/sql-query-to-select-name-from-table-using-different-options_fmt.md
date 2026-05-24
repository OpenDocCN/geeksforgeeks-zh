# SQL：使用不同选项从表中选择名称的查询

> 原文：[https://www.geeksforgeeks.org/sql-query-to-select-name-from-table-using-different-options/](https://www.geeksforgeeks.org/sql-query-to-select-name-from-table-using-different-options/)

## 让我们考虑下面这张名为 `Geeks` 的表格

| G_ID | FIRSTNAME | LASTNAME | DEPARTMENT |
| --- | --- | --- | --- |
| 1 | Mohan | Arora | Admin |
| 2 |  | Verma |  |
| 3 |  |  | Admin |
| 6 | Vinod | Diwan | Review |
| 7 |  | Singh | Review |
| 8 | Nisha |  |  |

## 使用别名作为名称从 `Geeks` 表中写入“名字”的 SQL 查询

```sql
Select FIRSTNAME AS NAME 
from Geeks;
```

**输出：**

| NAME |
| --- |
| Mohan |
| Nisha |

## 用大写字母从 `Geeks` 表中写出“名字”的 SQL 查询

```sql
Select upper(FIRSTNAME) 
from Geeks;
```

**输出：**

| (No column name) |
| --- |
| MOHAN |
| NISHA |

## 从 `Geeks` 表中查找 `FIRSTNAME` 前三个字符的 SQL 查询

```sql
Select substring(FIRSTNAME, 1, 3) 
from Geeks;
```

**输出：**

| (No column name) |
| --- |
| Moh |
| Nis |

## 将 `Geeks` 表中的名字和姓氏写入带有空格字符的单列 `COMPLETENAME` 的 SQL 查询应该将它们分开

```sql
Select CONCAT(FIRSTNAME, ' ', LASTNAME) AS 'COMPLETENAME' 
from Geeks;
```

**输出：**

| COMPLETENAME |
| --- |
| Mohan Arora |
| Nisha Verma |

## 编写一个 SQL 查询，按照名字升序打印 `Geeks` 表中的所有工作人员详细信息

```sql
Select * 
from Geeks 
order by FIRSTNAME asc;
```

**输出：**

| G_ID | FIRSTNAME | LASTNAME | DEPARTMENT |
| --- | --- | --- | --- |
| 4 | Aman |  | Admin |
| 1 | Mohan | Arora | Admin |
| 7 |  | Singh | Review |
| 6 | Vinod | Diwan | Review |
| 8 | Nisha | Kumar |  |