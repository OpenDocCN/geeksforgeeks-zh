# SQL Server 中的 UPPER()函数

> 原文:[https://www.geeksforgeeks.org/upper-function-in-sql-server/](https://www.geeksforgeeks.org/upper-function-in-sql-server/)

**UPPER():**
SQL Server 中的这个函数有助于将给定字符串的所有字母转换为大写。如果给定的字符串包含特殊字符或数值，那么它们将通过此函数保持不变。

**语法:**

```sql
UPPER( str )
```

**参数:**

*   **字符串–**将被转换为大写的字符串

**结果:**
该函数将返回大写字符串。

**示例-1 :**
使用带有小写字符串的 UPPER()函数。

```sql
SELECT UPPER('be patience be awake') 
As New;
```

**输出:**

| 

新的

 |
| 保持耐心保持清醒 |

**示例-2 :**
使用带混合大小写字符串的 UPPER()函数。

```sql
SELECT UPPER('EvERy DAy iS A NEW day') 
As New;
```

**输出:**

| 新的 |
| 每一天都是新的一天 |

**示例-3 :**
使用带有 Select 语句的 UPPER()函数。
创建玩家表，并在其中插入数值。

```sql
Create table Players
(
 Firstname varchar(40),
 Lastname varchar(40),
 Country varchar(40)
)

```

**向玩家插入数据:**

```sql
Insert into Players values 
('Kane', 'Williamson', 'New Zealand')

```

这张桌子看起来像。

| 西方人名的第一个字 | 姓 | 国家 |
| 凯恩 | 威廉森 | 新西兰 |

使用 UPPER()函数。

```sql
SELECT Firstname,  
      UPPER(Lastname) As New_name,  
      Country
FROM Players;

```

**输出:**

| 西方人名的第一个字 | 新名称 | 国家 |
| 凯恩 | 威廉森 | 新西兰 |

**示例-4 :**
在变量中使用 UPPER()函数。

```sql
DECLARE @text VARCHAR(45);
SET @text = 'be happy be light ';
SELECT @text,  
      UPPER(@text) AS Upper;

```

**输出:**

| 文本值 | 上面的 |
| 快乐，轻松 | 快乐，轻松 |