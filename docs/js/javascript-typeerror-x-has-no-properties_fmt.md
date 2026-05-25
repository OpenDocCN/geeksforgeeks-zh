# JavaScript TypeError–“X”没有属性

> 原文: [https://www.geeksforgeeks.org/javascript-typeerror-x-has-no-properties/](https://www.geeksforgeeks.org/javascript-typeerror-x-has-no-properties/)

这个 JavaScript 异常 `null`（或 `undefined`）没有属性，如果试图访问 `null` 和 `undefined` 的属性，就会出现这个异常。它们没有任何这样的属性。

**消息:**

```
TypeError: Unable to get property {x} of undefined or null reference (Edge)
TypeError: null has no properties (Firefox)
TypeError: undefined has no properties (Firefox)
```

**错误类型:**

```
TypeError
```

**错误原因:** 在某个地方，可以访问 `null` 或 `undefined` 的属性。

**示例 1:** 在本例中，变量 (`GFG`) 被赋予了 `null` 值，并且它没有任何属性，因此出现了错误。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>Type Error</title>
</head>
<body>
    <script>
    var GFG = null;
    document.write(GFG.prop_name);
    </script>
</body>
</html>
```

**输出 (在 Edge 控制台):**

```
TypeError: Unable to get property 'prop_name' of 
undefined or null reference
```

**例 2:** 在本例中，变量 (`var_name`) 被赋予了 `undefined` 值，它没有任何属性，因此出现了错误。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
<head>
    <title>Type Error</title>
</head>
<body>
    <script>
    var var_name = undefined;
    document.write(var_name.prop_name);
    </script>
</body>
</html>
```

**输出 (在 Edge 控制台):**

```
TypeError:Unable to get property 'prop_name' of 
undefined or null reference
```