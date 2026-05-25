# 解释 JavaScript 中 `in` 运算符的用途

> 原文: [https://www.geeksforgeeks.org/explain-the-purpose-of-the-in-operator-in-javascript/](https://www.geeksforgeeks.org/explain-the-purpose-of-the-in-operator-in-javascript/)

在本文中，我们将讨论 JavaScript 中可用的 `in` 运算符。`in` 运算符用于检查属性或索引是否存在于对象或数组中。在对象中，`in` 运算符只作用于对象的键或属性。如果键或属性存在，则该运算符返回 `true`，否则返回 `false`。类似地，对于数组，如果我们传递元素的索引而不是特定的值，它将返回 `true`。

以下示例将帮助您理解 `in` 运算符的用法。

## 示例 1: 使用 `in` 运算符处理对象

让我们首先创建一个对象。为了创建一个对象，我们必须分配键值对。

```javascript
const object = {
    User: 'Geek',
    Website: 'GeeksforGeeks',
    Language: 'JavaScript'
};
```

我们将通过使用 `in` 运算符来检查该键是否存在于对象中。

```html
<script>
    const object = {
        User: 'Geek',
        Website: 'GeeksforGeeks',
        Language: 'JavaScript',
    };

    if ('User' in object) {
        document.write("Found");
    }
    else {
        document.write("Not found");
    }
</script>
```

**输出:** 我们已经检查了 `'User'` 键是否在对象中，如果在对象中，则打印 `"Found"`，否则打印 `"Not found"`。

```
Found
```

## 示例 2: 使用带数组的 `in` 运算符

让我们先创建一个数组。要创建一个数组，我们必须给方括号中的数组赋值。

```javascript
const array1 = ["Geek", "GeeksforGeeks", "JavaScript"];
```

我们将检查数组中是否存在索引值。

```html
<script>
    const array1 = ["Geek", "GeeksforGeeks", "JavaScript"];
    if (1 in array1) {
        document.write("Found: ", array1[1]);
    }
    else {
        document.write("Not found");
    }
</script>
```

**输出:** 我们已经检查了数组中是否存在索引 `1`。

```
Found: GeeksforGeeks
```