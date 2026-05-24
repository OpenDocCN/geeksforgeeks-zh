# MS Access 中的 Hex() 和 Oct() 函数详解

> 原文：[https://www.geeksforgeeks.org/hex-and-oct-function-in-ms-access/](https://www.geeksforgeeks.org/hex-and-oct-function-in-ms-access/)

## 1. Hex() 函数

`Hex()` 函数用于返回一个代表数字十六进制值的字符串。

### 语法
```sql
Hex(number)
```

### 参数
该方法接受一个参数，如下所述：

*   `number`：任何有效的数值表达式或字符串表达式。

### 返回值
如果 `number` 为 `Null`，则返回 `Null`；如果 `number` 为 `Empty`，则返回零 (`0`)。否则，它将返回一个代表 `number` 十六进制值的字符串。

### 注意
如果 `number` 还不是一个整数，则先四舍五入到最接近的整数再进行求值。

### 示例-1
2 的十六进制表示。
```sql
SELECT Hex(2) AS HexNumber;
```
**输出：**
| HexNumber |
| --- |
| 2 |

### 示例-2
13 的十六进制表示。
```sql
SELECT Hex(13) AS HexNumber;
```
**输出：**
| HexNumber |
| --- |
| D |

### 示例-3
1134.80 的十六进制表示。
```sql
SELECT Hex(1134.80) AS HexNumber;
```
**输出：**
| HexNumber |
| --- |
| 46F |

## 2. Oct() 函数

`Oct()` 函数用于返回一个代表一个数的八进制值的字符串。

### 语法
```sql
Oct(number)
```

### 参数
该方法接受一个参数，如下所述：

*   `number`：任何有效的数值表达式或字符串表达式。

### 返回值
如果 `number` 为 `Null`，则返回 `Null`；如果 `number` 为 `Empty`，则返回零 (`0`)。否则，它将返回一个代表 `number` 八进制值的字符串。

### 注意
如果 `number` 还不是一个整数，则先四舍五入到最接近的整数再进行求值。

### 示例-1
7 的八进制表示。
```sql
SELECT Oct(7) AS OctNumber;
```
**输出：**
| OctNumber |
| --- |
| 7 |

### 示例-2
111.45 的八进制表示。
```sql
SELECT Oct(111.45) AS OctNumber;
```
**输出：**
| OctNumber |
| --- |
| 157 |