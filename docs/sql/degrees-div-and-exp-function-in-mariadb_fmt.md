# MariaDB 中的 DEGREES()、DIV() 和 EXP() 函数

> 原文：[https://www.geeksforgeeks.org/degrees-div-and-exp-function-in-mariadb/](https://www.geeksforgeeks.org/degrees-div-and-exp-function-in-mariadb/)

## DEGREES() 函数
在 MariaDB 中，`DEGREES()` 函数将弧度值转换为度数。该函数接受一个数字作为参数，并返回其对应的度数值。

**语法：**
```sql
DEGREES(number)
```

**参数：**
*   `number`：必选。要转换为度数的弧度值。

**返回：**
与输入的弧度值相等的度数。

**示例-1：**
```sql
SELECT DEGREES(-3.5);
```
**输出：**
```sql
-200.53522829578813
```

**示例-2：**
```sql
SELECT DEGREES(PI()*3);
```
**输出：**
```sql
540
```

**示例-3：**
```sql
SELECT DEGREES(1);
```
**输出：**
```sql
57.29577951308232
```

## DIV() 函数
在 MariaDB 中，`DIV()` 函数用于整数除法。它将 `n` 除以 `m`，并返回整数值。该函数接受两个数字作为参数，并返回整数结果。它也可以与 `BIGINT` 值一起使用。

**语法：**
```sql
n DIV m
```

**参数：**
*   `n`：必选。被除数（将被划分的值）。
*   `m`：必选。除数（被除数除以的值）。

**返回：**
除法结果的整数值。

**示例-1：**
```sql
SELECT 11 DIV 4;
```
**输出：**
```sql
2
```

**示例-2：**
```sql
SELECT 18 DIV 9;
```
**输出：**
```sql
2
```

**示例-3：**
```sql
SELECT 18.4 DIV -2.5;
```
**输出：**
```sql
-7
```

## EXP() 函数
在 MariaDB 中，`EXP()` 函数返回 e 的 `number` 次幂（即 e^`number`）。该函数接受一个数字作为参数，并返回 e 的该数次幂的值。其中，e 是自然对数的基数。

**语法：**
```sql
EXP(number)
```

**参数：**
*   `number`：必选。指数值，表示 e 被提升到的幂。

**返回：**
e 的 `number` 次幂。

**示例-1：**
```sql
SELECT EXP(2);
```
**输出：**
```sql
7.38905609893065
```

**示例-2：**
```sql
SELECT EXP(2.5);
```
**输出：**
```sql
12.182493960703473
```

**示例-3：**
```sql
SELECT EXP(-2.5);
```
**输出：**
```sql
0.0820849986238988
```