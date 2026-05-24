# SASS |字符串函数

> 原文:[https://www.geeksforgeeks.org/sass-string-functions/](https://www.geeksforgeeks.org/sass-string-functions/)

**SASS 字符串函数**与任何其他编程语言的字符串函数非常相似，只有一个区别，即 SASS 字符串使用基于 1 的索引。这意味着 SASS 字符串的第一个字符存储在索引 1(而不是 0)处。
我们创建了一个包含所有 SASS 函数列表的表格，并提供了简要描述和示例。

**1。quote($string)函数:**该函数将引号添加到不带引号的字符串中，并返回带引号的字符串。

*   **示例:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
quote(GeeksforGeeks);
```

*   **输出:**

```html
"GeeksforGeeks"
```

**2。str-index($string，$substring)函数:**该函数返回给定字符串中第一个出现的子字符串的索引。如果字符串不包含子字符串，则返回 null。

*   **示例:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
str-index("Geeksforgeeks", "G");
```