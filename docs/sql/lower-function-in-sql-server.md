# SQL Server 中的 LOWER()函数

> 原文:[https://www.geeksforgeeks.org/lower-function-in-sql-server/](https://www.geeksforgeeks.org/lower-function-in-sql-server/)

**LOWER():**
SQL Server 中的这个函数有助于将给定字符串的所有字母转换为小写。如果给定的字符串包含字母以外的字符，那么通过这个函数它们将保持不变。

**语法:**

```sql
LOWER( str )
```

**参数:**

*   **字符串–**将被转换为小写的字符串

**结果:**
该函数返回小写字符串。

**示例-1 :**
使用带大写字符串的 LOWER()函数。

```sql
SELECT LOWER('WAKE UP AND TAKE UP') 
As New;
```

**输出:**

<figure class="table">

| 

新增

 |
| Wake up and occupy |

</figure>

**示例-2 :**
使用带混合大小写字符串的 LOWER()函数。

```sql
SELECT LOWER('EvERy DAy iS A NEW day') 
As New;
```

**输出:**

<figure class="table">

| 

新

 |
| Every day is a new day. |

</figure>

**示例-3 :**
在 Select 语句中使用 LOWER()函数。现在，让我们创建玩家表并在其中插入值。

```sql
Create table Players
(
 Firstname varchar(40),
 Lastname varchar(40),
 Country varchar(40)
)
```

**插入数值:**

```sql
Insert into Players values 
('VIRAT', 'KOHLI', 'INDIA')
```

**输出:**
表格如下。

<figure class="table">

| name | surname | country |
| 维拉特 | KOHLI | India |

T21】</figure>

**使用 LOWER()函数:**

```sql
SELECT LOWER(Firstname) 
As firstname,  
Lastname,  
Country
FROM Players;
```

**输出:**

<figure class="table">

| name | surname | country |
| 维拉特 | KOHLI | India |

T21】</figure>

**示例-4 :**
在变量中使用 LOWER()函数。

```sql
DECLARE @text VARCHAR(45);
SET @text = 'LIFE IS AWESOME IF YOU LIVE ';
SELECT @text,  
      LOWER(@text) AS Lower;
```

**输出:**

<figure class="table">

| Text value | lower limit |
| Life is awesome. If you live. | Life is awesome. If you live. |

</figure>