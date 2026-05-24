# MySQL `NULLIF()`函数

> 原文：[https://www.geeksforgeeks.org/mysql-nullif-function/](https://www.geeksforgeeks.org/mysql-nullif-function/)

MySQL的`NULLIF()`函数用于比较两个表达式。如果两个表达式相等，函数返回`NULL`；否则返回第一个表达式。

## 语法
```sql
NULLIF(expression1, expression2)
```

## 参数
- **expression1**：指定第一个表达式。
- **expression2**：指定第二个表达式。

## 返回值
如果传递的两个表达式相等，`NULLIF()`函数返回`NULL`；否则返回第一个表达式。

## 支持的 MySQL 版本
* MySQL 5.7
* MySQL 5.6
* MySQL 5.5
* MySQL 5.1
* MySQL 5.0
* MySQL 4.1
* MySQL 4.0
* MySQL 3.23

## 示例

### 示例-1
通过比较两个相同的字符串来演示`NULLIF()`函数。
```sql
SELECT NULLIF("Geeksforgeeks", "Geeksforgeeks"); 
```
**输出：**
```sql
NULL 
```

### 示例-2
通过比较两个不相等的字符串来演示`NULLIF()`函数。
```sql
SELECT NULLIF("123", "Geeksforgeeks"); 
```
**输出：**
```sql
"123"
```

### 示例-3
通过比较两个整数值来演示`NULLIF()`函数。
```sql
SELECT NULLIF(2, 4); 
```
**输出：**
```sql
2
```