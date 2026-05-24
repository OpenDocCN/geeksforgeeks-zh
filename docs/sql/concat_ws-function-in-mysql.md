# MySQL 中的 CONCAT_WS()函数

> 原文:[https://www.geeksforgeeks.org/concat_ws-function-in-mysql/](https://www.geeksforgeeks.org/concat_ws-function-in-mysql/)

**CONCAT _ WS():**
MySQL 中的这个函数有助于将两个或多个字符串和一个分隔符连接起来。分隔符必须由用户指定，也可以是字符串。如果分隔符为空，那么结果也将为空。

**语法:**

```sql
CONCAT_WS(separator, string1, string2, ...)
```

**参数:**

*   **分隔符–**
    将在字符串 1、字符串 2 等连接时在字符串之间添加的分隔符。
*   **【字符串 1，字符串 2…】–**
    需要连接的输入字符串。

**Return :**
它将在连接所有给定的字符串后返回一个新的字符串，以及一个指定的分隔符。如果所有输入字符串都为空，那么结果将为空。如果分隔符为空，它将返回空。

**示例 1 :**
使用 CONCAT_WS 函数连接 2 个字符串，如下所示。

```sql
SELECT CONCAT_WS(": ", "Geek ", "Vansh ") AS ConcatWsStr;
```

**输出:**

| 串联字符串 |
| Geek : Vansh |

**示例-2 :**
使用 CONCAT_WS 函数连接 3 个字符串，如下所示。

```sql
SELECT CONCAT_WS("@ ", "Geek ", "Vansh ", 13 ) AS ConcatWsStr;
```

**输出:**

| 串联字符串 |
| 天才理论传第十三季第二十集 720 p 唳挂覃苺ㄩc |

**示例-3 :**
使用空分隔符串联一个空字符串，如下所示。

```sql
SELECT CONCAT_WS(NULL, NULL, "Vansh ", 13 ) AS ConcatWsStr;
```

**输出:**

| 串联字符串 |
| 空 |

**示例-4 :**
使用 CONCAT_WS 函数连接表的列，如下所示。

**创建员工表:**

```sql
CREATE TABLE Emp(
Employee_Id INT AUTO_INCREMENT,  
FirstName VARCHAR(100) NOT NULL,
LastName VARCHAR(100) NOT NULL,
Residence VARCHAR(50) NOT NULL,
Salary INT  NOT NULL,
PRIMARY KEY(Employee_Id )
);

```

**将数据插入表中:**

```sql
INSERT INTO Emp(FirstName, LastName, Residence, Salary )
VALUES
('Animesh', 'Garg', 'Delhi', 70000 ),
('Neshu', 'Sharma', 'Nepal', 73000 ),
('Aryan', 'Sharma', 'WestBengal', 72000 ),
('Abdul', 'Ali', 'Delhi', 73000 ),
('Seema', 'Sharma', 'Bihar', 70000 ) ;
```

要验证是否使用了以下命令，如下所示。

```sql
Select * From Emp;
```

**输出:**

| 员工标识 | 西方人名的第一个字 | 姓 | 居住 | 薪水 |
| one | 动漫大会 | 加里 | 德里 | Seventy thousand |
| Two | Neshu | 夏尔马 | 尼泊尔 | Seventy-three thousand |
| three | 雅利安人的 | 夏尔马 | 西孟加拉国 | Seventy-two thousand |
| four | 阿卜杜勒（男名） | 阿里 | 德里 | Seventy-three thousand |
| five | 似乎 | 夏尔马 | 比哈尔 | Seventy thousand |

现在，使用“_”作为分隔符连接给定 Emp 表的名字和姓氏，形成一个新列作为全名。

```sql
SELECT CONCAT_WS('_', FirstName,  LastName) AS FullName
From Emp;  
```

**输出:**

| 表 |
| animesh _ garg(动画集) |
| 内舒 _ 夏尔马 |
| 雅利安·夏尔马 |
| 阿卜杜勒·阿里 |
| Seema_Sharma |