# SASS |列表功能

> 原文:[https://www.geeksforgeeks.org/sass-list-functions/](https://www.geeksforgeeks.org/sass-list-functions/)

SASS 列表功能用于修改新列表。需要在圆形括号内创建列表，以便与其他列表区分开来。SASS 列表不能更改，因此在某些情况下会创建新列表。
就像字符串函数一样，SASS 列表是基于 1(而不是基于 0)的索引，这意味着字符串的第一个元素出现在索引 1(而不是索引 0)。

以下列表代表了 SASS 中的所有列表功能:

**1。list-separator($list)函数:**该函数以字符串形式返回列表中使用的分隔符的名称。

*   **例 1:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
list-separator((1, 2, 3))
```

*   **输出:**

```html
"comma"
```

*   **例 2:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
list-separator((1 2 3))
```