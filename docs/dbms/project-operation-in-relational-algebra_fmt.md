# 关系代数中的项目运算

> 原文: [https://www.geeksforgeeks.org/project-operation-in-relational-algebra/](https://www.geeksforgeeks.org/project-operation-in-relational-algebra/)

先决条件 – [关系代数](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)

`Project`操作选择（或选择）某些属性，丢弃其他属性。`Project`操作也称为垂直分区，因为它垂直分区关系或表，丢弃其他列或属性。

## 符号:

```
πA(R)
```

其中`A`是属性列表，它是来自关系`R`的属性的期望属性集，符号`π(pi)`用来表示`Project`运算符，`R`一般是关系代数表达式，它产生一个关系。

## 示例–

```
πAge(Student)
```

```
πDept, Sex(Emp)
```

## 示例–
给定一个具有以下元组的关系`Faculty( Class, Dept, Position)`:

| Class | Dept | Position |
| --- | --- | --- |
| five | 中学生毕业考试 | 助理教授 |
| five | 中学生毕业考试 | 助理教授 |
| six | 电子工程师 | 助理教授 |
| six | 电子工程师 | 助理教授 |

### 1. 教员的项目班级和部门–

```
πClass, Dept(Faculty)
```

| Class | Dept |
| --- | --- |
| five | 中学生毕业考试 |
| six | 电子工程师 |

在这里，我们可以观察到结果关系的度（属性数）是`2`，而`Faculty`关系的度是`3`，因此由此我们可以得出结论，在对关系应用`Project`操作时，我们可以得到不同程度的关系。

因此，结果关系的程度等于属性列表`A`中的属性数量。

### 2. 教员项目职位–

```
πPosition(Faculty)
```

| Position |
| --- |
| 助理教授 |

在这里，我们可以观察到所有重复的元组都从结果关系中移除了。这被称为重复消除。

### 3. 教员项目课–

```
πClass(Faculty)
```

| Class |
| --- |
| five |
| six |

## 重要点:

1.  `Project`操作删除重复的元组。
2.  `Project`操作不可交换，即:

```
πAttribute List 1(πAttribute List2(R)) != πAttribute List 2 (πAttribute List1(R))
```

3.  以下表达式仅在`Attribute List 1`是`Attribute List 2`的子集时才有效。

```
πAttribute List 1(πAttribute List2(R))
```

而且，写上面的表达式和写下面的表达式一样好:

```
πAttribute List 1(πAttribute List2(R)) = πAttribute List 1 (R)
```

4.  `Project`操作产生的关系的基数（元组数）为:

```
1 <= πA(R) <= |R|
```

5.  `Project`操作产生的关系的程度（属性数）等于属性列表`A`中的属性数。
6.  在 SQL 中，`SELECT DISTINCT`查询与这里的`PROJECT`完全相同。