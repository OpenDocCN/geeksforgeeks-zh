# MS Access 中的 Sgn()和 Skr()功能

> 原文:[https://www . geesforgeks . org/SGN-and-sqr-function-in-ms-access/](https://www.geeksforgeeks.org/sgn-and-sqr-function-in-ms-access/)

**1。Sgn()函数:**
sgn()函数返回一个数字的符号，如果这个数字是正数，那么它返回 1，如果这个数字等于 0，那么它返回 0，否则如果这个数字小于 0，那么它返回-1。

**语法:**

```sql
Sgn(number)
```

**示例-1 :**

```sql
SELECT Sgn(93.5) AS SgnNum;
```

**输出–**

| SGN um |
| one |

**示例-2 :**

```sql
SELECT Sgn(-93.5) AS SgnNum;
```

**输出–**

| SGN um |
| -1 |

**2。函数的作用是:返回一个数的平方根。在这个函数中，一个数字将作为参数传递，它将返回该数字的平方根。数字必须为正数。**

**语法:**

```sql
Sqr(number)
```

**示例-1**

```sql
SELECT Sqr(100) AS SqrNum;
```

**输出-**

| sqrnum |
| Ten |

**示例-2**

```sql
SELECT Sqr(169) AS SqrNum;
```

**输出–**

| sqrnum |
| Thirteen |