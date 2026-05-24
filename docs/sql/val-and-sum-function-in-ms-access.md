# MS 访问中的 Val()和 Sum()函数

> 原文:[https://www . geesforgeks . org/val-and-sum-function-in-ms-access/](https://www.geeksforgeeks.org/val-and-sum-function-in-ms-access/)

**1。Val()函数:**
val()函数返回在字符串中找到的数字。在这个函数中，它将字符串作为参数，并将返回字符串中的数字。

**注意:**当第一个非数字字符出现时，该功能将停止读取。

**语法:**

```sql
Val(string) 
```

**示例-1 :**

```sql
SELECT Val("234geeksforgeeks12") 
AS ValNum;
```

**输出–**

| 瓦隆 |
| Two hundred and thirty-four |

**示例-2 :**

```sql
SELECT Val("345") 
AS ValNum;
```

**输出–**

| 瓦隆 |
| Three hundred and forty-five |

**2。Sum()函数:**
Sum()函数返回该组值的和。在这个函数中，值集作为参数传递，它将返回总和。

**注意:**空值将被该函数忽略。

**语法:**

```sql
Sum(expression) 
```

**演示数据库示例:**

**表名:**学生

| 学生 id | 记号 |
| One hundred and one | eighty-nine |
| One hundred and two | Sixty-seven |
| One hundred and three | Forty |

**示例-1 :**

```sql
SELECT Sum(marks) AS Total 
From student;
```

**输出–**

| **总计** |
| One hundred and ninety-six |

**示例-2 :**

```sql
SELECT Sum(marks) AS Total 
From student Where marks>50;
```

**输出–**

| **总计** |
| One hundred and fifty-six |