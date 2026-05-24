# MS Access 中的 `Chr()` 和 `Asc()` 函数

> 原文：[https://www.geeksforgeeks.org/chr-and-asc-function-in-ms-access/](https://www.geeksforgeeks.org/chr-and-asc-function-in-ms-access/)

## 1. `Chr()` 函数

函数的作用是返回给定 ASCII 数字代码对应的字符。`Chr` 函数将整数作为参数，并返回相应的字符。它的工作原理与 `Asc()` 函数相反。

**语法：**

```
Chr(ASCII number code)
```

参数：必需；整数。
返回：一个字符。

**示例：**

```
SELECT Chr(75) 
AS NumberCodeToCharacter;
```

**输出：**

| 数字编码字符 |
| :--- |
| K |

## 2. `Asc()` 函数

`Asc()` 函数返回字符的 ASCII 值。如果在函数中传递了多个字符，那么它将返回第一个字符的 ASCII 值，否则返回指定字符的 ASCII 值。

**语法：**

```
ASC(Character)
```

参数：必需；字符或字符串。
返回：ASCII 值；整数值。

**示例：**

**表 –** Student

| 学生姓名 | 课程 |
| :--- | :--- |
| GFG_USER1 | 面向对象的程序设计系统(Object-Oriented Programming System) |
| XYZ | 每日生活津贴自定进度 |

```
SELECT STUDENT, Asc(STUDENTNAME) 
AS NumCodeOfFirstChar
FROM STUDENT;
```

**输出：**

| 学生 | NumCodeOfFirstChar |
| :--- | :--- |
| GFG_USER1 | One hundred and seven |
| XYZ | One hundred and thirty |