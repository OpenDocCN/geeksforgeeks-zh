# MySQL中的RIGHT()函数

> 原文：[https://www.geeksforgeeks.org/right-function-in-mysql/](https://www.geeksforgeeks.org/right-function-in-mysql/)

`RIGHT()`函数在MySQL中用于从给定字符串的右侧提取指定数量的字符。第二个参数用于决定它应该返回多少个字符。

## 语法

```sql
RIGHT( str, len )
```

## 参数

该函数接受两个参数，如上所述，如下所述：

*   `String`：一个给定的字符串，将从其右侧提取多个字符。
*   `len`：要提取的字符数。如果此参数大于字符串中的字符数，此函数将返回实际的字符串。

## 返回

它从一个字符串中返回多个字符（从右开始）。

## 示例

### 示例-1：将RIGHT()函数应用于给定的字符串

```sql
SELECT RIGHT("geeksforgeeks", 4) AS Right_Str;
```

**输出：**

| Right_Str |
| :-------- |
| ksforge   |

### 示例-2：将RIGHT()函数应用于数字

```sql
SELECT RIGHT(12345678, 4) AS Right_Num;
```

**输出：**

| Right_Num |
| :-------- |
| 5678      |

### 示例-3：在字符串中插入`>`字符时，对给定字符串应用RIGHT()函数

```sql
SELECT RIGHT("geeksforgeeks", 20) AS Right_Str;
```

**输出：**

| Right_Str    |
| :----------- |
| geeksforgeeks |

### 示例-4：应用RIGHT()函数查找表中玩家的姓氏

为了演示，创建一个名为`Player`的表格。

```sql
CREATE TABLE Player(
    Player_id INT AUTO_INCREMENT,
    Player_name VARCHAR(100) NOT NULL,
    Playing_team VARCHAR(20) NOT NULL,
    PRIMARY KEY(Player_id)
);
```

现在，在`Player`表中插入一些数据：

```sql
INSERT INTO
    Player(Player_name, Playing_team)
VALUES
    ('Virat Kohli', 'RCB'),
    ('Rohit Sharma', 'MI'),
    ('Dinesh Karthik', 'KKR'),
    ('Shreyash Iyer', 'DC'),
    ('David Warner', 'SRH'),
    ('Steve Smith', 'RR'),
    ('Andre Russell', 'KKR'),
    ('Jasprit Bumrah', 'MI'),
    ('Risabh Panth', 'DC');
```

所以，`Player`表是：

```sql
mysql> SELECT * FROM Player;
+-----------+----------------+--------------+
| Player_id | Player_name    | Playing_team |
+-----------+----------------+--------------+
|         1 | Virat Kohli    | RCB          |
|         2 | Rohit Sharma   | MI           |
|         3 | Dinesh Karthik | KKR          |
|         4 | Shreyash Iyer  | DC           |
|         5 | David Warner   | SRH          |
|         6 | Steve Smith    | RR           |
|         7 | Andre Russell  | KKR          |
|         8 | Jasprit Bumrah | MI           |
|         9 | Risabh Panth   | DC           |
+-----------+----------------+--------------+
```

现在我们将找到每个玩家的姓氏，要找到姓氏我们必须应用以下方法：

1.  首先，使用`INSTR()`函数查找空格（`' '`）在姓名中的位置。
2.  其次，使用`LENGTH()`函数查找玩家姓名的长度。`RIGHT`函数的`len`参数在这里将是`Player_name`的长度减去`' '`（空格）字符的位置。
3.  第三，使用`RIGHT()`函数提取玩家的姓氏。

```sql
SELECT
    Player_name,
    RIGHT(Player_name, LENGTH(Player_name) - INSTR(Player_name, ' ')) AS Lastname,
    Playing_team
FROM
    Player;
```

**输出：**

```sql
+----------------+----------+--------------+
| Player_name    | Lastname | Playing_team |
+----------------+----------+--------------+
| Virat Kohli    | Kohli    | RCB          |
| Rohit Sharma   | Sharma   | MI           |
| Dinesh Karthik | Karthik  | KKR          |
| Shreyash Iyer  | Iyer     | DC           |
| David Warner   | Warner   | SRH          |
| Steve Smith    | Smith    | RR           |
| Andre Russell  | Russell  | KKR          |
| Jasprit Bumrah | Bumrah   | MI           |
| Risabh Panth   | Panth    | DC           |
+----------------+----------+--------------+
```