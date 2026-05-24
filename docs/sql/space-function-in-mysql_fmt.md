# MySQL 中的 SPACE() 函数

> 原文: [https://www.geeksforgeeks.org/space-function-in-mysql/](https://www.geeksforgeeks.org/space-function-in-mysql/)

MySQL 中的 `SPACE()` 函数用于返回由指定数量的空格字符组成的字符串。

## 语法:

```sql
SPACE(num)
```

## 参数:

该方法接受一个参数，如下所述：

*   `num`: 一个整数，指示返回的字符串中包含多少个空格。

## 返回:

返回包含指定数量空格的字符串。

## 示例-1 :

`SPACE()` 函数返回只包含空格的字符串。

```sql
SELECT SPACE(6) AS String_Name;
```

**输出:**

| String_Name |
| --- |
|       |

## 示例-2 :

将 `SPACE()` 函数与 `CONCAT()` 函数一起应用将返回一个字符串。

```sql
SELECT CONCAT('Geeks', SPACE(3), 'For', SPACE(3), 'Geeks') AS Company_Name;
```

**输出:**

| Company_Name |
| --- |
| Geeks   For   Geeks |

## 示例-3 :

在表格中使用 `SPACE()` 函数。

**表: Player_Details:**

| Player_Id | First_Name | Last_Name |
| --- | --- | --- |
| 101 | Virat | Kohli |
| 103 | Rohit | Sharma |

```sql
SELECT CONCAT(First_Name, SPACE(1), Last_Name) AS Full_Name FROM Player_Details;
```

**输出:**

| Full_Name |
| --- |
| Virat Kohli |
| Rohit Sharma |