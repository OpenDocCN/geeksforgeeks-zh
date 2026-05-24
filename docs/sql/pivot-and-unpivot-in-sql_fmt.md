# 在 SQL 中透视和取消透视

> 原文: [https://www.geeksforgeeks.org/pivot-and-unpivot-in-sql/](https://www.geeksforgeeks.org/pivot-and-unpivot-in-sql/)

在 SQL 中，`Pivot` 和 `Unpivot` 是关系运算符，用于将一个表转换为另一个表，以实现更简单的表视图。按照惯例，我们可以说 `Pivot` 运算符将表的行数据转换为列数据。`Unpivot` 运算符的作用相反，它将基于列的数据转换为行。

## 语法

### 1. Pivot

```sql
SELECT (ColumnNames) 
FROM (TableName) 
PIVOT
 ( 
   AggregateFunction(ColumnToBeAggregated)
   FOR PivotColumn IN (PivotColumnValues)
 ) AS (Alias) -- Alias is a temporary name for a table
```

### 2. Unpivot

```sql
SELECT (ColumnNames) 
FROM (TableName) 
UNPIVOT
 ( 
   AggregateFunction(ColumnToBeAggregated)
   FOR PivotColumn IN (PivotColumnValues)
 ) AS (Alias)
```

## 示例-1

我们创建了一个名为 `geeksforgeeks` 的简单表格，其中包含 `CourseName`、`CourseCategory` 和 `Price` 等值，并插入了相应的值。

```sql
Create Table geeksforgeeks 
( 
CourseName nvarchar(50), 
CourseCategory nvarchar(50),
Price int  
)

Insert into geeksforgeeks  values('C', 'PROGRAMMING', 5000) 
Insert into geeksforgeeks  values('JAVA', 'PROGRAMMING', 6000) 
Insert into geeksforgeeks  values('PYTHON', 'PROGRAMMING', 8000) 
Insert into geeksforgeeks  values('PLACEMENT 100', 'INTERVIEWPREPARATION', 5000)

SELECT * FROM geeksforgeeks 
```

我们得到的输出是:

| CourseName | CourseCategory | Price |
| --- | --- | --- |
| C | PROGRAMMING | 5000 |
| JAVA | PROGRAMMING | 6000 |
| PYTHON | PROGRAMMING | 8000 |
| PLACEMENT 100 | INTERVIEWPREPARATION | 5000 |

现在，对该数据应用 `PIVOT` 运算符:

```sql
SELECT CourseName, PROGRAMMING, INTERVIEWPREPARATION
FROM geeksforgeeks 
PIVOT 
( 
SUM(Price) FOR CourseCategory IN (PROGRAMMING, INTERVIEWPREPARATION ) 
) AS PivotTable
```

使用透视运算符后，我们得到以下结果:

| CourseName | PROGRAMMING | INTERVIEWPREPARATION |
| --- | --- | --- |
| C | 5000 | NULL |
| JAVA | 6000 | NULL |
| PYTHON | 8000 | NULL |
| PLACEMENT 100 | NULL | 5000 |

## 示例-2

现在，我们使用上例中创建的同一个表 `geeksforgeeks`，并将 `Unpivot` 操作符应用于我们的透视表。

应用 `Unpivot` 操作符:

```sql
SELECT CourseName, CourseCategory, Price 
FROM 
(
SELECT CourseName, PROGRAMMING, INTERVIEWPREPARATION FROM geeksforgeeks 
PIVOT 
( 
SUM(Price) FOR CourseCategory IN (PROGRAMMING, INTERVIEWPREPARATION) 
) AS PivotTable
) P 
UNPIVOT 
( 
Price FOR CourseCategory IN (PROGRAMMING, INTERVIEWPREPARATION)
) 
AS UnpivotTable
```

在使用 `Unpivot` 操作符之后，我们得到了原始表，因为我们已经成功地将表的列转换回行:

| CourseName | CourseCategory | Price |
| --- | --- | --- |
| C | PROGRAMMING | 5000 |
| JAVA | PROGRAMMING | 6000 |
| PYTHON | PROGRAMMING | 8000 |
| PLACEMENT 100 | INTERVIEWPREPARATION | 5000 |