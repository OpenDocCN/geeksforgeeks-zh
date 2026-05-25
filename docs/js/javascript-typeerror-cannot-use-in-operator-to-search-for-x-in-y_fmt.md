# JavaScript 类型错误：不能使用“in”运算符在“Y”中搜索“X”

> 原文：[https://www.geeksforgeeks.org/javascript-typeerror-cannot-use-in-operator-to-search-for-x-in-y/](https://www.geeksforgeeks.org/javascript-typeerror-cannot-use-in-operator-to-search-for-x-in-y/)

如果使用 `in` 运算符搜索字符串、数字或其他基本类型，则会出现此 JavaScript 异常：**无法使用“in”运算符在“Y”中搜索“X”**。除了类型检查，它不能被使用。

## 消息

> TypeError: Invalid operand to 'in' (Edge)
> TypeError: right-hand side of 'in' must be an object, got 'x' (Firefox)
> TypeError: cannot use 'in' operator to search for 'x' in 'y' (Firefox, Chrome)

## 错误类型

```
TypeError
```

## 错误原因

`in` 运算符只能用于检查对象中是否有属性。这不能用于字符串、数字或其他基本类型的搜索。

## 例 1：`in` 运算符不能用于字符串搜索，因此出现了错误。

### HTML

```html
<script>
"Geek" in "GeeksForGeeks"; // error here
</script>
```

### 输出

```
TypeError: Invalid operand to 'in'
```

## 例 2：`in` 运算符不能用于字符串搜索，因此出现了错误。

### HTML

```html
<script>
var gfg = null;
"Geek" in gfg; // error here
</script>
```

### 输出

```
TypeError: Invalid operand to 'in'
```