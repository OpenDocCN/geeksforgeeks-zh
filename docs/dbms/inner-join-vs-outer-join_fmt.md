# 内连接 vs 外连接

> 原文：[https://www.geeksforgeeks.org/inner-join-vs-outer-join/](https://www.geeksforgeeks.org/inner-join-vs-outer-join/)

## 什么是连接？

基于两个或多个表之间的公共字段，使用一个 SQL 连接来组合两个或多个表中的数据。例如，考虑以下两个表。

**学生表**

| `EnrollNo` | `StudentName` | `Address` |
| --- | --- | --- |
| 1001 | 极客 1 | 极客 squiz1 |
| 1002 | 极客 2 | 极客 squiz2 |
| 1003 | 极客 3 | 极客 squiz3 |
| 1004 | 极客 4 | 极客 squiz4 |

**学生课程表**

| `CourseID` | `EnrollNo` |
| --- | --- |
| 1 | 1001 |
| 2 | 1001 |
| 3 | 1001 |
| 1 | 1002 |
| 2 | 1003 |

下面是连接查询，显示注册不同课程号的学生姓名。

```sql
SELECT StudentCourse.CourseID, Student.StudentName
FROM Student
INNER JOIN StudentCourse 
ON StudentCourse.EnrollNo = Student.EnrollNo
ORDER BY StudentCourse.CourseID
```

**注**：以上 `INNER` 可选。简单连接也被认为是内部连接。

上述查询将产生以下结果。

| `CourseID` | `StudentName` |
| --- | --- |
| 1 | 极客 1 |
| 1 | 极客 2 |
| 2 | 极客 1 |
| 2 | 极客 3 |
| 3 | 极客 1 |

## 内连接和外连接有什么区别？

外连接有 3 种类型：
1.  左外连接
2.  右外连接
3.  完全连接

### 1) 左外连接

返回连接左侧的所有表格行。右侧没有匹配行的行，结果右侧包含空。

```sql
SELECT Student.StudentName,
       StudentCourse.CourseID
FROM Student
LEFT OUTER JOIN StudentCourse 
ON StudentCourse.EnrollNo = Student.EnrollNo
ORDER BY StudentCourse.CourseID
```

**注**：以上 `OUTER` 为可选。简单的左连接也被认为是左外连接。

| `StudentName` | `CourseID` |
| --- | --- |
| 极客 4 | *NULL* |
| 极客 2 | 1 |
| 极客 1 | 1 |
| 极客 1 | 2 |
| 极客 3 | 2 |
| 极客 1 | 3 |

### 2) 右外连接

类似于左外连接（右处处代替左）。

### 3) 完全外连接

包含左右外连接的结果。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的更多信息，请写评论。