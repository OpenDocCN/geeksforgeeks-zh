# TypeScript字符串`charCodeAt()`方法

> 原文：[https://www.geeksforgeeks.org/typescript-string-charcodeat-method/](https://www.geeksforgeeks.org/typescript-string-charcodeat-method/)

`charCodeAt()`是[`TypeScript`](https://www.geeksforgeeks.org/hello-world-in-typescript-language/)中的一个内置函数，用于返回指定索引处字符的Unicode值。

## 语法

```
string.charCodeAt(index);
```

## 参数

该方法接受如上所述和如下所述的单个参数。

*   **索引**：该参数是一个小于字符串长度的0到1之间的整数。

## 返回值

这个方法返回一个数字，表示给定索引处字符的Unicode值。

以下示例说明了TypeScript JS中的字符串`charCodeAt()`方法：

## 示例1

### JavaScript

```
var str = new String("JavaScript is object oriented language");

// Finding number indicating the Unicode value
// of the character at the given index
var value = str.charCodeAt(14);
console.log(value);
```

### 输出

```

```

## 示例2

### JavaScript

```
var str = new String('JavaScript is object oriented language');

// Finding number indicating the Unicode value
// of the character at the given index
console.log("Character at 0 is : " + str.charCodeAt(0));
console.log("Character at 1 is : " + str.charCodeAt(1));
```

### 输出

```
Character at 0 is : 74
Character at 1 is : 97
```