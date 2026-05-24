# 移动台接入中的最大()和最小()功能

> 原文:[https://www . geesforgeks . org/max-and-min-function-in-ms-access/](https://www.geeksforgeeks.org/max-and-min-function-in-ms-access/)

**1。Max()函数:**
max()函数返回给定集合的最大值。在函数中传递一个查询，在符合条件的记录中，作为结果返回的最大值是多少。表达式将作为参数传递，并将返回表达式中的最大值。

**语法:**

```sql
Max (expression)
```

**演示数据库示例:**

**表名**:学生

| 学生 id | 马克斯（英格兰人姓氏） |
| One hundred and twenty-one | Fifty-six |
| 122 | Forty-five |
| One hundred and twenty-three | eighty-nine |
| One hundred and twenty-four | Fifty |

**示例-1 :**

```sql
SELECT Max(Marks) AS marks 
FROM student;
```

**输出–**

| 记号 |
| eighty-nine |

**示例-2 :**

```sql
SELECT Max(Marks) AS marks 
FROM student
where Marks<80;
```

**输出–**

| 记号 |
| Fifty-six |

**2。Min()函数:**
min()函数的工作方式与 max()函数类似，但它将返回表达式的最小值。在这个函数中，查询将作为参数传递，并将返回最小记录。

**语法:**

```sql
 Min(expression)
```

**示例-1 :**

```sql
SELECT Min(Marks) AS marks 
FROM student;
```

**输出–**

| 记号 |
| Forty-five |

**示例-2 :**

```sql
SELECT Min(Marks) AS marks 
FROM student
where Marks>50;
```

**输出–**

| 记号 |
| Fifty-six |