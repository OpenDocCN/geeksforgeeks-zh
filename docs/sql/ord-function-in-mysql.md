# MySQL 中的 order()函数

> 原文:[https://www.geeksforgeeks.org/ord-function-in-mysql/](https://www.geeksforgeeks.org/ord-function-in-mysql/)

**order**()函数在 MySQL 中用于查找字符串中最左边字符的代码。如果最左边的字符不是多字节字符，它将返回 ASCII 值。如果字符串最左边的字符是多字节字符，ORD 将返回该字符的代码，使用以下公式从其组成字节的数值计算:

**(第一字节码)+(第二字节码* 256)+(第三字节码* 256^2) ……**

**语法:**

```sql
ORD( str )

```

**参数:**该函数接受一个参数，如上所述，如下所述:

*   **字符串:**给定字符串，其最左边的字符代码将被找到。

**返回:**返回字符串中最左边字符的代码。

**示例-1 :** 对单个字符应用 ORD()函数。

```sql
SELECT ORD('S') as Find_Code;

```

**输出:**

| 查找 _ 代码 |
| --- |
| Eighty-three |

**示例-2 :** 将 ORD()函数应用于字符串。

```sql
SELECT ORD('geeksforgeeks') as Find_Code;

```

**输出:**

| 查找 _ 代码 |
| --- |
| One hundred and three |

**示例-3 :** 对数字应用 ORD()函数。

```sql
SELECT ORD(100) as Find_Code;

```

**输出:**

| 查找 _ 代码 |
| --- |
| forty-nine |

**示例-4:**
order 函数也可以用来查找列数据最左边字符的代码。演示创建一个名为。

**玩家**

```sql
CREATE TABLE Player(

    Player_id INT AUTO_INCREMENT,  
    Player_name VARCHAR(100) NOT NULL,
    Playing_team VARCHAR(20) NOT NULL,
    PRIMARY KEY(Player_id )

);

```

现在向播放器表中插入一些数据:

```sql
INSERT INTO  
    Player(Player_name ,Playing_team)

VALUES
    ('Virat Kohli' , 'RCB' ) ,
    ('Rohit Sharma' , 'MI' ) ,
    ('Dinesh Karthik', 'KKR'  ) ,
    ('Shreyash Iyer' , 'DC'  ) ,
    ('David Warner' , 'SRH' ) ,
    ('Steve Smith' , 'RR'  ) ,
    ('Andre Russell' , 'KKR' ) ,
    ('Jasprit Bumrah' , 'MI' ) ,
    ('Risabh Panth', 'DC'  ) ;

```

因此，玩家表是:

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

现在，我们将应用 ORD 函数来查找 Player_name 和 Playing_team 列最左边字符的代码。

```sql
Select 
    * ,
    ORD(Player_name) ,   
    ORD(Playing_team)  
FROM Player;

```

**输出:**

```sql
+-----------+----------------+--------------+------------------+-------------------+
| Player_id | Player_name    | Playing_team | ORD(Player_name) | ORD(Playing_team) |
+-----------+----------------+--------------+------------------+-------------------+
|         1 | Virat Kohli    | RCB          |               86 |                82 |
|         2 | Rohit Sharma   | MI           |               82 |                77 |
|         3 | Dinesh Karthik | KKR          |               68 |                75 |
|         4 | Shreyash Iyer  | DC           |               83 |                68 |
|         5 | David Warner   | SRH          |               68 |                83 |
|         6 | Steve Smith    | RR           |               83 |                82 |
|         7 | Andre Russell  | KKR          |               65 |                75 |
|         8 | Jasprit Bumrah | MI           |               74 |                77 |
|         9 | Risabh Panth   | DC           |               82 |                68 |
+-----------+----------------+--------------+------------------+-------------------+

```