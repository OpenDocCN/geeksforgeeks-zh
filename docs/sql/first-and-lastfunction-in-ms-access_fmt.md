# MS Access 中的 First() 和 Last() 函数

> 原文：[`https://www.geeksforgeks.org/first-and-last-function-in-ms-access/`](https://www.geeksforgeks.org/first-and-last-function-in-ms-access/)

## 1. First() 函数
在 MS Access 中，`First()` 函数用于从查询返回的结果集中的第一条记录返回字段值。

### 语法
```sql
First(expr)
```

### 参数
*   `expr`：它表示一个字符串表达式，标识包含我们要使用的数据的字段，或者表示使用该字段中的数据执行计算的表达式。

### 返回
返回结果集中的第一条记录。

**Table – Employee_Details**

| `Emp_id` | `Emp_Name` | 经验 |
| --- | --- | --- |
| 101 | Amit | 5 |
| 102 | Rahul | 10 |
| 103 | 苏哈尼 | 8 |

### 示例-1
```sql
SELECT First(Emp_id) AS EmployeeId FROM Employee_Details;
```

**输出**

| 员工 Id |
| --- |
| 101 |

### 示例-2
```sql
SELECT First(Emp_Name) AS FirstEmployee FROM Employee_Details;
```

**输出**

| 第一个员工 |
| --- |
| Amit |

## 2. Last() 函数
在 MS Access 中，`Last()` 函数用于返回查询返回的结果集中最后一条记录的字段值。

### 语法
```sql
Last(expr)
```

### 参数
*   `expr`：它表示一个字符串表达式，标识包含我们要使用的数据的字段，或者表示使用该字段中的数据执行计算的表达式。

### 返回
返回结果集中的最后一条记录。

### 示例-1
```sql
SELECT Last(Emp_id) AS EmployeeId FROM Employee_Details;
```

**输出**

| 员工 Id |
| --- |
| 103 |

### 示例-2
```sql
SELECT Last(Emp_Name) AS LastEmployee FROM Employee_Details;
```

**输出**

| lastEmployee |
| --- |
| 苏哈尼 |