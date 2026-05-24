# MySQL 中的 EXPORT_SET() 函数

> 原文: [https://www.geeksforgeeks.org/export_set-function-in-mysql/](https://www.geeksforgeeks.org/export_set-function-in-mysql/)

## EXPORT_SET() 函数说明

`EXPORT_SET()` 函数有助于返回一个字符串，该字符串将显示数字位。该函数需要 5 个参数才能运行。该函数将第一个参数（即整数）转换为二进制数字，如果二进制数字为 1，则返回“开”，如果二进制数字为 0，则返回“关”。

## 语法

```sql
EXPORT_SET(bits, on, off, separator, number of bits)
```

## 参数

这个函数接受 5 个参数。

*   **`bits`** – 结果将被格式化的整数。
*   **`on`** – 如果二进制数为 1，则返回。
*   **`off`** – 如果二进制数为 0，则返回。
*   **`separator`** – 将放在返回值之间的分隔符。
*   **`number of bits`** – 结果将出现的位数。

## 返回值

该函数将返回一个字符串，该字符串将显示数字位。

## 示例

### 示例 1

`EXPORT_SET()` 函数的一般工作原理。

```sql
SELECT EXPORT_SET(10, 'On', 'Off', ':', 5) AS Export;
```

**输出:**

| Export |
| :--- |
| Off:On:Off:On:Off |

### 示例 2

通过更改第 2 个和第 3 个参数来运行 `EXPORT_SET()` 函数。

*   **使用 “Y” 和 “N” 分别作为第二和第三个参数**

```sql
SELECT EXPORT_SET(11, 'Y', 'N', ', ', 4) AS Export;
```

**输出:**

| Export |
| :--- |
| Y, Y, N, Y |

*   **使用 “1” 和 “0” 分别作为第二和第三个参数**

```sql
SELECT EXPORT_SET(11, 1, 0, ', ', 4) AS Export;
```

**输出:**

| Export |
| :--- |
| 1, 1, 0, 1 |

### 示例 3

通过更改第 4 个参数来运行 `EXPORT_SET()` 函数。

*   **使用 “-” 作为第四个参数**

```sql
SELECT EXPORT_SET(10, 1, 0, '-', 4) AS Export;
```

**输出:**

| Export |
| :--- |
| 0-1-0-1 |

*   **使用 “::” 作为第四个参数**

```sql
SELECT EXPORT_SET(10, 1, 0, '::', 4) AS Export;
```

**输出:**

| Export |
| :--- |
| 0::1::0::1 |

### 示例 4

通过更改第 5 个参数来运行 `EXPORT_SET()` 函数。

*   **使用 10 作为第五个参数**

```sql
SELECT EXPORT_SET(9, 'Y', 'N', ' ', 10) AS Export;
```

**输出:**

| Export |
| :--- |
| N N N N N N N N Y Y |

*   **使用 20 作为第五个参数**

```sql
SELECT EXPORT_SET(9, 1, 0, ' ', 20) AS Export;
```

**输出:**

| Export |
| :--- |
| 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 1 0 0 1 |